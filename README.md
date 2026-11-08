# Repolex Knowledge Graph of argilla-io/coset

RDF knowledge graph data for [argilla-io/coset](https://github.com/argilla-io/coset), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/coset
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f7e56e7973a7a51e470d883ad61e674818410761
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f7e56e7973a7a51e470d883ad61e674818410761
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e113323f08e70597edb7a72fdb8f43f27863dd7.nq.gz
│   ├── 163ca22c7173979a61a576d475a61a2759dcabf9.nq.gz
│   ├── 337066c29519ddd86d9eb5cd6db3978db151b1c8.nq.gz
│   ├── 65164850ae45bae29cc151009f591be74033eacc.nq.gz
│   ├── a0be9a36529c7561391d6b29e3a3c260fe86271c.nq.gz
│   ├── b3f0e91d7e535bf14ca342a9cd5ba288156234ee.nq.gz
│   ├── bfaed5d798b928c7f6bd12ca0c93d50b9dac6fa2.nq.gz
│   ├── e321b66e736e19b57ce2b794b0c86d9e1f02cd3b.nq.gz
│   ├── e5ea451bc15e65619a4f7d6def8cf142a262554a.nq.gz
│   ├── ec5d11c4d7d5b44b6ff1b4bcb30cfef7c97fcdcb.nq.gz
│   └── f31f7d593478a3fad7e305544766ce281446acd7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f7e56e7973a7a51e470d883ad61e674818410761.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 17 files
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

[argilla-io/coset](https://github.com/argilla-io/coset)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
