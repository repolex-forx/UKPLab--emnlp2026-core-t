# Repolex Knowledge Graph of UKPLab/emnlp2026-core-t

RDF knowledge graph data for [UKPLab/emnlp2026-core-t](https://github.com/UKPLab/emnlp2026-core-t), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/emnlp2026-core-t
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 93b7f01e5e9111b9f120463f4c21a726d75b0f4f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 93b7f01e5e9111b9f120463f4c21a726d75b0f4f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0130a7950c6c024796195beb7fae6326ae704532.nq.gz
│   ├── 113fdc8232bc349d7c8b3d92ae931f97caad35fe.nq.gz
│   ├── 21df1fe14b8337acc4b2b1413a2800023a5dc3ee.nq.gz
│   ├── 26ab629c57d93a2544b1b57f65cb3ba097748cd7.nq.gz
│   ├── 3522478e9773dd101d32c082e05958c6dfd2c1f3.nq.gz
│   ├── 3531e946d681cefd559c83f2049c208aae81e235.nq.gz
│   ├── 3bb775dc3ce4fd31387a90254054b4a95cd5286b.nq.gz
│   ├── 3e5f9450028d99fbdc6c9ba941cf199003040043.nq.gz
│   ├── 52b2b0e2b99fd0a22b5bc4ad25780505af06b8a8.nq.gz
│   ├── 5dcef726f671e400c7a0873dc8e9d9f061889630.nq.gz
│   ├── 5f126b6c100f64b1ebdb5808177239d9e587c28b.nq.gz
│   ├── 6a1268cc087e7b95af919bdc6eeb989314866e94.nq.gz
│   ├── 6c230bd551fc9137cafd443d2b463c8650389343.nq.gz
│   ├── 6fcde9d19dde3549a87c236d082ad146edc6fc3d.nq.gz
│   ├── 76403011dd6495f969c2be769bd8dc517d248b9c.nq.gz
│   ├── 8b137891791fe96927ad78e64b0aad7bded08bdc.nq.gz
│   ├── 8cbf308509a25bf820a8c7fdb9699cc099acf87e.nq.gz
│   ├── 8d283a539c1cd06aa75c4cd06534238aa69a5b42.nq.gz
│   ├── 953ab1d425769bb5c415bc9f5cef825d5524f5d5.nq.gz
│   ├── 9adebcee1627eeba2acf52f640a0c1f275acf894.nq.gz
│   ├── aba4321ba06b1ca4ac6cfdb50b92dcdf1325b0f2.nq.gz
│   ├── acf404da7e4bc2a07e01ccc0708ab819494c6ba4.nq.gz
│   ├── bf10fb71af1fd6fe31df96f63f92d3c48f8cb737.nq.gz
│   ├── c32b2e176ad93d24cc55bfdc648cca5f55d73cbb.nq.gz
│   ├── cb7306af529a9764055e7bf80d65e177ddf13d26.nq.gz
│   ├── d7219dddde3780c5676420e14cacb346a9c2b1a5.nq.gz
│   ├── d8f13521aa590e7aa42b50023d1d924e118f9da1.nq.gz
│   ├── df4f31cf32906b84d39946f6c84e7f378950c98c.nq.gz
│   ├── e3585d6db26066c65523ebca62a1d0f9b9c85686.nq.gz
│   ├── ebb07bfa22bc4f7ae17cf5e1461a5ed5a93c2ced.nq.gz
│   └── ece43ce8e6c12dc28eb7dacf6f4d7aa90972de38.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 93b7f01e5e9111b9f120463f4c21a726d75b0f4f.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 37 files
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

[UKPLab/emnlp2026-core-t](https://github.com/UKPLab/emnlp2026-core-t)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
