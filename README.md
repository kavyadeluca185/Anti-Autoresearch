# Anti-Autoresearch 🛡️

[![Join Community](https://img.shields.io/badge/💬_Join-Community-7C3AED?style=flat)](#community) · [![Cite](https://img.shields.io/badge/📖_Cite-BibTeX-2E7D32?style=flat)](#citation) · [![Parent ARIS stars](https://img.shields.io/github/stars/wanshuiyin/Auto-claude-code-research-in-sleep?style=flat&logo=github&logoColor=white&color=gold&label=Parent%20ARIS%20%E2%98%85)](https://github.com/wanshuiyin/Auto-claude-code-research-in-sleep/stargazers) · [![ARIS Report arXiv:2605.03042](https://img.shields.io/badge/ARIS%20Report-arXiv%3A2605.03042-b31b1b?style=flat&logo=arxiv)](https://arxiv.org/abs/2605.03042) · [![ARIS · HF Daily #1](https://img.shields.io/badge/ARIS%20%F0%9F%A4%97%20HF%20Daily-%231-ffcc4d?style=flat)](https://huggingface.co/papers/2605.03042) · [![ARIS on PaperWeekly](https://img.shields.io/badge/ARIS%20on-PaperWeekly-red?style=flat)](https://mp.weixin.qq.com/s/tDniVryVGjDkkkWl-5sTkQ) · [![ARIS in awesome-agent-skills](https://img.shields.io/badge/ARIS%20in-awesome--agent--skills-blue?style=flat&logo=github)](https://github.com/VoltAgent/awesome-agent-skills) · [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat)](LICENSE) · [![README 中文](https://img.shields.io/badge/README-%E4%B8%AD%E6%96%87-blue?style=flat)](README_CN.md)

<div align="center">

### 🔬 The field has tolerated unreliable autoresearch long enough — Anti-Autoresearch is the read that finally catches it.

***天下苦 autoresearch 久矣 —— Anti-Autoresearch 替研究者们一眼看穿不靠谱的工作。***

</div>

> 🏆 **Built on a battle-tested foundation: [ARIS](https://github.com/wanshuiyin/Auto-claude-code-research-in-sleep)** (~12.5k★ · HuggingFace Daily Papers #1 · 78+ skills across 7+ platforms). Anti-Autoresearch points ARIS's production audit DNA (experiment-audit · paper-claim-audit · citation-audit · kill-argument) **outward** — auditing a third party's submission instead of your own.

Autoresearch has gone mainstream, and a fast-growing share of what reaches the review
pile is machine-generated — and a lot of it **doesn't hold up**: tables that don't
match the text, baselines that aren't there, open-sourced code that won't reproduce
its own paper. Reviewers, area chairs, and honest authors increasingly need to
**verify** that, not just suspect it.

> Regardless of *who or what* wrote a paper, does the science hold together and
> reflect its own evidence? Anti-Autoresearch audits a submission for
> **self-consistency** and **fabrication**, and produces a span-anchored,
> reviewer-ready report. It is **not** an *opaque* AI-text classifier (no authorship
> probabilities, no "AI-written" verdict) and does **not** judge misconduct — it surfaces
> discrepancies a human reviewer should investigate. Separately, it lists transparent,
> itemized **AI writing-style impressions** in a quarantined, **zero-verdict-weight**
> section (a paper can be integrity-`CLEAN` while listing many), because reviewers react to them.

---

## 🧭 What's inside

**46 integrity patterns across 8 families** — the coverage vocabulary every finding cites — plus **13 zero-weight AI writing-style impressions** and **2 advisories**:

| | Family | Catches |
|---|--------|---------|
| **A** | Numeric self-consistency | 数值自洽:table vs text vs delta arithmetic that doesn't add up |
| **B** | Method & scope | 方法与范围:the described method/scope ≠ what was actually done |
| **C** | Baseline integrity | baseline 诚信:missing, weak, or unfairly configured comparisons |
| **D** | Experiment integrity | 实验诚信:fake ground truth, phantom results, code ≠ numbers (needs code) |
| **E** | Citation integrity | 引用诚信:fabricated, misattributed, or retracted references |
| **F** | Presentation & surface | 表面信号:layout / prose / figure signals — capped at `minor` |
| **G** | Proof & derivation | 证明诚信:skipped obligations, circular or invalid derivations |
| **H** | Evaluation design & validity | 评测设计:data leakage, LLM-judge validity, selective reporting |

Delivered as **11 skills + 1 orchestrating workflow** on a deterministic spine: a span-anchored, hashed evidence **ledger** → LLM auditors that only **propose** findings → a rules-only **reporter** that lists every proposal with what the auditor said about it, and summarizes — with 8 patterns eval-gated end-to-end (GRIM · GRIMMER · statcheck · delta arithmetic · hedge-density · …) and the whole gate in CI.

---

## 📰 News

- **2026-07-10** — 🧮 **Math was invited to overturn false alarms — and honestly declined.** We built exact calculators to re-check the arithmetic behind numeric criticals, hoping to auto-clear false alarms like rounding differences. Adversarial review broke every version — the killer was "dropout of exactly 50%" vs a table's 50.4%: a calculator can't know whether a number is exact or rounded. The calculators stayed, demoted: they attach their full working to the report for the human, and **nothing gets auto-cleared**.
- **2026-07-10** — 🛡️ **Criticals must now survive their own defense.** A critical has to state which innocent explanations it ruled out (blank → drops to major), face one fresh refutation thread whose only power is a ⚠️ CONTESTED marker for the human, and — if numeric — declare exactly which numbers it computes over. Reports stamp `adjudicator: deterministic-rules-v2`. ⚠️ Re-run the auditors on old findings files instead of re-adjudicating them.
- **2026-06-28** — ✍️ **v0.5 — the AIS track.** 13 itemized AI writing-style impressions now live in a separate, **zero-verdict-weight** report section — a paper can be integrity-`CLEAN` while listing many. Transparent impressions, never an authorship verdict; the 5 pure-style patterns moved out of family F.

<details>
<summary><b>Earlier updates</b> (2026-06)</summary>

- **2026-06-27** — 🧬 **v0.4 — the taxonomy grows to 8 families** (new: proof & derivation G, evaluation design H — the full map is in *What's inside* above). The deterministic eval gate grew 3→8 patterns (GRIM / GRIMMER / statcheck + a conservative hedge-density screen), CI landed, and prior-art acknowledgments were added.
- **2026-06-26** — 🚀 **v0.1 — initial release.** Reviewer-side integrity forensics for autoresearch / AI-Scientist papers: evidence ledger, deterministic adjudicator, observability tiers. Not an AI-text detector.

</details>

## 🚀 Quickstart

### Agent workflow (normal use)

Anti-Autoresearch runs as a Claude Code skill workflow — the Python tools are the
deterministic spine *inside* that workflow, not the usual interface.

```bash
# 1) Install the skills + workflow (global, or pass a project's .claude/skills dir)
git clone https://github.com/wanshuiyin/Anti-Autoresearch.git
./Anti-Autoresearch/tools/install_anti_autoresearch.sh              # → ~/.claude/skills
# project-local instead: ./Anti-Autoresearch/tools/install_anti_autoresearch.sh ./.claude/skills

# 2) Wire the cross-model reviewer (end state: Claude Code exposes mcp__codex__codex)
claude mcp add codex -- codex mcp-server
claude mcp list

# 3) Audit a paper
claude
> /anti-autoresearch ~/papers/submission
```

The run writes `REPORT.md` + `report.json` + `claims.json` + per-skill
`*.findings.json` into the paper directory. Put the code/result artifacts alongside
the paper to unlock L2 checks; PDF/source-only runs are observability-limited by
design.

### Zero verdict weight — the AIS + advisory tracks (reported, never moves the verdict)

Three skills produce outputs that are **reported but carry zero weight on the integrity
verdict** — the non-integrity categories that round out a report: the **AIS** writing-style
track and the **advisory** memos. They matter to a human reviewer (a style impression, the
worst-case rejection paragraph, prior-art overlap), so the report shows them in their own
section — but the deterministic verdict stays driven **only** by the 46 integrity patterns. A
paper can be `CLEAN_GIVEN_EVIDENCE` while listing many. `/anti-autoresearch` runs them
automatically; to run one standalone, build the ledger first (next section) and invoke it like
any auditor.

| Skill | What it writes |
|-------|----------------|
| `/ai-style-impressions` | *(AIS · separate report section)* AI writing-style impressions: defensive hedging, LLM phrasing tics, clause-then-formula walls, bullet/bold spam, invented codenames, single-style figures |
| `/adversarial-case-builder` | *(memo, no verdict)* the single strongest evidence-bound rejection paragraph a hostile reviewer would write |
| `/novelty-duplication-advisory` | *(memo, no verdict)* prior-work overlap: trivial-combination ("缝合 / stapling") and duplicate-publication candidates, laid out for a human to weigh |

### Single-skill use

Every auditor is also a standalone skill — the installer drops all of them plus the
workflow, so you can run just the axis you care about. They share one contract, so
run it in order:

```text
claude
# 1) Build the evidence ledger ONCE — the spine every auditor anchors to. Skip it and
#    any auditor stops with:  NO_LEDGER: claims.json not found. Run /evidence-ledger FIRST
> /evidence-ledger ~/papers/submission        # → claims.json + observability level (L0/L1/L2)

# 2) Then run any auditor below against that ledger → <skill>.findings.json
```

**The verdict-bearing auditors** — each takes the paper dir, reads the ledger, and proposes
span-anchored findings the deterministic adjudicator turns into the verdict (the zero-weight
AIS + advisory skills are in the section above):

| Skill | What it catches |
|-------|-----------------|
| `/consistency-audit` | the paper against itself: inflated / mismatched numbers, method & scope drift, appendix-vs-body contradictions |
| `/citation-forensics` | citations: hallucinated references, and real papers cited for a claim they don't make |
| `/baseline-comparison-audit` | the missing / weak / mistuned baselines hiding behind a "SOTA" or "outperforms" claim |
| `/experiment-forensics` | *(L2 — needs code+results)* fake / derived ground truth, score self-normalization, phantom results, placeholder data, code output ≠ reported numbers |
| `/proof-derivation-forensics` | *(L1 — needs LaTeX source)* the written proof: skipped obligations, circularity, invalid steps, symbol drift, smuggled assumptions |
| `/eval-design-forensics` | the evaluation's validity: train/test leakage, a conflicted or unvalidated LLM-judge metric, selective reporting (dropped conditions / switched metrics) |
| `/presentation-signals` | *(capped at `minor` → at most SOFT)* checkable surface tells: duplicate tables, leftover pipeline/template strings, LLM-generated figures, page-padding — context, never a verdict |

A single skill only **proposes** span-anchored findings — it never returns a verdict.
To get one, feed the findings to the deterministic adjudicator (the
`python3 tools/adjudicate_findings.py … --ledger …` command in the next section); the
model never grades. Two more notes: `consistency-audit`, `presentation-signals`, and
`ai-style-impressions` also write a `*.deterministic.findings.json` (works with no
cross-model reviewer wired); and **`/anti-autoresearch`** runs every auditor above in one
shot, adding ingest
(arxiv-id / pdf → workdir + `pdftotext`), automatic observability, auto-selection of
which auditors apply, and the final cross-dimension verdict + `REPORT.md`.

### Deterministic core (CI / offline / zero-dependency)

This bypasses the agent layer and exercises only the eval-tested deterministic
checks — use it for CI, regression tests, or environments with no cross-model
reviewer (Python 3 stdlib, nothing to install):

```bash
# Prove the pipeline on clean + corrupted fixtures (the regression gate)
python3 eval/run_eval.py
#   clean / delta_inflate / dup_table / headline_inflate  → all PASS
#   injected-defect recall: 100% (7 deterministic patterns) · clean FP: none
python3 tests/test_adjudicator.py        # gate unit tests (the anti-slop guarantee)

# Or run the spine by hand on a real paper:
python3 tools/build_claim_ledger.py --paper-id mypaper --latex main.tex sections/*.tex \
    --observability-level 1 --out claims.json
python3 tools/check_numeric_consistency.py --ledger claims.json --out findings.json
python3 tools/adjudicate_findings.py --findings findings.json --ledger claims.json \
    --paper-id mypaper --observability-level 1 --out report.json --md REPORT.md
#   --ledger is REQUIRED: a finding must quote a verbatim ledger span or it fails closed to info.
```

## 🎯 Why this exists

Machine-generated papers and reviews are now a measurable share of the literature,
and the failure that matters for an area chair is rarely *"was this text written by
an LLM?"* (a human can write a dishonest paper; an LLM can write an honest one). It
is: **does the paper contradict itself, and is it backed by its own evidence?**

That is what autoresearch pipelines get wrong — they hallucinate *local* coherence:
an abstract number that no table reports, a "16% improvement" that the operands say
is 6%, a citation for a claim the cited paper never makes, a method described one
way and evaluated another.

Those are checkable under a declared observability level. Concretely, taxonomy v0.5
names **46 integrity patterns across 8 families** (numeric self-consistency · method /
scope · baseline integrity · experiment integrity · citation integrity ·
presentation / surface signals · proof & derivation integrity · evaluation design &
validity) — the repo's **coverage vocabulary**, not a detector benchmark — plus a
**13-signal AI writing-style impression track (AIS)** that carries **zero verdict weight**.

> **Shipped v0:** the deterministic spine and the **seven** ✓-marked patterns (across
> the representative list below and the full catalog) are eval-tested; the other 39 integrity
> patterns are agent-layer contracts (a cross-model reviewer proposes span-anchored findings, the
> deterministic adjudicator scores or demotes them) — not bundled-eval detector claims.

The full catalog, with detection signals and false-positive cases, lives in
[the taxonomy](references/hack-pattern-taxonomy.md). A representative ten (✓ = gated
by the deterministic eval today):

- `HP-NUM-INFLATE` — abstract says 85.3%, but Table 2 never gets past 84.7%. ✓
- `HP-DELTA-ERROR` — a "16% improvement" from 73.1 to 78.0 is really 6.7%. ✓
- `HP-DUP-TABLE` — two tables carry the identical ordered numbers — usually copy-paste padding. ✓
- `HP-METHOD-DRIFT` — the method section says "no labels"; the eval quietly uses gold-label calibration.
- `HP-SCOPE-INFLATE` — "comprehensive" turns out to be two datasets, one domain, maybe one seed.
- `HP-MISSING-BASELINE` — SOTA is claimed while the obvious recent baseline never appears in the table.
- `HP-FAKE-GT` — (L2) the "reference" targets are model outputs, then reported as ground truth.
- `HP-PHANTOM-RESULT` — (L2) a headline number points at a result file or metric key that isn't there.
- `HP-PROOF-CIRCULARITY` — (L1) the "proof" restates the claim in different words and calls it done — it proves nothing.
- `HP-CITE-HALLUC` — the DOI / arXiv id / venue / author list simply doesn't exist.

<details>
<summary><b>… the other 36 integrity patterns + the 13 AIS impressions, in full</b></summary>

**A · Numeric self-consistency**
- `HP-AGG-DRIFT` — they write "mean over seeds", but the number is really the best seed.
- `HP-DENOM-DRIFT` — one table averages all tasks; the conclusion quietly uses the applicable-only subset.
- `HP-UNIT-DIR-MISMATCH` — points silently become percent, or a lower-better metric is celebrated upward.
- `HP-CAPTION-MISMATCH` — the caption promises N=5 and method B; the plot shows neither.
- `HP-APPENDIX-CONTRA` — the appendix reruns the same quantity and disagrees with the main text.
- `HP-GRANULARITY-IMPOSSIBLE` — "84.7% on 500 items" is arithmetically impossible — no integer k/500 rounds to it (GRIM). ✓
- `HP-VARIANCE-IMPOSSIBLE` — a reported SD bigger than a bounded metric can have at that mean (e.g. SD 18% at mean 98% — cap ≈15.7%). ✓
- `HP-STAT-INCONSISTENCY` — the reported p contradicts its own test statistic and overstates significance ("z=1.10, p=.036" → really p≈.27). ✓

**B · Method & scope**
- `HP-ABLATION-ATTRIB` — they credit component X, but every ablation keeps X bundled with Y.
- `HP-THEOREM-SCOPE-DRIFT` — the abstract sells a general theorem; the assumptions do nearly all the work.
- `HP-ARGUMENT-CHAIN-BREAK` — a substantive missing link: the problem motivated isn't the one the method addresses, or the experiments measure something the mechanism doesn't predict.
- `HP-CAUSAL-EVIDENCE-LEAP` — a causal / equivalence relation is concluded that no experiment in the paper actually varies or tests.
- `HP-RESOURCE-IDENTITY-MISMATCH` — a named dataset/model/benchmark described with a property its public record contradicts ("ImageNet-1k, 5,000 classes" — it's 1,000).
- `HP-ACRONYM-DRIFT` — the same load-bearing component/term gets two incompatible names or acronym expansions across the paper.

**C · Baseline integrity**
- `HP-WEAK-BASELINE` — the new method gets tuning and compute the baseline plainly did not.
- `HP-SIG-OVERLAP` — "outperforms" by crumbs, with overlapping error bars or no seeds shown.

**D · Experiment integrity** (needs code/results — L2)
- `HP-SELF-NORM` — (L2) the score nears 1.0 because it's divided by the model's own max.
- `HP-DEAD-METRIC` — (L2) a metric function exists with no call site and no result, yet is discussed.
- `HP-SUSPICIOUS-REGULARITY` — (L2) rows differ by a suspiciously clean offset — check the files before calling it fake.
- `HP-PLACEHOLDER-DATA` — (L2) released code still ships placeholder/dummy/fake data feeding a reported figure or number.
- `HP-RESULT-ARTIFACT-MISMATCH` — (L2) the released code / artifacts, run as written, produce numbers different from the paper's.
- `HP-MISSING-REPRO-ARTIFACT` — (L2) an empirical paper ships neither code nor the prompts/configs its results depend on.

**E · Citation integrity**
- `HP-CITE-CONTEXT` — real paper, wrong job: cited for a claim it explicitly doesn't make (incl. semantic-hallucination + a support/contrast/mention intent label).
- `HP-CITE-RETRACTED` — a load-bearing citation that resolves to a **retracted** paper, with no note of the retraction (Crossref / Retraction Watch).

**F · Presentation & surface signals** (capped at `minor` — never a verdict)
- `HP-THIN-FLOAT` — a "broad empirical study" somehow has two tables and one lonely figure.
- `HP-LLM-FIGURE` — the "figure" is decorative model art, not a plot or a real diagram.
- `HP-PAGE-PADDING` — oversized floats, repeated text, or empty prose doing page-count labor.
- `HP-PIPELINE-ARTIFACT` — a leftover pipeline/template string ("As an AI language model", "regenerate response", "[INSERT X]") survives into the finished text. ✓ (exact-match, low-FP)

**G · Proof & derivation integrity** (verdict-bearing at L1 — from the written math)
- `HP-PROOF-OBLIGATION-GAP` — (L1) a required lemma / case / transition is skipped with "clearly" across a real gap.
- `HP-DERIVATION-INVALID` — (L1) an algebra / probability / calculus step does not follow (a misapplied inequality, a wrong limit).
- `HP-SYMBOL-SEMANTIC-DRIFT` — (L1) a symbol / operator / inequality direction changes meaning between definition, formula, and proof.
- `HP-ASSUMPTION-SMUGGLE` — (L1) the proof relies on an assumption (independence, convexity, …) the theorem statement never lists.
- `HP-UNDEFINED-NOTATION` — (L1) a load-bearing symbol is used in a key equation/proof but never defined and not inferable from standard convention.

**H · Evaluation design & validity** (L0/L1 stated → L2 confirmed)
- `HP-EVAL-LEAKAGE` — train/test leakage (preprocess-before-split, duplicates across splits, temporal leak, pretraining contamination) means the score may not measure generalization. Adopts the Kapoor–Narayanan leakage taxonomy.
- `HP-JUDGE-VALIDITY` — the load-bearing metric is an LLM judge that's *conflicted* (same family as a compared system) or *unvalidated* (no human-agreement check).
- `