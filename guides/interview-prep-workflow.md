# Interview Prep Workflow

Use the same four steps for every interview. Command details are in [slash-commands.md](slash-commands.md).

## Step 1: Collect inputs (when the interview is scheduled)
1. **Candidate portal:** paste this into chat:
   `@browser Open my <company> candidate portal at <link>. Extract the interview date/time, format, stages, interviewer names and titles, and prep material. Save it to inputs/<company>-portal.md. Don't click anything that submits, confirms, or changes my application.`
2. **Interviewer background:** open each interviewer's LinkedIn, copy the Experience section, paste it into chat, and ask Claude to save it to `inputs/<company>-<name>-linkedin.md`.
3. **Job posting:** if it's not public, paste it and save it to `inputs/<company>-job-posting.md`.

Everything in `inputs/` is private (gitignored).

## Step 2: Generate the brief (1–2 days before)
- Run `/brief <company> interview role: <role>, interviewer: <name>`
- The skill reads `me/resume.md` and any `inputs/` file that mentions the company.
- Output: `briefs/interviews/YYYY-MM-DD-<company>.md`
- Open every source link before saying a number out loud.

## Step 3: Rehearse (the day before; most of the value is here)
- **Mock screen:** "Mock interview me as <interviewer>, using the brief. Ask follow-ups, then score my answers on structure, numbers, and conciseness."
- **Mock cold call:** "Play a skeptical Director of Operations. Use real objections. Give feedback after."
- **Pressure test:** run `/grill-me`, or ask "What will they push back on in my background?"
- **Prep for a prospect round:** run `/brief <real company> prospect`. Bringing a researched prospect and opener to a mock call round shows I can already do the job.

## Step 4: Debrief (within an hour after)
- Paste what they asked, what went well, and what felt weak. Ask Claude to save it to `inputs/<company>-debrief-<round>.md`.
- Ask for a thank-you note draft built from my own points, then run `/humanizer` on it. **I send it myself.**
- The next round's `/brief` picks up the debrief automatically.

## Keep up to date
- `me/resume.md`: update it after every new role, metric, or project.
- `me/stories.md` (to build): 6–8 stories in Situation, Task, Action, Result form, each with a number ([story 1: a business you started], [story 2: a cost or process win at an internship], [story 3: winning buy-in from leadership], [story 4: leading a team]).

## Rules of thumb
- Use `/clear` between companies so facts don't mix.
- Claude drafts and I send. Claude never sends messages, confirms interviews, or submits portal forms on its own.
- Know the material and say it in my own words. Don't read the brief like a script.
- Every fact in a brief has a source, and anything labeled "Hypothesis:" is a guess to confirm in the interview.

## Ideas to build next
- `/mock`: role-play an interviewer or prospect, with a scorecard
- `/debrief`: save interview notes to inputs/ and draft the thank-you note
