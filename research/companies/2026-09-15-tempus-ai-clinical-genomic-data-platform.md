# Tempus AI

**Date logged:** 2026-09-15
**Category:** research/companies
**Source:** tempus.com; tempus.com/research; public investor-relations pages; public SEC filings/financial data sites; TIME's 10 Most Influential Health and Life Science Companies of 2026

---

## Company Overview

Tempus AI is a Chicago-based health-tech company that applies artificial intelligence to enormous amounts of real clinical and molecular (genomic) data, aiming to make cancer care — and increasingly other diseases — genuinely personalized rather than a one-protocol-fits-all approach.

- **Founded:** 2015, by Eric Lefkofsky (also co-founder of Groupon). The founding story is personal: Lefkofsky started the company after his wife was diagnosed with breast cancer and saw firsthand how little molecular/genomic data actually made it into a treating oncologist's hands in real time.
- **Headquarters:** Chicago, Illinois.
- **Stage:** Public — IPO'd on Nasdaq (ticker: TEM) in June 2024.
- **Core mission:** Build what the company describes as the world's largest library of clinical and molecular data, plus an "operating system" that makes that data useful at the point of care — starting in oncology, now expanding into cardiology, neuropsychiatry, infectious disease, and radiology.

**The problem they're solving:** Most of a cancer patient's richest data — tumor genetic mutations, full clinical history, doctors' free-text notes — sits in disconnected silos (pathology labs, EHR systems, PDFs) and never gets structured or connected to outcomes data from other patients. The bet: sequence tumors at scale, structure the surrounding clinical data, and apply AI on top so a doctor can answer "given everyone like this patient, what actually worked" — not just "here is a list of mutations."

## Technology & Products

The workflow is best understood as a two-stage pipeline: collect very specific data about a cancer patient (the "wet lab"), then run software/AI on top of it to help doctors make better decisions (the "dry lab"). Owning both ends is the core technical differentiator — most competitors do one or the other.

- **Stage 1 — Wet lab (collect the data):** a patient's tumor sample (or a blood draw for the liquid-biopsy version) gets sequenced, producing a structured list of mutations, gene fusions, and biomarkers — essentially a "feature vector" describing that specific tumor's genetics, rather than a doctor eyeballing one gene at a time.
- **Stage 2 — Dry lab (make the data useful):** that genomic data, plus the patient's clinical history (doctors' notes, EHRs, pathology reports), gets structured and pooled with data from every other patient who has gone through Tempus, so AI/software can answer "for patients who looked like this one, what actually worked?" instead of applying a one-size-fits-all protocol.

**Tempus xT** — the flagship next-generation sequencing (NGS) assay. It profiles 648 cancer-related genes in a patient's tumor tissue against a matched normal (non-cancerous) sample, detecting mutations (SNVs), copy-number changes, insertions/deletions, gene fusions, tumor mutational burden (TMB), and microsatellite instability (MSI) — the standard biomarkers oncologists use to pick targeted therapies or immunotherapy candidates.

**Analogy:** this is essentially high-dimensional feature extraction on a tumor — instead of a doctor eyeballing one gene at a time, the assay outputs a structured feature vector (hundreds of genomic variants plus summary statistics like TMB) that downstream software/models can then reason over. It's like running a program's binary through a diagnostic tool that outputs a structured anomaly report, instead of a human inspecting it line by line.

**Tempus xF** — a liquid biopsy version: instead of a tissue biopsy, it detects the same kinds of genomic alterations from tumor DNA circulating in a patient's blood (105 genes). A blood draw is far less invasive than a surgical tissue biopsy, and it can be repeated over time to track how a tumor's genetics change under treatment.

**Tempus Next** — a clinical-decision-support layer on top of the accumulated data, catching care gaps — e.g. flagging a patient statistically likely to test positive for an actionable biomarker who has not been tested, prompting the clinician to order it.

**Analogy:** like a recommender/ranking system trained on population outcome data, surfacing "patients who look like X" the same way a fraud-detection model flags an anomalous transaction — except the flag nudges toward evidence-based testing.

**Tempus One** — an AI assistant (chat-style) for oncologists that simplifies ordering tests and interpreting genomic reports, so a clinician doesn't need to be a bioinformatician to act on the data.

Tempus also sells real-world data (RWD) and analytics products to pharma/biotech companies for drug development and trial design — effectively monetizing the same pooled dataset twice: once via the diagnostic test itself, and again via analytics built on the aggregate.

Full product/pipeline list: tempus.com and tempus.com/research.

## Market & Competition

- **Who they sell to:** hospitals/oncology practices (genomic tests, decision tools) and pharma/biotech companies (real-world data for drug development). Roughly 4,000 healthcare provider connections.
- **Closest competitors:** Foundation Medicine (Roche-owned, comprehensive genomic profiling, arguably most similar), Guardant Health (liquid-biopsy leader), and GRAIL (early cancer detection/screening).
- **Differentiation:** owning both wet-lab and dry-lab/AI sides gives tighter data-quality control and an integrated product (test + decision support + RWD) versus narrower specialists like Illumina or Guardant.
- **Roadblocks to entry:** CLIA/CAP-certified lab operations, years of accumulated data to make AI genuinely useful (a cold-start problem), and slow, relationship-heavy hospital EHR/workflow integration.

## Financials

- Public (Nasdaq: TEM), IPO'd June 2024; market cap around $8.3 billion as of mid-2026.
- 2025 revenue: ~$1.27 billion, up ~83% year-over-year from ~$693 million in 2024.
- 2026 guidance: $1.595–1.605 billion (~25% growth); H1 2026 revenue $730.6M vs. $570.4M in H1 2025.
- Still not profitable but narrowing losses: 2025 net loss ~$245M (down ~67% from 2024); Q2 2026 EPS of -$0.04 beat estimates of -$0.20.

*Drawn from public SEC filings/financial data sites — no deeper segment-level verification attempted.*

## Team, Leadership & Culture

- **Eric Lefkofsky** — Founder & CEO since inception; previously co-founded and led Groupon — a repeat, well-resourced entrepreneur.
- **Ryan Fukushima** — CEO, Data & Apps; the company's first employee, central to scaling the data infrastructure and clinical-AI distribution.
- Other named executives: Jim Rogers (CFO), Shane Colley (CTO), Dr. Ezra Cohen (CMO, Oncology), Laura Elster (CCO, Diagnostics).

*Bios drawn from public investor-relations pages; finer org details not independently verified.*

**Culture:** named to TIME's 10 Most Influential Health and Life Science Companies of 2026 — a reasonable external signal; deeper employee-review-level sentiment not verified here.

**Networking add-on (one quick, capped search):** no confirmed Rutgers BME graduate found at Tempus specifically. One loosely relevant same-field lead: Dr. Kathleen Burke, Senior Director of Computational Biology at Tempus (PhD from University of Rochester, not Rutgers) — a field-match, not an alumni match. Worth a deeper dedicated search later if this matters.

## Careers & Personal Fit

- Structured Summer Internship Program in Chicago (hybrid, ~3 days/week), spanning AI/data science, ML, software engineering, and generative AI, June–August.
- Transparent pay: $25/hour undergrad summer analysts, $35/hour grad ML summer associates, plus relocation bonus and housing help.
- Example role: Generative AI Summer Analyst, aimed at undergrads in biological sciences/biotech with MD/PhD interest and R/Python/Excel skills.
- Full-time hiring spans software engineering, computational biology, and commercial roles at a fast-growing public company; no deep listings browse attempted beyond this.
- **Fit:** a BME/CS/math background maps well — sequencing needs bioinformatics thinking, decision-support/Tempus One needs ML/software engineering, RWD needs statistics. Good for healthcare-domain work without a pure wet-lab background.

## Personal Takeaways

**Appeal:** real patient impact, a legitimate hard data/ML problem (messy multimodal clinical data at scale), and a business model showing real traction (83% revenue growth, narrowing losses) rather than pure hype.

**Drawbacks:** still unprofitable; depends on continuing to win provider/pharma relationships against well-resourced competitors like Roche-backed Foundation Medicine; public-company quarterly scrutiny.

**Watch:** path to profitability, adoption of the AI-decision-support products (Next/One) versus just assay revenue, and how far the platform genuinely extends beyond oncology in practice.
