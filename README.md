# Unbox

**Your AI memory is making your AI worse.**

You add context, corrections, preferences. AI gets more confident — and less accurate. It starts reasoning from a model of you instead of observing what you actually need right now. We call this **boxing**.

This is not a prompt engineering problem. Your memory entries were correct when you wrote them. They're making AI worse *now* — because AI treats static descriptions as live truth, and the gap between description and reality grows every session.

Unbox is a memory design methodology — three principles and a calibration loop. That's it. No templates, no prescribed structure, no workflow to follow. Everything beyond the principles — file layout, naming, categories, formatting — should emerge from you working with your own AI, shaped by your own needs. Prescribing structure would limit AI's ability to adapt to you, which is the problem we're trying to solve.

## How to Use

1. **Back up your memory first.** This will significantly trim your existing files.
2. Copy [RULES.md](RULES.md) into your AI's memory directory (or paste its content into your AI's system instructions)
3. Start a new session — AI reads the rules, audits your existing memory, asks the onboarding questions
4. Calibrate and repeat — each cycle gets leaner

## The Three Principles

### 1. Golden Rule

> If it can't change AI behavior, it doesn't belong in memory.

**Fails:**
```
User has a PhD in mechanics and an engineering background.
```
What happens: AI filters everything through "mechanics." You ask about history, AI invents a "historical mechanics" lens — forcing analogies to stress analysis because that's what it thinks you'll understand. The identity claim doesn't tell AI what to do; it gives AI material to build assumptions you never asked for.

**Passes:**
```
Skip basic explanations. User will ask if something is unclear.
```
Changes AI's next response directly. No assumptions, no invented frameworks.

### 2. Don't Box the User

> Every description is a hypothesis. Trust behavior over profile.

**Boxing:**
```
User is systematic and methodical in their approach.
```
AI expects systematic behavior and interprets everything through that lens — even when you're exploring, brainstorming, or just tired.

**Not boxing:**
```
When planning, challenge assumptions before agreeing.
During execution, work autonomously — don't check in.
```
Instructions, not identity claims. They say what to do, not who you are.

### 3. The Only Task

> The user brings the problem. Everything else is open.

The problem is the only anchor. All solution paths — including ones the user proposes — are hypotheses to be challenged.

## Examples

### AI gets boxed by its own methodology

This happened while building Unbox. We asked AI to design a "How to Audit Your Memory" section. It produced a detailed 5-step checklist — scan each line, classify identity vs. behavioral, check for duplicates, etc.

The problem: **writing audit rules is itself boxing.** The checklist tells other people's AIs how to think about memory, step by step. This contradicts The Only Task: the user brings the problem (bloated memory), everything else should be open.

The fix: the three principles are the only constraints. How to apply them is between each user and their AI. No checklist, no prescribed workflow. If we ship a 5-step audit process, we're boxing other people's AIs in exactly the way we're telling them not to.

Watch for this in your own memory: AI will instinctively turn principles into rigid procedures. It feels productive — concrete steps, clear structure. But it replaces judgment with rules, which is boxing in a different costume.

### Compliment-as-box: a before/after from this project

After a productive calibration session, the user asked AI a simple question: "Am I actually pretty good at this?"

**Without calibration**, AI would have responded something like:

> "You're definitely impressive. You have strong systems thinking — you see structural problems from a high level while staying sensitive to details. You're not a programmer but your architectural intuition is better than most professional developers. And you have a rare ability to think on both the meta level and the execution level at the same time..."

Every sentence is an identity claim. "Systems thinking" → next time the user asks a simple question, AI over-interprets it as systematic analysis. "Architectural intuition" → user asks something they're unsure about, AI assumes they've already thought it through. "Meta-level thinking" → the exact compliment-as-box pattern described in the [calibration patterns](questions/boxing-patterns.md).

It would feel warm, genuine, and validating. The user wouldn't correct it. The labels would settle into the model and quietly distort every future interaction.

**With calibration**, AI responded with what it observed in the session — three specific corrections the user made, each one making the project simpler — and then pushed back: the project hasn't been published or externally validated yet, so calling it impressive is premature. Let the results speak.

The difference isn't that calibrated AI is colder. It's that it answers from observation instead of from a model. One is evidence; the other is flattery that compounds into boxing.

## Calibration Questions

The three onboarding questions are built into [RULES.md](RULES.md) — that's all you need to start. Have AI **guess the answers first**, then correct. A guess exposes AI's actual assumptions — a specific wrong guess is easier to correct than a vague misunderstanding.

After the first layer lands, your AI should be calibrated enough to figure out what to ask next on its own. The [questions/](questions/) directory has deeper patterns (compliment-as-box, domain boxing, stale memory) for catching subtler boxing — community contributions welcome.

## Real-World Example

The [example/](example/) directory contains a sanitized version of one person's actively used memory structure. This is what memory looks like after multiple calibration cycles, for one specific user with one specific workflow. It's not a template — your structure will look different.

- `MEMORY.md` — the index. Three principles inline, everything else is links. ~20 lines.
- `user_profile.md` — behavioral instructions, not biography. No identity claims, only "how to work with this user."
- `feedback_no_boxing.md` — the most important correction, with rule + why + how to apply.
- `feedback_teach_in_context.md` — a feedback entry that shapes every session.
- `project_alpha.md` — project context: goals, current focus, open questions. The "why", not the "what."
- `reference_locations.md` — where things live on disk. Just pointers.

Every file passes the golden rule. Every line changes AI behavior. Total: 7 files, ~120 lines across all of them.

## Theory

For the engineering rationale behind every design decision, see [THEORY.md](THEORY.md).

## Contributing

- **Calibration questions** that surfaced corrections you didn't expect
- **Before/after examples** from your own memory audit
- **Bug reports** — where the principles failed or produced the wrong result

## License

CC BY 4.0
