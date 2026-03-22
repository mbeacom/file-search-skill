# AGENTS.md — file-search-skill

## Repo Structure

```
.
├── skills/file-search/
│   ├── SKILL.md                        # Main skill definition
│   └── references/
│       ├── ripgrep-patterns.md         # rg flags, patterns, and recipes
│       ├── ast-grep-patterns.md        # Structural search patterns by language
│       ├── fd-guide.md                 # fd file finder guide
│       ├── rga-guide.md               # ripgrep-all for non-code files
│       ├── tool-comparison.md          # Detailed tool comparison and decision guide
│       ├── search-strategies.md        # Search targeting strategies
│       └── code-metrics.md            # tokei/scc code statistics guide
├── .github/workflows/                  # CI workflows
├── composer.json                       # PHP package metadata
├── docs/                               # Architecture and planning docs
│   ├── ARCHITECTURE.md
│   └── exec-plans/
├── scripts/
│   └── verify-harness.sh              # Harness verification script
└── README.md
```

## Commands

No Makefile or build scripts. This is a documentation-only skill repo.

- `bash scripts/verify-harness.sh --format=text --status` — check harness maturity level

## Rules

1. **Use `rg` instead of `grep`** for text search in source code.
2. **Use `fd` instead of `find`** for file discovery.
3. **Use `rga` instead of `rg`** when searching non-code files (PDFs, Office docs, archives).
4. **Use `sg` (ast-grep) instead of regex** when matching code structure.
5. **Use `tokei` or `scc`** for codebase size, not `cloc` or `wc -l`.
6. **Always start narrow** — most specific search first, widen only if needed.
7. **Always specify file types/languages** (`-t`, `--lang`, `-e`) to limit scope.
8. **Count matches before viewing** (`rg -c | wc -l`) to avoid overwhelming output.

## References

- [SKILL.md](skills/file-search/SKILL.md) — full skill definition and tool selection guide
- [ripgrep Patterns](skills/file-search/references/ripgrep-patterns.md) — rg patterns and recipes
- [ast-grep Patterns](skills/file-search/references/ast-grep-patterns.md) — structural search by language
- [fd Guide](skills/file-search/references/fd-guide.md) — file finder reference
- [rga Guide](skills/file-search/references/rga-guide.md) — searching non-code files
- [Tool Comparison](skills/file-search/references/tool-comparison.md) — decision guide
- [Search Strategies](skills/file-search/references/search-strategies.md) — targeting strategies
- [Code Metrics](skills/file-search/references/code-metrics.md) — tokei/scc guide
