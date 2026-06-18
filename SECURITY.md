# Security Policy

## Core rule

This project is a template for public, reusable project operations. It must not contain secrets, credentials, customer data, or account-specific identifiers.

## Do not commit

- `.env` files or environment dumps.
- API keys, access tokens, private keys, or session cookies.
- Organization IDs for paid services or billing/account identifiers.
- GitHub authentication material.
- Private emails, phone numbers, addresses, or customer records.
- Production-only URLs or infrastructure details that should stay private.

## Safe placeholders

Use placeholders instead of real values:

- `<PUBLIC_REPO_URL>`
- `<MAINTAINER_NAME>`
- `<PROJECT_METRICS_TO_BE_FILLED>`
- `<SERVICE_ORG_ID_TO_BE_ENTERED_BY_USER>`

## Reporting issues

For now, use the future public repository's issue tracker after publication. Until then, review locally and remove any sensitive material before publishing.

## Before publishing

Run a secret scan and manually inspect examples. Automated scans are helpful, but they do not replace human review.
