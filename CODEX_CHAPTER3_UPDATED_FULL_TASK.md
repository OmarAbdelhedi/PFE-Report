# Codex Task — Write Chapter 3 of the Thesis Report
# Probing Compositional Question Difficulty in Language Model Representations

## Repository

```text
/home/omar/work/PFE/report
```

## Target Chapter 3 file

The current report still contains a legacy Chapter 3 titled:

```text
A Systematic Survey of the Trust Layer of RAG
```

That is old placeholder content and should now be replaced by the probing chapter.

Before editing, inspect the main LaTeX file and determine the exact Chapter 3 source file included by the report.

It is likely similar to:

```text
/home/omar/work/PFE/report/chapters/3-third-chapter.tex
```

but **verify the path from the main `.tex` file rather than assuming it**.

Replace the contents of the existing Chapter 3 source file.  
Do not create a second Chapter 3.

---

# 0. IMPORTANT PROJECT CONTEXT

The thesis is currently being written from the technical core outward.

The current order is:

```text
Chapter 2 — Background and State of the Art                       DONE / FREEZE FOR NOW
Chapter 3 — Probing Compositional Question Difficulty             ← CURRENT TASK
Chapter 4 — Evidence-Aware Evaluation / Arm–Evidence Attribution  LATER
Chapter 5 — Prompt Optimization for Efficient Decomposition       LATER
Chapter 1 / General Introduction / General Conclusion             FINALIZED LATER
```

Chapter 2 has now been revised and should be considered the **technical background baseline** for this task.

Do not modify Chapter 2 as part of this task unless a compilation-breaking cross-reference absolutely requires it.

We will revisit Chapter 2 only after Chapters 4 and 5 are written.

---

# 1. RELATION TO THE FINALIZED CHAPTER 2

Chapter 2 already contains the background needed for this chapter.

In particular it already explains:

```text
2.1 Multi-Hop Question Answering and RAG
2.2 Retrieval for Multi-Hop Reasoning
2.3 Difficulty-Aware and Adaptive Computation
2.4 Probing Internal Representations of Language Models
    2.4.1 Linear Probing and Representation Analysis
    2.4.2 Latent Properties in LLM Representations
2.5 Question Decomposition for Multi-Hop Reasoning
2.6 Adaptive Decomposition and Efficient Evidence Retrieval
2.7 Research Gap and Thesis Positioning
```

Section 2.4 already explains:

- what probing is;
- why a frozen representation can be studied with a simple readout;
- linear probing;
- the linear representation hypothesis;
- the limitations of interpreting probe accuracy;
- Alain & Bengio;
- Hewitt & Liang;
- Park et al.;
- prior work on truth, knowledge, correctness, and confidence;
- the distinction between latent multi-hop reasoning and compositional difficulty.

Section 2.7.1 already establishes the first thesis research question:

> Does the LLM already encode how much compositional reasoning a question requires?

Therefore Chapter 3 must **not repeat the probing literature review**.

The boundary is:

```text
Chapter 2:
What is probing?
What has prior work probed?
Why is probing relevant?

Chapter 3:
How exactly do we probe compositional difficulty?
What validation protocol do we use?
What do the experiments show?
What can and cannot be concluded?
```

Use cross-references to Chapter 2 where useful rather than rewriting its explanations.

---

# 2. PRIMARY SCIENTIFIC SOURCE

This chapter is based on the accepted paper:

**Omar Abdelhedi, O. R. Heidari, S. Chaari, X. Chen Zhu, M. Hamed, D. Azzam, and Y. Yaakoubi,  
“Probing Compositional Question Difficulty in Language Model Representations,”  
IEEE AIDIST 2026, accepted, to appear.**

The thesis bibliography already contains this publication.

The local workspace also contains the probing research project and/or multiple versions of the paper.

Before writing Chapter 3, search the local workspace, especially under:

```text
/home/omar/work/PFE/
```

for:

- the final accepted paper PDF;
- its LaTeX source;
- experiment code;
- configuration files;
- result CSV/JSON/NPY/PKL files;
- tables;
- original plots;
- plotting scripts.

Do not rely only on numbers manually copied from this task file if the actual experiment artifacts are available.

The priority order is:

```text
1. final experiment outputs / code
2. final accepted paper LaTeX source
3. final accepted paper PDF
4. this task document
```

If two local paper versions disagree, determine which corresponds to the accepted results before writing.

Do not invent or silently infer missing experiment details.

---

# 3. CHAPTER TITLE

Use:

```latex
\chapter{Probing Compositional Question Difficulty in Language Model Representations}
```

If the template supports an optional shorter running header, use it only for the page header if needed.

Do not shorten the actual chapter title merely for convenience.

---

# 4. PURPOSE OF CHAPTER 3

This chapter experimentally addresses the first research gap identified in Chapter 2:

```latex
\boxed{
\text{Does an LLM encode the compositional difficulty of a question before producing an answer?}
}
```

The chapter must establish:

1. how difficulty is operationalized in each benchmark;
2. how hidden representations are extracted from the frozen LLM;
3. how the question representation is constructed;
4. how a deliberately simple linear probe is fitted at each layer;
5. how decodability is evaluated without training/test leakage;
6. how probe-capacity and surface-form explanations are controlled;
7. whether the decoded signal behaves as an ordered difficulty axis;
8. whether it transfers across different benchmark definitions of difficulty;
9. what the results imply for adaptive computation;
10. what the results **do not** establish.

The central claim is:

```text
compositional difficulty is linearly decodable from the question representation
```

—not:

```text
the model causally uses a difficulty score to allocate computation.
```

This distinction must be preserved throughout the chapter.

---

# 5. ENGINEERING-THESIS WRITING STYLE

Do not simply paste the 8-page IEEE paper into the report.

Rewrite it as a thesis chapter.

The chapter should:

- be more explanatory than the conference paper;
- have a clear methodology/result progression;
- expand important experimental details needed for reproducibility;
- explain plots in prose;
- use readable thesis-style captions;
- avoid duplicating related work from Chapter 2;
- avoid paper-style compressed sentences and all-uppercase table captions.

Use the spelling/style already established in the report:

```text
optimisation
characterised
organised
residualisation
```

rather than switching randomly between British and American English.

Target roughly:

```text
12–16 compiled pages
```

depending on figures and tables.

Do not force a page count.

---

# 6. RECOMMENDED FINAL STRUCTURE

Use:

```text
Chapter 3 — Probing Compositional Question Difficulty in Language Model Representations

Introduction

3.1 Research Question and Problem Formulation

3.2 Methodology
    3.2.1 Hidden-State Extraction and Question Representation
    3.2.2 Linear Probe and Layer-Wise Evaluation
    3.2.3 Label-Permutation Null
    3.2.4 Surface-Feature Control and Residualisation
    3.2.5 Ordinality Test
    3.2.6 Cross-Dataset Transfer

3.3 Experimental Setup
    3.3.1 Language Models
    3.3.2 Benchmarks and Difficulty Labels
    3.3.3 Sampling and Evaluation Configuration

3.4 Results
    3.4.1 Difficulty Is Decodable Across Model Depth
    3.4.2 The Signal Is Not Reducible to Surface Form
    3.4.3 The Decoded Direction Is Ordinal
    3.4.4 The Surface-Independent Axis Transfers Across Benchmarks

3.5 Discussion and Limitations
    3.5.1 Interpretation and Implications for Adaptive Computation
    3.5.2 Limitations and Future Directions

Conclusion
```

Do **not** add a standalone Related Work section.

Chapter 2 already performs that function.

---

# 7. CHAPTER INTRODUCTION — SHORT

The introduction should be approximately **2–3 short paragraphs**.

Do not repeat the Chapter 2 introduction.

Do not reproduce the full paper introduction.

## Target content

Paragraph 1:

Chapter 2 established that adaptive systems can benefit from a signal describing how much computation a question requires. It also reviewed evidence that several latent properties can be decoded from LLM internal representations. The remaining question is whether **the compositional difficulty of the question itself** is represented before an answer is produced.

Paragraph 2:

State what Chapter 3 does:

- take labelled multi-hop questions;
- run the question through frozen instruction-tuned LLMs;
- extract representations across depth;
- fit a simple linear probe at every layer;
- validate positive results with:
  - permutation null;
  - surface controls;
  - ordinality;
  - cross-dataset transfer.

Optional third short paragraph:

State that the study is based on the accepted AIDIST 2026 paper if this matches the report's publication-disclosure convention.

Do not list every numerical result in the introduction.

A suitable style is:

> This chapter investigates whether the representation formed by a language model after reading a question already contains information about the amount of compositional reasoning that the question requires. Rather than predicting the answer, the analysis treats benchmark-defined difficulty as the target and asks where, across model depth, this property becomes linearly decodable.

Improve the prose as needed.

---

# 8. FULL CONTENT DRAFT

The following specifies the scientific content that should be written.

Use it as the actual draft target, not merely as a checklist.

Adapt wording and notation to the local LaTeX project, but preserve the scientific meaning.

---

# 3.1 Research Question and Problem Formulation

Start from the research gap established in Section 2.7.1.

A multi-hop question may require several dependent reasoning operations. If this demand is represented internally before answer generation, it could in principle provide a signal for adaptive computation.

The objective here is purely representational.

Let the labelled dataset be:

```latex
\mathcal{D}
=
\{(q_i,y_i)\}_{i=1}^{N},
```

where:

- \(q_i\) is a question;
- \(y_i\) is the benchmark-specific difficulty label.

Let \(M\) be a frozen causal language model with \(L\) transformer blocks.

For each layer \(\ell\), define a pooled question representation:

```latex
\mathbf{r}^{(\ell)}_i
\in
\mathbb{R}^{d}.
```

Use **\(\mathbf r_i^{(\ell)}\)** for the pooled question representation.

Do not use \(a_i\) for activations because Chapter 2 already uses:

```latex
a_i
```

for decomposition arms.

This notation collision must be avoided.

The central question at layer \(\ell\) is whether a simple linear function:

```latex
g_\ell:
\mathbb{R}^{d}
\rightarrow
\mathcal{Y}
```

can decode \(y_i\) from \(\mathbf r_i^{(\ell)}\).

Make the interpretation precise:

A successful probe demonstrates that difficulty information is **linearly accessible under the tested representation and data distribution**.

It does not establish:

- causal use;
- a deployed difficulty predictor;
- dynamic routing;
- successful execution of reasoning.

It also does not require generating an answer.

The chapter studies the question representation **before answer generation**.

## Suggested research questions

Present them compactly if useful:

### RQ1 — Decodability

Is benchmark-defined compositional difficulty linearly decodable from the question representation, and how does decodability change across model depth?

### RQ2 — Surface confounds

Does the signal survive controls for simple surface statistics and shuffled labels?

### RQ3 — Ordinality

Does the learned direction behave as a graded difficulty axis, with an unseen intermediate class lying between easy and hard extremes?

### RQ4 — Generality across benchmarks

Does the direction transfer across benchmarks that operationalise difficulty differently?

Do not add a fifth research question about routing because routing is not implemented.

---

# 3.2 Methodology

Add a compact overview paragraph before the subsections:

```text
question
→ frozen LLM forward pass
→ representation at every layer
→ linear probe
→ layer-wise decodability
→ validation controls
```

A methodology overview figure should be placed here.

---

# 3.2.1 Hidden-State Extraction and Question Representation

For question \(q_i\), tokenize the input using the exact tokenizer/input formatting used by the experiment.

**Inspect the local code before describing input formatting.**

Determine:

- whether raw question text was passed directly;
- whether a chat/instruction template was used;
- what special tokens were present;
- whether BOS/EOS tokens affected the last-token position.

Do not guess.

Run no answer generation.

The model performs only a forward pass.

Let:

```latex
\mathbf h^{(\ell)}_{i,t}
\in
\mathbb{R}^{d}
```

denote the hidden representation of token position \(t\) for question \(i\) at layer \(\ell\).

Use:

```text
layer 0 = token embedding output
layers 1,...,L = transformer block outputs
```

if this matches the local Hugging Face hidden-state indexing.

Verify it from code.

Let:

```latex
m_{i,t}\in\{0,1\}
```

be the attention mask.

## Main pooling strategy

The accepted paper's reported experiments use **last-token pooling**.

Define:

```latex
t_i^\star
=
\max\{t:m_{i,t}=1\},
```

and:

```latex
\mathbf r_i^{(\ell)}
=
\mathbf h^{(\ell)}_{i,t_i^\star}.
```

Explain why padding must not determine \(t_i^\star\).

### Mean pooling

The paper methodology also defines mean pooling, but the final paper's limitations describe the reported study as using last-token pooling.

Therefore:

- inspect the final implementation;
- if mean pooling was implemented but not used in reported results, mention it only as an available alternative or omit it from the main method;
- do **not** imply that a mean-pooling ablation was performed unless actual results exist;
- state clearly that the figures/tables in this chapter use the pooling method actually used by the reported experiment.

For each question the extracted representations form:

```latex
R_i
=
[
\mathbf r_i^{(0)},
\mathbf r_i^{(1)},
\ldots,
\mathbf r_i^{(L)}
].
```

Do not spend unnecessary space describing storage formats.

---

# 3.2.2 Linear Probe and Layer-Wise Evaluation

Chapter 2 already explains why linear probes are useful.

Here explain the exact probe used.

The experiment uses a **regularisation-free diagonal-LDA-style linear probe**.

The model remains frozen.

At each layer, only the readout is fitted.

Explain why the probe is deliberately simple:

```text
d >> N
```

and a low-capacity linear readout reduces the risk that the probe itself learns a complex task.

## Fold-local standardisation

Within each training fold, standardise activation feature \(j\):

```latex
\widehat r_{ij}
=
\frac{
r_{ij}-\mu_j
}{
\sigma_j
}.
```

The mean and standard deviation must be estimated from the **training fold only** and then applied to the held-out fold.

No held-out example may influence the transformation.

For a binary contrast, let the standardised class centroids be:

```latex
\bar{\mathbf r}_{+},
\qquad
\bar{\mathbf r}_{-}.
```

Define the difficulty direction:

```latex
\mathbf w
=
\bar{\mathbf r}_{+}
-
\bar{\mathbf r}_{-},
```

and the score:

```latex
s_i
=
\mathbf w^\top
\widehat{\mathbf r}_i.
```

## Multiclass evaluation

The experiment reports:

```text
binary AUC for 2Wiki
macro one-vs-rest AUC for multiclass benchmarks
```

Inspect the implementation and describe exactly:

- how multiclass directions/scores are produced;
- how one-vs-rest scores are pooled;
- how macro AUC is computed.

Do not invent the implementation from the binary formula.

## Cross-validation

Use:

```text
5-fold cross-validation
```

at every layer.

All preprocessing must be fold-local.

Pool the out-of-fold scores and compute the AUC once from predictions produced only on held-out examples.

Explain that AUC around 0.5 corresponds to chance-level ranking.

The result is:

```text
AUC versus layer
```

If the final analysis reports balanced accuracy or centroid separation as secondary diagnostics, include them only if they materially help the thesis and verified results are available.

---

# 3.2.3 Label-Permutation Null

Construct a null by randomly permuting difficulty labels while keeping the representations fixed.

Repeat:

```text
P = 200
```

times.

For each permutation, repeat the probing procedure.

Important terminology:

The paper/table reports:

```text
Null_95
```

as the **95th percentile of the shuffled-label null**.

Do not describe values around 0.53–0.55 as the "null mean" unless the plotting code verifies that.

The expected random AUC baseline remains approximately 0.5.

Describe exactly what the actual plotting script uses:

- null mean;
- percentile band;
- 95th-percentile curve;

rather than guessing.

---

# 3.2.4 Surface-Feature Control and Residualisation

The reported surface features are:

```text
1. character length
2. word count
3. capitalised-word count
4. punctuation count
```

Verify the exact implementation from code.

Let:

```latex
\boldsymbol{\phi}_i
\in
\mathbb{R}^{p}
```

be the surface feature vector.

Two controls are used.

## Surface-only baseline

Fit a classifier/probe using only \(\boldsymbol{\phi}_i\).

## Residualised activation probe

Within each training fold, regress each activation dimension on the surface features:

```latex
\mathbf r_i
=
B\boldsymbol{\phi}_i
+
\boldsymbol{\epsilon}_i.
```

Estimate \(\widehat B\) from the training fold only and compute:

```latex
\mathbf r_i^{\mathrm{res}}
=
\mathbf r_i
-
\widehat B\boldsymbol{\phi}_i.
```

Apply training-fold coefficients to the held-out fold.

**Residualisation must remain fold-local.**

## Important interpretation rule

Compare:

```text
raw activation probe
surface-only baseline
surface-residualised activation probe
permutation null
```

Do **not** state that the residualised probe must outperform the surface-only baseline.

The final Table I contains cases where the surface-only score is higher.

The correct claim is:

> A non-trivial signal remains after the selected surface features are removed, and that residual signal remains above the permutation null.

Use:

```text
not reducible to the selected surface statistics
```

rather than:

```text
independent of all surface form.
```

---

# 3.2.5 Ordinality Test

Fit a binary direction using only the two extreme classes and leave the middle class unseen during fitting.

Let:

```latex
\bar s_{\mathrm{low}},
\qquad
\bar s_{\mathrm{mid}},
\qquad
\bar s_{\mathrm{high}}
```

be mean projected scores.

Define:

```latex
\rho^{(\ell)}
=
\frac{
\bar s_{\mathrm{mid}}
-
\bar s_{\mathrm{low}}
}{
\bar s_{\mathrm{high}}
-
\bar s_{\mathrm{low}}
}.
```

Interpret:

```text
rho ≈ 0  → middle resembles low extreme
rho ≈ 1  → middle resembles high extreme
0 < rho < 1 → middle lies between the extremes
```

For MuSiQue:

```text
fit: 2-hop vs 4-hop
hold out: 3-hop
```

For HotpotQA:

```text
fit: easy vs hard
hold out: medium
```

if this matches the final experiment.

The source geometry figure describes the projection as **out-of-fold**.

Inspect the ordinality implementation and describe exactly how cross-validation/out-of-fold projection is performed.

---

# 3.2.6 Cross-Dataset Transfer

Important:

**Transfer is across datasets within the same model.**

The experiments do not demonstrate a single axis that transfers between Qwen, Mistral, and Gemma activation spaces.

For a fixed model, align labels ordinally:

```text
lowest difficulty → low
highest difficulty → high
```

Define retention:

```latex
R^{(\ell)}_{A\rightarrow B}
=
\frac{
\operatorname{AUC}_{A\rightarrow B}-\frac{1}{2}
}{
\operatorname{AUC}_{B,\mathrm{within}}-\frac{1}{2}
}.
```

Interpret:

```text
R ≈ 1 → transferred axis retains roughly the within-dataset separability above chance
R ≈ 0 → little transferable separation
R < 0 → transfer is below chance in the expected orientation
```

## Final table protocol

The final paper's Table II uses a **leave-one-benchmark-out fused protocol**:

```text
fit the axis on the pooled extreme classes of two benchmarks
test on the third held-out benchmark
```

for each model separately.

Make this distinction explicit.

The table caption refers to AUC averaged over "informative layers".

**Inspect the final code/source to determine exactly how informative layers are selected.**

Do not invent the criterion.

If the criterion cannot be verified, describe only what the final paper supports and report the unresolved detail to the user.

---

# 3.3 Experimental Setup

Keep this section compact.

---

# 3.3.1 Language Models

The reported study evaluates:

```text
Qwen2.5-32B
Mistral-24B
Gemma-27B
```

Search the experiment configuration for exact model identifiers.

Verify:

- checkpoint identifier;
- transformer-block count;
- hidden-state count;
- hidden dimension if relevant;
- extraction dtype if relevant.

Do not guess.

The paper's layer indexing appears consistent with:

```text
Qwen:    65 hidden-state positions including embeddings
Mistral: 41 hidden-state positions including embeddings
Gemma:   47 hidden-state positions including embeddings
```

Verify this before writing.

---

# 3.3.2 Benchmarks and Difficulty Labels

Use:

```text
2WikiMultiHopQA
HotpotQA
MuSiQue
```

Do not repeat their general descriptions from Chapter 2.

## MuSiQue

Difficulty:

```text
2-hop
3-hop
4-hop
```

for the selected subset.

## HotpotQA

Difficulty:

```text
easy
medium
hard
```

Verify the exact dataset field/filtering used.

## 2WikiMultiHopQA

The paper describes a binary:

```text
easy / hard
```

task.

The exact construction is not sufficiently explicit in the paper text available here.

**Recover it from the local data-preparation/experiment code.**

Do not invent it.

The final Codex response must tell the user exactly how the binary label was defined and which source file implements it.

---

# 3.3.3 Sampling and Evaluation Configuration

The paper reports:

```text
300 questions per class
```

Expected totals:

```text
2Wiki:    600
HotpotQA: 900
MuSiQue:  900
```

Verify from processed data.

Common settings:

```text
5-fold cross-validation
200 label permutations
all layers
AUC as primary metric
```

Only report seeds/hardware if verified.

---

# 9. FIGURE 3.1 — METHODOLOGY OVERVIEW

Create one original thesis-quality overview figure:

```text
labelled question
      ↓
frozen LLM
      ↓
hidden states 0...L
      ↓
pooled representation at each layer
      ↓
linear probe
      ↓
AUC versus layer
```

Indicate validation branches:

```text
Permutation null
Surface residualisation
Ordinality
Cross-dataset transfer
```

Prefer TikZ if it matches the existing project.

---

# 3.4 Results

Use actual experiment artifacts.

Search for files/scripts related to:

```text
probe_auc_by_layer
tier2_probe_auc_by_layer
permutation
null
surface
residual
ordinal
interpolation
projection
transfer
```

Do not screenshot figures from the paper if original data/plots exist.

---

# 3.4.1 Difficulty Is Decodable Across Model Depth

Reported peak ranges:

```text
2Wiki:    approximately 0.97–0.99
MuSiQue:  approximately 0.87–0.90
HotpotQA: approximately 0.69–0.72
```

The signal is near chance at embeddings and develops through depth.

Use/regenerate the layer-wise plot for:

```text
Qwen2.5-32B on MuSiQue
```

## Main table

Recreate Table I in thesis style.

Expected values:

| Model | Benchmark | N | C | Best layer | Probe AUC | Surface only | Surface residualised | Null95 |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| Qwen2.5-32B | 2Wiki | 600 | 2 | 64 | 0.987 | 0.907 | 0.838 | 0.55 |
| Qwen2.5-32B | HotpotQA | 900 | 3 | 44 | 0.716 | 0.661 | 0.627 | 0.53 |
| Qwen2.5-32B | MuSiQue | 900 | 3 | 24 | 0.896 | 0.779 | 0.774 | 0.53 |
| Mistral-24B | 2Wiki | 600 | 2 | 21 | 0.972 | 0.911 | 0.829 | 0.55 |
| Mistral-24B | HotpotQA | 900 | 3 | 18 | 0.694 | 0.660 | 0.603 | 0.53 |
| Mistral-24B | MuSiQue | 900 | 3 | 12 | 0.874 | 0.776 | 0.756 | 0.53 |
| Gemma-27B | 2Wiki | 600 | 2 | 44 | 0.978 | 0.909 | 0.833 | 0.54 |
| Gemma-27B | HotpotQA | 900 | 3 | 23 | 0.709 | 0.661 | 0.606 | 0.53 |
| Gemma-27B | MuSiQue | 900 | 3 | 24 | 0.880 | 0.780 | 0.766 | 0.53 |

**Verify every number locally before insertion.**

Explain each column in the thesis caption/prose.

---

# 3.4.2 The Signal Is Not Reducible to Surface Form

Permutation null upper percentiles are roughly:

```text
0.53–0.55
```

while chance AUC is approximately:

```text
0.5
```

Surface-only prediction is itself strong:

```text
MuSiQue ≈ 0.78
2Wiki ≈ 0.91
```

After residualisation, a substantial above-null signal remains.

Correct interpretation:

> Difficulty is partly associated with surface form, but the selected surface statistics do not fully explain the hidden-state decodability.

Do not claim full surface independence.

Use/regenerate:

- permutation-null plot;
- raw vs residualised vs surface-only plot.

Combine as subfigures only if readable.

---

# 3.4.3 The Decoded Direction Is Ordinal

For MuSiQue:

```text
2-hop vs 4-hop axis
3-hop held out
```

Reported interpolation fractions:

```text
Qwen2.5-32B: 0.58
Mistral-24B: 0.56
Gemma-27B: 0.47
```

HotpotQA medium also lies between easy/hard but nearer the hard side:

```text
approximately 0.93–0.96
```

Verify exact values.

Use/regenerate the ordinality figure.

The activation-geometry projection is optional if it adds clear intuition.

---

# 3.4.4 The Surface-Independent Axis Transfers Across Benchmarks

Important wording:

```text
cross-benchmark transfer within each model
```

The raw axis transfers unevenly.

The residualised axis transfers more strongly and consistently.

Recreate Table II.

Expected values:

| Model | Held-out benchmark | Raw AUC | Raw R | Residualised AUC | Residualised R |
|---|---|---:|---:|---:|---:|
| Qwen2.5-32B | 2Wiki | 0.823 | 0.71 | 0.796 | 0.94 |
| Qwen2.5-32B | HotpotQA | 0.384 | -0.43 | 0.774 | 1.95 |
| Qwen2.5-32B | MuSiQue | 0.685 | 0.39 | 0.769 | 1.22 |
| Mistral-24B | 2Wiki | 0.774 | 0.61 | 0.779 | 0.98 |
| Mistral-24B | HotpotQA | 0.379 | -0.48 | 0.764 | 2.21 |
| Mistral-24B | MuSiQue | 0.627 | 0.27 | 0.720 | 1.02 |
| Gemma-27B | 2Wiki | 0.744 | 0.54 | 0.724 | 0.80 |
| Gemma-27B | HotpotQA | 0.398 | -0.42 | 0.756 | 2.44 |
| Gemma-27B | MuSiQue | 0.610 | 0.25 | 0.768 | 1.29 |

Verify every value.

Explain carefully that `R > 1` does not mean "more than 100% of difficulty transfers".

Use/regenerate the transfer plot.

---

# 3.5 Discussion and Limitations

# 3.5.1 Interpretation and Implications for Adaptive Computation

Main interpretation:

> After reading the question but before generating an answer, the tested LLMs contain a linearly accessible signal associated with benchmark-defined compositional difficulty.

Supporting observations:

1. signal develops after embeddings;
2. survives selected surface residualisation;
3. behaves ordinally;
4. residualised axis transfers across heterogeneous benchmarks within a model.

Use precise language:

```text
linearly decodable
linearly accessible
```

Avoid anthropomorphic or causal overclaims.

## Adaptive computation

Connect to Chapter 2's adaptive-computation discussion.

The results suggest a possible future alternative to a separate surface classifier:

```text
question
→ intermediate hidden representation
→ difficulty estimate
→ computational policy
```

But state:

```latex
\boxed{
\text{decodable difficulty signal}
\neq
\text{implemented adaptive router}.
}
```

This chapter does not:

- calibrate routing thresholds;
- measure routing savings;
- decide when decomposition runs;
- integrate the probe into Chapters 4–5;
- prove causal use.

Transition carefully to Chapter 4:

> Chapter 3 studies whether computational demand can be anticipated from the representation. Chapter 4 addresses a complementary problem: how to evaluate a generated decomposition according to the accessibility of the evidence required by its subquestions.

Do not imply Chapter 4 consumes the probe output.

---

# 3.5.2 Limitations and Future Directions

Include:

## Surface form

Surface-only probes are strong.

Residualisation removes only the selected features, not all lexical/syntactic/topic confounds.

## Difficulty labels

The benchmarks use heterogeneous proxies.

Do not claim universal abstract difficulty.

## Correlational nature

Decodability does not establish causal use.

Possible future work includes intervention/steering/ablation if appropriately cited.

## Scope

Limited to:

```text
three open instruction-tuned models
approximately 24–32B parameter scale
English Wikipedia-based multi-hop QA
selected pooling strategy
selected probe family
```

Not tested broadly across:

- model sizes;
- base models;
- architectures;
- languages;
- domains;
- task families;
- pooling methods;
- probe families.

## No cross-model transfer

Transfer is across datasets within a fixed model.

Do not imply direct transfer between activation spaces of different LLMs.

---

# 10. CHAPTER CONCLUSION — SHORT

Approximately two concise paragraphs.

Paragraph 1:

Summarise:

- decodability across tested settings;
- emergence across depth;
- residual signal above null;
- ordinality;
- cross-benchmark transfer after residualisation.

Paragraph 2:

Interpret cautiously:

- in-model difficulty estimation is plausible;
- causal use and deployment are not established;
- transition to Chapter 4's retrieval-oriented decomposition evaluation.

---

# 11. REQUIRED TABLES AND FIGURES

Recommended:

```text
Figure 3.1  Probing methodology overview       NEW ORIGINAL
Figure 3.2  Layer-wise AUC                     ACTUAL DATA
Figure 3.3  Permutation/surface controls       ACTUAL DATA
Figure 3.4  Ordinality                         ACTUAL DATA
Figure 3.5  Geometry projection                OPTIONAL
Figure 3.6  Cross-dataset transfer             ACTUAL DATA

Table 3.1   Experimental setup                 OPTIONAL
Table 3.2   Main decodability/control results  PAPER TABLE I
Table 3.3   Cross-dataset transfer             PAPER TABLE II
```

Do not force every optional figure/table if it hurts readability.

---

# 12. FIGURE RULES

1. Prefer original experiment plots/data.
2. Do not screenshot figures from the paper if source files exist.
3. Search local experiment directories.
4. Regenerate from real data if necessary.
5. Do not fabricate data.
6. Adapt captions to thesis style.
7. Keep fonts readable.
8. Reference each figure in prose.
9. Explain the takeaway after each major figure.
10. Follow the existing figure-directory convention.

---

# 13. REFERENCES

Reuse Chapter 2 bibliography entries.

Do not duplicate references.

Cite benchmark papers and methodological references where directly needed.

For model citations, use exact authoritative references/model cards corresponding to the actual checkpoints if the project style supports them.

Do not invent publication metadata.

Do not repeatedly self-cite the probing paper throughout the chapter.

If appropriate, state once that the chapter is based on the accepted AIDIST 2026 work.

---

# 14. IMPORTANT SOURCE CONSISTENCY CHECKS

Before finalising, verify from code/data:

### A. 2Wiki easy/hard label construction
Must be recovered exactly.

### B. Main pooling strategy
Verify last-token pooling for reported results.

### C. Multiclass probe
Verify exact scoring/AUC implementation.

### D. Ordinality cross-validation
Verify out-of-fold projection mechanics.

### E. "Informative layers"
Verify exact criterion used in transfer table aggregation.

### F. Transfer protocol
Confirm fused leave-one-benchmark-out training.

### G. Surface features
Confirm implementation.

### H. Numerical tables
Verify every number.

---

# 15. CLAIM BOUNDARIES — STRICT

Supported:

```text
difficulty is linearly decodable
a residual component remains beyond selected surface features
the direction behaves ordinally
residualised difficulty directions transfer across benchmarks within each model
the result suggests a potential signal for adaptive computation
```

Do not claim:

```text
the model causally computes or uses a difficulty score
the probe is already a router
the signal is entirely surface-independent
difficulty is universally one-dimensional
the axis transfers between different LLMs
the result generalises to all LLMs
the study proves better retrieval, EM, or F1
```

Chapter 3 does not evaluate retrieval coverage/depth or answer EM/F1.

Those belong later.

---

# 16. LATEX AND NOTATION

Use:

```text
a_i              = decomposition arm in Chapters 2/4/5
h_{i,t}^{(l)}    = token hidden state
r_i^{(l)}        = pooled question representation
```

Avoid notation collisions.

Add sensible labels such as:

```latex
\label{chap:probing}
\label{sec:probing-formulation}
\label{sec:probing-method}
\label{sec:probing-setup}
\label{sec:probing-results}
\label{sec:probing-discussion}
```

Use existing citation/acronym/cross-reference conventions.

---

# 17. REQUIRED WORKFLOW

## Phase A — Inspect

1. determine exact Chapter 3 file;
2. inspect Chapter 2 final text;
3. inspect final probing paper;
4. inspect experiment code;
5. inspect result files;
6. locate original figures;
7. locate bibliography entries;
8. resolve all ambiguous implementation details.

## Phase B — Write

Replace the legacy chapter with the complete Chapter 3.

Do not modify unrelated chapters.

---

# 18. REVIEW ROUND 1 — SCIENTIFIC / STRUCTURAL

Check:

- no duplicated Chapter 2 literature review;
- research target is difficulty before answering;
- exact input formatting;
- exact layer indexing;
- exact pooling;
- fold-local preprocessing;
- exact multiclass evaluation;
- leakage-free residualisation;
- exact ordinality protocol;
- exact transfer protocol;
- conservative claims;
- no cross-model-transfer confusion;
- surface confounds acknowledged.

Correct all issues.

---

# 19. REVIEW ROUND 2 — NUMERICAL / FIGURE / LATEX

Verify every value against final experiment sources:

```text
N
C
model IDs
layer counts
best layers
probe AUC
surface-only AUC
residualised AUC
Null95
ordinal rho
transfer AUC
retention R
```

Verify figures and tables.

Compile the whole report.

Fix:

- undefined references;
- undefined citations;
- missing images;
- duplicate labels;
- layout problems introduced by Chapter 3.

---

# 20. FINAL VALIDATION CHECKLIST

- [ ] Legacy Chapter 3 replaced.
- [ ] No duplicate Chapter 3.
- [ ] Introduction short.
- [ ] No repeated probing literature.
- [ ] Research question explicit.
- [ ] Activation notation does not collide with arms.
- [ ] Input formatting verified.
- [ ] Layer indexing verified.
- [ ] Pooling verified.
- [ ] Probe implementation verified.
- [ ] Multiclass implementation verified.
- [ ] 5-fold CV correct.
- [ ] Standardisation fold-local.
- [ ] 200 permutations correct.
- [ ] Null95 correctly interpreted.
- [ ] Surface features verified.
- [ ] Residualisation fold-local.
- [ ] No false claim residual > surface-only.
- [ ] Ordinality protocol verified.
- [ ] 2Wiki labels verified.
- [ ] Transfer described as cross-dataset within model.
- [ ] Fused leave-one-out protocol verified.
- [ ] Informative-layer criterion verified or flagged.
- [ ] Tables verified.
- [ ] Original figures used/regenerated.
- [ ] No causal/router overclaim.
- [ ] Limitations included.
- [ ] Conclusion short.
- [ ] Transition to Chapter 4 does not imply probe integration.
- [ ] Full report compiles.

---

# 21. FINAL CODEX RESPONSE

When finished, report:

1. exact Chapter 3 file modified;
2. legacy content removed;
3. final chapter structure;
4. paper/code/result sources used;
5. exact 2Wiki difficulty-label definition;
6. exact model checkpoint identifiers;
7. pooling method;
8. multiclass probe implementation;
9. ordinality cross-validation procedure;
10. informative-layer definition;
11. figures used/regenerated/created;
12. tables created;
13. bibliography changes;
14. compiled Chapter 3 page count;
15. compilation status;
16. remaining warnings;
17. Review Round 1 changes;
18. Review Round 2 corrections;
19. any detail that could not be verified.

Do not merely provide a plan.

Actually rewrite Chapter 3, compile the report, inspect the output, perform both review rounds, and leave the project in a compiling state.
