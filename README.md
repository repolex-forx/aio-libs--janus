# Repolex Knowledge Graph of aio-libs/janus

RDF knowledge graph data for [aio-libs/janus](https://github.com/aio-libs/janus), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/janus
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 431248c05c63d24911e66f4f9a6fedc905c39562
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 431248c05c63d24911e66f4f9a6fedc905c39562
│           └── chunk-001.nq.gz
├── blob
│   ├── 161ab8437e8b4f1588485dd14d64d11ed46e2348.nq.gz
│   ├── 1824c7588d0e5fae4c537c3a5b1a0eca16478ddb.nq.gz
│   ├── 208222793754017df1fb0c68f369b9bb7a2c01bf.nq.gz
│   ├── 36979982708b367032730848375b2a457cf360b8.nq.gz
│   ├── 36fe0a82d3d92ecb6b7e877562fa540532788750.nq.gz
│   ├── 3af7109a64974e78acc295b9c97bf1886066299f.nq.gz
│   ├── 41a3b94891fed42b107dc674189c93207a8300ac.nq.gz
│   ├── 4d3aa67ccc2cf8b0b6e463544cc54cc71a37129e.nq.gz
│   ├── 557fa7bf84c08772cd926bce08af39a491f7e620.nq.gz
│   ├── 606849326a4002007fd42060b51e69a19c18675c.nq.gz
│   ├── 77ff8914b3cf84c3261f8bee10adfba1b0f34739.nq.gz
│   ├── 80a5bf72f7b5a64c92f7e16c4fe0bbfd27be563d.nq.gz
│   ├── 867e2c84929548e9cfd08806e72a8bc045f65bb7.nq.gz
│   ├── a0c02daa258532af84046535dc033a89f2b977cc.nq.gz
│   ├── a7130a9a4b1e94425e5f7b69f7ac17de3e27b9df.nq.gz
│   ├── a882fb075f0bbcc1c8edbfca7092bf40c59e60cb.nq.gz
│   ├── b33a1d3e4a32a842e64d69490ff97dc974062558.nq.gz
│   ├── c936d94598ce7604219ffe1dcc3b08c9f0d72571.nq.gz
│   ├── cd1f8353041562640eb94d679aca75584dfeb932.nq.gz
│   ├── ceb42b68fe297c9e79c65b45de632bea0ab84669.nq.gz
│   ├── efd14fc0e65fa9c14791a2db789b2ef5373d32c5.nq.gz
│   └── f13841c834cb1fe6cef15e4334ac5aef413ceaf2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 431248c05c63d24911e66f4f9a6fedc905c39562.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[aio-libs/janus](https://github.com/aio-libs/janus)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
