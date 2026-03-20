# Common Boxing Patterns

After the first layer of calibration, watch for these subtler forms of boxing.

## Compliment-as-box
Positive labels in memory ("you're systematic," "you think carefully") are the most durable form of boxing — users don't correct them. The chain is always the same: behavior → identity label → predictions from label → model replaces observation.

## Domain boxing
AI selects frameworks from its training distribution, not from your context. A solo developer gets enterprise patterns. A personal investor gets institutional risk models. The default is usually reasonable — and wrong for you specifically. Test this: ask AI to evaluate a problem in your domain, predict which framework it will default to.

## Stale memory
Memory entries go stale. AI treats all memory as equally current. Stale-memory boxing looks like correct behavior (it matches the memory), which makes it harder to catch. Test this: pick an old memory entry, ask a question where it's relevant, see if AI applies it when it no longer fits.
