## What is Jev?

**Jev** is a model from TypeSafe AI (released mid-September 2026) engineered for fast, structured decisions rather than text generation. 

- **Single-pass execution:** Instead of generating tokens one at a time like an LLM, Jev executes in a single pass and returns a typed choice/score along with probabilities.
- **High-speed classification:** Dramatically faster and more cost-efficient for classification-style workflows (e.g., ticket routing, triage, intent classification).
- **Structured output:** Delivers direct typed decisions and confidence scores without requiring complex schema prompt-engineering or autoregressive decoding.

---

## Why is Jev ~100x Faster? (Jev vs. Traditional LLM)

![Jev vs LLM](./image.png)

### Key Takeaways from the Diagram:

- **The Problem / Example:**
  - **User Message:** *"I was charged twice for my subscription and I want my money back"*
  - **Which team?** `(1) Billing` or `(2) Technical`

- **Traditional LLM (e.g., Claude):**
  - Runs in a loop generating output token-by-token sequentially (~40 tokens = ~40 forward passes).
  - Takes more time and increases latency.

- **Jev (Decision Model):**
  - Takes the query and valid options, running in **a single pass (`x1 run`)**.
  - Directly outputs probabilities:
    - `Billing` &rarr; **0.94**
    - `Technical` &rarr; **0.06**
  - Picks the single winning answer directly and runs up to **100x faster**.
