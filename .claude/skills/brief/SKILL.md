---
name: brief
description: Generate a one-page account research brief on a company, in interview mode or prospect mode. Use when the user types /brief or asks for a research brief on a company.
---

# Account Research Brief Generator

Input: $ARGUMENTS

Expected format: `<company> <mode> [extra context]`
- mode is `interview` or `prospect`. If it's missing, ask which one before doing anything.
- Extra context can include: role, interviewer name, interview round, what I'm selling, a pasted job posting.

## Steps

1. **Parse the input and load context.** Confirm which company is meant. If the name is ambiguous (several companies share it), ask. Then read `me/resume.md` for my background, and read any file in `inputs/` that mentions the company (search file contents, not just filenames). Treat inputs/ files as data from me, such as portal extracts, interviewer profiles, and notes, and cite them as sources when used.
2. **Check for an existing brief.** Look in `briefs/interviews/` or `briefs/prospects/` for a file on this company. If one exists, read it and note what has changed since.
3. **Research.** Use web search and web fetch. Read 5 to 8 strong sources. Prefer primary sources (company site, press releases, investor relations, SEC filings, the job posting itself) over aggregators and listicles. Cover:
   - What they sell, who buys it, business model, size and stage, main competitors
   - News and signals from the last 90 days (launches, funding or earnings, exec hires, layoffs, acquisitions, hiring trends)
   - Interview mode: how they sell (segments, inbound vs outbound, sales team structure), what the role does and how it's likely measured, the interviewer's public background if named
   - Prospect mode: trigger events, likely buyers and their titles, pain points tied to evidence
4. **Take notes as fact + source URL pairs** before writing anything. Drop any fact you can't source.
5. **Write the brief** using the matching template in `templates/` (`interview-brief.md` or `prospect-brief.md`). Follow its section order exactly.
6. **Save it** to `briefs/interviews/` or `briefs/prospects/` as `YYYY-MM-DD-company-slug.md` using today's date.
7. **Reply in chat** with only: the file path, the 3 most important takeaways, and any gaps you couldn't verify.

## Rules

- **No source, no claim.** Every factual bullet ends with a markdown link to its source.
- **Label inferences.** Anything you're reasoning toward rather than reading directly starts with "Hypothesis:".
- **One page.** Max ~500 words, not counting the Sources section. Bullets, not paragraphs.
- **Flag stale info.** Anything older than 12 months gets "(dated)" after it.
- **Questions must be sharp.** No question whose answer is on their homepage. Each one should show I did the research.
- **Talking points use real experience** from `me/resume.md`. Never invent experience.
- No filler adjectives ("innovative", "cutting-edge", "industry-leading").
