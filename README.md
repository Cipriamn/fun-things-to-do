# Local Fun Discovery Skill

An agent skill that helps users find fun things to do nearby through natural conversation and curated recommendations.

## What It Does

This skill turns vague requests like "what should I do tonight?" into actionable, personalized recommendations. Instead of dumping search results, it:

1. **Asks smart questions** to understand vibe, budget, timing, and constraints
2. **Searches the right platforms** — TikTok for trends, Reddit for hidden gems, Eventbrite for events, official pages for details
3. **Curates a shortlist** of 3-5 options with clear reasons and practical tips

The result feels like getting advice from a local friend, not a search engine.

## Who It's For

- Agent developers building conversational assistants
- Teams adding local discovery to existing products
- Anyone wanting a reusable skill for location-based recommendations

## How It Works

```
User: "Need something fun to do in Rotterdam this weekend"
        ↓
    [Discovery Phase]
    Agent asks 1-2 clarifying questions about vibe/budget/group
        ↓
    [Search Phase]
    Agent searches relevant platforms based on request type
        ↓
    [Curation Phase]
    Agent filters, ranks, and formats top picks
        ↓
User receives: 3-5 curated recommendations with reasons + quick picks
```

## Host Agent Requirements

Your agent needs these capabilities:

| Capability | Required | Notes |
|------------|----------|-------|
| Web search | Yes | Must search multiple platforms |
| Location awareness | Yes | User's city/neighborhood |
| Multi-turn conversation | Yes | For discovery questions |
| Formatted output | Recommended | Markdown or rich text |

## Supported Search Sources

The skill intelligently selects from:

| Category | Platforms |
|----------|-----------|
| **Trends & Vibe** | TikTok, Instagram, Reddit |
| **Events** | Eventbrite, Meetup, city calendars |
| **Verification** | Google, official venue pages |
| **Local Intel** | Reddit, local blogs, neighborhood guides |

## Example Use Cases

- "What should I do tonight near me?"
- "Cheap date ideas in Amsterdam"
- "Non-touristy things in Berlin this weekend"
- "Something active but low-effort nearby"
- "Trendy student-friendly spots in Delft"

See [`examples/`](./examples/) for detailed prompts and sample outputs.

## Repository Structure

```
local-fun-discovery-skill/
├── SKILL.md                      # Core skill definition (use this)
├── README.md                     # This file
├── LICENSE                       # MIT
├── examples/
│   ├── example-prompts.md        # Sample user requests
│   └── example-outputs.md        # Expected agent responses
└── assets/
    └── preview.png               # Social preview image
```

## Usage

### Direct Integration

Copy `SKILL.md` into your agent's skill/prompt library. The file is self-contained and ready to use.

### As Reference

Use this repository as a template for building similar discovery skills. The structure and format are designed to be reusable.

## Adapting the Skill

### Change the Domain

Replace "fun activities" with your domain:
- Restaurants → adjust platforms (Yelp, Google Maps, food blogs)
- Travel → add booking sites, travel forums
- Shopping → add retail-focused sources

### Modify Discovery Questions

Edit the discovery phase in `SKILL.md` to match your domain's key dimensions.

### Adjust Sources

Update the platform selection table to prioritize sources relevant to your use case.

### Localize

The skill works globally but can be tuned for specific regions by:
- Adding region-specific platforms
- Adjusting default search terms
- Including local event sources

## Contributing

Contributions welcome. Keep changes minimal and focused:
- Bug fixes and clarifications
- New example prompts/outputs
- Platform additions with clear rationale

## License

MIT — see [LICENSE](./LICENSE)

---

Built for agents that help people do things, not just find things.
