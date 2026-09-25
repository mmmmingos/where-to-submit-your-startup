# Contributing

This is a shared resource for founders. Help keep it useful by adding a site, correcting a detail, or sharing what happened when you tried one. You do not need a success story: a long wait, a confusing form, or a rejected submission can help someone else. Edit [README.md](README.md) and open a pull request, or [open an issue](https://github.com/mmmmingos/where-to-submit-your-startup/issues/new/choose) with your findings.

## Choose the right table

| Section | What belongs here |
| --- | --- |
| [Directories & submission services](README.md#directories--submission-services) | Free and paid directories, company profiles, listings, reviews, and submission services. Use Free? to distinguish pricing. |
| [Reddit communities](README.md#reddit-communities) | Subreddits where founders can share a product under each community's rules. Keep posting limits in Notes. Do not mix these into the directories table. |
| [Regional and specialist options](README.md#regional-and-specialist-options) | Opportunities limited to a region, audience, or purpose, such as beta testing or fundraising. |
| [Reported submission problems](README.md#reported-submission-problems) | Broken submission forms, access failures, closed directories, banned communities, or unrelated redirects. |

Keep each table sorted A–Z. Update an existing entry instead of adding a duplicate. If pricing changes, update Free? and Notes in place. Move an entry only when its scope or submission status belongs in a different table; explain the change in your pull request.

## Use the existing format

### Directories & submission services

Keep the four columns in this order: **Site | Free? | Notes | Last checked**.

Copy this Markdown row and replace every placeholder. Choose one value for Free?: `Yes`, `Yes*`, `No`, or `Unknown`, using the definitions below.

```markdown
| [Site name](SUBMISSION_URL) | Yes | Short submission notes. | YYYY-MM-DD |
```

### Reddit communities

Keep the four columns in this order: **Community | Free? | Notes | Last checked**. Use the same Free? definitions. Link the subreddit; put promo and posting-rule limits in Notes.

```markdown
| [r/Example](https://www.reddit.com/r/example/) | Yes | Short posting-rule notes. | YYYY-MM-DD |
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
- **Free?:** use `Yes` when a free listing path has no material catch. Optional paid upgrades alone are not enough for `Yes*`. Use `No` when payment is required and `Unknown` when free eligibility is unconfirmed. `Yes*` means a free listing path exists, but there is a material catch founders should know (homepage badge, long free queue, niche/geo gate, or paid skip/sponsor). Paid-only stays `No`. Describe any conditions for a free listing, such as a reciprocal link, in Notes. Free and paid entries belong in the same table.
- **Notes:** public Notes are directory facts only (free path and any catch). Write one or two short, factual sentences covering requirements, fees, queue length or other wait the directory itself advertises, regional restrictions, or the observed problem. Do not include a personal launch window, pending-review status, or other submission scheduling. Include currency and one-time versus recurring charges. Label estimates and optional upgrades clearly.
- **Last checked:** use the date you manually reviewed the submission route and terms, in `YYYY-MM-DD` format. Keep the existing date for formatting-only edits or automated link checks.

A free submission does not guarantee acceptance. Do not add DR, dofollow, or traffic claims; the current tables do not assess them.

This is the open-source directory for **Where to Submit Your Startup**, hosted at [submitmystartup.com](https://submitmystartup.com/). The website shares bundles, guides, and my own submission experiences. Reviewed listing details and completed submissions are recorded separately. Do not change Last checked merely because a new traffic report or blog article was published.

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
