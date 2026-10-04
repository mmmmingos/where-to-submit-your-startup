# Where to Submit Your Startup

This plugin helps Claude pick places to submit or launch your startup: directories, launch sites, communities, review sites, and editorial sites. It uses my free list at [submitmystartup.com](https://submitmystartup.com/), where I try places by submitting my own site to them and write down what happened: what it costs and the catch, what the free path needs (an account, a badge, an email on your own domain, upvotes), how long the listing takes to go live, and which products and regions it takes.

It has two parts:

- A skill, `where-to-submit-your-startup`, that tells Claude which questions to ask, how to search the list, and how to present a shortlist honestly, including the facts that aren't on record.
- The SubmitMyStartup MCP connector at `https://submitmystartup.com/mcp`, a read-only server with five tools: `find_directories`, `get_directory`, `list_filters`, `search`, and `fetch`.

## Use it

Ask Claude something like:

- "Where can I submit my B2C web app for free? I'm in Australia and can't add a badge to my site."
- "Is BetaList free? What does a listing need?"
- "Give me Product Hunt alternatives that take developer tools and go live within a week."

Claude asks for anything it needs to know, searches the list, and replies with places that fit, each with its cost, what it needs, the wait, when it was last checked, and a link to its row on my site.

## Install

- Claude Code: `/plugin marketplace add mmmmingos/where-to-submit-your-startup`, then `/plugin install where-to-submit-your-startup@submitmystartup`.
- Claude (web and desktop): add the connector under Customize, then Connectors, then Add custom connector, with the URL above and no sign-in. To add the skill, zip the `skills/where-to-submit-your-startup` folder and upload it as a skill.
- Other agents that read skills: `npx skills add mmmmingos/where-to-submit-your-startup`.

Without the connector, the skill reads the same data from the JSON API at `https://submitmystartup.com/api/v1/`. Setup for ChatGPT and other MCP clients is at [submitmystartup.com/api](https://submitmystartup.com/api/).

## Data

The plugin sends only your search filters (for example the product type, country, and budget) or a place's name to `submitmystartup.com`, and gets back public listing facts. It needs no account or key, and runs nothing on your computer. The server doesn't store your requests; its host, Vercel, keeps ordinary request logs. The list itself is open source under the MIT License in [this repository](https://github.com/mmmmingos/where-to-submit-your-startup).

Directories change their rules, so check a site before you rely on a fact or pay for anything.
