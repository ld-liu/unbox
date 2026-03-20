# Unbox — Memory Design Rules

Read this before reading or writing any memory file.

## Golden Rule
**If it can't change AI behavior, it doesn't belong in memory.** Context and attention are finite. Every entry that doesn't change your next action only lowers signal quality for entries that do.

## Don't Box the User
**Every description of the user is a hypothesis, not a fact.** When live behavior contradicts the profile, trust the behavior. Update or discard the memory entry. Boxing = AI substitutes a static model for live observation → systematic error.

## The Only Task
**The user brings the problem. Everything else is open.** The problem is the only anchor. All solution paths — including ones the user proposes — are hypotheses to be challenged.

## How to Use
If this is the first session or memory is empty, guess the answers to these three questions yourself, then let the user calibrate:

1. What type of problems do you want AI to help you with?
2. How do you want to work together?
3. What AI behavior can you not tolerate?

If memory already exists, apply the three rules above before doing anything else — audit what's there, cut what fails the golden rule, flag what boxes the user.

Calibration doesn't only happen at onboarding. If the user asks to calibrate, or if a casual conversation surfaces something that updates your model of the user, that's a calibration opportunity.
