# Repolex Knowledge Graph of kivy/angle-builder

RDF knowledge graph data for [kivy/angle-builder](https://github.com/kivy/angle-builder), parsed by [repolex](https://repolex.ai).

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
rlex download kivy/angle-builder
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2e0cffee9de5b1f19f7fb07264718331db387d83
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2e0cffee9de5b1f19f7fb07264718331db387d83
│           └── chunk-001.nq.gz
├── blob
│   ├── 06b553e785df9ab24054fed423dcaa4888ac3c70.nq.gz
│   ├── 1c0ea63e1b515f9b48e29da4d50af5812eb96afd.nq.gz
│   ├── 29e3ea1728a2502a55c4aa71dbb40ee6111d36ef.nq.gz
│   ├── 2a6b6176297ce5cf6079c761a9145ebe30a72ca0.nq.gz
│   ├── 4420b19c601d02fd1c7cfacf04936cecfd326339.nq.gz
│   ├── 4635c77a13814d39e3732f5ae50733068d57822b.nq.gz
│   ├── 46d8c96e6ebd2bd9f0c8baac80d54482a90d1618.nq.gz
│   ├── 522e9016fab3b955e1e4dd5b76c3a211f955c962.nq.gz
│   ├── 7303e4b1d03925778bfdabec63acef7bde1123b3.nq.gz
│   ├── 776063815ca3e7a8a2d9382673a16478700aedaf.nq.gz
│   ├── 7c7f513b10dc91357dd3bdf76fb3f9f28c8941d6.nq.gz
│   ├── 88e22556fd0722b3dd282d13d86929627b6685ca.nq.gz
│   ├── 919e91ee46d7c42cd0a67cbf8cdc9f6e28a056df.nq.gz
│   ├── 937a83fc6d281ff93cbd18d4316fc6d10a8c421d.nq.gz
│   ├── b03de1ab4fde14808780a729bc18e454f46f7cd7.nq.gz
│   ├── cf40bdc094f0e0065a96be61e11c0755b38ba150.nq.gz
│   ├── da59f2278bc1b4d35b41c4b8de4f0ebd5e14c2e2.nq.gz
│   ├── e9e1e9b790eeb90a4ab90a59c96fbb667b9a0cce.nq.gz
│   ├── ec51ec6a0e5393a80855a5deae6e4e1312451a54.nq.gz
│   └── fd67fc4c09f139367f9c54744faf4a1772777be7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2e0cffee9de5b1f19f7fb07264718331db387d83.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[kivy/angle-builder](https://github.com/kivy/angle-builder)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
