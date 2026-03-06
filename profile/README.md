# THE ARMORY

Pre-built Claude Code rig templates for AI Captains Academy Gold members. Each template is a fully self-contained multi-agent rig that produces professional marketing deliverables.

## How Templates Work

Each template follows the three-layer rig pattern:

1. **CLAUDE.md** orchestrates the pipeline -- spawning agents, tracking status, enforcing quality gates
2. **Commands** define user-invoked workflows (`/build-funnel`, `/deploy`, `/setup`)
3. **Agents** do the specialized work (research, strategy, copywriting, page building, QA)
4. **Skills** provide domain knowledge that agents load themselves

Members copy a template directory, run `/setup` to configure their branding, then run the primary command to generate deliverables for a client.

## Available Templates

| Template | What It Does | Modes | Deliverables |
|----------|-------------|-------|--------------|
| **lead-getter** | Finds pitch-ready leads in any niche with verified contact info, pain signals, and cold email hooks | **Full**: Enriched leads + hooks + cards. **Quick** (`--quick`): Raw list only. | leads.csv, lead cards (one per lead), run summary, Apify usage log |
| **aeo-audit** | AEO & SEO audit + outreach package for a client website | **Light**: AEO snapshot + cold email. **Full**: 25-35 page branded report. | AEO assessment (the lead), technical SEO, competitor analysis, follow-up email sequence, cover letter |
| **funnel-builder-release** | Generates marketing funnels from a business name + URL | **Light**: Landing page + live site + cold email. **Full**: Complete funnel package. | Landing page copy, lead magnet outline, 5-email sequence, ad copy (3 variants), deployed landing page, client-ready PDF package |
| **content-repurposing** | Turns one piece of content into 8+ platform-ready posts | **Light**: X thread + LinkedIn post + cold email. **Full**: 8 content pieces across all platforms. | X thread, LinkedIn post, IG carousel, email, blog, 3 video scripts, pull quotes, audiograms, cover letter |
| **content-strategy** | Builds a full content strategy from a business URL and social profiles | **Light**: Brand voice doc + 30-day calendar + cold email. **Full**: 90-day calendar + 20 templates + 3 outreach sequences. | Brand voice document, content calendar, platform templates, competitor analysis, outreach sequences, cover letter |
| **email-automation** | Builds complete email marketing systems in a client's voice | **Light**: Email audit snapshot + 3-email welcome sample + cold email. **Full**: 13 deliverables across 5 sequence types. | Welcome sequence, nurture sequence, re-engagement flow, 3 campaign frameworks, newsletter template, subject line swipe file, platform setup guide, cover letter |

## Getting Started

```bash
# 1. Copy a template to your project
cp -r funnel-builder-release/ ~/my-agency/funnel-builder/

# 2. Open the template directory in Claude Code
cd ~/my-agency/funnel-builder/

# 3. Run setup to configure your branding
/setup

# 4. Build a funnel for a client
/build-funnel
```

## Architecture

Based on the SAFe Agentic Workflow pattern (MIT, Bybren LLC) -- a three-layer rig architecture where the orchestrator stays lean by passing file paths (not contents) to sub-agents, and agents read their own instructions and domain knowledge from disk.

### Context Engineering Rules

The orchestrator (CLAUDE.md) never reads agent or skill files. It dispatches work via the Task tool, agents read their own `.md` files and skills, write output to disk, and return only status + file paths. This prevents context window exhaustion during multi-agent pipelines.

Each rig ships with a pre-configured `.claude/settings.local.json` so sub-agents don't trigger permission prompts during runs.

## Attribution

- **Rig architecture**: [SAFe Agentic Workflow](https://github.com/bybren-llc/safe-agentic-workflow) pattern (MIT License, Bybren LLC)
- **Marketing domain knowledge**: Adapted from [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) (MIT License). Copywriting, email sequence, and page CRO skills are adapted and enhanced from that project. Ad copy and landing page HTML skills are custom.
- **Template design**: AI Captains Academy

## License

MIT
