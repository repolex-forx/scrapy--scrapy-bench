# Repolex Knowledge Graph of scrapy/scrapy-bench

RDF knowledge graph data for [scrapy/scrapy-bench](https://github.com/scrapy/scrapy-bench), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/scrapy-bench
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 48626327dc5d3b2195a16ad755b92174de123e35
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 48626327dc5d3b2195a16ad755b92174de123e35
│           └── chunk-001.nq.gz
├── blob
│   ├── 131cefc936c2b6e83f75a4089bbbf2053940dd90.nq.gz
│   ├── 1da24ef2ddb5f3085746a8abcd7419cd18177484.nq.gz
│   ├── 1fab0101eac6df9c1eb38ac994b56e15f192ded1.nq.gz
│   ├── 27f655aba1fda238aef686068a31dcc8892797ce.nq.gz
│   ├── 2ed4a88287f120418587a49f61c533185c126006.nq.gz
│   ├── 31b048c1cb902e5c33ea29250fb18c9ab19ab42e.nq.gz
│   ├── 4bb020a64a61da1efa78ac6a964a0f44f5663426.nq.gz
│   ├── 4f24aeaf949fa6072ae58c5aac5322061a2d622d.nq.gz
│   ├── 5e83f2737e03b6af140884e88534e5dd7071e1e4.nq.gz
│   ├── 6132c000bf3cbb50310488c1b97ddc700f6642c1.nq.gz
│   ├── 77bec14cb2615ab394906d1c56ea566d4a859615.nq.gz
│   ├── 98009bf07aabd40c1eb26ed741958c8488530e04.nq.gz
│   ├── 9a49ae526e6e8de9c16a55e39fab927be8b3cca7.nq.gz
│   ├── 9ad5f13903eb2894d90cf8c0bc6a33fafc5e3e0f.nq.gz
│   ├── ad246b0c61b848037805b00bdff4f043dfcaa7dc.nq.gz
│   ├── bdac39896befcc72f0e0eb6be6741e881c0b0ea3.nq.gz
│   ├── c0989b0873e778794f2f64b5414ec264a9c345bc.nq.gz
│   ├── c288a5601403d8b6946b3847ae0614b8b5432fcb.nq.gz
│   ├── c5c46986f2b7232f850532ab8b04e53ca4a3781c.nq.gz
│   ├── d901564b8ad15e9508ffb4d3e8c209f9bdd4ff76.nq.gz
│   ├── e2c03f843de1122c06351f1a491dab1ed79b99db.nq.gz
│   ├── e47452e139c151a17582f079f4ecadd5892e9144.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb717ad0143cd7a83036fbedf0cf0c9bfe2a3217.nq.gz
│   ├── ebae02c8a876d0847d38c472bcf05748bf2dce84.nq.gz
│   ├── ebd689ac51d69c5e1dbbe80083c2b20a39f8bb79.nq.gz
│   ├── ee658043628bc3c11efef334c5195eb7fe7ac2aa.nq.gz
│   ├── ef5d8f0a41e41de95f0a0dcc14a510eb759a9f90.nq.gz
│   ├── f20c301d6dab87b39f72f3a900b51479e4609ee0.nq.gz
│   ├── f3ed5428be0536f341e998097c28c3cb758dc316.nq.gz
│   ├── f5ede4c57922a3bd09c5bf47c0b6b86b339c57e3.nq.gz
│   ├── f7647a3128279e92ec8f6729eabfa79bdc3623c0.nq.gz
│   └── f8792aeaf6927f8dc8be50fee23fc4ad6bba6eb4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 48626327dc5d3b2195a16ad755b92174de123e35.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[scrapy/scrapy-bench](https://github.com/scrapy/scrapy-bench)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
