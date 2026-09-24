# Contributing

Add directory entries directly to the README. Keep the list useful, current, and easy to scan.

## Add a directory

1. Open the actual submission page and check the current eligibility and pricing terms.
2. Add or update the directory in the alphabetical Directories table (do not invent new category sections).
3. Use the date you performed the review. If you only checked a URL's HTTP status, do not update Last checked.
4. Open a pull request with your sources. Disclose any relationship to the directory.

Copy this row:

```markdown
| [Directory name](SUBMISSION_URL) | Yes / No / Conditional / Unknown | Amount + currency + billing period, or Unknown | YYYY-MM-DD |
```


## Evidence to include

- **Price:** distinguish free submission from optional promotion. Include currency, one-time vs recurring fees, and required reciprocal links.
- **Long queues:** if review can take months, say so in Price (for example "Free review queue; often many months").
- **Availability:** distinguish a reviewed public submission form, a login-only route, and an actual accepted submission. Do not imply you completed a submission if you only read the documentation.

## Correct or remove a listing

Update changed URLs, prices, and requirements wherever the directory appears. Move closed or unsuitable entries to Skip these with dated evidence. Investigate failed link checks before declaring a site dead.

## Link checks

The GitHub Actions workflow checks README.md and CONTRIBUTING.md using lychee. You can also run it locally after installing lychee:

```sh
lychee --config lychee.toml README.md CONTRIBUTING.md
```

Review the report in the Actions run summary or download the `link-check-report` artifact. Authentication and bot protection can cause failures; exclusions should be narrow, documented, and reviewed. Link checks never replace manual review of prices, submission policies, or backlinks.
