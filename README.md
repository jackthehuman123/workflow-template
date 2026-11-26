```
repo/
├── AGENTS.md                       # source of truth for instructions (Codex, Cursor read it. Gemini reads GEMINI.md)
├── CLAUDE.md                       # one line: @AGENTS.md
├── CLAUDE.local.md                 # your personal notes, not committed
│
├── .agents/
│   └── skills/                     # source of truth for skills (the open standard's location)
│       └── <skill-name>/
│           ├── SKILL.md            # spec-only frontmatter: name, description, allowed-tools
│           ├── scripts/            # logic and hard rules: executed, not loaded into context
│           ├── references/         # long docs: read only when needed
│           └── assets/             # templates and files the scripts copy
│
├── .claude/
│   ├── skills → ../.agents/skills  # symlink, committed (git mode 120000) bash`ln -s ../.agents/skills .claude/skills`
│   ├── settings.json               # team permissions and hooks (Claude-only)
│   └── settings.local.json         # your personal settings, not committed
│
└── docs/                           # your knowledge: design, notes, understanding logs
```
