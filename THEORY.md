# Why We Think It Works

Engineering rationale behind the three principles. Not a paper — just the reasoning so you can judge the design yourself and adapt it. This is based on one user's experience with multiple calibration cycles, supported by existing research on context effects in LLMs.

## Boxing: A User-Side Pattern

Sycophancy, anchoring bias, filter bubbles, and Theory of Mind failure in LLMs are studied as separate problems with different mechanisms at the model level. From the user's side, they share a common surface pattern:

**AI builds a model from descriptions → reasons from the model instead of observing → systematic error.**

- **Sycophancy** = boxing on preferences. AI locks in what it thinks you want to hear.
- **Anchoring** = boxing on first impressions. Early info gets stuck, later corrections don't fully override it.
- **ToM failure** = boxing on predicted mental states. AI guesses what you know from the model, not from what you're actually saying.
- **Filter bubbles** = boxing as a feedback loop. The model narrows what AI shows you, which narrows the signal that updates the model.

Whether these share a deeper mechanism is an open question. What matters for this project: from the user's side, they look the same and have the same fix — treat every description as a hypothesis, update or discard when behavior contradicts it.

The intervention point is memory design, not model design. Training-side fixes are improving, but you don't need to wait for them. You can fix what goes into your memory files now.

## Why the Golden Rule Works

> If it can't change AI behavior, it doesn't belong in memory.

AI's context window has a fixed attention budget. Every memory entry competes for it. An entry with zero behavioral signal — an identity claim, a derivable fact, a compliment disguised as observation — eats budget without contributing. Worse: research shows irrelevant context actively degrades output quality (Shi et al. 2023), and LLMs underutilize information in long contexts (Liu et al. 2024, "Lost in the Middle").

More memory ≠ better AI. Leaner memory = less noise = each remaining entry gets more attention = better behavior.

The golden rule isn't minimalism for aesthetics. It's a signal-to-noise constraint.

## Why Guess-Then-Calibrate Works

AI has a hidden model of you. In normal conversation, you can't see it — AI generates plausible responses that may or may not reflect its actual assumptions. You can't tell "AI understood correctly" from "AI produced a reasonable-sounding answer from a wrong model."

Asking AI to **guess** something you already know the answer to forces the model into the open. A specific wrong guess is:
- Easier to spot than a vague misunderstanding
- Easier to correct than a hedged response
- Self-verifying — you can immediately check if the correction landed

One round does three things at once: exposes the assumption, corrects it, confirms the correction. That's why it's more efficient than open-ended conversation.

## Why Calibration Should Compound

Each session is a round. Memory is what carries between rounds.

In a one-off conversation, boxing is fine — AI builds a quick model, gets through the session, no consequences. With persistent memory, errors compound: a wrong assumption in memory produces wrong behavior next session, which produces more wrong assumptions, and the model drifts further from reality.

Calibration reverses this. Each cycle either finds an error (which gets fixed) or finds no errors (convergence). It shouldn't regress because corrections are human-validated. In our experience, early cycles produce big corrections; later cycles produce small refinements.

The system doesn't need perfect initial design. Any starting state that's close enough should converge. The first cycle feels rough — roughness is expected and self-correcting.

## References

- Liu et al. 2024. "Lost in the Middle: How Language Models Use Long Contexts." TACL.
- Shi et al. 2023. "Large Language Models Can Be Easily Distracted by Irrelevant Context." ICML.
- Co-Alignment (2025). arxiv.org/html/2509.12179v5
- Decision-Theoretic Framework for Agent Memory. arxiv.org/html/2512.21567v1
