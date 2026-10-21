# Repolex Knowledge Graph of executablebooks/mdformat-myst

RDF knowledge graph data for [executablebooks/mdformat-myst](https://github.com/executablebooks/mdformat-myst), parsed by [repolex](https://repolex.ai).

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
rlex download executablebooks/mdformat-myst
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 888b07deb5714307df4dd104350d472f0bfb41aa
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 888b07deb5714307df4dd104350d472f0bfb41aa
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b70e449a645a9052f3030c73cda4afb17fa75a9.nq.gz
│   ├── 19c537808832de3ddb4c626e7631896cd46fbe8e.nq.gz
│   ├── 1a5545a976adfbb93b6f585b7a20269e7a75d4c2.nq.gz
│   ├── 40c899f9b32e8ca965a314a6e3c36610d4c2857a.nq.gz
│   ├── 4706af62f8885ba03c0179b23c7123d7bfe77445.nq.gz
│   ├── 51fffb7b322b1d7681b30539f0ae09685a72a560.nq.gz
│   ├── 60b42826aaf14a679eb50cdb2bbc5a7ab673f685.nq.gz
│   ├── 7632ecf77545c5e5501cb3fc5719df0761104ca2.nq.gz
│   ├── 82f77e3f62a91598b5286cd297c9cf1bdb0ec51b.nq.gz
│   ├── 8729f36c5b96e0fce6fc113e9af8e465aa921b9f.nq.gz
│   ├── 88f2a1a8b0a06327dd3023ff82decbbfb21c732f.nq.gz
│   ├── 8c9a832cf0a1d544d8d04033e96fd0563d240b7c.nq.gz
│   ├── c3eed504fcabd2c9ac206510f77c0ebc658bf544.nq.gz
│   ├── c95540794e7e632bdd72402bda1514ccf040cf6f.nq.gz
│   ├── e06ffb1f404dd0b81395d397042a7d95f96c76dd.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e859590f886cd78344206af1a8ccb3080d4385e0.nq.gz
│   └── ed0e7940a070149aec66bddb14a90ca45e09eb8c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 888b07deb5714307df4dd104350d472f0bfb41aa.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[executablebooks/mdformat-myst](https://github.com/executablebooks/mdformat-myst)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
