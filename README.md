# Slop Shield

Filter AI slop. Reject unverified completion claims. That's it.

## Install

```bash
# Local
claude --plugin-dir /Users/sanghee/dev/slop-shield

# Marketplace
claude marketplace add slop-shield https://github.com/sh-ai-x/slop-shield
claude plugin install slop-shield
```

## What it does

Two hooks, run automatically:

| Hook | When | Action |
|---|---|---|
| `slop-detector` | Write / Edit | Flags banned phrases (`delve into`, `leverage`, `comprehensive`, ...) |
| `verify-gate` | Stop | Flags completion claims without quoted test output |

Both print to stderr. Neither blocks. You decide whether to act.

## Layout

```
slop-shield/
├── .claude-plugin/plugin.json   # Manifest
├── CLAUDE.md                    # Iron laws (3) — auto-loaded
├── README.md
└── hooks/
    ├── hooks.json
    ├── slop-detector.sh
    └── verify-gate.sh
```

## License

MIT