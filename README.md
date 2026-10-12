# Repolex Knowledge Graph of jpvanhal/inflection

RDF knowledge graph data for [jpvanhal/inflection](https://github.com/jpvanhal/inflection), parsed by [repolex](https://repolex.ai).

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
rlex download jpvanhal/inflection
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 88eefaacf7d0caaa701af7c8ab2d0ab3f17086f1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 88eefaacf7d0caaa701af7c8ab2d0ab3f17086f1
│           └── chunk-001.nq.gz
├── blob
│   ├── 09a346ca5bbe97b6e57c53ee19957d254337aea1.nq.gz
│   ├── 0fe0fe1d181467b1001f4a432bff15e1ca3f9ae8.nq.gz
│   ├── 353e029dabc81c1c255e09f943d190f5f53a4a31.nq.gz
│   ├── 38558bf3772264eefb5473229510501d347c7d5b.nq.gz
│   ├── 48f8de6a8e80669368bad0ad8e2d6233c1f2d029.nq.gz
│   ├── 66ddafdbe32835512fc4222f56e4f472fa0f2c6b.nq.gz
│   ├── 7424ff6b2b8a24650c0eabc799c2cf85255cf975.nq.gz
│   ├── 74c7482792e866fe4b47ff9d61b8007474f8c645.nq.gz
│   ├── 810868e516aeca2e9978995b5e74a410666f1804.nq.gz
│   ├── a6dce86a7a3154caf9d191a162fd387626c6caaa.nq.gz
│   ├── ac449972a9f366486e1018d160de4460362ac6b8.nq.gz
│   ├── c85001d31d2635defe693bd06d8b23b9c8dad844.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb7c289273aff46aca88db7c3e38873590284e48.nq.gz
│   ├── f1e64a3d2117ef4baca2afa040f622bd91fa85e9.nq.gz
│   ├── f97550317ff19f282e97409b39740afdf8707830.nq.gz
│   └── ffac5ce22e60816f18267d742455e4936b6d1c1a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 88eefaacf7d0caaa701af7c8ab2d0ab3f17086f1.nq.gz
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

[jpvanhal/inflection](https://github.com/jpvanhal/inflection)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
