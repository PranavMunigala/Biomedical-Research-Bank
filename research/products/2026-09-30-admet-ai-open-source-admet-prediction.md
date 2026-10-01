# ADMET-AI

**Date logged:** 2026-09-30
**Category:** research/products
**Source:** Code: github.com/swansonk14/admet_ai | Paper: Bioinformatics (2024) | Web server: admet.ai.greenstonebio.com

Product profile: open-source machine-learning platform for predicting drug ADMET properties. See also: Computational Drug Discovery.

---

## What It Does

ADMET-AI is a free tool that takes a molecule (written as a SMILES string) and predicts how it would behave in the body, before anyone synthesizes or tests it.

- **ADMET** = Absorption, Distribution, Metabolism, Excretion, Toxicity: the properties that decide whether a molecule that hits its target can become a safe, usable drug.
- Predicts **41 ADMET properties** per molecule, trained on datasets from the Therapeutics Data Commons (TDC).
- **Built for scale:** designed to screen large chemical libraries (millions of molecules from virtual docking or generative AI) where lab-testing every compound is impossible.
- **Who uses it:** computational/medicinal chemists, academic drug-discovery labs, and AI drug-design groups needing a fast drug-likeness filter.
- **Two ways to run it:**
  - a web server (admet.ai.greenstonebio.com, up to 1,000 molecules per query)
  - an open-source Python package (`pip install admet-ai`, MIT license) for local batch or private-molecule prediction

## How It Works

- **Molecule as a graph:** atoms are nodes, bonds are edges.
- **Model:** Chemprop-RDKit, a message-passing graph neural network from the Chemprop library, augmented with 200 RDKit physicochemical features (molecular weight, logP, H-bond donors, etc.).
- **Multi-task learning:** two multi-task models, one for the 10 regression properties (e.g. solubility) and one for the 31 classification properties (e.g. hERG-toxic yes/no).
- **Ensembling:** each prediction averages 5 models trained on different data splits.
- **DrugBank context:** each prediction also gets a percentile vs. ~2,579 approved drugs in DrugBank (optionally filtered by ATC drug class).

**Analogies:**

- **Message passing** = iterative neighbor aggregation on a graph: each atom updates its vector from its neighbors for k rounds, so it encodes its k-hop neighborhood; summing gives a molecule embedding.
- **Multi-task model** = shared encoder, many output heads: related tasks regularize each other, like transfer learning.
- **DrugBank percentile** = percentile normalization against a reference distribution.
- **Plain language:** a spellchecker for drug candidates — flags likely problems before you spend money making the molecule.

## Company & Competing Products

**Made by:** Kyle Swanson (Stanford PhD, Paul Berg Interdisciplinary Biomedical Graduate Fellow) with collaborators including James Zou (Stanford biomedical data science). Web server hosted on a Greenstone Bio domain; that relationship not independently verified.

**Sibling project:** SyntheMol (Nature Machine Intelligence, March 2024) designed 6 novel antibiotic candidates against drug-resistant *A. baumannii* from 130,000+ building blocks.

**Competitors:**
- **ADMETlab 3.0** — 119 endpoints, 400,000+ entries, similar multi-task D-MPNN + descriptors; adds uncertainty and structural alerts.
- SwissADME, pkCSM, admetSAR 2.0, vNN-ADMET.
- Commercial tools (Simulations Plus ADMET Predictor, Schrödinger) and in-house pharma models.

**Differentiator:** speed + open-source local deployment + DrugBank contextualization.

## Stage & Validation

- Released research software, peer-reviewed in *Bioinformatics* (June 2024).
- Highest average rank on the TDC ADMET Leaderboard (22 datasets) at publication.
- R² > 0.6 on 5 regression datasets; AUROC > 0.85 on 20 classification datasets.
- 45% faster than the next-fastest public web server; 1M molecules in ~3.1 h locally (32 CPU + GPU).

**Version note:** the current v2 package uses Chemprop v2 without RDKit features, so it differs from the benchmarked model.

## Personal Takeaways

- Great learning entry point: small open-source codebase combining GNNs, multi-task learning, and ensembling.
- **Open question:** generalization to novel chemical space (applicability domain).
- **Watch:** ADMETlab updates, TDC leaderboard, foundation-model approaches.
