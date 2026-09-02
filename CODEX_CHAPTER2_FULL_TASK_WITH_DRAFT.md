# Codex Task — Write Chapter 2 of the Thesis Report

## Target file

Write and complete:

```text
/home/omar/work/PFE/report/chapters/2-second-chapter.tex
```

This is an engineering thesis / final internship report written in LaTeX in VS Code.  
The LaTeX environment is already configured.

---

# 0. IMPORTANT PROJECT CONTEXT — READ THIS FIRST

The repository is **not a clean new thesis project**.

It already contains material inherited from an **older / similar report**, including:

- content in Chapter 1;
- content in other chapter `.tex` files;
- a bibliography containing many entries from a related report;
- potentially old figures, labels, terminology, section structures, and references that are not part of the current thesis.

Therefore, existing files must be treated carefully.

## What the existing project IS useful for

Use the existing repository to recover:

- LaTeX formatting conventions;
- document class and packages;
- bibliography system;
- citation commands;
- figure-directory conventions;
- equation and label conventions;
- acronym handling;
- macros already defined in the project;
- reusable BibTeX entries that correspond to references actually needed here;
- any existing verified bibliography entries from the probing paper or related work;
- existing figure styles and caption conventions.

## What the existing project is NOT authoritative for

Do **not** assume that:

- the current Chapter 1 content represents the final Chapter 1;
- the current General Introduction is final;
- the current Chapter 3/4/5 content follows the new thesis narrative;
- old section titles should be preserved;
- old chapter transitions are still correct;
- old figures belong in the new report;
- every bibliography entry is relevant;
- terminology from the old report should be copied into the new thesis.

Some files are remnants of a previous/similar report and will be rewritten later.

---

# 1. Current writing order for the thesis

The thesis is being rewritten **from the technical core outward**.

The intended workflow is:

```text
1. Write Chapter 2 — Background and State of the Art   ← CURRENT TASK
2. Rewrite/write Chapter 3 — Probing Compositional Question Difficulty
3. Write Chapter 4 — Evidence-Aware Evaluation / Arm–Evidence Attribution
4. Write Chapter 5 — Prompt Optimization for Efficient Decomposition
5. Return to Chapter 1 — Internship Presentation and Context
6. Write/refine the General Introduction
7. Write/refine the General Conclusion and Perspectives
```

This is intentional.

Chapter 2 should therefore be written as a **stable technical foundation for the chapters that will follow**, even if the current Chapter 3/4/5 files in the repository still contain old content.

Do **not** distort Chapter 2 to match obsolete chapter text.

Instead, Chapter 2 must follow the structure and scientific narrative specified in this instruction file.

---

# 2. Consequence for repository inspection

Before editing:

1. Open the current:
   ```text
   /home/omar/work/PFE/report/chapters/2-second-chapter.tex
   ```
2. Inspect the project main `.tex` file.
3. Inspect:
   - preamble,
   - packages,
   - bibliography configuration,
   - figure conventions,
   - labels,
   - macros,
   - acronym conventions.
4. Inspect the `.bib` file(s).
5. Reuse existing bibliography entries whenever they correspond to references required below.
6. Search for duplicate BibTeX entries before adding anything.
7. Inspect old Chapter 1 / 3 / 4 / 5 only for:
   - formatting,
   - macros,
   - terminology already standardized,
   - references that can be reused.
8. Do **not** treat their scientific structure as authoritative.

If Chapter 3 currently contains an old report's material, that is fine. Chapter 2 must still end by preparing the **new** Chapter 3 described below.

---

# 3. Purpose of Chapter 2

The chapter title should be:

```latex
\chapter{Background and State of the Art}
```

or the exact equivalent already required by the template.

This chapter is the **first genuinely technical chapter** of the thesis.

Its role is to provide all technical background required for the remainder of the report and progressively funnel the reader toward two research problems:

1. **Can the compositional difficulty of a question be identified from the LLM before answering?**
   - This leads to Chapter 3.

2. **Can a complex multi-hop question be decomposed so that its required evidence becomes easier to retrieve while preserving evidence coverage?**
   - This leads to Chapters 4 and 5.

The chapter must **not** read as a collection of unrelated literature summaries.

The intended narrative is:

```text
RAG and multi-hop QA
        ↓
retrieval and its bottlenecks
        ↓
different questions require different amounts of computation
        ↓
difficulty-aware / adaptive computation
        ↓
question decomposition
        ↓
decomposition as a way to create easier retrieval queries
        ↓
need to evaluate coverage + retrieval depth
        ↓
research gaps addressed by the thesis
```

---

# 4. Important writing constraints

## 4.1 Engineering-thesis style

This is an engineering thesis report, not a journal survey.

Write:

- clearly,
- technically,
- concisely,
- with smooth transitions,
- with equations only when useful later,
- with figures where visual explanation is better than text.

Avoid:

- very long literature-review paragraphs,
- excessive philosophical framing,
- overly general AI history,
- unnecessary material that is not used later.

---

## 4.2 Chapter introduction must be short

Each chapter has its own introduction and conclusion.

The Chapter 2 introduction should be approximately **2 short paragraphs**.

Do not repeat the General Introduction.

It should only:

1. explain why multi-hop QA creates retrieval/reasoning difficulties;
2. state briefly what the chapter covers.

Use the draft given later in this file as the content target.

---

## 4.3 Chapter conclusion must be short and different from the introduction

Use the project’s existing convention, for example:

```latex
\section*{Conclusion}
```

The conclusion should be approximately **2 concise paragraphs**.

It should synthesize what was established and identify the two remaining problems:

- difficulty estimation → Chapter 3;
- decomposition evaluation/optimization → Chapters 4–5.

Do not restate the opening paragraph.

---

# 5. Exact Chapter 2 structure

Use:

```text
Chapter 2 — Background and State of the Art

Introduction

2.1 Multi-Hop Question Answering and Retrieval-Augmented Generation
    2.1.1 Retrieval-Augmented Generation
    2.1.2 Multi-Hop Question Answering
    2.1.3 Multi-Hop Question Answering Benchmarks
    2.1.4 Evidence and Supporting Passages

2.2 Retrieval for Multi-Hop Reasoning
    2.2.1 Sparse Retrieval
    2.2.2 Dense Retrieval
    2.2.3 Late-Interaction Retrieval and Reranking
    2.2.4 Iterative and Multi-Hop Retrieval
    2.2.5 Evidence Coverage and Retrieval Depth

2.3 Difficulty-Aware and Adaptive Computation
    2.3.1 Query Complexity and Routing
    2.3.2 Adaptive Retrieval During Generation
    2.3.3 Difficulty and Uncertainty

2.4 Question Decomposition for Multi-Hop Reasoning
    2.4.1 Dependency-Aware Decomposition
    2.4.2 The Compositionality Gap
    2.4.3 Earlier Question-Decomposition Approaches
    2.4.4 LLM-Based Decomposition
    2.4.5 From Answer-Oriented to Retrieval-Oriented Decomposition

2.5 Adaptive Decomposition and Efficient Evidence Retrieval
    2.5.1 The Evidence-Responsibility Problem
    2.5.2 Coverage–Depth Trade-Off
    2.5.3 Evaluating the Quality of a Decomposition

2.6 Research Gap and Thesis Positioning
    2.6.1 Anticipating Compositional Difficulty
    2.6.2 Optimizing Decomposition for Retrieval Efficiency

Conclusion
```

**Do not create Section 2.6.3.**

---

# 6. FULL CONTENT DRAFT TO IMPLEMENT

The following is the actual content target for Chapter 2.

Do not merely use it as a checklist.

Use it as the **draft scientific content** that should be written into the LaTeX chapter.

You may:

- improve sentence flow,
- adapt wording to the thesis style,
- replace citation placeholders with verified local BibTeX keys,
- adjust notation to match existing project macros,
- improve figure references,
- shorten redundant passages.

Do **not** change the scientific meaning unless required for correctness.

---

# Chapter 2 — Background and State of the Art

## Introduction — target draft

Multi-hop question answering requires a system to retrieve and combine several pieces of evidence before producing an answer. In Retrieval-Augmented Generation (RAG), this creates a particular difficulty: the evidence needed for a complex question may not be easily retrieved from the original query, and different questions may require very different amounts of retrieval and reasoning.

This chapter introduces the concepts needed for the remainder of the thesis. It first presents RAG and multi-hop question answering, then reviews retrieval methods and the notions of evidence coverage and retrieval depth. It subsequently discusses adaptive computation and question decomposition, before focusing on the use of decomposition to make evidence easier to retrieve. The chapter concludes by identifying the two research gaps addressed in the following chapters.

Keep the final introduction around this length.

---

# 2.1 Multi-Hop Question Answering and Retrieval-Augmented Generation

## 2.1.1 Retrieval-Augmented Generation

Explain that Large Language Models acquire substantial knowledge during pre-training, but their parametric knowledge may be incomplete, outdated, or insufficient for questions requiring specific external information.

Introduce Retrieval-Augmented Generation as the combination of a language model and an external corpus.

Use notation:

```latex
\mathcal{C}
=
\{d_1,d_2,\ldots,d_N\}.
```

For query \(q\), the retriever assigns:

```latex
s(q,d)
```

and returns:

```latex
D_k(q)
=
\operatorname{TopK}_{d\in\mathcal{C}} s(q,d).
```

The generator predicts:

```latex
p(y\mid q,D_k(q)).
```

Explain explicitly:

- the retriever determines what external information the model sees;
- the generator reasons over that information;
- improving the language model alone does not solve retrieval failure.

Include the idea:

> A stronger generator cannot directly exploit a relevant passage if that passage is never retrieved.

Reference the original RAG paper by Lewis et al. (NeurIPS 2020).

### Required Figure — RAG pipeline

Create an original figure, preferably TikZ if supported.

Concept:

```text
Question
   ↓
Retriever ↔ External Corpus
   ↓
Top-k Evidence Passages
   ↓
LLM
   ↓
Answer
```

Caption should explain the separation between retrieval and generation.

---

## 2.1.2 Multi-Hop Question Answering

Explain:

- single-hop = one principal factual relation/evidence source;
- multi-hop = multiple dependent facts/evidence pieces.

Use:

```latex
r_1
\rightarrow
r_2
\rightarrow
\cdots
\rightarrow
r_h.
```

Explain clearly:

```latex
\boxed{
\text{reasoning hop count}
\neq
\text{retrieval depth}.
}
```

Example:

- four-hop question = four dependent reasoning operations;
- retrieval depth \(k=50\) = considering/retrieving up to fifty ranked passages.

This distinction is essential because later chapters optimize **retrieval depth**, not dataset hop count.

### Required Figure — Multi-hop reasoning chain

Create an original example.

Suggested conceptual example:

```text
Question:
Which country is the birthplace of the author of Book X?

Subquestion 1:
Who wrote Book X?
       ↓
Author Y

Subquestion 2:
Where was Author Y born?
       ↓
Country Z

Final answer:
Country Z
```

Show the bridge entity.

Do not copy a figure from a paper.

---

## 2.1.3 Multi-Hop Question Answering Benchmarks

Cover only the benchmarks needed later.

### HotpotQA

Explain:

- Wikipedia-based multi-hop QA;
- supporting-fact supervision;
- allows answer and evidence evaluation.

Reference:
Yang et al., EMNLP 2018.

### 2WikiMultiHopQA

Explain:

- multi-hop QA with explicit reasoning/evidence structure;
- constructed using Wikipedia/Wikidata information.

Reference:
Ho et al., COLING 2020.

### MuSiQue

Explain:

- constructed bottom-up from connected single-hop questions;
- 2–4 hops;
- preserves dependencies between intermediate questions;
- particularly useful later because decomposition structure relates intermediate questions to supporting evidence.

Reference:
Trivedi et al., TACL 2022.

Mention briefly that the probing chapter uses these benchmarks because they provide different operational notions of compositional difficulty.

Do not give probing results.

---

## 2.1.4 Evidence and Supporting Passages

Define:

```latex
E(q)
=
\{e_1,e_2,\ldots,e_m\}
```

for gold evidence.

Define ranked retrieval output:

```latex
R(q)
=
(d_1,d_2,\ldots,d_N).
```

Define:

```latex
\operatorname{rank}(e\mid q).
```

Explain difference between:

- answer correctness;
- evidence retrieval success.

Important point:

An LLM may sometimes answer correctly from parametric memory even if required evidence was not retrieved.

Therefore, later chapters explicitly evaluate whether required evidence is available.

---

# 2.2 Retrieval for Multi-Hop Reasoning

Explain that retrieval methods differ in how they measure relevance.

Only include retrieval background needed for later work.

---

## 2.2.1 Sparse Retrieval

### TF-IDF

Use:

```latex
w(t,d)
=
\operatorname{tf}(t,d)
\operatorname{idf}(t)
```

with:

```latex
\operatorname{idf}(t)
=
\log
\frac{N}
{\operatorname{df}(t)}.
```

Explain lexical term weighting and cosine-style vector matching.

Reference:
Salton & Buckley, 1988.

### BM25

Use:

```latex
\operatorname{BM25}(q,d)
=
\sum_{t\in q}
\operatorname{IDF}(t)
\frac{
f(t,d)(k_1+1)
}{
f(t,d)
+
k_1
\left(
1-b+
b\frac{|d|}{\operatorname{avgdl}}
\right)
}.
```

Briefly define:

- \(f(t,d)\),
- \(k_1\),
- \(b\),
- document-length normalization.

Reference:
Robertson & Zaragoza, 2009.

End with lexical mismatch limitation.

---

## 2.2.2 Dense Retrieval

Explain learned dense representations.

Use DPR:

```latex
\mathbf q=f_q(q),
\qquad
\mathbf d=f_d(d)
```

with:

```latex
s(q,d)
=
\mathbf q^\top \mathbf d.
```

Explain:

- semantic similarity advantage;
- precomputed passage vectors;
- nearest-neighbour retrieval;
- limitation of compressing an entire passage into one vector.

Reference:
Karpukhin et al., EMNLP 2020.

---

## 2.2.3 Late-Interaction Retrieval and Reranking

Introduce ColBERT.

Use:

```latex
s_{\mathrm{ColBERT}}(q,d)
=
\sum_i
\max_j
\mathbf q_i^\top\mathbf d_j.
```

Explain:

- contextual token representations;
- MaxSim;
- fine-grained matching;
- precomputable document representations.

Reference:
Khattab & Zaharia, SIGIR 2020.

Mention why this matters later:

Arm–evidence attribution is partly a fine-grained query/passage matching problem.

Also explain a standard reranking architecture:

```text
fast retriever
→ candidate set
→ stronger reranker
→ reordered passages
```

Do not turn reranking into a large standalone survey.

---

## 2.2.4 Iterative and Multi-Hop Retrieval

Discuss three key methods.

### MDR

Reference:
Xiong et al., ICLR 2021.

Explain:

- iterative dense retrieval;
- earlier evidence informs later search.

### Baleen

Reference:
Khattab, Potts & Zaharia, NeurIPS 2021.

Explain:

- condensed retrieval;
- manages the expanding multi-hop search space.

### IRCoT

Reference:
Trivedi et al., ACL 2023.

Explain:

- interleaves reasoning and retrieval;
- intermediate reasoning determines what to retrieve next;
- retrieved evidence updates the next reasoning step.

End with:

```latex
\boxed{
\text{the original full question is not necessarily the best retrieval query for every evidence passage.}
}
```

This sentence is an important transition toward decomposition.

---

## 2.2.5 Evidence Coverage and Retrieval Depth

This subsection is essential.

Given top-\(k\) passages \(D_k(q)\), define:

```latex
\operatorname{Coverage}@k(q)
=
\frac{
|E(q)\cap D_k(q)|
}{
|E(q)|
}.
```

If useful for the actual evaluation, also define:

```latex
\operatorname{Complete}(q,k)
=
\mathbb{1}
[
E(q)\subseteq D_k(q)
].
```

Define minimum depth needed to recover all available evidence:

```latex
K^\star(q)
=
\max_{e\in E(q)}
\operatorname{rank}(e\mid q).
```

Explain:

- if one or more required passages are not retrieved within the search horizon, the question is **uncovered**;
- do not assign an artificial finite depth;
- \(K^\star\) is a retrieval-depth proxy;
- it is not reasoning hop count;
- it is not identical to wall-clock computation.

Very important:

Coverage and depth must be evaluated jointly.

Use:

```latex
\boxed{
\text{high evidence coverage}
\quad+\quad
\text{low retrieval depth}.
}
```

Also explicitly distinguish:

- **evidence coverage** used in Chapters 4–5;
- **conformal/statistical coverage** used in uncertainty-quantification literature.

### Required Figure — Ranked evidence list

Create an original figure illustrating:

```text
Rank      1   2   3   4   5   6   7
Passage   d   e1  d   d   e2  d   e3
```

Highlight gold evidence.

Show:

- coverage at some \(k\);
- \(K^\star\).

---

# 2.3 Difficulty-Aware and Adaptive Computation

The purpose of this section is not to introduce a full uncertainty-quantification survey.

The key principle is:

```latex
\boxed{
\text{signal}
\rightarrow
\text{adaptive computational action}.
}
```

---

## 2.3.1 Query Complexity and Routing

Discuss Adaptive-RAG.

Reference:
Jeong et al., NAACL 2024.

Explain:

- not every query receives the same strategy;
- query complexity is estimated;
- different retrieval/reasoning policies are selected.

Use generic form:

```latex
q
\rightarrow
\widehat d(q)
\rightarrow
\pi_{\widehat d}.
```

where:

- \(\widehat d(q)\) = estimated difficulty/complexity;
- \(\pi\) = chosen computational policy.

Also mention AGENTIQL briefly if its reference is already verified in the local project.

Use it only as another complexity-routing example.

End with:

> Instead of estimating difficulty only from surface characteristics using an external classifier, could the target LLM itself already encode this information internally?

This prepares Chapter 3.

---

## 2.3.2 Adaptive Retrieval During Generation

Discuss briefly:

### FLARE
Jiang et al., EMNLP 2023.

Explain:

- retrieval triggered dynamically according to confidence in future generation.

### Self-RAG
Asai et al., ICLR 2024.

Explain:

- learned reflection signals;
- retrieval on demand;
- critique of retrieved evidence and generated answer.

Use the Trust Layer survey only for the broad signal-to-action idea.

Mention actions such as:

- retrieval,
- re-retrieval,
- routing,
- stopping,
- filtering,
- abstention.

Do not reproduce the Trust Layer taxonomy.

Do not create a standalone UQ chapter/section.

---

## 2.3.3 Difficulty and Uncertainty

Keep concise.

Explicitly state:

```latex
\boxed{
\text{difficulty}
\neq
\text{uncertainty}.
}
```

Define:

**Difficulty**
= amount/complexity of reasoning structurally required by the question.

**Uncertainty**
= reliability of the current prediction, retrieval state, or answer.

Explain examples:

- difficult but confident;
- easy but uncertain due to retrieval failure;
- difficult and uncertain;
- easy and confident.

End by stating:

Chapter 3 studies **compositional difficulty before answer generation**, not answer uncertainty.

---

# 2.4 Question Decomposition for Multi-Hop Reasoning

Define:

```latex
D(q)
=
\{a_1,a_2,\ldots,a_m\}
```

where each \(a_i\) is a simpler subquestion / arm.

Explain that decomposition exposes intermediate information needs implicit in the original question.

---

## 2.4.1 Dependency-Aware Decomposition

This should prepare the reader for the actual type of decomposition later used in the thesis.

Subquestions are not necessarily independent.

A later question can depend on a bridge entity produced by an earlier question.

Use:

```latex
a_1
\rightarrow
z_1
\rightarrow
a_2(z_1)
\rightarrow
z_2
\rightarrow
a_3(z_2).
```

where \(z_i\) is an intermediate answer / bridge entity.

Explain DAG formulation:

```latex
G=(V,E),
\qquad
V=\{a_1,\ldots,a_m\}.
```

Directed edges represent dependency relations.

Important background that can be mentioned generically:

- later questions may depend on bridge entities from previous questions;
- unresolved bridge entities can be represented by placeholders;
- execution resolves dependencies in order;
- the final downstream subquestion produces the information needed for the final answer.

Do **not** yet explain:

- exact decomposer prompt;
- exact placeholder syntax;
- output JSON/list format;
- exact local execution code;
- exact prompt-optimization procedure.

Those belong later.

### Required Figure — DAG / chained decomposition

Create an original conceptual figure.

Example:

```text
Full multi-hop question
        |
   ┌────┴────┐
   ↓         ↓
Arm 1      Arm 2
   |         |
bridge       |
entity       |
   └────┬────┘
        ↓
      Arm 3
        ↓
   Final answer
```

If the actual decomposition is mostly sequential, use a chain and note that a chain is a special case of a DAG.

---

## 2.4.2 The Compositionality Gap

Discuss:

Press et al.,
"Measuring and Narrowing the Compositionality Gap in Language Models,"
Findings of EMNLP 2023.

Explain:

- models may answer component questions correctly but fail on the full composed question;
- model scaling does not necessarily remove the gap;
- Self-Ask generates explicit follow-up questions.

Use this only as motivation for explicit decomposition.

---

## 2.4.3 Earlier Question-Decomposition Approaches

Discuss concisely:

### Min et al., ACL 2019
"Multi-Hop Reading Comprehension through Question Decomposition and Rescoring"

Explain:
- complex multi-hop questions decomposed into simpler single-hop questions;
- rescoring/selecting decompositions and answers.

### Perez et al., EMNLP 2020
"Unsupervised Question Decomposition for Question Answering"

Explain:
- unsupervised generation of simpler subquestions;
- no expensive explicit decomposition supervision required.

---

## 2.4.4 LLM-Based Decomposition

Discuss:

### Successive Prompting
Dua et al., EMNLP 2022.

### Least-to-Most Prompting
Zhou et al., ICLR 2023.

### Decomposed Prompting
Khot et al., ICLR 2023.

Explain shared idea:

```text
complex question
→ explicit simpler subproblems
→ solve according to dependencies/order
→ aggregate final result
```

Emphasize:

Decomposition is itself a configurable reasoning component, so decomposition quality can affect later retrieval/reasoning.

---

## 2.4.5 From Answer-Oriented to Retrieval-Oriented Decomposition

This subsection is the key transition.

State carefully:

Most decomposition approaches are primarily evaluated according to final task/answer performance.

The perspective in this thesis adds another question:

> Does decomposition make the required evidence easier to retrieve?

Use illustrative example:

```latex
\operatorname{rank}(e\mid q)=80
```

versus:

```latex
\operatorname{rank}(e\mid a_i)=4.
```

Explain:

- the reasoning problem still exists;
- the subquestion expresses a more targeted information need;
- evidence can therefore move to a much shallower rank.

Do not claim that prior work ignores retrieval.

Self-Ask and IRCoT already integrate search.

The thesis contribution is narrower:
**make evidence coverage and maximum retrieval depth explicit evaluation/optimization criteria.**

---

# 2.5 Adaptive Decomposition and Efficient Evidence Retrieval

This section should directly prepare Chapter 4.

---

## 2.5.1 The Evidence-Responsibility Problem

Given:

```latex
D(q)
=
\{a_1,\ldots,a_m\}
```

and:

```latex
E(q)
=
\{e_1,\ldots,e_n\},
```

explain:

For the full question, all gold evidence belongs to one retrieval query.

For a decomposition, each arm should only be evaluated against evidence relevant to its subproblem.

Define:

```latex
z_{ij}
=
\begin{cases}
1, & \text{if arm } a_i \text{ is responsible for evidence } e_j,\\
0, & \text{otherwise}.
\end{cases}
```

Then:

```latex
E_i
=
\{e_j : z_{ij}=1\}.
```

Arm depth:

```latex
K_i
=
\max_{e\in E_i}
\operatorname{rank}(e\mid a_i).
```

Overall decomposition depth:

```latex
K_{\mathrm{decomp}}
=
\max_i K_i.
```

Explain:

The main challenge is determining \(z_{ij}\) for arbitrary generated decompositions.

Mention MuSiQue as useful because its structured decomposition provides relations between intermediate questions and evidence.

Do **not** explain the classifier yet.

Specifically do not include:

- logistic regression;
- decision tree;
- exact feature vector;
- threshold calibration;
- confusion matrix;
- feature weights.

These are Chapter 4 methodology.

---

## 2.5.2 Coverage–Depth Trade-Off

Explain with a conceptual example.

Method A:

```text
coverage = high
Kmax = 10
```

Method B:

```text
coverage = lower
Kmax = 3
```

Method B is not automatically better because it may obtain shallow depth by missing difficult evidence.

Therefore:

```latex
\max \operatorname{Coverage}
```

while:

```latex
\min K_{\max}.
```

Explain:

- equal coverage → lower depth is better;
- equal depth → higher coverage is better.

Mention a Pareto/frontier view if useful.

### Required Figure — Coverage vs depth schematic

Create an illustrative, non-experimental figure.

Axes:

```text
x = maximum retrieval depth Kmax (lower better)
y = evidence coverage (higher better)
```

Indicate preferred direction toward upper-left.

Do not fabricate experiment results.

---

## 2.5.3 Evaluating the Quality of a Decomposition

State that a useful evaluator must determine whether an arbitrary decomposition:

1. preserves required evidence;
2. assigns evidence appropriately to arms;
3. reduces arm-specific retrieval depth;
4. produces an overall question-level metric;
5. provides a signal that can later optimize the decomposer.

Use conservative wording:

> Existing work demonstrates that decomposition can improve reasoning and that intermediate queries can guide retrieval. The perspective adopted in this thesis is to make evidence coverage and maximum retrieval depth explicit evaluation and optimization criteria for the decomposition.

Transition:

- Chapter 4 develops evaluator + arm–evidence attribution.
- Chapter 5 uses this evaluation as feedback for prompt optimization.

---

# 2.6 Research Gap and Thesis Positioning

Only two subsections.

No 2.6.3.

---

## 2.6.1 Anticipating Compositional Difficulty

Summarize:

- adaptive systems use query complexity and runtime signals;
- many use external classifiers, surface characteristics, or signals obtained after generation starts;
- the thesis asks whether compositional difficulty is already encoded inside the LLM before answering.

Use:

```latex
\boxed{
\text{Does the LLM already encode how much compositional reasoning a question requires?}
}
```

End:

> Chapter 3 addresses this question through layer-wise probing of question representations.

Do not report Chapter 3 results.

---

## 2.6.2 Optimizing Decomposition for Retrieval Efficiency

Summarize:

- decomposition makes intermediate information needs explicit;
- iterative retrieval shows that better intermediate queries can improve retrieval;
- the thesis asks whether decomposition can maintain evidence coverage while reducing retrieval depth.

Use:

```latex
\boxed{
\text{Can a decomposition preserve evidence coverage while reducing the maximum depth required to retrieve that evidence?}
}
```

Explain three requirements:

1. determine which evidence each generated arm is responsible for;
2. evaluate arbitrary decompositions through coverage and depth;
3. optimize the decomposition-generation strategy according to those metrics.

End:

- Chapter 4: evidence-aware evaluation and arm–evidence attribution;
- Chapter 5: prompt optimization.

Do not create Section 2.6.3.

---

# Chapter conclusion — target draft

Use approximately the following content, keeping it concise:

This chapter presented the background necessary for the experimental work developed in the remainder of the thesis. Multi-hop QA requires both reasoning across several pieces of evidence and retrieval mechanisms capable of exposing this evidence efficiently. Existing work has addressed these challenges through improved retrieval, iterative search, adaptive computation, and question decomposition.

Two questions remain central to this thesis. The first is whether the difficulty of a multi-hop question can be identified directly from the model before answering, which is investigated in Chapter 3. The second is whether decomposition can be evaluated and optimized specifically to preserve evidence coverage while reducing retrieval depth, which motivates Chapters 4 and 5.

Do not make the conclusion longer unless genuinely necessary.

---

# 7. Required figures

Create original figures when useful.

At minimum try to include:

## Figure 2.1 — RAG pipeline

Location:
Section 2.1.1.

Content:

```text
Question → Retriever ↔ External Corpus → Top-k passages → LLM → Answer
```

Purpose:
explain RAG.

---

## Figure 2.2 — Multi-hop reasoning / bridge entity

Location:
Section 2.1.2.

Show:
- question,
- evidence/subquestion 1,
- bridge entity,
- evidence/subquestion 2,
- final answer.

Purpose:
explain multi-hop dependency.

---

## Figure 2.3 — Evidence coverage and retrieval depth

Location:
Section 2.2.5.

Show ranked list and gold passages.

Explain:
- coverage at \(k\);
- \(K^\star\).

---

## Figure 2.4 — Dependency-aware decomposition / DAG

Location:
Section 2.4.1.

Show:
- full question,
- arms/subquestions,
- dependencies,
- bridge entities/placeholders,
- final answer.

This is generic background, not the exact proposed pipeline.

---

## Figure 2.5 — Coverage–depth trade-off

Location:
Section 2.5.2.

Schematic only.

Do not fabricate experimental values.

x-axis:
\(K_{\max}\), lower better.

y-axis:
evidence coverage, higher better.

Preferred direction:
upper-left.

---

# 8. Figure implementation rules

1. Prefer TikZ if already supported.
2. Reuse current project figure style.
3. Do not copy copyrighted figures from papers.
4. Figures must teach something useful.
5. Every figure must:
   - have a descriptive caption;
   - have a label;
   - be referenced in text;
   - fit within margins;
   - be readable.
6. Avoid tiny text.
7. If TikZ is inconvenient, create vector PDFs locally using Python/matplotlib/Graphviz.
8. Store figures according to the existing project convention.
9. Do not invent experimental data.

---

# 9. References that Chapter 2 should use

Before adding bibliography entries:

1. Search existing `.bib` files.
2. Reuse entries already present.
3. Do not create duplicate keys.
4. Verify missing entries from authoritative sources.
5. Never invent metadata.

Required/core references:

---

## RAG

Lewis et al.  
**Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks.**  
NeurIPS 2020.

Suggested key only if no local key exists:

```text
lewis2020rag
```

---

## TF-IDF

Salton and Buckley.  
**Term-Weighting Approaches in Automatic Text Retrieval.**  
Information Processing & Management, 1988.

Suggested key:

```text
salton1988term
```

---

## BM25

Robertson and Zaragoza.  
**The Probabilistic Relevance Framework: BM25 and Beyond.**  
Foundations and Trends in Information Retrieval, 2009.

Suggested key:

```text
robertson2009bm25
```

---

## DPR

Karpukhin et al.  
**Dense Passage Retrieval for Open-Domain Question Answering.**  
EMNLP 2020.

Suggested key:

```text
karpukhin2020dense
```

---

## ColBERT

Khattab and Zaharia.  
**ColBERT: Efficient and Effective Passage Search via Contextualized Late Interaction over BERT.**  
SIGIR 2020.

Suggested key:

```text
khattab2020colbert
```

---

## HotpotQA

Yang et al.  
**HotpotQA: A Dataset for Diverse, Explainable Multi-Hop Question Answering.**  
EMNLP 2018.

Suggested key:

```text
yang2018hotpotqa
```

---

## 2WikiMultiHopQA

Ho et al.  
**Constructing a Multi-Hop QA Dataset for Comprehensive Evaluation of Reasoning Steps.**  
COLING 2020.

Suggested key:

```text
ho2020twowiki
```

---

## MuSiQue

Trivedi et al.  
**MuSiQue: Multihop Questions via Single-Hop Question Composition.**  
TACL 2022.

Suggested key:

```text
trivedi2022musique
```

---

## MDR

Xiong et al.  
**Answering Complex Open-Domain Questions with Multi-Hop Dense Retrieval.**  
ICLR 2021.

Suggested key:

```text
xiong2021mdr
```

---

## Baleen

Khattab, Potts, and Zaharia.  
**Baleen: Robust Multi-Hop Reasoning at Scale via Condensed Retrieval.**  
NeurIPS 2021.

Suggested key:

```text
khattab2021baleen
```

---

## IRCoT

Trivedi et al.  
**Interleaving Retrieval with Chain-of-Thought Reasoning for Knowledge-Intensive Multi-Step Questions.**  
ACL 2023.

Suggested key:

```text
trivedi2023ircot
```

---

## FLARE

Jiang et al.  
**Active Retrieval Augmented Generation.**  
EMNLP 2023.

Suggested key:

```text
jiang2023flare
```

---

## Self-RAG

Asai et al.  
**Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection.**  
ICLR 2024.

Suggested key:

```text
asai2024selfrag
```

---

## Adaptive-RAG

Jeong et al.  
**Adaptive-RAG: Learning to Adapt Retrieval-Augmented Large Language Models through Question Complexity.**  
NAACL-HLT 2024.

Suggested key:

```text
jeong2024adaptiverag
```

---

## AGENTIQL

O. R. Heidari, S. Reid, and Y. Yaakoubi.  
**AGENTIQL: An Agent-Inspired Multi-Expert Framework for Text-to-SQL Generation.**  
NeurIPS 2025 Workshop on Efficient Reasoning.

Use only after verifying exact local metadata.

Suggested key:

```text
heidari2025agentiql
```

---

## Compositionality gap / Self-Ask

Press et al.  
**Measuring and Narrowing the Compositionality Gap in Language Models.**  
Findings of EMNLP 2023.

Suggested key:

```text
press2023compositionality
```

---

## Question decomposition and rescoring

Min et al.  
**Multi-Hop Reading Comprehension through Question Decomposition and Rescoring.**  
ACL 2019.

Suggested key:

```text
min2019multihop
```

---

## Unsupervised decomposition

Perez et al.  
**Unsupervised Question Decomposition for Question Answering.**  
EMNLP 2020.

Suggested key:

```text
perez2020unsupervised
```

---

## Successive Prompting

Dua et al.  
**Successive Prompting for Decomposing Complex Questions.**  
EMNLP 2022.

Suggested key:

```text
dua2022successive
```

---

## Least-to-Most

Zhou et al.  
**Least-to-Most Prompting Enables Complex Reasoning in Large Language Models.**  
ICLR 2023.

Suggested key:

```text
zhou2023leasttomost
```

---

## Decomposed Prompting

Khot et al.  
**Decomposed Prompting: A Modular Approach for Solving Complex Tasks.**  
ICLR 2023.

Suggested key:

```text
khot2023decomposed
```

---

# 10. User's own / internship papers

## Probing compositional question difficulty

Search the project for the exact paper source and exact bibliography metadata.

Do not invent:

- title,
- author order,
- venue,
- publication status,
- BibTeX key.

Use it in Chapter 2 only for:

- motivation of compositional difficulty;
- relation to adaptive computation;
- use of MuSiQue / 2Wiki / HotpotQA;
- transition to Chapter 3.

Do not report its experimental results in Chapter 2.

Those belong in Chapter 3.

---

## Trust Layer / UQ survey

Search the local repository for the exact manuscript:

**The Trust Layer of Retrieval-Augmented Generation: A Systematic Survey of Uncertainty Quantification, Verification, and Guarantees**

Use only the relevant conceptual point:

```text
signals → adaptive actions
```

such as:

- routing;
- re-retrieval;
- stopping;
- filtering;
- abstention.

Do not turn Chapter 2 into a UQ survey.

Do not copy the survey taxonomy.

If unpublished, cite using the existing project convention for manuscript/preprint work.

---

# 11. Citation style

Use the project's existing citation command.

Do not introduce a new citation package.

Every named:

- method,
- benchmark,
- claimed prior result

should be cited.

Avoid citation dumps.

Place citations near the exact claim they support.

---

# 12. Terminology consistency

## Hop

Use for:
reasoning/compositional hops.

## Retrieval depth

Use for:
rank cutoff \(k\).

Never casually use "hop" to mean retrieval depth.

---

## Evidence coverage

Use for:
retrieved gold supporting evidence.

Do not confuse with conformal/statistical coverage.

---

## Arm

Use for:
a generated decomposition subquestion in the later thesis framework.

When discussing general literature, "subquestion" is often clearer.

Introduce once:

> In the remainder of this thesis, generated subquestions are also referred to as decomposition arms.

---

## Bridge entity

Use for:
an intermediate entity/answer needed by a downstream question.

---

## DAG

Spell out:

```text
directed acyclic graph (DAG)
```

at first use.

A sequential chain is a special case of a DAG.

---

# 13. What must NOT be placed in Chapter 2

Do not include:

- exact decomposer prompt;
- exact LLM/API used by the proposed method;
- exact decomposition output list/JSON format;
- exact placeholder syntax;
- exact local placeholder-substitution code;
- full algorithm for executing the proposed DAG;
- logistic regression implementation;
- decision-tree experiments;
- exact arm–passage feature vector;
- calibration folds;
- threshold values;
- confusion-matrix results;
- false-positive/negative counts;
- Original vs Atomic-6 results;
- prompt-optimization algorithm details;
- optimization rounds/results;
- real coverage-depth results.

Those belong in Chapters 4 and 5.

Chapter 2 only prepares the reader.

---

# 14. LaTeX quality requirements

Follow the existing project conventions.

Add sensible labels such as:

```latex
\label{chap:background}
\label{sec:rag-multihop}
\label{sec:retrieval}
\label{sec:adaptive-computation}
\label{sec:decomposition}
\label{sec:adaptive-decomposition}
\label{sec:research-gap}
```

Use equation labels only if referenced later.

Use existing acronym support.

Use `\cref`, `\autoref`, `\citep`, etc. only if already configured.

Avoid:

- hard-coded page numbers;
- unnecessary `\vspace`;
- duplicate labels;
- package changes unless genuinely necessary.

---

# 15. Expected length

Target approximately:

```text
12–18 compiled pages
```

depending on:

- thesis formatting;
- figures;
- spacing;
- equation sizes.

Do not force the chapter to hit a page count.

Avoid turning it into a 25–30 page generic RAG survey.

---

# 16. Required execution workflow

## Phase A — Inspect

1. Read current Chapter 2.
2. Read main LaTeX file.
3. Inspect packages/macros.
4. Inspect bibliography configuration.
5. Search bibliography for existing references.
6. Inspect old chapters only for formatting and reusable bibliography context.
7. Inspect figure directories and conventions.
8. Identify old material that should not influence the new chapter.

---

## Phase B — Draft

Write the complete Chapter 2 according to the **full content draft above**.

Do not stop after producing an outline.

Actually edit:

```text
/home/omar/work/PFE/report/chapters/2-second-chapter.tex
```

Add figures and bibliography entries as needed.

---

# 17. Mandatory Review Round 1 — Scientific and structural review

After drafting, read the compiled Chapter 2 as if you were a thesis committee member.

Check:

## Narrative

- Does 2.1 naturally lead to 2.2?
- Does 2.2 establish why retrieval depth matters?
- Does 2.3 explain adaptive computation without becoming a UQ survey?
- Does 2.4 prepare dependency-aware decomposition without revealing the proposed method too early?
- Does 2.5 clearly connect decomposition to evidence retrieval?
- Does 2.6 state exactly the two research gaps?

## Scope

Ensure:

- Chapter 3 results are not leaked;
- Chapter 4 methodology is not written prematurely;
- Chapter 5 prompt optimization is not written prematurely;
- irrelevant old-report material was not copied;
- UQ remains subordinate to adaptive computation.

## Definitions

Before Chapter 3, the reader must understand:

- RAG;
- multi-hop QA;
- supporting evidence;
- reasoning hop;
- retrieval depth;
- sparse retrieval;
- dense retrieval;
- late interaction;
- reranking;
- iterative retrieval;
- evidence coverage;
- adaptive computation;
- decomposition;
- bridge entity;
- DAG;
- arm/subquestion.

## Research gap

Make novelty wording conservative and defensible.

Correct everything found.

---

# 18. Mandatory Review Round 2 — Technical, citation, figure, and LaTeX review

After correcting Round 1:

## References

Verify:

- every method citation;
- every dataset citation;
- no undefined keys;
- no duplicate BibTeX entries;
- metadata accuracy;
- no fabricated references.

## Mathematics

Verify consistency of:

```text
q
E(q)
D_k(q)
rank(e|q)
Coverage@k
K*
a_i
z_ij
E_i
K_i
K_decomp
K_max
```

Ensure:

- hop count ≠ retrieval depth;
- evidence coverage ≠ conformal coverage.

## Figures

Verify:

- readable fonts;
- no clipping;
- captions explain the figure;
- all labels resolve;
- figures are original;
- no fake experimental results.

## Writing

Correct:

- repetitive wording;
- long sentences;
- weak transitions;
- excessive filler;
- overly strong claims;
- duplication between intro and conclusion.

## Build

Compile the full thesis if feasible.

Fix:

- undefined citations;
- undefined references;
- missing figure files;
- new overfull boxes;
- duplicate labels;
- compilation errors.

Do not stop until the new Chapter 2 compiles cleanly, except for clearly unrelated pre-existing warnings.

---

# 19. Final validation checklist

Before completion:

- [ ] Chapter 2 is fully written.
- [ ] Introduction is short.
- [ ] Conclusion is short and different from introduction.
- [ ] No Section 2.6.3 exists.
- [ ] RAG figure included.
- [ ] Multi-hop figure included.
- [ ] Coverage/retrieval-depth figure included.
- [ ] Dependency-aware decomposition/DAG figure included.
- [ ] Coverage–depth schematic included.
- [ ] Hop count and retrieval depth distinguished.
- [ ] Evidence coverage and conformal coverage distinguished.
- [ ] Sparse retrieval covered.
- [ ] Dense retrieval covered.
- [ ] ColBERT / late interaction covered.
- [ ] Reranking covered briefly.
- [ ] MDR, Baleen, IRCoT covered.
- [ ] Adaptive-RAG covered.
- [ ] FLARE and Self-RAG covered briefly.
- [ ] Difficulty vs uncertainty clarified.
- [ ] Decomposition literature covered.
- [ ] Bridge entities / dependency-aware decomposition explained generically.
- [ ] Evidence-responsibility problem formulated.
- [ ] Proposed classifier not described yet.
- [ ] Coverage–depth objective is clear.
- [ ] Gap 1 leads to Chapter 3.
- [ ] Gap 2 leads to Chapters 4–5.
- [ ] Existing old-report content was not blindly reused.
- [ ] Existing useful bibliography entries were reused.
- [ ] New bibliography entries are verified.
- [ ] Two review/correction rounds completed.
- [ ] LaTeX project compiles.

---

# 20. Final Codex response

When finished, report:

1. files modified;
2. figures created;
3. bibliography entries added or reused;
4. final Chapter 2 structure;
5. compiled Chapter 2 page count;
6. compilation status;
7. remaining warnings, if any;
8. what changed during Review Round 1;
9. what changed during Review Round 2.

Do not merely explain what should be done.

Actually edit the LaTeX project and validate it.
