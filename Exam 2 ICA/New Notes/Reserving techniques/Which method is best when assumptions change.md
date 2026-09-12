# Which method is best when assumptions change

> Summary of how each reserving approach reacts when key assumptions are violated, and which method to prefer in each scenario. Synthesized from [[BF]], [[Cape Cod]], [[Chain Ladder]], [[Expected method]], [[Freq-Sev]], [[Closure Method]], and [[Berquist sherman]].

## The big idea

Every reserving method carries implicit assumptions. When reality breaks those assumptions, the method produces biased reserves. No single method is always best — you pick the one whose assumptions are *most likely to hold* (or least hurt when broken) for the situation. This note groups the methods into three families and compares them under each changing assumption.

## The three families of methods

| Family | Methods | Core assumption |
| --- | --- | --- |
| **Development** | [[Chain Ladder]] (paid & reported) | Past development repeats; future mirrors history |
| **Expected / Bornhuetter-Ferguson (BF)** | [[Expected method]], [[BF]], [[Cape Cod]], [[Generalized Cape Cod]] | Ultimate is driven by an *a priori* / expected claim ratio blended with actual experience |
| **Specialized / structural** | [[Freq-Sev]], [[Closure Method]], [[Berquist sherman]] | Breakdown claims into components (frequency/severity, closure counts, adjusted settlements) |

The key trade-off: **development methods are most responsive** to recent experience but **most fragile** when assumptions change; **expected-based methods are stable** and dampen the impact of assumption violations.

## Comparison under each changing assumption

### 1. Change in settlement rate (speed-up or slow-down of payments)

| Method                | Paid claims                                                                                                  | Reported claims |
| --------------------- | ------------------------------------------------------------------------------------------------------------ | --------------- |
| [[Chain Ladder]]      | **Over-projects** on speed-up; **under-projects** on slow-down (historical factors assume slower settlement) | **Accurate**    |
| [[BF]] / [[Cape Cod]] | Same direction but **smaller error** then CL (expected weight cushions it)                                   | Accurate        |
| [[Expected method]]   | Error only if the estimated claim ratio is affected; otherwise no impact                                     | No impact       |
| [[Berquist sherman]]  | Adjusts paid data explicitly (fit paid vs closed counts)                                                     | **Accurate**    |

**Best method:** Reported-based development, or any method using reported claims. B-S adjusts for the settlement change when using paid.

### 2. Change in case reserve adequacy

| Method               | Paid claims                           | Reported claims                                                    |
| -------------------- | ------------------------------------- | ------------------------------------------------------------------ |
| [[Chain Ladder]]     | Accurate (paid ignores case strength) | **Overstates** IBNR on increase; understates on decrease           |
| [[BF]]               | Accurate                              | Over/under-estimates but **smaller error** than development method |
| [[Cape Cod]]         | Accurate                              | Over/under-estimates — **larger error than BF**                    |
| [[Expected method]]  | No impact                             | Error only if claim ratio affected; otherwise no impact            |
| [[Berquist sherman]] | Accurate (paid ignores case strength) | Adjusts reported, evaluates tail factor impact                     |

**Best method:** Paid-based development, or paid-based BF for more stability. Use [[Berquist sherman]] when you want to *correct* the reported data rather than avoid it.

### 3. Change in claim ratio (LVL / loss ratio level)

| Method | Response |
| --- | --- |
| [[Chain Ladder]] | Consistent with development; ignores the change in level |
| [[BF]] | **Does not fully react** — heavy expected weight; reported is more precise than paid |
| [[Cape Cod]] | **More responsive than BF** (ECR estimated from data), still not fully reactive |
| [[Expected method]] | **Does not react at all** — claim ratio is fixed → becomes inaccurate |

**Best method:** A development method (reported) is most responsive to a true change in claim ratio. Avoid [[Expected method]]. BF/Cape Cod react only partially.

### 4. Exposure growth

All development and expected methods are **unaffected by exposure growth on its own**. The only issue arises if the *average accident date* changes — then estimates move in the same direction as chain ladder but lower (for BF/Cape Cod/Expected).

**Best method:** Any — exposure growth alone is not a differentiator; watch average accident date shifts.

### 5. Change in mix of business

All methods (development, BF, Cape Cod, Expected) are **impacted** when:
- The changing segments have a **different claim ratio** (acts like a claim-ratio change), or
- The changing segments have the **same claim ratio but a different development pattern**.

For [[Freq-Sev]], mix changes break the *homogeneity* assumption directly.

**Best method:** Segmented analysis is really the answer — no single method fixes a mix shift; reserve by segment.

### 6. Change in inflation / cost level (structural)

| Method | Response |
| --- | --- |
| [[Chain Ladder]] | Assumes inflation has been consistent & stable and will continue — does **not** adjust for calendar-year effects |
| [[Freq-Sev]] | **Best** — trend and inflation assumptions can be directly integrated |
| [[Expected method]] / [[BF]] | Depend on the selected expected claim ratio staying valid |

**Best method:** [[Freq-Sev]] when inflation is the dominant driver, because trend/inflation is an explicit input.

### 7. Immature data / new LOB / no credible history

| Method              | Response                                                           |
| ------------------- | ------------------------------------------------------------------ |
| [[Chain Ladder]]    | **Not usable** — no credible data / unstable recent diagonal       |
| [[Expected method]] | **Best** — a priori estimate when there's not enough credible data |
| [[BF]]              | Good — blends expected with early immature experience              |
| [[Cape Cod]]        | **Not usable** for new LOB (no data to compute ECR)                |
| [[Freq-Sev]]        | **Not usable** — no credible data / unstable recent diagonal       |

**Best method:** [[Expected method]] (most stable), then BF if a little experience exists.

## Quick decision guide

| What changed / situation | Prefer |
| --- | --- |
| Settlement rate changed | Reported-based methods; Berquist-Sherman to adjust paid |
| Case reserve adequacy changed | Paid-based methods; B-S to correct reported |
| Claim ratio level changed | Development (reported) — most responsive; avoid Expected |
| Exposure growth only | Any method (no effect by itself) |
| Mix of business shifting | Segment the data first |
| Inflation / trend dominant | Freq-Sev |
| Immature / new LOB / no data | Expected method, then BF |
| Case adequacy + claim ratio both changed | Paid development (accurate on both); reported overstates |

## Key takeaways

- **Reported claims** are more credible/lower-volatility, but vulnerable to **case reserve adequacy** changes.
- **Paid claims** are immune to case strength changes, but vulnerable to **settlement rate** changes.
- **Expected-based (BF/Cape Cod)** methods trade responsiveness for **stability** — their errors from a broken assumption are smaller than development methods, at the cost of not fully capturing a true change.
- **Freq-Sev** shines when **inflation/trend** matters and breaks when **mix** is not homogeneous.
- **Berquist-Sherman** is the *repair* tool: it adjusts the data to undo the effect of a settlement-rate or case-adequacy change rather than switching methods.
- Bottom line: **choose the method whose key assumptions most plausibly hold** for the scenario, and pair with [[How to select reserving methods]] thinking — no single "best" method exists.
