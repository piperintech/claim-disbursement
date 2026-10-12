# CLADIS — Claims Distribution System

**Routes, balances and tracks every new auto claim across Property Damage (PD) and Bodily Injury (BI) adjusters, replacing a paper sign-up sheet.**

[Live demo](https://piperintech.github.io/claim-disbursement/) · Built for SNAP Insurance Service LLC (Texas & New Mexico non-standard auto MGA)

---

## The problem

Each morning, new claims from Modotech (the claims system) were split between adjusters by hand on a paper sheet. Auditing that process turned up **7 structural errors**. Workload drifted out of balance, PTO wasn't accounted for, transfers weren't logged, and nobody could answer "who has this claim?" without asking around.

## What it does

| Module | Purpose |
|---|---|
| **Batch intake** | Paste the morning's new claims and get a recommended distribution across PD and BI adjusters |
| **Leadership dashboard** | Live workload by adjuster: cards, stacked bars, capacity, variance |
| **Transfer** | Move a claim between adjusters, with a timestamped log |
| **Search** | Look up any claim number: adjuster, department, type, weight, and the FNOL clerk who took the call |
| **PTO calendar** | Mark days off; feeds straight into capacity and the algorithm |
| **History** | Every batch ever sent, with algorithm accuracy and where people overrode it |

## How the distribution works

1. Each claim gets a **weight** by type and severity. A split claim counts once for PD and once for BI.
2. Adjusters on PTO are dropped from that day's capacity.
3. Claims go to the adjuster with the lowest weighted load, keeping **variance** (max − min) as low as possible.
4. Fatality claims are flagged in a pre-scan for leadership review.
5. When a lead overrides a recommendation, it's logged. That's how algorithm accuracy is measured.

## Stack

Single-file HTML/CSS/JavaScript, no build step, hosted on GitHub Pages. Uses the **CLADIS design system**, which I built and reused across SNAP's internal tools.

## My role

Mapped the paper process, identified the failure points, designed the algorithm and the UI, built it, and rolled it out to the claims team.

> All claim data in this demo is fictional.

---

Built by **Manuela Gonzalez Piper** · Product & AI · [GitHub](https://github.com/piperintech)
