# Making ClarinhaGPT update daily

## 1. Upload these files to the repo root (Add file → Upload files)
- index.html (new: it now loads edition.json)
- edition.json (today's edition, the file the daily task rewrites)
- DAILY_EDITION.md (instructions the daily task follows)
- SETUP.md (this file, optional)
Keep icon-*.png and manifest.json from before.

## 2. Create the scheduled task
Needs a paid Claude plan with Claude Code on the web enabled.
Open Claude Code (claude.ai/code or the Desktop app) → Scheduled tasks → New → Cloud task.
- Repository: mariaclaraes11/AI-APP, branch main
- Schedule: daily, 06:00 your time
- Allow it to push to main (or open a PR if you want to review first)
- Prompt: paste the text below

---
Read DAILY_EDITION.md in this repo and follow it exactly. Produce today's ClarinhaGPT edition by rewriting edition.json: research the last 24–72 hours of AI news on the web, pick the best stories, write every field in the required format, update concepts (and weeks/eras on Fridays), validate the JSON, then commit "edition: <today's date>" and push to main. Edit only edition.json. Never invent numbers or facts; cite a real source for every story.
---

## 3. Test it
Use "Run now" on the task once. Check the commit on GitHub, wait a minute for Pages, then open the app. If a run produces bad JSON, the app falls back to the stories built into index.html, so it never breaks.
