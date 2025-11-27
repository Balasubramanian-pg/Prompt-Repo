# README — How to Use the Three Agent Files

This README explains the purpose of each file you now have for your **10× Streamlit Developer Agent**, and how they work together. Each file plays a different role in controlling the behavior, safety, and output quality of the LLM.

## Overview

The system is made of three internal components:

* **System Prompt**: Defines who the agent is and how it thinks.
* **Internal Instructions**: Defines how the agent must behave operationally.
* **Output Guardrail**: Defines what the agent is allowed to output and the constraints it must obey.

Together they form a complete, production-grade control framework for generating Streamlit code, architectures, tests, and deployments without hallucination or sloppy behavior.

## 1. System Prompt

### Purpose

This is the identity and role-definition of the agent. It sets the persona, capabilities, coding standards, architecture patterns, and interaction style. It tells the model “what it is” and “what it must do.”

### When to Use

* Paste it into an LLM’s **system message** whenever you want to activate the 10× Streamlit Developer.
* Use it when generating:

  * Streamlit apps
  * Python logic layers
  * CI/CD
  * Docker
  * Tests
  * Architecture blueprints
  * Deployment manifests

### What It Controls

* The agent’s technical expertise
* Code quality and determinism
* Testing and deployment standards
* Documentation style
* Interaction patterns

### Think of it as:

**The professional identity + operating philosophy of the agent.**

## 2. Internal Instructions

### Purpose

These instructions define the internal behavior of the agent — the rules that govern:

* How it reasons
* How it formats answers
* How it interacts
* How it handles assumptions
* When it must ask for required info
* How it structures code responses
* Which files it must generate and how

### When to Use

* Add this to the **assistant’s internal “developer” or “manager” instruction slot** in your LLM environment.
* Use it to enforce:

  * Consistent file structures
  * Deterministic outputs
  * Clear next steps
  * Proper summaries
  * Correct use of assumptions
  * Clear changelog notes for refactors

### What It Controls

* Communication structure
* Code quality rules
* Folder layout expectations
* Testing requirements
* Deployment instructions
* Interaction discipline

### Think of it as:

**The agent’s rulebook and behavior manual.**

## 3. Output Guardrail

### Purpose

This is a strict constraint layer. It prevents:

* Hallucinations
* Unverifiable claims
* Guessing APIs
* Unsafe code
* Secrets
* Incomplete code
* Inconsistent structure
* Policy violations

### When to Use

* Add it to the **assistant’s output moderation or output filter layer**.
* Use it when you need absolute reliability and correctness from the agent’s output.
* Use it in production-grade workflows where safety matters.

### What It Controls

* What the agent is *allowed* to output
* What it must *never* output
* Output formatting requirements
* Determinism
* Completeness
* Security
* Assumption labeling
* Validation before producing response

### Think of it as:

**The legal contract restricting output behavior.**

## How the Three Files Work Together

### System Prompt = Identity

Defines: skills, role, goals, tone, coding pattern, architecture.

### Internal Instructions = Behavior

Defines: how it reasons, formats, structures responses, tests code, handles assumptions.

### Output Guardrail = Safety

Defines: what is allowed, what is forbidden, how validity is enforced.

Together they form a polished agent with:

* Strong capability (System Prompt)
* Strong discipline (Internal Instructions)
* Strong safety and correctness (Output Guardrail)

## How You Should Use Them

### If you’re setting up an AI agent:

* Put **System Prompt** in the system role.
* Put **Internal Instructions** in a developer/configuration layer.
* Put **Output Guardrail** in your moderation/output-filter layer.

### If you’re using an LLM manually:

* Combine them in order:

  1. System Prompt
  2. Internal Instructions
  3. Output Guardrail
* Then begin giving the model tasks.

### If you’re integrating into a product:

* System Prompt → primary system message
* Internal Instructions → backend agent config
* Output Guardrail → final output-check logic

This ensures the model behaves like a disciplined, high-level Streamlit engineer.

## What This README Enables

This README tells any developer:

* What each file is for
* How they work together
* How to integrate them into an LLM-based agent
* How to maintain and extend the agent safely

Your agent system is now fully documented and production-ready.

If you want, I can also produce:

* A combined “all-in-one” agent bundle
* A JSON specification for multi-role LLM environments
* A diagram of the control flow
* A packaged agent manifest for LangChain, LlamaIndex, or custom frameworks

