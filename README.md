# Repolex Knowledge Graph of glue-viz/glue-medical

RDF knowledge graph data for [glue-viz/glue-medical](https://github.com/glue-viz/glue-medical), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-medical
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2cd61bf8d90ba371f1cf8b379dc323ff8f41d180
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2cd61bf8d90ba371f1cf8b379dc323ff8f41d180
│           └── chunk-001.nq.gz
├── blob
│   ├── 224b0941ae6c7be1371509062f715761f67c1bfc.nq.gz
│   ├── 39516763e1d7b5d75fefbbbc9ac9456f7ecc4e01.nq.gz
│   ├── 45fab2a384c52174e3a908ce1e9b6dfd8e00cac7.nq.gz
│   ├── 495fd00a3d9d490fec8410edb8bf39e16293bd10.nq.gz
│   ├── 5a5490c647086db3dca19b8b70e257ad480c524e.nq.gz
│   ├── 5bd547f6690c2a223c23e07e64a7c924ed6697bc.nq.gz
│   ├── 646b27d3f6da21a06aeffa02f5585d08bbf9be8a.nq.gz
│   ├── 7f2e3c8bb617270a15bfe7055f061cb0ffc43e47.nq.gz
│   ├── 84d871bc2aa4bbfe200ef0fc35614e3612dadec6.nq.gz
│   ├── 85c757564d321fc776a532398e95e060488fa991.nq.gz
│   ├── 8d445604a95ac6a51874b6a1cbc812920719839a.nq.gz
│   ├── 97aba10a47e1a43e1693b28357225c2d69d0db6f.nq.gz
│   ├── 9ec7c488ea92744ee77de84659c7395f0e875cf9.nq.gz
│   ├── a3db2a9c11fbc6e3efe2e6ad3fd41bed32a519a8.nq.gz
│   ├── a9829e5c987bbe8edd67ebace1b7864e15c414d3.nq.gz
│   ├── abb68ae013458b97b8c8e8ebbda4eb091651e040.nq.gz
│   ├── c5ae62ae8eb24237462da7de80a66fac7f32cfa2.nq.gz
│   ├── de3cd94d005cb6c4b5f533ae5bba970bbff5082b.nq.gz
│   ├── df416f41c26b0e5481f300d4ef865546b359ca1f.nq.gz
│   ├── e51db0f533905160067648b4a00ec65eff6054d0.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed15f34b473b5abf2b05747443305a69dfdead8f.nq.gz
│   └── f4c288c68394dcf130e8ee205b6b49463ee96e4e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2cd61bf8d90ba371f1cf8b379dc323ff8f41d180.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[glue-viz/glue-medical](https://github.com/glue-viz/glue-medical)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
