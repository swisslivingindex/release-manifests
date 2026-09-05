# Swiss Living Index — Release Manifests

Public, append-only record of every data release of [swisslivingindex.ch](https://swisslivingindex.ch)
— the official-source comparison of all 26 Swiss cantons.

## What this repo is
Reproducibility and audit surface (nothing more): for every immutable release you find here the
`manifest.json` listing **every source dataset with its SHA-256 checksum and byte size**, the
compiled-surface checksums, the git commit pin, and the public corrections register. The archived
data itself is served at `https://swisslivingindex.ch/archive/` (canton-level sources verbatim,
content-addressed).

## How to verify a figure
1. Open the metric page (e.g. `/de/steuern/`) → "Verify this figure" drawer → note dataset path + release.
2. Fetch the dataset object from `https://swisslivingindex.ch/archive/` (linked in the manifest).
3. `shasum -a 256` it and compare against the manifest here. Checksums never change: corrections
   create a NEW release and are logged in `corrections.json`.

## Scope
This repo intentionally contains **manifests and registers only** — no pipeline or engineering
code. Licensing: the Swiss Living Index compilation is CC BY 4.0; underlying figures remain
official Swiss federal data (BFS, ESTV, BAG, ElCom, MeteoSwiss, EFV, SECO) under each producer's
terms. Synced automatically on every release.

Powered by [Mirabello Consultancy](https://www.mirabelloconsultancy.com/).
