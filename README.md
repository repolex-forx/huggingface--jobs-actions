# Repolex Knowledge Graph of huggingface/jobs-actions

RDF knowledge graph data for [huggingface/jobs-actions](https://github.com/huggingface/jobs-actions), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/jobs-actions
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 10aa428cce8fa058291d2c6bccc7d0025863c689
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 10aa428cce8fa058291d2c6bccc7d0025863c689
│           └── chunk-001.nq.gz
├── blob
│   ├── 00b243a9ae7d2ef5bba14dac886181f8d59c8d0c.nq.gz
│   ├── 0839786ee8dfdee52226549bb97348d612cb46ad.nq.gz
│   ├── 0a02d6b1297b2bce27bc61444c6dff082a952f58.nq.gz
│   ├── 1280258ff1cfff7dea9313b1bf00fc1cfff00cfd.nq.gz
│   ├── 14fbf34d15c42dcac5d52a89f44adaf12a82cf49.nq.gz
│   ├── 15f7bdd7916ac5fca2274ad5d1239bafe0f0f5a2.nq.gz
│   ├── 20e3b1d67d298fcbc811badc5ecfb67982280cf3.nq.gz
│   ├── 24d062de3f09c0508c4d6cdab293cfcc22590981.nq.gz
│   ├── 33ec91d5872aa924fe2f260ba298e7f605d7b236.nq.gz
│   ├── 444a5d974b64c3d9f8ccb5843a0d5924f63ad48b.nq.gz
│   ├── 49ff9b506c7ef3cea6d533f95b59fdb6fda954eb.nq.gz
│   ├── 4c0ba09736a5dc2215376bb5d7d81b2503c22cb2.nq.gz
│   ├── 5301acc32a0c2b9600b9acbae6d2898e01f0278a.nq.gz
│   ├── 542b3ebc08a949659db5af922a846d7aeacd92d9.nq.gz
│   ├── 5e45bf8b798d271215848544d0906725d407b6ed.nq.gz
│   ├── 62e4707a9d80f9c85e860162dbdf6374b25ffbad.nq.gz
│   ├── 6e9acbfc10cbbd14164384c6aedbf31a842bc929.nq.gz
│   ├── 7149fa04d680a6cf38c948efca83ec81baf83feb.nq.gz
│   ├── 7848d8e93bc554bdb591a68230bf3935335b1e76.nq.gz
│   ├── 8c6bada54704042a056292881ccdfe5c7426c8b1.nq.gz
│   ├── 8dfd8cdf7b8c24c7845070a59fca7714e79b332b.nq.gz
│   ├── ac695f0ded78068555df6e8c7dea3675ace4d07c.nq.gz
│   ├── afd5bfa5ec2580fc44b994d974364c4426411d9b.nq.gz
│   ├── b044ce1cc57d7a57cc57760bfab0269897a33507.nq.gz
│   ├── b2db2322ba935de853d78e79f75e2990f66f8665.nq.gz
│   ├── b6ad50153e862d0e7abb2683d5ad0776b9d59f3a.nq.gz
│   ├── c634c013d88c57bac9b300f5536d9118a5d1abc6.nq.gz
│   ├── c6a26134991cd6dfe3e091fd9b3b37147d1cf5fd.nq.gz
│   ├── d28adf4ad848209d0a5c1c8b1bda06bf1385be2f.nq.gz
│   ├── d94e8e5d7b860da42c819a170448846e28eae7b5.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f793ba31278b33f01a3f967e41a801dcc600fa92.nq.gz
│   └── f7b7288faffd77ff99c29d6cfdb26f035b33ddd2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 10aa428cce8fa058291d2c6bccc7d0025863c689.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 40 files
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

[huggingface/jobs-actions](https://github.com/huggingface/jobs-actions)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
