# Repolex Knowledge Graph of sphinx-contrib/btn

RDF knowledge graph data for [sphinx-contrib/btn](https://github.com/sphinx-contrib/btn), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/btn
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9efc1948410e84a5ae32becfe0185a6f7b9245d5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9efc1948410e84a5ae32becfe0185a6f7b9245d5
│           └── chunk-001.nq.gz
├── blob
│   ├── 10a702e49d39e7a14c8bc90d0e7d1751243fb24f.nq.gz
│   ├── 12c4bb9850033098f1d597abcfb0a1a58cbe9f90.nq.gz
│   ├── 256fdb147feafa568b1f10b555012ed7e8359d67.nq.gz
│   ├── 25c621a8eeba4d0b4e3d797f44ca3aaa516689e8.nq.gz
│   ├── 2bc5d5f7118646c11eac4472d076e00ffdd1a944.nq.gz
│   ├── 3bb3189820f05744c8f286b78bda0636ef4e2147.nq.gz
│   ├── 49ed4fa684c8f665bc0c027956b2357efe91c625.nq.gz
│   ├── 5d1a3fd3aa8827cd3f86d06deb8892b7ac4c4847.nq.gz
│   ├── 606849326a4002007fd42060b51e69a19c18675c.nq.gz
│   ├── 66d68df3079d910dd8e1a0452785d7d993d1009e.nq.gz
│   ├── 6b5ff6472965ce27aecaabb6e60c85529f14908d.nq.gz
│   ├── 751122e07b2b1c828bbc7fc6f59875919aedb18b.nq.gz
│   ├── 7700ac672f38728bdae50a23f65526e58834364e.nq.gz
│   ├── 9b77ea713f9805f941350851fb4f79c0f70a0f4b.nq.gz
│   ├── 9e1bb2cdbc539767f456cb5d667ad22bb9f62096.nq.gz
│   ├── 9f1dce313935fea05f9becbb7df3113773d1b8c7.nq.gz
│   ├── a990eb4eff57bb2030ecc7b5b4993a9dc0bcdbeb.nq.gz
│   ├── b17ba329bee44a77f4a0ce74d18d118a0fd7f86d.nq.gz
│   ├── b911cff0f19d0500ca06099598df217be9d11e84.nq.gz
│   ├── babf9b2c03bd48b7086b64f1da9249278f3d8c3a.nq.gz
│   ├── c163a73d090eac0beadd3a0e574a8910992ed5c0.nq.gz
│   ├── c59b40ff0ffdfd5a68dd1ffae98250832e116ac0.nq.gz
│   ├── ca460b1316573a844cebc554279eca1cf70db15e.nq.gz
│   ├── d4b9eaa42769065f937246612223143853487154.nq.gz
│   ├── d761b69ec83570344c8a22b732c647e66be57f58.nq.gz
│   ├── db50b2601c7f7bf2fc664000ac1df5ac7cd43167.nq.gz
│   ├── dc05707b5080fb6d46576f66259ec3baafee258d.nq.gz
│   ├── f0343c60681c8a20cc25a9e1a32ae715d1aed647.nq.gz
│   ├── f4ebcddab7964ac97e3afb0275ca39ca1cfb463e.nq.gz
│   └── f9c309e0b4fcd39242dabd1d593cd7877b7493fb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9efc1948410e84a5ae32becfe0185a6f7b9245d5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 38 files
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

[sphinx-contrib/btn](https://github.com/sphinx-contrib/btn)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
