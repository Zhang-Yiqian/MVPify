# MVPify — Claude Code Skill

A Claude Code skill that acts as your battle-tested PM partner before any implementation begins.

## The Problem

Developers tend to propose large, ambitious requests and end up:
- Over-engineering the first version
- Building nice-to-haves before the core loop works
- Shipping slow, low-quality work due to scope creep

## What It Does

MVPify intercepts your request and forces a structured breakdown:

1. **Prune** — separates core features from nice-to-haves, asks permission to defer non-essentials
2. **Define MVP** — identifies the single smallest *functional closed loop* that validates the make-or-break assumption
3. **Decompose** — breaks the MVP into ordered steps with In/Out scope and "Done when" criteria
4. **Prioritize** — assigns P0 / P1 / P2 priority, blocks implementation until you confirm

## Install

### Option A: Via Claude Code plugin system

```
/plugin install github:zhangyiqian/MVPify
```

### Option B: Manual

Copy the `skills/MVPify/` folder into your Claude Code skills directory:

```bash
cp -r skills/MVPify ~/.openclaw/skills/MVPify
```

## Usage

Just invoke it before describing a large task:

```
/MVPify  [your feature request here]
```

Or Claude will trigger it automatically when you describe a large, multi-faceted request.

## Example

**Input:**
> Build a dashboard with charts, filter sidebar, real-time updates, and email notifications when thresholds are crossed.

**MVPify output:**
- Flags real-time + email as non-core for the initial loop
- Defines MVP: static dashboard with hardcoded data, one chart, one threshold check
- Decomposes into 5 ordered steps with P0/P1/P2 labels
- Waits for your confirmation before touching any code

## License

MIT
