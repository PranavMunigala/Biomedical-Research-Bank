# OpenAI Foundation Public Data for Health Program

**Date logged:** 2026-09-17
**Category:** research/topics
**Source:** OpenAI Foundation announcement, September 15, 2026 ("Public Data for Health")

---

## Definition & Why It Matters

The Public Data for Health program is a $125 million philanthropic initiative announced by the OpenAI Foundation on September 15, 2026, that funds nonprofits and universities to create, preserve, and share high-quality scientific datasets for AI-driven medical research.

Core problem it addresses: modern biomedical AI models are only as good as the data they are trained on, and much of the most valuable biological/clinical data is either locked away (regulatory filings, proprietary trial data), never collected in a standardized way, or at risk of being lost (aging cohort studies, discontinued registries).

The analogy: think of it like a training-data curation pipeline for a large ML system, except the "labels" are wet-lab measurements and the "dataset" is scattered across hundreds of labs and institutions with no shared schema — the program is essentially funding the ETL and annotation layer for biomedical AI, not the models themselves.

It sits inside a broader $1 billion+ first-year commitment by the OpenAI Foundation across life sciences/curing diseases, jobs/economic impact, AI resilience, and community programs — itself a down payment on a previously announced $25 billion commitment to curing diseases and AI resilience.

The OpenAI Foundation is the nonprofit parent that controls the for-profit OpenAI Group PBC and holds substantial equity in it — the program is funded out of that structure, not a separate charitable trust.

## Key Techniques & Approaches

The program organizes the kinds of data it prioritizes into three categories — useful as a mental model for what good AI training data means in biomedicine:

- **Connected data** — datasets that link multiple biological layers together (e.g. a tumor genomic sequence + protein expression + immune response over time for one patient), analogous to a multi-modal training set versus single-modality data — much more informative per sample because it captures correlations across layers, not just one slice.
- **Scarce data** — data that is difficult or expensive to obtain, or actively at risk of disappearing (e.g. long-running natural history cohorts, discontinued trial data) — the philanthropic case here is similar to funding a rare, non-reproducible experiment: once the sample/cohort is gone, no amount of compute recovers it.
- **Direct data** — measurements as close as possible to the clinically relevant phenomenon itself (e.g. actual patient outcomes rather than a proxy biomarker), which matters for AI the same way a classifier trained on ground-truth labels outperforms one trained on noisy proxies.

Initial funded projects (illustrative, not exhaustive):

- **OpenADMET** (hosted via the Open Molecular Software Foundation, with governance/personnel from UC San Francisco, Octant, and Memorial Sloan Kettering) — builds open predictive models and blinded benchmark datasets for ADMET properties (Absorption, Distribution, Metabolism, Excretion, Toxicity) of small-molecule drug candidates. It runs recurring "blind challenges" — e.g. predicting cytochrome P450 (CYP3A4/2C9/2D6/1A2) inhibition or hPXR induction — where participants submit model predictions against held-out experimental data, functioning like a public leaderboard/benchmark (similar in spirit to a Kaggle competition) to stress-test whether ADMET-prediction models actually generalize. James Fraser (UCSF Bioengineering and Therapeutic Sciences chair) sits on the OpenADMET governing board. Access is genuinely free and open to anyone: for challenges like the ExpansionRx blind challenge, a person just needs a free Hugging Face account to download the public training set and submit predictions against the blinded test set for scoring — no affiliation, institutional login, or payment required.
- **CTD Commons** — focused on preserving and organizing regulatory and drug-development knowledge that would otherwise remain siloed inside regulatory filings or company archives.
- **University of North Carolina** — supports a generative immunotherapy initiative producing personalized cancer vaccine data, linking tumor sequencing, protein display measurements, and immune response information into one connected dataset (an example of the "connected data" category above).

## Landscape

- **OpenAI Foundation Life Sciences and Curing Diseases division** — led by Jacob Trefethen, who joined from Coefficient Giving (formerly Open Philanthropy science/health grantmaking), where he oversaw $500M+ in science/health grants. His division work spans three sub-areas: AI for Alzheimer's disease, public data for health, and accelerating progress on high-mortality/underfunded diseases.
- **Chan Zuckerberg Initiative (CZI)** is the closest large-scale comparison — as of late 2025/2026 CZI shifted the bulk of its philanthropy toward its Biohub, building large-scale AI/ML models and computing infrastructure (targeting 10,000 GPUs by 2028) for biology, alongside open-source tooling like 3D Slicer and scvi-tools. Notably, CZI cut roughly 70 jobs (about 8% of staff) in early 2026 to refocus on AI-powered biomedical research — a sign this space is still finding its organizational footing even among well-funded players.
- The **OpenADMET consortium** itself spans multiple institutions (UCSF, Octant, MSKCC, hosted via the Open Molecular Software Foundation) rather than being a single lab — a distributed-collaboration model common to open biomedical data infrastructure projects.
- Grantees are explicitly **not required to use OpenAI technology** with the funded data — a notable design choice that positions this as public-goods infrastructure funding rather than a captive pipeline for OpenAI's own models.

## Open Problems & Bottlenecks

- **Privacy vs. openness tension:** the Foundation states data will be made "as broadly accessible as possible" while protecting patient privacy/consent, but the concrete governance mechanics (de-identification standards, consent-reuse policy for old cohort data, cross-institution data-sharing agreements) are not detailed in public reporting — worth watching as grantees publish their first datasets. In practice this means access isn't uniform across the program: non-patient datasets like OpenADMET's are already free and open to download today, while datasets involving real patient data are expected to be gated more carefully and released on a slower, case-by-case timeline.
- **Sustainability of scarce-data preservation:** funding a one-time preservation effort does not guarantee long-term maintenance/hosting of a dataset once initial grant money runs out — a common failure mode for open-data infrastructure projects generally.
- **Benchmark gaming risk:** blind-challenge formats like OpenADMET's are only as good as how well the held-out data represents real-world distribution shift; a model that does well on one blind challenge (e.g. CYP inhibition) does not necessarily generalize to novel chemical scaffolds.
- **Concentration of influence:** a single well-capitalized funder (backed by OpenAI's valuation, per some financial press coverage) choosing which datasets get built could shape the field's research priorities disproportionately, even without requiring recipients to use OpenAI's own models.
- Independent verification of specifics (exact grant sizes per project beyond the $125M headline figure, timelines for public dataset releases) was not found in publicly available sources as of this research — flagged here rather than guessed.

## Personal Takeaways

This is a genuinely interesting inflection point to watch as someone interested in biomedical AI/BME: it is a large, well-funded bet that data infrastructure, not just model architecture, is the current bottleneck in applying AI to drug discovery and disease research — a thesis worth tracking against how CZI Biohub and other funders allocate their own money over the next year.

OpenADMET in particular is a concrete, hands-on entry point (its blind challenges are open to any researcher or student who wants to submit predictions) — worth exploring directly rather than just reading about it, if the ADMET/drug-discovery angle is appealing.

Open question: whether "no requirement to use OpenAI technology" holds up in practice, or whether de facto standardization toward OpenAI tooling happens anyway once datasets are large and well-curated enough to become the default training corpus in the field.

Worth revisiting in 6-12 months once initial grantees start publishing datasets, to see how the privacy/openness balance was actually implemented.

**Not independently verified:** exact grant sizes per individual project beyond the $125M program headline, and concrete dataset-release timelines — flagged here rather than guessed.
