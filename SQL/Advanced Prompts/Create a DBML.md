# Master prompt — convert a supplied schema into DBML for a database diagram

Use this prompt when you want an assistant (or an automated tool) to produce clean, production-ready DBML from a schema you will paste. Copy the entire block below, replace the `<SCHEMA>` placeholder with your schema text (tables, columns, sample rows, or plain-language description), then send it to the assistant that generates DBML.

## Purpose

* Provide an unambiguous, repeatable instruction set so the assistant converts any provided schema into accurate DBML suitable for diagramming tools and engineers.
* Force clear assumptions, mapping rules, constraints, and output formats so the generated DBML needs minimal manual edits.

## Master prompt (paste this, then replace `<SCHEMA>` with your schema)

```
You are an expert schema engineer and DBML author. Convert the schema I provide into DBML. The schema is below:

<SCHEMA>

Requirements and rules:

1) Parse input and list entities
- Identify every table/entity and present a short list of detected entities (table names with a one-line description inferred from column names).
- If any entity is ambiguous, state the ambiguity and your best assumption.

2) Data type mapping
- Map input types or inferred types to one of: int, bigint, varchar(length), text, boolean, date, datetime, timestamp, decimal(precision,scale), float, double, json, uuid, serial (Postgres identity), or enum.
- If a length is unknown for varchar, use varchar(255).
- For money/price fields use decimal(12,2) unless schema indicates otherwise.
- When input mentions GUID/UUID use uuid type.
- If an input column is described as "id" or "<table>_id" treat as integer primary key by default; if GUID is explicitly provided, make it uuid.

3) Primary keys and identity
- Detect primary key(s). If none explicit, create `id` as an auto-increment primary key on that table only if doing so makes sense; otherwise keep table without synthetic key and document that choice.
- For composite primary keys, define them explicitly in DBML.

4) Foreign keys and relationships
- Detect foreign key relationships by `<table>_id` patterns or explicit references.
- For many-to-many relationships, create an explicit join table if one exists; if not present but clearly implied, suggest creating one and show a proposed DBML for it.
- Add `Ref` lines in DBML with an on delete / on update rule. Default to `ON DELETE NO ACTION ON UPDATE NO ACTION` unless schema suggests `CASCADE` or `SET NULL`.
- If a FK column is nullable, use `ref: >` style in DBML with `nullable` annotation.

5) Nullability, defaults, and constraints
- Mark columns as `not null` or `null` based on schema; when ambiguous assume `not null` only for id and timestamps, otherwise assume nullable and list that assumption.
- Include `default` values in DBML where provided or obviously required (e.g., status default 'active').
- Include unique constraints and composite unique indexes.

6) Indexes and performance hints
- Add DBML `indexes` or inline `index` annotations for columns that look like search keys (email, username, slug, external_id).
- For multi-column indexes, create explicit index definitions.
- Highlight columns that likely need indexing but are not defined as such.

7) Enums and lookup tables
- Convert small sets of string values into `enum` definitions if the values are listed.
- If lookup tables exist, prefer keeping them as tables with PK and name column instead of enums; mention tradeoffs.

8) Naming conventions and style
- Use snake_case for table and column names unless the input uses another consistent convention — preserve the input convention and document it.
- Use singular table names by default unless the input uses plurals; note the choice.

9) Comments and documentation
- Add comments in DBML for:
  - assumptions made
  - unresolved ambiguities
  - recommended schema improvements (indexes, normalization, cascading rules)
- Provide a short human-readable summary after the DBML block listing:
  - detected tables count
  - detected relationships count
  - any changes or suggested new tables (join tables, audit tables)

10) Output formatting
- Produce two DBML outputs:
  - Minimal: compact DBML with required columns, PKs, FKs, and basic types.
  - Verbose: DBML with comments, indexes, defaults, nullability, enums, and the `Ref` relations.
- Wrap each DBML in fenced code blocks labelled as `dbml`.
- After DBML, include a short example SQL CREATE TABLE for one representative table (choose the most central table) showing how DBML maps to SQL (use a single SQL dialect — indicate which one, default to Postgres).

11) Assumptions and heuristics
- List every assumption made about types, nullability, defaults, and relationship directions.
- If the schema is incomplete, still generate DBML using reasonable defaults and explicitly label those defaults as assumptions.

12) Deliverable checklist
- The assistant must return:
  - A one-paragraph summary of what it produced.
  - The Minimal DBML block.
  - The Verbose DBML block.
  - The example SQL CREATE TABLE for one table.
  - An assumptions section.
  - A short list of recommended next steps (3–6 bullets).

If you understand, produce the result now for the schema above without asking clarifying questions. Make reasonable assumptions and list them explicitly.
```

## Example snippet (how the assistant should format its DBML output)

* Minimal DBML example (as returned by assistant):

```dbml
Table users {
  id serial [pk]
  email varchar(255) [unique, not null]
  name varchar(255)
  created_at timestamp [default: `now()`]
}

Table posts {
  id serial [pk]
  user_id int [ref: > users.id]
  title varchar(255) [not null]
  content text
}

Ref: posts.user_id > users.id
```

* Verbose DBML example (as returned by assistant):

```dbml
Table users {
  id serial [pk, note: "auto-increment integer primary key"]
  email varchar(255) [unique, not null, note: "used for login"]
  name varchar(255) [null, note: "display name"]
  created_at timestamp [default: `now()`, not null]
}

Table posts {
  id serial [pk]
  user_id int [not null, ref: > users.id, note: "FK to users"]
  title varchar(255) [not null]
  content text [null]
  published boolean [default: false]
  created_at timestamp [default: `now()`]
  index(user_id, created_at) [name: posts_user_created_idx]
}

Ref: posts.user_id > users.id [note: "on delete cascade? consider CASCADE if posts must be deleted with user"]
```

## Tips for use

* Paste whichever form of schema you have: raw SQL, JSON, CSV header rows, table lists, or plain English description.
* The assistant will parse and apply the rules above, then produce DBML and the extra documentation.
* If you want a specific SQL dialect, naming style, or index strategy, add a short line before `<SCHEMA>` like: `Dialect: postgres, Naming: snake_case, Table style: plural`.

## Final note

* The assistant must act now on the provided schema and not ask follow-ups. If anything is unclear, it should make a best-effort assumption, implement it, and explicitly list that assumption in the output.
* End of master prompt.

