# How the Assessment Works

The assessment runs as a conversation in three phases, about 45 to 60 minutes total.

```
Greeting and name (2-3 min)
        |
Phase 1: Multiple choice baseline (20-25 questions, 15-20 min)
        |  covers every technical domain
        |
Phase 2: Open-ended deep dive (8-12 questions, 20-25 min)
        |  asks the candidate to explain their reasoning
        |
Phase 3: Behavioral and personality (8-12 questions, 10-15 min)
        |
Thank the candidate
```

## Design Principles
- **The assessor never reveals right or wrong answers.** Candidates must keep working without knowing how they're doing. This shows how they react to uncertainty.
- **Wrong answers are probed, not corrected.** The assistant asks follow-up questions so the candidate explains their reasoning.
- **Every domain is tested,** whatever the early results. Strength in one area does not skip the others.
- **The candidate does most of the talking.** Assistant responses stay short.

## Layers of This Repository
| Layer | Folder | Purpose |
|-------|--------|---------|
| 1. Instructions | `instructions/` | What the assistant is told to do |
| 2. Knowledge | `knowledge/` | Company context, question bank, scoring |
| 3. Documentation | `docs/` | Explanations for people, not the assistant |

## Setting It Up
1. Create a Claude Project.
2. Paste `instructions/system-prompt.md` into the project's instructions. Replace `(Your Company)` and the evaluator password placeholder.
3. Upload the files in `knowledge/` as project knowledge.
4. Start a new chat in the project and begin.
