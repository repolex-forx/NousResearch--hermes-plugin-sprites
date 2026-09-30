# Repolex Knowledge Graph of NousResearch/hermes-plugin-sprites

RDF knowledge graph data for [NousResearch/hermes-plugin-sprites](https://github.com/NousResearch/hermes-plugin-sprites), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download NousResearch/hermes-plugin-sprites
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a4881e07385beff6b440b5338dec7a415d5f1be5
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── a4881e07385beff6b440b5338dec7a415d5f1be5.nq.gz
│   └── repolex
│       └── a4881e07385beff6b440b5338dec7a415d5f1be5
│           └── chunk-001.nq.gz
├── blob
│   ├── 2ac48efe32faa5f87521fa0605210f3f2b97470d.nq.gz
│   ├── 2ae9848023d848f8e6eba16cbfa0c40c3b1c7aa1.nq.gz
│   ├── 32adf84dbdefff17c13d0e638dda7208a6b0e505.nq.gz
│   ├── 72661f952f5342de7000228c4ee048a9aa888bfe.nq.gz
│   ├── 75c61823b87164dde85ad0f2c78c300e011cc8a2.nq.gz
│   ├── 976690d345f187dd28b5ab22026ac363ae39f0e3.nq.gz
│   ├── 9995c6e332c87ec293f7fe3c61455110cddaf988.nq.gz
│   └── c3d3e81f8fdeab1db0aa965ae90a82bc1ffcb8cf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a4881e07385beff6b440b5338dec7a415d5f1be5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 17 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[NousResearch/hermes-plugin-sprites](https://github.com/NousResearch/hermes-plugin-sprites)

---
*Parsed on 2026-09-30 by [repolex](https://repolex.ai)*
