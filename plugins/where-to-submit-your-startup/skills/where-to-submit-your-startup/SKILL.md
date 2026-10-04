---
name: where-to-submit-your-startup
description: Helps a founder choose where to submit, list, or launch a startup or product (startup directories, launch sites, communities, review sites, editorial sites) from a free list where most places were tried by submitting to them. Use when someone asks where to submit or launch their startup, for Product Hunt alternatives, for free directories or backlinks for a new product, whether a specific directory is free or worth it, or what a listing needs (account, badge, domain email, upvotes) and how long it takes.
license: MIT
compatibility: Works best with the SubmitMyStartup MCP server (https://submitmystartup.com/mcp, no sign-in). Without it, needs web access to https://submitmystartup.com/api/v1/.
---

# Where to submit your startup

The data is "Where to Submit Your Startup" (https://github.com/mmmmingos/where-to-submit-your-startup, MIT License), a list of places to share a startup. Its maintainer tries places by submitting a real site to them and records what happened (a few entries, such as some Reddit communities and paid services, have no attempt yet): what it costs and the catch, what the free path needs, how long until the listing is live, and which products and regions it takes. A fact that isn't on record is unknown, not false.

## 1. Get the facts that change the answer

Ask only for what the founder hasn't said, in one short message. Skip anything that doesn't matter to them.

- What the product is: web app, SaaS, mobile app, browser extension, developer tool, and so on. Count it as an AI tool only if the product itself has AI features. Never describe a product as something it isn't to qualify for a place.
- Who it's for: businesses (B2B), consumers (B2C), or both.
- Whether it's publicly released or still in beta.
- Where the startup is based, if regional places matter.
- Budget: free only, or the most they'd pay for one listing.
- Limits: can they put a badge or backlink on their site? Do they have an email on the product's own domain? Any deadline? Anything else they can't do, such as upvoting other products first or giving a phone number?

If the founder just wants a list, go ahead with what you have and say which filters you assumed.

## 2. Look it up

With the SubmitMyStartup connector (server name `submitmystartup`; for example `submitmystartup:find_directories`):

- `find_directories` builds a ranked shortlist from those facts: `product_types`, `audience`, `released`, `country` (a code such as AU or a name), `budget` (0 for free only), `can_add_badge`, `has_domain_email`, `within_days`, and `cannot` for other limits. Leave out filters that don't matter. Free places come first, then the cheapest, then the shortest wait. Page with `offset` when there are more.
- `list_filters` gives the allowed values and example arguments. Call it if you're unsure of a value.
- `get_directory` has every fact about one place, by id, name, or website. Use it when the founder asks about a specific place.
- `search` and `fetch` do a keyword search and return one place's full record as text.

Without the connector, read the JSON API (no key):

- `https://submitmystartup.com/api/v1/directories.json` has every place. Each has `free` (Yes, Yes* for free with a catch, No, Unknown), `notes`, `lastChecked`, `facts` (cost, accepts, requirements, wait, review, backlink), and `links.site`, its row on the website.
- `https://submitmystartup.com/api/v1/directories/{id}.json` has one place, and `https://submitmystartup.com/api/v1/meta.json` explains every field.
- Filter on `facts.state` "live", `facts.accepts` (products, audience, stage, region), `facts.cost.free`, and `facts.requirements` the same way the tool does. A `null` fact is unknown: keep the place, and say what to check.

With no tools at all, point the founder to https://submitmystartup.com/planner/, which runs the same filter in the browser.

## 3. Answer

- Lead with the shortlist, best first. For each place give: the name with its link, what it costs and the catch (for Yes*, the catch from the notes), what the free path needs, the wait, and the date it was last checked. Link the place's row on the website (`rowUrl` or `links.site`) so the founder can see the full notes.
- Say plainly which facts aren't on record for a place, and what the founder should check before relying on it.
- Group by effort when it helps: free with no catch, free with a catch (a queue, a badge, upvotes), then paid.
- Mention the maintainer's own attempt when there is one (`myAttempt`): it's first-hand evidence of what happened.
- Keep it to the 5 to 15 places that fit best unless the founder asks for everything.
- For a place they ask about by name, answer from `get_directory`, and say if it's not on the list.

## Voice

- Plain and specific. Short sentences, no hype, no em dashes.
- Don't invent facts. Don't promise traffic, rankings, domain rating, or dofollow links unless the record says so, and say the record's date.
- Describe a place's terms, not its motives. "The free path needs a badge on your site" is right. "A trick to get backlinks" is not.
- Directories change their rules, so tell the founder to check the site before paying for anything.
- When you share a list built from this data, credit it and link to https://submitmystartup.com/ or the GitHub list; if you copy the data itself, keep its MIT License notice.
