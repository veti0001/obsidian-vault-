## Why |

- Actuaries mostly work with aggregated data

## Types of Aggregation |

### Calendar Year |

- **Definition:** Aggregate all transactions happening in a given year regardless of the effective date of the underlying policy or when the events giving rise to the claims occurred
- **Usage:** Accounting, financial reporting, and other management purposes
- **Advantages:** 
	- Readily available from financial systems
	- Useful for diagnosing operational/environmental changes
- **Disadvantages:** 
	- Poor indicator of pricing adequacy
	- Misaligned with risk period → not used for unpaid claim estimation
- **Actuary Usage:**
    - CY data is _not_ appropriate for projecting ultimate's but is valuable for understanding shifts in operations or claims handling.

### Accident Year |

- **Definition:** All claims from accidents occurring in the same year, regardless of report date. (emphasis on losses)
- **Advantages:** 
	- Faster availability than PY
	- Aligns losses with period of risk
- **Disadvantages:** 
	- Earned premium mismatch with CY premium
- **Actuary Usage:**
    - Most common aggregation pattern
    - Typically used with CY earned premium to estimate unpaid claims
- **Actuarial Implication:** AY balances timeliness and risk alignment → preferred for unpaid claim estimation.

### Policy (UW) Year Aggregation |

- **Definition:** All claims associated with policies that are effective during the calendar year are combined (emphasis on exposure)
- **Advantages:** Precise match of premium and claims
- **Disadvantages:** Slow emergence (extends across two CYs)
- **Actuary Usage:** Typically used with PY earned premium to estimate unpaid claims
- **Actuarial Implication:** Best for pricing studies; less practical for timely reserving.

### Report Year Aggregation |

- **Definition:** All claims reported in a year are aggregated together
- **Advantages:** None
- **Disadvantages:** Does not capture IBNR
- **Actuary Usage:** Used with claims-made coverage
- **Actuarial Implication:** Only useful when reporting triggers coverage (e.g., claims‑made liability).