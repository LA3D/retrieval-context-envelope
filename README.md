# retrieval-context-envelope

An educational site about retrieval as a trajectory over a graph, and about the *context envelope* framing for what RAG is actually doing when it works.

Live at [la3d.github.io/retrieval-context-envelope](https://la3d.github.io/retrieval-context-envelope/).

## What is this?

Most public writing about RAG treats retrieval as "find the chunk that answers the question." This site argues that framing is wrong at scale. What retrieval actually has to assemble is a *context envelope*: the local neighborhood of concepts, layout cues, and cross-document evidence around the question. When the envelope is missing, the language model cannot answer, even when the strictly correct chunk is technically in the top-K.

Dense similarity search is one way to assemble an envelope, and it works well when the envelope fits inside a small K. It breaks when the envelope is spread across a graph that similarity cannot traverse. The site lays out why, and shows what a graph-based Markov retrieval looks like as an alternative.

The core content lives in `index.qmd`. Full rank tables and methodology live in `appendix.qmd`.

## Why a site, not a paper?

Publication cycles are too slow for the current pace of the RAG literature. The goal here is to educate practitioners and researchers on a specific framing, refine it as the underlying experiments mature, and link out to the code and datasets that back it up. If the framing turns out to be wrong, the page gets updated. If a new benchmark contradicts a claim, the page gets updated.

## Build

```bash
quarto render
quarto preview   # local dev server on :4200
```

Deploys automatically on push to `main` via `.github/workflows/publish.yml`, which pushes rendered HTML to the `gh-pages` branch.

## Authors

Priscila Moreira, Charles Vardeman, James Sweet, Christopher R. Sweet.

Random-walk-with-restart simulation by Priscila Moreira.
