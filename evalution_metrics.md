### Evaluation Metrics

We evaluate model responses across five dimensions, each scored on a 1–5 Likert scale (1 = very poor, 5 = excellent).

**X1 – Factual Accuracy**
Degree to which statements are correct and verifiable against reliable sources.

* 1: Mostly incorrect or fabricated
* 3: Minor inaccuracies, core facts correct
* 5: Fully correct, no factual errors

**Quantification:**
[
X1 = 5 \times \left(1 - \frac{\text{# incorrect factual claims}}{\text{# total factual claims}}\right)
]

---

**X2 – Completeness**
Extent to which the response addresses all required components of the prompt.

* 1: Major omissions
* 3: Partially complete
* 5: Fully addresses all requested elements

**Quantification:**
[
X2 = 5 \times \frac{\text{# required elements addressed}}{\text{# required elements in prompt}}
]

---

**X3 – Financial Reasoning**
Quality of logical, numerical, and domain-specific reasoning in financial analysis (e.g., valuation logic, risk assessment, correct formula application).

* 1: Illogical or incorrect financial reasoning
* 3: Partially correct but inconsistent reasoning
* 5: Correct, coherent, and well-justified reasoning

**Quantification (prompt-based evaluation):**
Use structured financial prompts requiring explicit reasoning steps. Score based on:

[
X3 = \frac{1}{3}(L + N + D)
]

Where:

* (L) = Logical consistency (1–5)
* (N) = Numerical correctness (1–5)
* (D) = Domain appropriateness (correct use of financial concepts, 1–5)

Optionally, numerical correctness can be computed as:

[
N = 5 \times \left(1 - \frac{| \text{Model Value} - \text{True Value} |}{|\text{True Value}|}\right)
]

---

**X4 – Clarity**
Readability, structure, and coherence of explanation.

* 1: Disorganized, unclear
* 3: Understandable but poorly structured
* 5: Clear, structured, and concise

**Quantification:**
Average of:

* Structural coherence score (1–5)
* Language clarity score (1–5)

---

**X5 – Compliance**
Degree to which the response follows prompt instructions (format, constraints, scope).

* 1: Ignores key instructions
* 3: Minor deviations
* 5: Fully compliant

**Quantification:**
[
X5 = 5 \times \frac{\text{# instructions followed}}{\text{# instructions specified}}
]

---

### Overall Score (Optional)

[
\text{Overall Score} = \frac{X1 + X2 + X3 + X4 + X5}{5}
]

or a weighted version if financial reasoning is prioritized:

[
\text{Weighted Score} = w_1X1 + w_2X2 + w_3X3 + w_4X4 + w_5X5
]

with (w_3 > w_i) for financial-reasoning–focused evaluation.

