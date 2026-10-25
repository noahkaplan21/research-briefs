# Research Briefs

Turns a company name into a one-page, fully sourced research brief in about two minutes. Built with Claude Code.

## Why
Manual pre-call research took me ~25 minutes per company. This cuts it to ~2 and makes every brief consistent.

## Usage
Open this folder in VS Code, start Claude Code, then run:

```
/brief Acme Logistics interview role: Account Development Rep
/brief Acme Corp prospect selling: AI lead enrichment, contact: VP Sales
```

Briefs save to `briefs/interviews/` or `briefs/prospects/` as `YYYY-MM-DD-company.md`.

## How it works
1. Parses company + mode
2. Searches and reads 5-8 primary sources
3. Records every fact with its source link
4. Writes the brief from a template, labeling inferences as "Hypothesis:"
5. Saves it and returns the top 3 takeaways

## Roadmap
- [x] v1: Claude Code skill
- [ ] v2: Python + Claude API, batch mode over a CSV of leads
- [ ] v3: Output to Notion / Google Sheets, Gmail draft of first-touch email
