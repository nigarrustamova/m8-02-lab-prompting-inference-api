# Prompts & Bake-off Notes

Record the exact prompts you used and your verdict here. This file is graded.

## Task 2 — Prompt-pattern bake-off

### Zero-shot prompt

```
Classify this ticket: {text}
Label:
```

### Few-shot prompt

```
Classify the following tickets:
Ticket: I can't log in to my account.
Label: bug
Ticket: How much does the pro plan cost?
Label: billing
Ticket: I would like to have a feature to export to PDF.
Label: feature_request
Ticket: {text}
Label:
```

### Chain-of-thought / decomposition prompt

```
Classify this ticket: {text}
Explain your reasoning briefly, then provide the label in the format 'Label: <label>'.
```

### Verdict (3–4 sentences)

> Few-shot and Chain-of-Thought (CoT) patterns generally performed better than Zero-shot. Few-shot provided clear format guidance, reducing ambiguity for the model. CoT was particularly useful for complex tickets where the reasoning step helped the model correctly identify nuanced 'other' vs 'bug' cases, though for simple tickets, Zero-shot was often sufficient and more efficient.

## Task 3 — Structured output notes

> Gemini 2.0 Flash produced valid JSON 100% of the time when using the official structured output mode. For local Ollama models, I included validation logic to catch malformed JSON and fall back to a default 'other' label if parsing failed, ensuring the application remains robust even with less capable models.
