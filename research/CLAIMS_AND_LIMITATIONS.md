# Claims and Limitations Register

## Claims supported by this project record
- The project implemented and simulated a series of synthetic recommendation/evaluator experiments.
- Simulations show examples where evaluator proxy scores can improve while synthetic underlying utility worsens.
- Simulations illustrate failure modes in benchmark coverage, evaluator gaming, monitoring and fallback design.
- A local FastAPI prototype and a static fictional demonstration were developed.

## Claims not supported
- The design improves teen well-being in real life.
- It is safe for real minors or ready for deployment.
- It reduces addiction, harm, or mental-health risk.
- Human preferences or causal outcomes have been established.
- Simulated labels represent expert or teen judgments.
- Any synthetic result generalizes to real social platforms or production systems.

## Evidence boundaries
- Offline simulation only; no platform telemetry, real minor data, clinical data, or human-subject study.
- Prototype fixtures are fictional; static demo is illustrative and not connected to the FastAPI backend or a trained production model.
- A simulated hard safety filter's zero unsafe outputs is not proof of real-world safety.

## Known record limitations
- V5.8 paired-test CSV is validation-plus-test analysis, not test-only.
- V5.13 conflicting result records remain unresolved.
- Some milestone summaries lack raw artifacts in this publication; summaries are not independent replication.

## Reviewer guidance
Reviewers should challenge assumptions, definitions, simulator construction, split design, statistical methods, proxy choices, attack coverage, monitor performance, fallbacks, and interpretation. Negative findings and disagreement are welcome. Please distinguish technical reproducibility from external validity and real-world efficacy.
