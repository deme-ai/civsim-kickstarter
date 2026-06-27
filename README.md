# CivSim:Kickstarter

**Pre-launch behavioral simulation for tabletop crowdfunding.**

CivSim:Kickstarter predicts how different segments of the board game hobby audience will respond to a Kickstarter campaign before it launches. Given a campaign page, it produces implied backer count estimates across reach scenarios and extracts convergent qualitative findings — concerns and selling points that surface independently across demographically distinct audience segments — before the campaign closes.

---

## Background

CivSim was originally developed and validated on municipal ballot measures (Washington State property tax levies), where outcomes are binary, publicly recorded, and provide clean ground truth for evaluating whether a behavioral simulation is working. The core insight is that population response to a pre-decisional question — whether to vote yes on a levy, whether to back a campaign — can be compressed into a tractable behavioral representation without losing the dynamics that determine outcomes.

CivSim:Kickstarter applies this architecture to crowdfunding prediction. The same structural problem exists: a creator or publisher must decide whether to launch, at what goal, with what positioning — before they know how their audience will respond.

The architecture, validation methodology, and theoretical positioning are described in:

> Chung, E. (2026). *CivSim: An LLM-Calibrated Agent Architecture for Population-Scale Social Simulation.* Deme AI LLC. [arXiv preprint, forthcoming]

---

## What It Produces

For a given campaign, CivSim:Kickstarter generates:

**Quantitative:** Implied backer count estimates across reach scenarios (low / medium / high), with per-audience-segment breakdown showing which segments are driving or suppressing conversion.

**Qualitative:** Convergent concerns and selling points that surface independently across multiple audience segments without prompting. When the same concern appears across demographically distinct segments who dismissed other arguments as unpersuasive, that convergence is treated as a behavioral hypothesis about the backer population — available before any simulation runs and directly actionable for campaign positioning.

---

## Validation Campaigns (Retrospective)

Five campaigns with known outcomes were used to develop and validate the architecture:

| Campaign | Outcome | Actual backers |
|---|---|---|
| Cabals: The Board Game (May 2015) | Cancelled — 33% of goal | 392 |
| Terminator Genisys: Rise of the Resistance (2018) | Failed — 75% of goal | 419 |
| Everdell (2018) | Funded — 1,354% of goal | 9,269 |
| Cthulhu: Death May Die (2018) | Funded — 1,206% of goal | 15,831 |
| Frosthaven (2020) | Funded — 2,594% of goal | 83,184 |

Directional accuracy is consistent across all five campaign results. The more important finding is **threshold proximity**: the pipeline's implied backer count, compared directly against a real funding threshold, distinguishes a near-miss failure (Terminator at 75% of goal) from a clean failure — a distinction that matters for the decisions a creator actually needs to make. It also produces insights into which backer types (angelic, avid IP fan, etc) the campaign appeals to or does not appeal to the most.

---

## Prospective Validations

Prospective validations are predictions made before campaign outcomes are known. Calibration outputs and predictions are committed to this repository before campaign close; git timestamps provide independently verifiable proof of prediction date.

| Campaign | Prediction date | Campaign closes | Status |
|---|---|---|---|
| [The Monolith — Plaid Hat Games (2026)](predictions/monolith_2026/) | June 26, 2026 | ~July 25, 2026 | 🔄 In progress |

---

## Repository Structure

```
predictions/
  monolith_2026/
    README.md                          ← prediction document
    plaidhatgames_monolith-1_calibration.json

```

---

## Contact

Eddie Chung  
Deme AI LLC  
City Council Member, City of Clyde Hill, Washington  
eddiechung@gmail.com
