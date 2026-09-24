# Contributing

Add entries directly to the README. Keep notes short, practical, and supported by sources.

## Add or update an entry

1. Review the submission route, eligibility, and current fees.
2. Add free directories and company-profile sites to the A–Z Directories table. Place paid services and regional or specialist opportunities in the corresponding Other options table. Record access or submission failures under Reported submission problems.
3. Link the directory name to its submission page or official instructions. If only a homepage is available, say so in Notes. Add source links in Notes for pricing or requirements not covered by the main link.
4. Use the date you reviewed the entry. Do not refresh Last checked for copy edits or automated HTTP checks.
5. Open a pull request with your sources and disclose any relationship to the site.

Copy this row for the main table, replacing the placeholders:

```markdown
| [Directory name](SUBMISSION_URL) | Yes / Conditional / Unknown | Submission requirements, wait time, and any limitations. | YYYY-MM-DD |
```

Use this row for the three-column tables:

```markdown
| [Site name](SOURCE_URL) | Relevant service, eligibility, or recorded problem. | YYYY-MM-DD |
```

## Free eligibility

- **Yes:** a basic submission or listing is free. Optional paid promotion, normal account registration, and editorial approval do not make it Conditional.
- **Conditional:** a free listing requires something extra, such as a reciprocal link. Explain the condition.
- **Unknown:** current free eligibility has not been established. Describe what still needs checking.

If payment is required, use the Paid services table. Regional restrictions or a specialist audience belong under Regional and specialist options; they do not make a site broken.

## Evidence

- **Fees:** link the current pricing or submission page. Include currency and whether the charge is one-time or recurring. Identify optional upgrades separately.
- **Queues:** cite the publisher's estimate or label a dated contributor report. Do not present a reported wait as a guarantee.
- **Availability:** distinguish reading public instructions, opening a form, and completing a submission. Record login or bot-protection barriers accurately.
- **Problems:** provide the affected URL and a dated observation or screenshot. One failed request is not proof that the site is permanently closed.
- **Missing sources:** label gaps explicitly. Existing unsourced review notes are not a precedent for adding unsupported claims.

## Link checks

GitHub Actions checks README.md and CONTRIBUTING.md with lychee. After installing lychee, you can run the same check locally:

```sh
lychee --config lychee.toml README.md CONTRIBUTING.md
```

Review the Actions run summary or download its `link-check-report` artifact. Authentication and bot protection can cause failures; exclusions must be narrow, documented, and periodically reviewed. Do not exclude a failed URL solely to make the check pass.
