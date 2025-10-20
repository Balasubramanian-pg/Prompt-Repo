# Python Project Accelerator: Master Collection
*A structured, modular toolkit for Python projects—from data extraction to machine learning.*

## Quick Start Table

| Goal                     | Prompt               | Key Features                                                                 |
|--------------------------|----------------------|------------------------------------------------------------------------------|
| Extract web data         | Web Scraping         | Ethical scraping, JavaScript rendering, rate limits, anti-bot bypass       |
| Clean/transform data     | Data Processing      | Pandas/Numpy, memory optimization, parallel processing, data validation    |
| Build APIs/microservices | API Development      | FastAPI/Flask, authentication (JWT/OAuth), async support, OpenAPI docs      |
| Train ML models          | Data Science & ML    | Scikit-learn/TensorFlow, feature engineering, explainability, MLOps pipelines |
| Manage databases         | Database & SQL       | PostgreSQL/MongoDB, ORM (SQLAlchemy), migrations, query optimization        |
| Speed up tasks           | Async & Concurrency  | Asyncio, threading, multiprocessing, task queues (Celery/RQ)                |
| Modernize code           | Refactoring          | PEP 8 compliance, type hints, design patterns, technical debt reduction     |
| Fix errors               | Debugging            | Logging, error handling, memory leaks, race conditions, CI/CD integration   |

## Usage Template

Use this structure for any project:

```markdown
[PASTE PROMPT HERE]
PROJECT OVERVIEW
- Problem: [Describe the core issue in 1-2 sentences]
- Data/Inputs: [Specify format, size, and sources]
- Outputs: [Define expected deliverables]
- Constraints: [List time, tech stack, or compliance requirements]
- Edge Cases: [Identify 2-3 critical scenarios]
- Questions: [Highlight uncertainties or tradeoffs]
```

## Power User Patterns

### 1. Sequential Workflows
**Example: ETL Pipeline**
```
Step 1: Web Scraping → Extract data
Step 2: Data Processing → Clean and transform
Step 3: Database → Store processed data
Step 4: API Development → Serve data via API
```
**Recommendation:** Use `--resume` flags in scripts to handle interruptions.

### 2. Parallel Tracks
**Example: ML + API**
- **Track 1:** Data Science & ML → Train and save model (e.g., `.pkl` file)
- **Track 2:** API Development → Build API endpoint to load and serve the model
- **Merge:** Deploy the API with the model using Docker.

### 3. Legacy System Improvement
**Example: Refactor Monolith**
1. Debugging → Identify bottlenecks and errors.
2. Refactoring → Modularize components and improve code quality.
3. Async & Concurrency → Add concurrency for slow or blocking tasks.

## Risk Mitigation Matrix

| Risk                     | Prompt       | Solution                                                                 |
|--------------------------|--------------|--------------------------------------------------------------------------|
| Scraping blocked         | Web Scraping | Rotate user agents, use proxies, respect `robots.txt`                     |
| Memory errors            | Data Processing | Chunk data, use `dask`, optimize data types                            |
| API downtime             | API Development | Implement rate limiting, circuit breakers, and health checks          |
| Model drift              | Data Science & ML | Monitor predictions, set retraining triggers, use A/B testing       |
| Slow database queries    | Database & SQL | Add indexes, analyze queries, use read replicas                         |
| Race conditions          | Async & Concurrency | Use locks, `asyncio.Semaphore`, ensure transactional integrity         |
| Technical debt           | Refactoring  | Prioritize using `pylint`, refactor incrementally, write tests first   |
| Silent failures          | Debugging    | Implement structured logging, integrate Sentry, use assert statements |

## Edge Cases Checklist

Always consider:
- **Data:** Are there nulls, duplicates, or inconsistent formats? (Web Scraping, Data Processing)
- **Scale:** Will the solution handle 10x the current data volume? (Data Processing, Database & SQL)
- **Security:** Are API keys, secrets, or sensitive data exposed? (API Development, Database & SQL)
- **Failure:** What happens if a dependency crashes or a network request fails? (Async & Concurrency, Debugging)
- **Compliance:** Are there legal or regulatory requirements (e.g., GDPR, CCPA)? (Web Scraping, Data Science & ML)

## Performance Cheat Sheet

| Task                     | Tool                     | When to Use                                      |
|--------------------------|--------------------------|--------------------------------------------------|
| Scrape 10,000+ pages     | Scrapy + Scrapy-Zyte     | JavaScript-heavy sites, distributed crawling     |
| Process 10GB+ CSV files  | Dask or Modin            | Out-of-core computation                          |
| High-traffic API         | FastAPI + Uvicorn        | Async routes, WebSocket support                  |
| Real-time ML predictions | TensorFlow Serving       | Low-latency inference                            |
| Database migrations      | Alembic                  | Schema changes without downtime                 |

## Debugging Flowchart

1. **Error Occurs**
   - Is there a log available?
     - **Yes:** Check the traceback for details.
     - **No:** Add logging to capture the error.
2. **Known Issue?**
   - **Yes:** Apply the fix from the Debugging prompt.
   - **No:** Isolate the issue in a test case and seek community input.

## Real-World Examples

### 1. Competitor Price Tracker
```markdown
[Web Scraping]
PROJECT OVERVIEW
- Problem: Track 200 SKUs across 5 retailers daily.
- Data: Dynamic JavaScript-rendered pages, potential CAPTCHAs.
- Outputs: CSV reports + Slack alerts for price changes.
- Constraints: Avoid IP blocks, budget under $50/month.
- Edge Cases: Flash sales, login walls, regional pricing.
```

### 2. Healthcare Data Pipeline
```markdown
[Data Processing] + [Database]
PROJECT OVERVIEW
- Problem: Ingest and process 1M patient records while ensuring HIPAA compliance.
- Data: HL7/FHIR formats, 30% missing values.
- Outputs: PostgreSQL database + audit logs.
- Constraints: No Protected Health Information (PHI) in logs, 99.9% uptime required.
```

## Advanced Tips

1. **Combine Prompts:** Use Web Scraping + Data Processing + Database for end-to-end data pipelines.
2. **Parameterize:** Replace hardcoded values with environment variables (e.g., `DB_URL`).
3. **Test Modes:** Every prompt includes a `--dry-run` flag for safe testing.
4. **Documentation:** Auto-generate documentation with API Development (FastAPI) or Data Science & ML (model metadata).
5. **Monitoring:** Integrate Debugging with Prometheus and Grafana for observability.

## Starter Kits

| Prompt               | GitHub Template          | Key Files                          |
|----------------------|--------------------------|-------------------------------------|
| Web Scraping         | scrapy-project           | `settings.py`, `middlewares.py`     |
| API Development      | fastapi-template         | `main.py`, `Dockerfile`, `test.py`  |
| Data Science & ML    | mlops-baseline           | `train.py`, `requirements.txt`     |

## The Path To Usage

1. **Start Small:** Pick one prompt and complete a project end-to-end.
2. **Combine Prompts:** Use two prompts (e.g., Web Scraping + API Development) for a real-world use case.
3. **Contribute:** Share edge cases, optimizations, or templates with the community.
