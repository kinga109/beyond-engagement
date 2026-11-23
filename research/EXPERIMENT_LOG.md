# Experiment Log — Beyond Engagement (V5.5–V5.30)

**Evidence status:** Synthetic offline simulation only. The log is a high-level summary, not raw experiment data.

| Range / milestone | Focus | Key result / caution |
|---|---|---|
| V5.5–V5.8 | Pairwise ranker, diversity reranking, context-aware optimization, audit | V5.8 computationally reproducible after report correction; no demonstrated objective-alignment improvement. CSV analysis was validation-plus-test, not test-only. |
| V5.9–V5.13 | Objective weighting, held-out evaluation, robustness, safety/Pareto, reproducibility | V5.13 result conflict unresolved. Report prior negative interpretation as provisional, not reconciled. |
| V5.14–V5.18 | Generator shift, uncertainty-aware weighting, centered confidence, reliability-aware calibration | Reliability and calibration explored; detailed numerical run records not included in this summary. |
| V5.19–V5.23 | Intent uncertainty, clarification, burden, abstention, drift detection | V5.22 OOD detection struggled with silent response drift; V5.23 fewer prompts but alignment trade-off and feedback-starvation concern. |
| V5.24 | Monitoring without burden | Hybrid: 86.1% detection, 1.7% FPR, 0.0198 prompts/session; 7-session median delay. Sentinel-only same detection but 4.2% FPR and 30-session median delay. |
| V5.25 | Coverage and evaluator integrity | Coverage-directed rotation 80/80 known cells in two epochs; evaluator-bias-only audit flagged 40/40; proxy gaming quality detection only 2/40. |
| V5.26 | Gaming, leakage, independent test | Surface-cue gamer improved evaluator score but lowered synthetic true utility vs robust multisignal. |
| V5.27 | Counterfactual styles and adversarial benchmark | Style changes shifted scores; integrity monitor 38.5% sensitivity, 27.2% FPR; no overall significant ranking improvement. |
| V5.28 | Adaptive red-team and silent drift | Hybrid monitor 97.5% sensitivity and 2.5% FPR in synthetic test; wide intervals; gated ranking below content-only anchor. |
| V5.29 | Adaptive evasion | Continuous 87.5% sensitivity / 2.1% FPR; sequential hybrid 81.7% / 12.5%; threshold shaping difficult. |
| V5.30 | Proxy-independent fallbacks | Audit-adaptive reduced attacks but lost 0.0043 utility vs primary (Holm-significant); online calibration error worsened; 43.5% post-change abstention. |

## Corrections / unresolved issues
- V5.8 existing paired-test CSV must be labeled validation-plus-test; it cannot support test-only claims.
- V5.13 result/archive discrepancy is unresolved; do not merge conflicting records or claim reconciliation.
- All results are synthetic; no real-world or human-subject validation.
- Raw experiment archives, code, seeds, run manifests and analysis scripts should accompany any replication claim.
