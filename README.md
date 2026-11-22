# Beyond Engagement
## Independent research case study on user-goal-aligned recommendation systems

**Status:** synthetic research and local prototype; independent expert review pending.  
**Independence:** This is independent portfolio work. It is not affiliated with, sponsored by, or based on internal data from Meta or any social platform.

### Research question
How might a recommendation system serve a user's explicitly stated goal while respecting safety constraints, uncertainty, user control, and the reliability limits of its own measurement process?

### What this repository contains
- `research/` — research report, product requirements, case study, audit records, and claims/evidence register.
- `prototype/` — FastAPI local demonstration, static UI, deterministic fictional fixtures, and tests.
- `review/` — adult expert review guide, reviewer scorecard, and feedback analysis utilities.
- `site/` — static portfolio website and fictional interactive demo.

### Evidence boundary — read before citing results
All reported experiment findings are **synthetic offline simulations**. No human participants, teenagers, real user data, production telemetry, live platform systems, clinical outcomes, or causal evidence were involved. The prototype uses fictional deterministic fixtures. It is not production-ready and must not be used to make decisions about real minors.

The synthetic safety filter is not a real moderation classifier. A zero-unsafe-selection result in a simulator is not evidence of real-world safety. No independent expert feedback is represented as received until it is actually submitted and documented.

### Key research themes
1. User-intent uncertainty is distinct from prediction reliability.
2. Automated evaluators can reward presentation cues without improving underlying utility.
3. Benchmark coverage, evaluator integrity, and monitoring quality are separate problems.
4. Monitoring can be attacked; fallback systems can inherit proxy weaknesses.
5. More feedback or online calibration is not automatically better.
6. Safety constraints should not be treated as interchangeable with ordinary relevance scores.

### Start here
1. Read [Project overview](research/PROJECT_OVERVIEW.md).
2. Read the [final research report](research/FINAL_RESEARCH_REPORT.md).
3. Review the [claims and evidence register](research/CLAIMS_AND_EVIDENCE_REGISTER.csv).
4. Read the [prototype instructions](prototype/README.md).
5. Read the [adult expert review guide](review/ADULT_EXPERT_REVIEW_GUIDE.md).

### Local prototype (Windows)
Use Python 3.11 or newer. Follow `prototype/README.md`; the Windows launcher is `prototype/START_DEMO.bat`. The local API documentation is available at `http://127.0.0.1:8000/docs` while the server is running. Keep the terminal window open.

### Verification
The included deterministic test suite is software verification, not validation of real-world recommendation quality or safety. The Windows run reported **12 passed, 1 warning** on 22 November 2026. The warning concerns deprecated Starlette/httpx test-client integration and is recorded for maintenance.

### Publication and review status
The repository is public. The static website and demonstration are not considered deployed until a live hosting URL is verified. Adult reviewer invitations and feedback remain pending; no independent review or endorsement is claimed.

### Research integrity notes
The consolidated report documents historical split/provenance limitations, including an unresolved V5.13 result-record conflict. Do not silently reconcile it or present it as settled. See the archive integrity and cross-milestone audit files.

### Future work
- Publish and verify the static portfolio and fictional demo.
- Obtain independent adult expert critique and adult usability feedback.
- Analyze reviewer disagreement and revise only where evidence supports changes.
- Seek external replication of selected synthetic experiments.
- Any future research involving minors requires a separate ethics-reviewed protocol, applicable Kenyan approvals, guardian permission where required, teen assent, privacy safeguards, independent safeguarding, and voluntary withdrawal.

### Citation and reuse
Please cite the repository URL and identify results as synthetic simulations. See `LICENSE-AND-USE.md` for use restrictions.
