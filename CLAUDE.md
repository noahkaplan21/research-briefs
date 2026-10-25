# Research Briefs

## What this project is
A tool that turns a company name into a one-page research brief I can read in 90 seconds before a call.
Two modes:
- **interview**: I'm interviewing with this company. Help me sound informed and ask sharp questions.
- **prospect**: I'm selling to this company. Find the trigger, the likely pain, and my opening line.

Run it with: `/brief <company> <mode> [extra context]`
Example: `/brief Acme Logistics interview role: Account Development Rep, interviewer: Jane Doe`

## Folder structure
```
research-briefs/
├── CLAUDE.md                  ← this file (project context Claude reads every session)
├── README.md                  ← how to use it (for GitHub)
├── .gitignore                 ← keeps me/, inputs/, briefs/interviews/ out of git
├── .claude/skills/brief/
│   └── SKILL.md               ← the brief generator's instructions (the "logic")
├── me/
│   └── resume.md              ← my background (private, gitignored)
├── inputs/                    ← raw material: portal extracts, notes, job posts (private)
├── guides/
│   ├── slash-commands.md      ← which commands to use and when
│   └── interview-prep-workflow.md ← step-by-step prep process for every interview
├── templates/
│   ├── interview-brief.md     ← output format for interview mode
│   └── prospect-brief.md      ← output format for prospect mode
└── briefs/
    ├── interviews/            ← finished interview briefs
    └── prospects/             ← finished prospect briefs
```

## Conventions
- Brief filenames: `YYYY-MM-DD-company-slug.md` (e.g. `2026-10-24-acme-logistics.md`)
- Logic lives in SKILL.md. Format lives in templates/. Change one without touching the other.
- Never invent facts. Every claim needs a source link. Inferences are labeled "Hypothesis:".

## About me
My background lives in `me/resume.md`. Read it before writing any "My angle" section. Never invent experience that isn't in it.
