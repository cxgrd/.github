# cxgrd - AI context guardrail

cxgrd is a lightweight developer CLI utility that acts as an automated architectural guardrail for people building apps using AI.

- The Core Feature: The tool maps how different modules, APIs, and database schemas connect in a local codebase.
- The Workflow: Before a developer prompts their AI assistant to make a sweeping change, the tool calculates the 
downstream blast radius. It tells them: "If you change auth_controller.py , you will also need to update the AI
prompt to account for changes in middleware.ts and user_schema.sql ."
- The "Diff" Checker: It reviews the code written by the AI before it is committed, scanning for logic gaps, 
missing imports, or broken structural dependencies.


## Persistent repo intelligence
### AI agents mostly:
- have temporary context
- limited session memory
- have prompt-based understanding
### ContextGuard will maintain:
- structural memory
- dependency memory
- architecture memory

in a json format inside the local project directory.
This persistent intelligence will help users write more architecturally accurate code and maintain consistency across the codebase.


## Project structure:
```
cxgrd/
├── core/ ← C++ engine
├── cli/ ← TS wrapper
├── plugins/ ← VS Code / Cursor
├── cloud/ ← API + auth (Supabase and GitHub auth)
└── docs/ ← Documentation
```


## Commands
- `cxgrd scan` → writes .cg/ from scratch (or diffs it)
- `cxgrd input` → reads graph + arch + history, writes to history.json
- `cxgrd prompt` → reads everything, sends subgraph to LLM, returns enriched prompt
- `cxgrd check` → reads graph + compiler output, writes result to history.json
- `cxgrd scan` → next run diffs graph.json against previous, updates patterns.json
- `cxgrd auth login` → login command for Pro users


## Build roadmap:
The project is under development. Here is the phase-wise schedule :
- Phase 1 — get the graph working. This is the foundation everything else sits on.
The C++ core parses source files with tree-sitter and writes the dependency
graph to .cg/ . TypeScript wraps it into a usable CLI ( check, scan, input, prompt ).
- Phase 2— blast radius. The killer feature. Once the graph traversal is successful, we
can answer "what breaks if I touch this?" This is also where we wire in precommit hooks 
and watch mode — the things that make it feel native to a dev workflow.
- Phase 3 — compiler-backed diff checker. Integrating actual
language servers (tsc, pyright, rustc) to validate AI-generated diffs means we're
not just doing structural analysis — we're doing semantic validation. Hard to
replicate, high value.
- Phase 4 — prompt generation + repo memory. This is where the .cg/ persistent
memory becomes a serious differentiator. AI agents are stateless; we'll give
them architectural memory.
- Phase 5 — team/enterprise. Shared graph server, audit policies, dashboards,
SSO. The per-seat pricing model, gate collaboration and org-wide memory.
AI context guardrail 5
- Phase 6 — VSCode/Cursor Plugins. Integrating cxgrd inside code editors.


## Contributing
The project is under active development. Contributions are welcomed!
