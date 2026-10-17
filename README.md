# Repolex Knowledge Graph of colcon/colcon-installed-package-information

RDF knowledge graph data for [colcon/colcon-installed-package-information](https://github.com/colcon/colcon-installed-package-information), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-installed-package-information
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 081b198084967fdff738ad23163218f890d54048
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 081b198084967fdff738ad23163218f890d54048
│           └── chunk-001.nq.gz
├── blob
│   ├── 069e185a3d0c4b5139730d7ee7293a54a84baf39.nq.gz
│   ├── 0c1cb2e539626de1bfc4b6e00589bf8712e41369.nq.gz
│   ├── 173e45a4067b265ea1999d09d7b5e06e9418cf21.nq.gz
│   ├── 2eaf67f7a95b9b70b0692f1aaedc4ca036801196.nq.gz
│   ├── 4103e0d7ba4269a51f33fa0a8c3385be52e60d53.nq.gz
│   ├── 51c82703bcb0fc33170ead04d7101ef0b13eb912.nq.gz
│   ├── 5b2988407eb78c1099e90d9933fd6a055be0ca63.nq.gz
│   ├── 6d42b6372a2705b3aeb3a8e9c5eccfe0b8327543.nq.gz
│   ├── 8b070690ce783883451d8d9f11bb62b40cd619cc.nq.gz
│   ├── a0ef5669faac028816e25f5e8596969ed094c12d.nq.gz
│   ├── bd7c8693b373f16474a10254e75b502ef8389f27.nq.gz
│   ├── c18dd8d83ceed1806b50b0aaa46beb7e335fff13.nq.gz
│   ├── c2926f122b1ed36cbc233086206c923c039e9373.nq.gz
│   ├── d2deb1153574b81344d0258226569e94b8c1fe18.nq.gz
│   ├── d547f9b3caaba8814736ed0d639a0aa7496c4f87.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── de8e0956bc04c50bea41ff7b95268451004c2355.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   ├── ec8f82b3e7be6d202de16b95380261f41f1087e4.nq.gz
│   └── fa7212388c90f2830b3ac4d3269026454bb6e49a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 081b198084967fdff738ad23163218f890d54048.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[colcon/colcon-installed-package-information](https://github.com/colcon/colcon-installed-package-information)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
