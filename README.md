 
# Mechanism Design

**Goal**  
Ship a 2 to 3 page memo that a buyer can paste into a procurement or grant document, plus a minimal demo that shows how eligibility and scoring work.

**Definition of done**
- Memo contains the sections below and fits on 2 to 3 pages
- Rubric table scored on at least one public example
- Two sample clauses compile in legal style and reference the rubric
- Demo computes the score from stub data

## Memo structure (copy this outline)
1. **Context and problem**  
   What risk we shift and why the buyer cares.
2. **Instrument overview**  
   Mechanism family, buyer type, scope, timeline.
3. **Eligibility rules**  
   Minimum floors that must be met to be evaluated.
4. **Scoring rubric**  
   Weighted criteria, ranges, data sources, verification notes.
5. **Award or payment rules**  
   How scores translate to awards or selection.
6. **Monitoring and verification**  
   What is checked, when, and by whom.
7. **Contract language blocks**  
   Short clauses a buyer can paste into a contract or RFP.
8. **Risks and mitigations**  
   Known failure modes and how we reduce them.
9. **Recommendation**  
   One or two sentences on why this is the best fit for the buyer.

## Rubric template (edit in place)

| Criterion | Description | Evidence or test | Scale | Weight | Notes |
|---|---|---|---|---:|---|
| Eval completeness | Coverage on relevant safety evals | Links to reports | 0 to 4 | 0.25 | Must meet floor X |
| Post-training controls | Red teaming, fine-tuning guardrails | Docs and artifacts | 0 to 4 | 0.20 |  |
| Deployment safeguards | Rate limits, abuse monitoring | Config and logs | 0 to 4 | 0.20 |  |
| Incident response | Process and SLOs | Policy and drills | 0 to 4 | 0.15 |  |
| Transparency | Model card, changes, disclosures | Public docs | 0 to 4 | 0.20 |  |

Total score = sum(score_i * weight_i). Floors: define minimums here.

## Contract clause template (edit in place)

> **Safety Eligibility.** Vendor must meet the minimum floors in Annex A.  
> **Scoring.** Vendor will be scored per Annex B. Award goes to the highest eligible total score.  
> **Verification.** Buyer may request artifacts and run checks listed in Annex B.  
> **Ongoing Duties.** Material model or policy changes that affect Annex B must be disclosed within 10 business days.

## Demo hook
- Input: CSV or JSON with fields that map to rubric tests
- Output: score breakdown and pass or fail of floors
- File: `/app/Main.py` reads `/data/example.json` and renders two tabs

## Tasks
- [ ] Mechanism sketch and two clauses (owner: Fabio)
- [ ] Rubric v0.1 and data dictionary (owner: Jack, co: Abdullahi)
- [ ] Demo skeleton with stub data (owner: Abdullahi)
- [ ] QA tests for scoring math (owner: Jonas)
- [ ] Precedent citations to reuse in memo (owner: Nick)

## Sources to cite
Short list only. Add URLs in the memo footnotes and here in `/docs/refs.md`.
