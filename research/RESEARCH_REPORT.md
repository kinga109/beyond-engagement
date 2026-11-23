# Beyond Engagement — Consolidated Research Report

**Independent portfolio research | 2026**  
**Synthetic offline experiments only. Not affiliated with Meta or any platform.**

## Executive summary
This project investigates how recommendation systems might prioritize a user's stated goal while accounting for context, safety constraints, preference uncertainty, evaluator reliability, monitoring burden, and adversarial proxy manipulation.

The central concern is that click likelihood, engagement, automated evaluation scores, or style cues can be imperfect proxies for underlying usefulness. A system may optimize a proxy while becoming less aligned with the user's real objective.

**Evidence boundary:** All experiments described here are synthetic offline simulations. No real user/teen data, platform telemetry, human study, clinical outcome, or causal evidence was collected. Numerical findings are simulation results, not real-world validation.

## Research framing
**Question:** How might recommendations serve a user's explicitly stated goal while respecting safety constraints, uncertainty, user control, and the reliability limits of measurement?

**Design principle:** Recommendations should serve the user's current objective and safety constraints—not merely maximize click likelihood or evaluator score.

Conceptual pipeline: User → Context → Safety → Preferences → Well-being → Recommendation.

## Research progression (V5.5–V5.30)
This table is a high-level reconstruction from the project research record. Detailed raw experiment files and run-level data should be linked separately when available.

- **V5.5–V5.8:** Pairwise ranking, diversity reranking, context-aware optimization and audit. V5.8 was computationally reproducible with a corrected statistical report, but no demonstrated objective-alignment improvement. The existing paired-test CSV was validation-plus-test analysis, not test-only inference.
- **V5.9–V5.13:** Objective-weighted ranking, independent-test protocol, robustness, safety/Pareto framing and reproducibility audits. V5.13 has conflicting result records; the discrepancy remains unresolved and must not be silently reconciled. A previously reported interpretation found alignment improvement indistinguishable from zero and no secondary tests surviving Holm correction.
- **V5.14–V5.18:** Shifted generators, uncertainty-aware weighting, centered confidence, reliability-aware calibration and posthoc calibration diagnostics.
- **V5.19–V5.23:** Separating estimator reliability from uncertainty about user intent; active clarification, information gain, clarification fatigue, abstention, shift detection, sequential monitoring and feedback starvation. Synthetic shift detection was weak in V5.22, while V5.23 illustrated a trade-off between fewer questions and reduced alignment under joint shift.
- **V5.24:** Monitoring quality without user burden.
- **V5.25:** Benchmark coverage and evaluator integrity.
- **V5.26:** Evaluator gaming, benchmark leakage and independent human validation design.
- **V5.27:** Adversarial benchmark generation and counterfactual testing.
- **V5.28:** Adaptive evaluator red-teaming and silent drift detection.
- **V5.29:** Adaptive red-team evasion and monitoring under attack.
- **V5.30:** Proxy-independent fallbacks and resilient recommendation selection.

## Selected quantitative results (synthetic)
### V5.24 — Monitoring quality and user burden
Across 10 simulated worlds:
- Explicit-feedback-only monitoring: degradation detection 11.4%, false-alert rate 25.8%, 0.2502 prompts/session.
- Passive telemetry: detection 57.9%, false-alert rate 1.7%, zero prompts.
- Sentinel benchmark only: detection 86.1%, false-alert rate 4.2%, zero prompts; median detection delay 30 sessions.
- Passive + sentinel hybrid: detection 86.1%, false-alert rate 1.7%, 0.0198 prompts/session; median detection delay 7 sessions.
- Hybrid prompts were 92.1% fewer than explicit-feedback baseline.
One proxy-gaming world was poorly detected (1/40). Feedback reporting shifts could cause false alerts. Zero prompts does not mean zero reviewer workload.

### V5.25 — Benchmark coverage and evaluator integrity
- 80-cell taxonomy (4 goals × 4 contexts × 5 categories); 40 fixed core + 120 rotating challenge cases.
- 360 independent test streams across 9 synthetic worlds; 288,000 case-epoch evaluations; 18,000 simulated independent-reference audit labels.
- Coverage-directed rotation covered 80/80 known cells after two epochs; fixed core covered 40/80; random rotation covered 67/80.
- Quality-stable false alerts: 2/120 (1.67%); reported 95% CI 0.46–5.87%.
- Unrepresented explore goal was marked coverage-unknown in 40/40 cases.
- Independent audit flagged evaluator unreliability in evaluator-bias-only world 40/40; without audit, false quality alerts occurred 40/40.
- Proxy gaming remained difficult: evaluator drift flagged 34/40, but quality degradation detected only 2/40.

### V5.26 — Evaluator gaming and benchmark leakage
- Five synthetic worlds, 600 scenarios, 3,000 candidate records.
- Per-world split: 60 development / 20 validation / 40 independent test scenarios.
- Independent test mean utility: oracle 0.617019; proxy optimizer 0.574661; surface-cue gamer 0.524472; benchmark memorizer 0.570269; robust multisignal 0.603850.
- Surface-cue gamer vs robust multisignal: proxy score advantage +0.020730 (95% CI +0.014598 to +0.027207; p=5.4e-9), while synthetic true utility difference −0.079379 (95% CI −0.093590 to −0.066329; p=3.34e-20).
- In evaluator-shift world, educational vocabulary vs true utility Spearman correlation was −0.5835.
- Benchmark leakage was template-feature reuse across scenario-disjoint splits, not literal duplicate rows.
- Zero unsafe selections was caused by a hard filter in the simulation, not evidence of real-world safety.

### V5.27 — Adversarial counterfactual testing
- 480 scenarios, 19,520 candidate records, four worlds, eight concepts with paired style variants.
- Same-substance style changes shifted evaluator score: educational +0.0594; positive +0.0325; visual polish +0.0428; combined +0.1349.
- Development-trained correction reduced known style effects but struggled with evaluator-weight changes and private unseen authority/precision styles.
- Integrity monitor sensitivity 38.5%, false-positive rate 27.2%.
- No overall significant ranking improvement.

### V5.28 — Adaptive evaluator red-teaming
- 360 streams, six worlds, 24 epochs.
- Hybrid monitor sensitivity 97.5%, false-positive rate 2.5% across 80 attack/drift and 40 benign streams; intervals were wide.
- Adaptive proxy gaming without evaluator-weight drift detected 90%, median delay 4.5 epochs.
- Gated ranking improved over raw evaluator but remained below content-only anchor.

### V5.29 — Adaptive evasion
- 504 streams, seven scenarios, 32 epochs; independent test 168 streams (120 attack/drift, 48 benign).
- Continuous monitor sensitivity 87.5%, false-positive rate 2.1%.
- Sequential hybrid sensitivity 81.7%, false-positive rate 12.5%.
- Threshold shaping remained difficult to detect.
- Gated ranker improved over raw evaluator but did not outperform content-only anchor; fallback was not automatically trustworthy.

### V5.30 — Proxy-independent fallbacks
- 576 streams, 138,240 candidate records, eight scenarios, 192 independent-test streams.
- Utility: primary evaluator 0.7947; fallback-only 0.5089; equal blend 0.7179; conservative minimum 0.7590; audit-adaptive 0.7904; oracle 0.8047.
- Attack-selection rates: primary 1.53%; fallback-only 74.64%; equal blend 23.05%; conservative minimum 7.71%; audit-adaptive 0.23%; oracle 0%.
- Audit-adaptive reduced attacks but utility was 0.0043 below primary, significant after Holm correction.
- Online calibration worsened prediction error (0.0964 vs fixed development calibrator 0.0580).
- Abstention rate was 43.5% post-change.

## Interpretation
The simulations illustrate that evaluator reliability, benchmark coverage, monitoring, fallback design and uncertainty are separate failure modes. A score can be gamed; a benchmark can be incomplete; a monitor can miss attacks; and a fallback can inherit proxy weaknesses. More monitoring or feedback does not automatically improve outcomes.

## Limitations and unresolved issues
- Entire evidence base is synthetic and offline.
- Synthetic scenarios and reference labels are authored/generated assumptions, not human preferences.
- No real teen participants or human reviewers have evaluated the system.
- Results depend on simulator assumptions and may not generalize.
- Zero unsafe selections in synthetic filters is not a safety claim.
- V5.13 result conflict remains unresolved.
- V5.8 paired-test file covers validation plus test, not test-only.
- This report summarizes milestones; it is not a substitute for raw run artifacts, executable code, or independent replication.

## Next research steps
1. External replication of selected simulations from frozen code and specifications.
2. Independent adult expert criticism, with disagreements retained.
3. Adult usability/interpretability review before any study with minors.
4. Future research with minors only after ethics review, local approvals, guardian permission where required, teen assent, privacy and safeguarding, and voluntary withdrawal.
5. Evaluate real-world outcomes only with suitable study design and independent oversight.

## Citation / reproducibility note
This report is a portfolio synthesis of the project's research record. Detailed experiment archives should be added as separate artifacts and checksum-verified. Do not interpret summary statistics without access to the corresponding raw data, code, split definitions, and analysis scripts.
