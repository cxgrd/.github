<h1 align="center">
  <img src="https://cxgrd.com//cxgrdlogo.png" height=90 /><br>
  <p align="center">
    <img src="./assets/cxgrd-text.svg" width="800" alt="CXGRD">
  </p>

  <p align="center" style="font-size: 20px; margin-top: 10px">
    Architectural guardrails for AI native development
  </p>

</h1>

Modern codebases are deeply interconnected — changing one file can silently break a dozen others. When you ask an AI assistant to refactor a service or add a feature, it typically has no awareness of your project's dependency graph, architectural layers, or downstream impact.

**CXGRD** solves this. It scans your project and builds a complete dependency graph, then uses that graph to:

- **Tell you exactly what will break** before you make a change
- **Enrich your AI prompts** with architectural context so the AI makes safer, smarter suggestions
- **Validate your code** for circular dependencies, orphaned files, and layer violations — both structurally and with compiler-backed checks
- **Enforce merge policies** on pull requests via GitHub Actions, blocking merges that exceed your team's blast radius limits

Think of it as giving your AI assistant a map of your codebase before it starts digging.

---

## Typical Workflow

```bash
# 1. Install
npm install -g cxgrd

# 2. Authenticate
cxgrd auth login
# Required for Pro, Team and Enterprise plans

# 3. Scan your project
cxgrd scan

# 4. Before making a change — check the blast radius
cxgrd input "extract UserService into a separate module"

# 5. Generate an enriched prompt for your AI
cxgrd prompt "extract UserService into a separate module"

# Paste this prompt into your AI tool, make the changes

# 6. Validate the result
cxgrd check
```

---

## See it in action 

[![CXGRD Demo]](https://private-user-images.githubusercontent.com/181568300/617205952-03ec81c7-1717-43ea-9a01-b2e42c24c439.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODMyNTQwNTcsIm5iZiI6MTc4MzI1Mzc1NywicGF0aCI6Ii8xODE1NjgzMDAvNjE3MjA1OTUyLTAzZWM4MWM3LTE3MTctNDNlYS05YTAxLWIyZTQyYzI0YzQzOS5tcDQ_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNzA1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDcwNVQxMjE1NTdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1kOTg4OWI5ZWEzNTkzNTY4YmQ3M2RiOWI3ZTRjNTNjYmE1ZjRjYjdmZjZhOWNiOWUyMTM2ZWExZWZjN2I0MmM3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9dmlkZW8lMkZtcDQifQ.LLQLYo3imZA4sjJNM6ZhXyy-l7SJXuIzCDB9Ztz5y2w)

---

## Persistent repo intelligence
### AI agents mostly:
- have temporary context
- limited session memory
- have prompt-based understanding
### CXGRD will maintain:
- structural memory
- dependency memory
- architecture memory

in json format inside the local project directory.
This persistent intelligence will help users write more architecturally accurate code and maintain consistency across the codebase.


## Commands
- `cxgrd scan` → writes .cg/ from scratch (or diffs it)
- `cxgrd input` → reads graph + arch + history, writes to history.json
- `cxgrd prompt` → reads everything, sends subgraph to LLM, returns enriched prompt
- `cxgrd check` → reads graph + compiler output, writes result to history.json
- `cxgrd auth login` → login command for Pro/Team/Enterprise users
- `cxgrd doctor` → verifies your toolchain is ready before enabling strict checks.
- `cxgrd watch` → Runs in the background and monitors your project for dependency changes in real time.
- `cxgrd init-hooks` → Sets up a pre-commit hook so CXGRD checks run automatically before every commit.

---

## Tech stack

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" alt="TypeScript" height="34" />
<img src="https://github.com/devicons/devicon/blob/v2.17.0/icons/nextjs/nextjs-original.svg" alt="NextJS" height="34" />
<img src="https://github.com/devicons/devicon/blob/v2.17.0/icons/supabase/supabase-original.svg" alt="Supabase" height="34">

---

<p align="left" style="font-size: 20px; margin-top: 10px">
  For more information, visit the <a href="https://cxgrd.com"> official website </a>,
  or read the docs <a href="https://docs.cxgrd.com">here</a> .

</p>