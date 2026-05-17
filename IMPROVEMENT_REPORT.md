# Feature Improvement Report

**Tool:** Random Date Generator — codebeautify.org/generate-random-date  
**Report Type:** Feature Improvement (no critical bugs found)  
**Reported By:** [Your Name]  
**Date:** May 16, 2026

---

## FI-001 — No Date Range Configuration

### Summary
The tool generates dates across a wide, uncontrolled year range (observed: 2022–2096). Users cannot specify a start date or end date, making the tool impractical for real-world use cases such as generating test data for a specific time window.

### Steps to Reproduce
1. Navigate to https://codebeautify.org/generate-random-date
2. Click "Generate"
3. Observe that dates are spread across a ~100-year span with no user input

### Current Behavior
Dates are generated at random across a pre-defined (and invisible) year range. The user has no control over the output window.

### Expected / Improved Behavior
The tool should provide **Start Date** and **End Date** input fields so users can confine output to a meaningful range.

**Example UI Addition:**
```
Start Date: [MM-DD-YYYY]    End Date: [MM-DD-YYYY]    [ Generate ]
```

### Impact
**Medium** — The tool is functionally correct but limited in practical applicability. QA engineers, data scientists, and developers generating test datasets typically need dates within a specific domain (e.g., last 3 years, next fiscal quarter).

### Priority
**P2 — Enhancement**

---

## FI-002 — Single Output Format (MM-DD-YYYY Only)

### Summary
The tool only outputs dates in `MM-DD-YYYY` format. International users and developers working with ISO standards or database-oriented formats have no way to get output in their required format without manual reformatting.

### Steps to Reproduce
1. Navigate to https://codebeautify.org/generate-random-date
2. Click "Generate"
3. Observe all dates are in MM-DD-YYYY format only — no format selector exists

### Current Behavior
All output is hardcoded to `MM-DD-YYYY`.

### Expected / Improved Behavior
Add a **Format Selector** dropdown allowing users to choose from common formats:

| Option | Example |
|--------|---------|
| MM-DD-YYYY (default) | 05-16-2026 |
| DD-MM-YYYY | 16-05-2026 |
| YYYY-MM-DD (ISO 8601) | 2026-05-16 |
| MMM DD, YYYY | May 16, 2026 |

### Impact
**Medium** — Limits the tool's usefulness for non-US users and for developers needing ISO 8601 format for databases, APIs, and modern frameworks.

### Priority
**P2 — Enhancement**

---

*No critical or high-severity bugs were identified during testing. The above improvements are recommended to increase the tool's utility and real-world relevance.*
