# GeneBench-Pro

**Date logged:** 2026-09-12
**Category:** research/products
**Source:** bioRxiv preprint (2026.06.29.735386v2) by Jeremiah Li and Andrew Ho (OpenAI); also mirrored on SSRN and released alongside an OpenAI blog post and a technical PDF

---

## What It Does

GeneBench-Pro is a benchmark released by OpenAI on June 30, 2026 to measure whether AI agents can do the judgment part of computational biology research, not just recall facts or run a known pipeline.

The gap it targets: existing biomedical QA benchmarks mostly test whether a model knows things (facts, definitions, standard pipeline steps). GeneBench-Pro instead tests whether a model can navigate a messy, realistic analysis — the kind a computational biologist actually does — where the data has quality problems and the right method is not obvious upfront.

Who it is for: AI labs and biomedical-AI teams benchmarking whether their models are trustworthy enough to be used as research collaborators (not just chat assistants) on real genomics/translational-biomedicine problems.

Analogy (CS framing): think of it like the difference between a leetcode-style unit test (a fixed, well-specified problem with a known correct algorithm) and a real production incident where you first have to figure out which metric is even broken, whether the data feeding it is corrupted, and only then decide what to fix — GeneBench-Pro scores the second kind of task, where recognizing the problem is half the work.

## How It Works

Structure: 129 problems spanning 10 primary domains and 21 terminal subdomains with a genomics-centered core — including population genetics, pharmacogenomics, cancer somatic genomics, statistical genetics, and clinical diagnostics.

Problem format: each problem hands the agent a messy dataset, brief context, and a target quantity to estimate (an estimand). The agent must work through a chain of dependent inferential decision points — filtering/correcting data, spotting QC or ascertainment issues, choosing a statistical method, running the inference, and revising the plan if intermediate results contradict the initial hypothesis — to reach one verifiable final number.

Deterministic grading: every problem is generated from a known causal structure, so there is a single correct answer despite the open-ended path to get there — similar to how a randomized simulation with a known ground-truth parameter lets you grade an estimator objectively even though many different modeling choices could plausibly be tried along the way.

Human baseline: reviewers estimated a typical problem takes a human expert 20-40 hours to complete properly; models attempt the same problem for a small fraction of that compute cost.

Key finding — the noticing-to-acting gap: models often do flag a data-quality problem (an outlier, a confounder, a QC failure) in their reasoning trace/scratchpad — the observation gets written down — but then proceed with the original analysis plan anyway, as if the flag had never happened: the wrong statistical test still gets run, the outlier still isn't filtered, the estimate still isn't adjusted. It's the same shape as a program with an `if (anomaly_detected) { log.warn(...) }` check where the branch body never actually does anything — no return, no changed code path, no adjusted parameter — the warning fires and execution keeps going down the original path regardless. The failure isn't perception (models can see the problem); it's the missing link between noticing something and acting on it. OpenAI frames the target skill as research taste: the accumulated judgment calls about which questions the data can support, how a warning sign should update your model, and when to discard your original plan entirely.

Results so far (as of the June 2026 release): top scorer GPT-5.6 Sol Pro at 31.5% accuracy, GPT-5.6 Sol at 28.7%, Claude Opus 4.8 at 16.0%, GPT-5.5 at 12.0%, and Gemini 3.5 Flash at 8.1% — meaning even the best model is wrong roughly two-thirds of the time. OpenAI notes it tried to guard against building a benchmark biased toward its own model family, but competitor models did not outperform the comparable-generation GPT model in testing.

## Company & Competing Products

Publisher: OpenAI (no dedicated company profile yet in this research tree; general-purpose frontier AI lab, not a biomedical-specific company). The models being scored (GPT-5.6, Claude Opus 4.8, Gemini 3.5 Flash, etc.) are likewise general-purpose frontier chat/agent models repurposed for this task, not specialized bio-specific systems — the benchmark is asking how far today's general reasoning models get on real computational-biology judgment calls, not evaluating a purpose-built biomedical model.

Competing/adjacent benchmarks in the same can-AI-actually-do-bio-research-work space:
- **BixBench (FutureHouse)** — roughly 50 real-world computational-biology data-analysis scenarios (genomics, RNA-seq, variant analysis, phylogenetics) with open-answer questions; frontier models score around 17% open-answer / near-random multiple-choice, though GPT-5.5 leads its leaderboard at 0.805 on an easier scoring variant.
- **BioLP-Bench** — a different angle: injects deliberate errors into wet-lab protocols to test whether a model can catch failure-causing mistakes, rather than testing statistical-analysis judgment.
- Broader family of similar 2026-era efforts (BioProBench, BioKGBench, LAB-Bench/LABBench2) reflects a wider trend of the field moving from fact-recall QA toward process/judgment evaluation for AI in biology.

GeneBench-Pro differentiates itself by grounding every problem in a deterministic causal structure (objective grading) and by explicitly targeting the multi-step, revise-your-plan nature of statistical genetics work, rather than single-shot data analysis or protocol review.

## Stage & Validation

**Stage:** freshly released research-level benchmark (June 2026), not yet a widely adopted industry standard — more analogous to a new academic leaderboard than a mature/certified evaluation suite.

**Validation approach:** problems are grounded in real genomics research scenarios and graded against a known ground-truth causal structure rather than human judges, which gives objective, reproducible scoring — but the benchmark's real-world predictive validity (does scoring well on GeneBench-Pro actually predict a model being useful on a real wet-lab-adjacent research project) has not been independently tested yet since it just shipped.

Low absolute scores across every current frontier model (under one-third accuracy for the best model) suggest the benchmark is currently far from saturated — a meaningfully harder bar than most existing biomedical-AI evaluations.

## Personal Takeaways

Interesting as a concrete, measurable definition of research taste — the noticing-to-acting gap is a clean way to describe a failure mode (detecting a problem but not acting on it) that shows up constantly in real data analysis, human or AI.

Worth revisiting in 6-12 months to see whether scores climb quickly (suggesting it is a tractable/gameable benchmark) or stay low (suggesting it is capturing something genuinely hard about scientific judgment) — the BixBench comparison suggests these judgment-heavy biology benchmarks currently resist rapid progress.

Open question: since OpenAI both built the benchmark and currently leads it, worth watching whether independent groups replicate the ranking and whether the problems get gamed/overfit once training labs have visibility into the eval format — the same overfitting risk any widely-publicized eval faces once it becomes a target metric.

**Not independently verified:** full breakdown of all 129 problems, the exact 21 subdomains, and reviewer methodology for the 20-40 hour human-baseline estimate — the underlying PDF was not directly parsed for this profile, only summarized via secondary sources.
