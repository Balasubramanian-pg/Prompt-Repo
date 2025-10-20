## HOW TO USE THIS COLLECTION

### Quick Reference Guide:

| **Use Case** | **Prompt to Use** | **Best For** |
|--------------|-------------------|--------------|
| Scraping websites | #1 Web Scraping | APIs, HTML parsing, browser automation |
| Processing CSV/data | #2 Data Processing | pandas, large files, ETL pipelines |
| Building APIs | #3 API Development | REST, FastAPI, Flask, Django REST |
| Machine learning | #4 Data Science & ML | Modeling, predictions, analysis |
| Database work | #5 Database & SQL | Schema design, queries, ORMs |
| Concurrent tasks | #6 Async & Concurrency | Parallel processing, async/await |
| Improving code | #7 Refactoring | Cleanup, optimization, modernization |
| Fixing bugs | #8 Debugging | Error handling, troubleshooting |

### Usage Template:

```
[Copy one of the 8 prompts above]

MY [TYPE] PROJECT:

Problem: [What you're trying to solve]
Context: [Any relevant details]
Code: [If improving/debugging existing code]
Constraints: [Time, resources, requirements]
Questions: [Anything specific you're unsure about]
```

## POWER USER TIPS

### 1. **Combine Prompts When Needed**
Example: "I need to scrape data (#1) and then build an API (#3) to serve it"
- Use both prompts sequentially
- Reference outputs between them

### 2. **Start Simple, Scale Up**
Every prompt emphasizes MVP:
- Test with small data first
- Add features incrementally
- Measure before optimizing

### 3. **Trust the Recommendations**
Prompts are designed to reduce decision fatigue:
- "I recommend X because Y" - just go with it
- Test the MVP, adjust later if needed
- Don't overthink the initial approach

### 4. **Save Your Customizations**
Add project-specific context:
```
[Paste prompt]

ADDITIONAL CONTEXT FOR MY PROJECT:
- We use Python 3.11
- Deploy on AWS Lambda
- Team prefers FastAPI over Flask
- Must work with legacy database
```

### 5. **Keep Edge Cases in Mind**
Each prompt lists 8-15 edge cases:
- Review them before starting
- Mention any that apply to your case
- Trust the code will handle them

## PROMPT COMPARISON MATRIX

| Feature | General | Scraping | Data | API | ML | Database | Async | Refactor | Debug |
|---------|---------|----------|------|-----|----|----|-------|----------|-------|
| MVP Focus | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Edge Cases Listed | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Test Mode | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Error Handling | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅✅ |
| Progress Tracking | ✅ | ✅ | ✅ | - | ✅ | - | ✅ | - | - |
| Resume Capability | ✅ | ✅ | ✅ | - | - | - | ✅ | - | - |
| Security Focus | ✅ | ✅ | - | ✅✅ | - | ✅ | - | - | - |
| Performance Focus | ✅ | ✅ | ✅✅ | ✅ | ✅ | ✅✅ | ✅✅ | ✅✅ | - |
| Ethical Guidelines | - | ✅✅ | - | - | ✅ | - | - | - | - |

**Legend:**
- ✅ = Included
- ✅✅ = Major Focus
- \- = Not Primary Focus

## 🎓 ADVANCED USAGE PATTERNS

### Pattern 1: Sequential Pipeline
```
Step 1: Use #1 (Web Scraping) to get data
Step 2: Use #2 (Data Processing) to clean it
Step 3: Use #5 (Database) to store it
Step 4: Use #3 (API) to serve it
```

### Pattern 2: ML Project Lifecycle
```
Step 1: Use #2 (Data Processing) for EDA
Step 2: Use #4 (ML) for modeling
Step 3: Use #3 (API) for serving predictions
Step 4: Use #8 (Debugging) for production issues
```

### Pattern 3: Legacy Code Improvement
```
Step 1: Use #8 (Debugging) to understand issues
Step 2: Use #7 (Refactoring) to modernize
Step 3: Use #6 (Async) to improve performance
```

## REAL-WORLD EXAMPLES

### Example 1: E-commerce Price Monitor
```
[Use Prompt #1: Web Scraping]

MY WEB SCRAPING PROJECT:
I want to monitor prices of 50 products across 3 e-commerce sites daily.
Need to detect price changes and send alerts.
Sites use JavaScript for dynamic loading.
```

### Example 2: Customer Data ETL
```
[Use Prompt #2: Data Processing]

MY DATA PROCESSING TASK:
Process 5GB of customer transaction CSV files daily.
Need to clean, aggregate, and generate reports.
Current pandas script runs out of memory.
```

### Example 3: Internal Tool API
```
[Use Prompt #3: API Development]

MY API PROJECT:
Build internal API for employee directory.
CRUD operations on employee records.
Need auth (SSO), search, filtering.
Will be used by 3 internal apps.
```

### Example 4: Sales Forecasting
```
[Use Prompt #4: Data Science & ML]

MY ML PROJECT:
Predict next month's sales for 100 product categories.
Have 2 years of historical sales data.
Need model that explains predictions to business users.
```

## MASTER COLLECTION SUMMARY

You now have **9 specialized prompts** (including the original general one):

1. **General Python** - Any Python task
2. **Web Scraping** - Ethical data extraction
3. **Data Processing** - pandas, large files, ETL
4. **API Development** - REST APIs, backends
5. **ML & Data Science** - Modeling, predictions
6. **Database & SQL** - Schema design, queries
7. **Async & Concurrency** - Parallel processing
8. **Code Refactoring** - Improve existing code
9. **Debugging & Errors** - Fix issues, robust handling

**Each prompt delivers:**
- 10-15 clarifying questions
- 8-12 edge cases identified
- Clear recommendations (reduce decision fatigue)
- MVP-first approach with test modes
- Production-ready code
- First-time success rate: Very high! 

**Save this artifact** - it's your complete Python development toolkit! 
