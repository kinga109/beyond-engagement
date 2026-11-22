# Beyond Engagement
## A user-goal-aligned recommendation research and product prototype

**Independent research and prototype project | 2026**  
**Not affiliated with Meta or any social platform.**

### The problem
Recommendation systems are often evaluated using proxies such as clicks, watch time, engagement, or automated relevance scores. Those measures do not necessarily tell us whether a recommendation serves the user's current goal, preserves meaningful choice, avoids unhealthy repetition, or remains trustworthy when the evaluator itself is manipulated.

### Research question
How might a recommendation system serve a user's explicitly stated goal while respecting safety constraints, uncertainty, user control, and the reliability limits of its own measurement process?

### Work completed
- Developed a synthetic research programme (V5.5–V5.30) comparing engagement-oriented, objective-aware, context-aware and uncertainty-aware strategies.
- Studied feedback burden, benchmark coverage, evaluator gaming, counterfactual invariance, adaptive attacks, monitoring drift and fallback poisoning.
- Reported negative findings, uncertainty and limitations rather than treating every new policy as an improvement.
- Consolidated the work into a research report, product requirements document and adult expert-review protocol.
- Built a local FastAPI prototype with fictional fixtures, deterministic ranking, goal selection, controls, research-state diagnostics and automated tests.

### Key lessons
1. Optimizing an objective does not guarantee that the objective is correctly understood.
2. An evaluator can reward surface features that do not improve underlying usefulness.
3. Benchmark coverage and evaluator reliability are distinct: an unknown case is not the same as a trustworthy score.
4. Monitoring can itself be gamed; a fallback can inherit the same proxy failure.
5. More feedback or online calibration is not automatically better; small, biased audits can worsen calibration.
6. Safety constraints should be treated separately from ordinary relevance or quality scores.

### Evidence boundary
All experiments are synthetic offline simulations. The prototype uses hand-authored fictional examples and transparent deterministic scores. No real teenager data, platform telemetry, user study, clinical outcomes, or causal evidence were collected. No teen study has been conducted. The synthetic safety filter is not a real moderation classifier. The project does not establish that the proposed design improves adolescent well-being.

### Technical implementation
- Python and FastAPI backend.
- Browser-based HTML/CSS/JavaScript interface.
- Deterministic ranking with explicit, inspectable weights.
- Synthetic eligibility filter before ranking.
- Research status endpoints distinguishing benchmark coverage and evaluator reliability.
- Pytest automated API suite.

### What remains
- Obtain independent adult expert critique and adult usability feedback.
- Analyze inter-rater disagreement and revise the design based on evidence.
- Conduct external replication of selected synthetic experiments.
- Consider any future research involving minors only after institutional ethics review, applicable local approvals, guardian permission where required, teen assent, privacy and safeguarding arrangements.
