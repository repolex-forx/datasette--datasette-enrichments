# Repolex Knowledge Graph of datasette/datasette-enrichments

RDF knowledge graph data for [datasette/datasette-enrichments](https://github.com/datasette/datasette-enrichments), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-enrichments
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 76a4de39f54de57b42cfb6a77c8908459ceec89d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 76a4de39f54de57b42cfb6a77c8908459ceec89d
│           └── chunk-001.nq.gz
├── blob
│   ├── 14d5885de2c52f08c362b9b5dc71e135bca10f1a.nq.gz
│   ├── 175b9b87cf6a3826e3333ae8bc841baed69d53dc.nq.gz
│   ├── 1ec5eac981f9771b04d89001da1231af7054c67a.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 29ccfb756db7080cf9492a4b22a22aa1cebf2eea.nq.gz
│   ├── 39219754d3cd72481d924fa5c911487a3c2b1f20.nq.gz
│   ├── 41030af05a0c799ced08ff8ac64603656d981bf6.nq.gz
│   ├── 441f3b537d48b4bd003d4726b604f082ee1c2415.nq.gz
│   ├── 4ba6e475df1d0706dfb2df2a859ecaaa6244ef67.nq.gz
│   ├── 4cdda0ea97aeb7a7e28ab7e9ba12f0cd72997d60.nq.gz
│   ├── 578b1e60197796dbf00368e369630339116cf5d9.nq.gz
│   ├── 5b40b31684ad549fd1d9dfcbebeaff62d48e13cf.nq.gz
│   ├── 6b64e0088e653e7c895d887aef423c3704a92d09.nq.gz
│   ├── 6d9755964066fedd5bd6b95154fe327682aa1b0e.nq.gz
│   ├── 78614cc7e55a12384394af3e8735f3f7b0bfba7c.nq.gz
│   ├── 94a9890a2e6ba32601024d904ec74504f5e4d9d9.nq.gz
│   ├── 9c9ccedebf79ac8224e2be474c34cbf994dc2f79.nq.gz
│   ├── a279768f126b210e024ba7e983a9ee2ccfd15118.nq.gz
│   ├── a780ae79e3ba227a7d8a871c58d72d88f24f190d.nq.gz
│   ├── af9ee28f234999fbdb2e09a582aef04443a78b65.nq.gz
│   ├── bf8c1f3922d0b8648e6642693704f46b6640b87b.nq.gz
│   ├── c483b66e03429b532e23b6f44e817f80638b11f2.nq.gz
│   ├── c50221c38dc29230a43c5059fd63ef3aa966e397.nq.gz
│   ├── ce828c2d5a3a7136dab035dcb5f7860c0b22e12b.nq.gz
│   ├── e35d8850c9688b1ce82711694692cc574a799396.nq.gz
│   ├── e40129626db60dc6df288dcf6d5be6e03a8584d8.nq.gz
│   └── ea6a81bceda982a608d3ec4e272c8baf26748bd4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 76a4de39f54de57b42cfb6a77c8908459ceec89d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[datasette/datasette-enrichments](https://github.com/datasette/datasette-enrichments)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
