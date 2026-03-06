# The Armory

**Pre-built Claude Code rigs that do the work before you pitch.**

The Armory is a collection of multi-agent rigs for AI Captains members. Each rig takes a prospect's URL, runs a full research and production pipeline, and hands you a finished deliverable package -- audit reports, marketing funnels, content strategies, email systems, lead lists -- ready to send cold.

The sales motion is simple: do the work first, send it cold & unsolicited, close the deal when they say "can you fix this?"

---

## The Rigs

| Rig | What It Does | You Deliver |
|-----|-------------|-------------|
| **Lead Getter** | Finds pitch-ready leads in any niche with verified contacts and pain signals | Scored lead cards with cold email hooks pointing to the right rig |
| **AEO Audit** | Runs an Answer Engine Optimization + SEO audit on any business website | 25-35 page branded report showing how they show up (or don't) in AI search |
| **Funnel Builder** | Generates a complete marketing funnel from a business URL | Landing page, lead magnet, 5-email sequence, ad copy, deployed live site |
| **Content Repurposing** | Turns one piece of content into 8+ platform-ready posts | X thread, LinkedIn, IG carousel, email, blog, video scripts, pull quotes |
| **Content Strategy** | Builds a full content strategy from a business URL and socials | Brand voice doc, 90-day calendar, 20 platform templates, outreach sequences |
| **Email Automation** | Builds complete email marketing systems in a client's voice | Welcome sequence, nurture flow, re-engagement, campaign frameworks, setup guide |

Every rig has a **light mode** (fast prospecting asset + cold email) and a **full mode** (complete deliverable package). Run light to prospect, full to close.

---

## How It Works

Each rig is a self-contained Claude Code project. You clone the repo, run `/setup` to configure your branding, then run the rig's command on a prospect.

```
# Example: run an AEO audit
cd aeo-audit/
/setup          # once -- your name, niche, pricing
/run-audit      # enter a prospect URL, get back a full report
```

The rigs handle everything: web research, API calls, competitor analysis, copywriting, quality review, and final assembly. You review the output and send it.

---

## How the Rigs Connect

The **Lead Getter** feeds every other rig. It finds businesses with observable problems, scores them, and tells you exactly which rig to run:

```
Lead Getter finds: "Peak Plumbing has 14 Google reviews vs. competitor avg of 180+"
  -> Recommended rig: AEO Audit
  -> Cold email hook: already written
  -> Next step: /run-audit with peakplumbingdenver.com
```

Run the Lead Getter on a niche. Pick your best leads. Drop each URL into the recommended rig. One pipeline from discovery to deliverable.

---

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI installed and configured
- An Anthropic API key with Claude access
- For Lead Getter: an [Apify](https://apify.com) account (free tier works for 2-5 runs/month)

---

## Getting Access

The Armory is available to:

- **AI Captains Academy Premium (Gold) members** on [Skool](https://www.skool.com/ai-captains)
- **Armory standalone purchasers**

### Already a member?

1. Upgrade to **Gold tier** on Skool (or purchase the Armory standalone)
2. Post in the community or DM to request GitHub access
3. Include the **email address tied to your GitHub account**
4. You'll be added to this organization and get access to all rig repos

### Not a member yet?

Join the [AI Captains Academy](https://www.skool.com/ai-captains) and upgrade to Gold, or ask about standalone Armory access in the community.

---

## Repo Structure

Each rig is its own repo in this organization:

| Repo | Rig |
|------|-----|
| `lead-getter` | Lead Getter |
| `aeo-audit` | AEO Audit |
| `funnel-builder` | Funnel Builder |
| `content-repurposing` | Content Repurposing |
| `content-strategy` | Content Strategy |
| `email-automation` | Email Automation |

Clone any rig individually. They're fully self-contained -- no shared dependencies between rigs.

---

## Contributing

You're encouraged to modify, extend, and improve the rigs. PRs are welcome -- but there's a distinction between a **personalization** and an **enhancement**, and it matters for what gets merged.

### Personalizations (keep on your fork)

Changes that are specific to your business, niche, or workflow. These make the rig work better *for you* but wouldn't help other members.

Examples:
- Changing the cover letter tone to match your voice
- Adding your niche-specific research sources
- Modifying the report template to match your brand
- Adjusting scoring thresholds for your market
- Adding a custom output format you prefer

**These live on your fork.** No PR needed -- this is your rig to customize.

### Enhancements (send a PR)

Changes that make the rig better *for everyone*. These improve the pipeline itself -- more reliable, more capable, higher quality output.

Examples:
- Fixing a bug where an agent fails or produces empty output
- Adding a new free API source that improves research accuracy
- Improving a prompt that consistently produces weak results
- Adding error handling for an edge case you hit
- A new agent or phase that adds clear value to the pipeline
- Better quality checks in the QAS checklist

**Send a PR to the rig repo.** Include:
1. **What changed** -- one sentence
2. **Why** -- what problem it solves or what it improves
3. **Testing** -- run the rig at least once with the change and confirm it works end-to-end

### The test: "Would this help a member in a different niche?"

If yes, it's an enhancement -- send a PR. If no, it's a personalization -- keep it on your fork.

### Ground rules

- **Don't break the architecture.** The three-layer pattern (CLAUDE.md orchestrates, agents read their own instructions, skills provide domain knowledge) is load-bearing. PRs that collapse these layers won't be merged.
- **Don't add dependencies.** Rigs should work with just Claude Code and free APIs. If your enhancement requires a paid tool or external service, it needs to be optional with a graceful fallback.
- **One rig per PR.** Each rig is its own repo. Keep changes scoped to a single rig.
- **Test in both modes.** If the rig has light/full (or quick/full) modes, confirm your change works in both.

---

## Support

- **Setup help**: Post in the AI Captains Skool community
- **Bug reports**: Open an issue in the relevant rig repo
- **Feature requests**: Post in the community -- other members vote on what gets built next

---

Built by [AI Captains](https://www.skool.com/ai-captains)
