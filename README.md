# Repolex Knowledge Graph of mrabarnett/mrab-regex

RDF knowledge graph data for [mrabarnett/mrab-regex](https://github.com/mrabarnett/mrab-regex), parsed by [repolex](https://repolex.ai).

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
rlex download mrabarnett/mrab-regex
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0e8cb0596ba6572c66e5d153a1d7c901b381e15e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0e8cb0596ba6572c66e5d153a1d7c901b381e15e
│           └── chunk-001.nq.gz
├── blob
│   ├── 1ee79b212747b37afa85c9962af4ea2c6836b2e0.nq.gz
│   ├── 2b0f9bd989fd8062222000c314c62f15fd3d9afb.nq.gz
│   ├── 39c493d6c8e235f37fb03bc131ff78053f63ba06.nq.gz
│   ├── 585b75fd0b0cefb6de7e258358fff624a7f1aad7.nq.gz
│   ├── 5ce0ad5ba85933c3b4a42ee019cf306c08042ba7.nq.gz
│   ├── 60678919c2a774a2a8a6d0701bfd79b17e4d4ac8.nq.gz
│   ├── 64957538d24ba3f63fb6a76d54257b0c7704411c.nq.gz
│   ├── 90f9212076c50abf356cc92d7111668ec7fb4d5c.nq.gz
│   ├── 98b4b199918a2e97b9676e225f7a5cc718d17492.nq.gz
│   ├── 99c19cf844141395a87c34325da3a537f1e95815.nq.gz
│   ├── b391472b5bb4ea94924376c448a3674b8c6ff8ad.nq.gz
│   ├── b5f0e8774ed9bb9d9ae1c844c9c6843f346cc50e.nq.gz
│   ├── c20e2381151c367551ebc71c896e23386ea41536.nq.gz
│   ├── c6cf85ddb4cf88790742e781ff0970426d991330.nq.gz
│   ├── e78a0e633cdd358c5258a37efc36ba38c0270da5.nq.gz
│   ├── eaaa84af936ba46ed13833f3a2c71cca8a0cc9e5.nq.gz
│   └── f88d3cdae300710852dc3266a55a267d0f2a5731.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0e8cb0596ba6572c66e5d153a1d7c901b381e15e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[mrabarnett/mrab-regex](https://github.com/mrabarnett/mrab-regex)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
