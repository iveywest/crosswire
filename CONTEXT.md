# CrossWire — Reference Context
Created: 2026-07-22
Updated: 2026-07-22 (added Tech + Commanders editions)
Status: LIVE

## What it is
Twice-daily multi-edition briefing service for Ivey. Delivered via RSS to Feedly.
Three editions in one feed, distinguished by title prefix:
- **CrossWire: Hermes** — Hermes Agent ecosystem
- **CrossWire: Tech** — Apple, home automation, technology
- **CrossWire: Commanders** — Washington Commanders football

## Feed URL
https://iveywest.github.io/crosswire/radar.xml

## Schedule
- Morning Brief: 8:30 AM ET daily (cron job: f0941bdbc277)
- Evening Brief: 4:30 PM ET daily (cron job: d0ccd4aac788)
- Both run 7 days a week, all three editions per run

## Data Collection Scripts
- Combined wrapper: ~/.hermes/scripts/crosswire-all.sh (runs all three)
  - crosswire-data.sh — Hermes: GitHub API (releases, issues, PRs, community repos)
  - tech-data.sh — Tech: Apple Newsroom, MacRumors, 9to5Mac, Ars Technica, Home Assistant
  - commanders-data.sh — Commanders: ESPN schedule/standings, NFL news

## Editions & Sections

### CrossWire: Hermes
1. Release Radar — Hermes Agent releases and what they mean for MOCR
2. New Community Builds — repos created this week
3. Gaining Popularity — repos gaining traction
4. Trending on GitHub — interesting issues/PRs with context
5. Worth Reading — blog posts, articles
6. New Tutorials — YouTube videos

### CrossWire: Tech
1. Apple — Newsroom, MacRumors, 9to5Mac headlines
2. Home Automation — Home Assistant, Matter/Thread updates
3. Tech News — Ars Technica, broader tech landscape

### CrossWire: Commanders
1. Games & Schedule — upcoming matchups, results
2. Standings — division rank, record
3. News — NFL headlines, team-specific coverage

## Infrastructure
- Repo: github.com/iveywest/crosswire (public, Pages enabled)
- Combined data script: ~/.hermes/scripts/crosswire-all.sh
- Hermes script: ~/.hermes/scripts/crosswire-data.sh
- Tech script: ~/.hermes/scripts/tech-data.sh
- Commanders script: ~/.hermes/scripts/commanders-data.sh
- Data output injected into cron agent prompt; agent synthesizes into RSS HTML
- Agent also runs web_search for supplementary content
