# Contributing

Help keep the list useful by adding a site, correcting its details, or reporting a submission problem. Edit [README.md](README.md) and open a pull request, or [open an issue](https://github.com/mmmmingos/where-to-submit-your-startup/issues/new/choose) with your findings.

## Choose the right table

| Section | What belongs here |
| --- | --- |
| [Directories & submission services](README.md#directories--submission-services) | Free and paid directories, company profiles, listings, reviews, Reddit communities, and submission services. Use Free? to distinguish pricing; put posting-rule limits in Notes. |
| [Regional and specialist options](README.md#regional-and-specialist-options) | Opportunities limited to a region, audience, or purpose, such as beta testing or fundraising. |
| [Reported submission problems](README.md#reported-submission-problems) | Broken submission forms, access failures, closed directories, or unrelated redirects. |

Keep each table sorted A–Z. Update an existing entry instead of adding a duplicate. If pricing changes, update Free? and Notes in place. Move an entry only when its scope or submission status belongs in a different table; explain the change in your pull request.

## Use the existing format

### Directories & submission services

Keep the four columns in this order: **Site | Free? | Notes | Last checked**.

Copy this Markdown row and replace every placeholder. Choose one value for Free? using the definitions below.

```markdown
| [Site name](SUBMISSION_URL) | Yes | Short submission notes. | YYYY-MM-DD |
```

### Other options and reported problems

Both tables use **Site | Notes | Last checked**, with Notes in the second column.

Add this HTML row inside the relevant `<tbody>`. Keep the existing `<thead>`, the Notes header's `width="9999"`, and the date cell's `nowrap` attribute so the tables retain their layout.

```html
<tr><td><a href="SITE_OR_SUBMISSION_URL">Site name</a></td><td>Short notes about the service, eligibility, or problem.</td><td nowrap>YYYY-MM-DD</td></tr>
```

Use HTML links inside these rows, not Markdown links. Escape `&` as `&amp;` and `<` as `&lt;` in text.

## Fill in the fields

- **Site name:** always link it. Prefer the direct submission page or official instructions. If only the homepage is available, say so in Notes. For reported problems, link the affected site or page.
- **Free?:** use `Yes` when basic submission or listing is free, even if optional upgrades exist. Use `No` when payment is required and `Unknown` when free eligibility is unconfirmed. Describe any conditions for a free listing, such as a reciprocal link, in Notes. Free and paid entries belong in the same table.
- **Notes:** write one or two short, factual sentences covering requirements, fees, wait times, regional restrictions, or the observed problem. Include currency and one-time versus recurring charges. Label estimates and optional upgrades clearly.
- **Last checked:** use the date you manually reviewed the submission route and terms, in `YYYY-MM-DD` format. Keep the existing date for formatting-only edits or automated link checks.

A free submission does not guarantee acceptance. Do not add DR, dofollow, or traffic claims; the current tables do not assess them.

This is the open-source directory for **Where to Submit Your Startup**, hosted at [submitmystartup.com](https://submitmystartup.com/). The website's bundles and field notes keep the maintainer's submission results separate from these source facts. Do not change Last checked merely because a new traffic report or blog article was published.

## Include evidence

Link official submission instructions, pricing, or eligibility rules in your pull request. Add a source in Notes when the site's main link does not support a material claim.

Say whether you read public instructions, opened the form, or completed a submission. For errors, include the affected URL, date, and observed message or screenshot. A temporary failure does not prove a site has permanently closed.

Mark missing information explicitly rather than guessing. Disclose if you own, work for, or earn commission from the site.

## Before submitting

- Check that the entry is in the right table and alphabetical position.
- Confirm the site name is linked and every placeholder is replaced.
- Preview the README to check column order, links, and formatting.
- Include sources and preserve review dates unless you performed a new manual review.

GitHub Actions runs lychee on README.md and CONTRIBUTING.md weekly and when either file changes. It checks URL availability, not pricing or submission eligibility. You can also run it locally after installing lychee:

```sh
lychee --config lychee.toml README.md CONTRIBUTING.md
```

Review the Actions summary or its `link-check-report` artifact. URLs excluded in [lychee.toml](lychee.toml) are not tested. Investigate failures before adding an exclusion; any exception must identify the exact affected URL, the date, and the reason, and unresolved availability should be clear in the entry.
