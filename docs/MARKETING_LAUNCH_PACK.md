# TrustLayer Marketing (A→Z) — Traffic that actually works for infra APIs

## What RapidAPI is (and isn’t)
RapidAPI is great for billing + subscriptions. It is **not** a guaranteed discovery engine.
Traffic comes from GitHub + integrations + communities.

## Week 1: Make TrustLayer discoverable
1) Create a public GitHub repo (or mirror) called `trustlayer-ai`
2) Add:
   - README with 60-second quickstart
   - examples (curl + node + python)
   - Postman collection
3) Add a benchmarks folder: "OWASP LLM Top 10 prompts"

## Week 2: Integrations (this is how infra wins)
Publish 3 tiny integration repos:
- trustlayer-langchain-middleware
- trustlayer-crewai-guard
- trustlayer-vercel-ai-sdk

Each repo should have a 10-line snippet + link back to RapidAPI.

## Week 3: Show HN launch
Title:
Show HN: TrustLayer — universal AI safety control plane (tool-hijack + drift kill switch)

Body: explain:
- agent tool hijack is the new prompt injection
- TrustLayer enforces safety policies across any model
- includes CI gate + incident lockdown

## Week 4: Outreach that converts
Message 30 agent startups:
“I’ll run a free agent tool-hijack audit on your workflow and show you the risks in 15 minutes.”

## Ongoing
- Post 1 “attack of the week” screenshot (prompt → verdict → why it was blocked)
- Add 1 new benchmark case weekly
- Maintain changelog releases on GitHub

## KPI to focus on
Not website visitors.
The KPI is: “how many devs integrated TrustLayer into CI?”

