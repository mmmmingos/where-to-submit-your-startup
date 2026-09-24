# Contributing

Add directory entries directly to the README. Keep the list useful, current, and easy to scan.

## Add a directory

1. Open the actual submission page and check the current eligibility and pricing terms.
2. Add or update the directory in the alphabetical Directories table (do not invent new category sections).
3. Fill in the row below and add evidence in DIY submission notes. Replace the placeholders before submitting.
4. Use the date you performed the review. If you only checked a URL's HTTP status, do not update Last checked.
5. Open a pull request with your sources. Disclose any relationship to the directory.

Copy this row:

```markdown
| Directory name | [Submit](SUBMISSION_URL) | Yes / No / Conditional / Unknown | Amount + currency + billing period, or Unknown | YYYY-MM-DD |
```

Add a corresponding notes row:

```markdown
| Directory name | Required fields and assets | Account, eligibility, reciprocal link, or other requirements | Published estimate or Unknown | [Submission rules](SOURCE_URL) |
```

## Evidence to include

- **Price:** distinguish free submission from optional promotion. Include currency, one-time vs recurring fees, and required reciprocal links.
- **Approval time:** cite the publisher's estimate or label your own dated experience. Use `Unknown` if neither is available.
- **Availability:** distinguish a reviewed public submission form, a login-only route, and an actual accepted submission. Do not imply you completed a submission if you only read the documentation.

## Correct or remove a listing

Update changed URLs, prices, and requirements wherever the directory appears. Move closed or unsuitable entries to Skip these with dated evidence. Investigate failed link checks before declaring a site dead.

## Link checks

The GitHub Actions workflow checks README.md and CONTRIBUTING.md using lychee. You can also run it locally after installing lychee:

```sh
lychee --config lychee.toml README.md CONTRIBUTING.md
```

Review the report in the Actions run summary or download the `link-check-report` artifact. Authentication and bot protection can cause failures; exclusions should be narrow, documented, and reviewed. Link checks never replace manual review of prices, submission policies, or backlinks.
