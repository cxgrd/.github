<h1 align="center">
  <img src="https://www.cxgrd.com//cxgrdlogo.png" height=90 /><br>
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

Watch the demo for cxgrd-cli here:

[CXGRD Demo](https://youtu.be/eL8mkYsATFA)

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

<p align= "left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" alt="TypeScript" height="34" />
  <img src="https://github.com/devicons/devicon/blob/v2.17.0/icons/nextjs/nextjs-original.svg" alt="NextJS" height="34" />
  <img src="https://github.com/devicons/devicon/blob/v2.17.0/icons/supabase/supabase-original.svg" alt="Supabase" height="34">
</p>

---

<p align="left" style="font-size: 20px; margin-top: 10px">
  For more information, visit the <a href="https://www.cxgrd.com"> official website </a>,
  or read the docs <a href="https://docs.cxgrd.com">here</a> .

</p>