# OpenAI Codex for OSS Research Notes

Date: 2026-06-06
Updated: 2026-06-12T02:16:48+09:00

Latest local artifact: `docs/codex-for-oss-pro-acquisition-brief.md` records a fresh verification snapshot and acquisition plan.

## Scope

This note records what could be checked from this local environment without submitting forms, logging into accounts, or touching private information.

## Official/public URLs attempted

The following OpenAI URLs were requested with a normal browser-like user agent from this VPS environment:

- `https://openai.com/form/codex-for-oss/`
- `https://openai.com/index/introducing-codex/`
- `https://help.openai.com/en/articles/11369540-codex-in-chatgpt`

Result: the requests returned HTTP 403 pages in this environment, apparently protected by Cloudflare or similar access controls. Because of this, the official form contents could not be directly verified here.

## Public information found outside the official form

A public article found via DuckDuckGo described the program as support for open-source maintainers, with possible benefits such as six months of ChatGPT Pro, API credits from an OSS-related fund, and selective security-tool access.

The same article said the application likely asks for:

- public repository link,
- GitHub stars,
- monthly downloads or comparable usage metrics,
- explanation of the project's importance or impact.

It also stated that no rigid minimum star threshold was publicly visible on OpenAI pages, while some third-party reports mention thresholds. Because the official form could not be accessed from this environment, this remains **unverified public-report information**, not a confirmed rule.

## Working assumptions for preparation

These assumptions are safe for local preparation and do not require personal data:

1. A real public OSS repository will be needed before applying.
2. The application should describe real usage, real scope, and real maintainer intent.
3. Metrics should never be invented or inflated.
4. If the project is new, the application should honestly say so and focus on usefulness, roadmap, and maintenance plan.
5. Account-specific fields, such as maintainer identity or organization IDs, must be filled only by the user.

## Uncertainties

- Whether applications are currently open.
- Exact eligibility criteria.
- Exact fields in the form.
- Whether a new but useful project is likely to be accepted.
- Whether any geographic or account-plan restrictions apply.
- Whether OpenAI requires a specific OpenAI organization/account state.

## Practical implication

Prepare the OSS project honestly first. After human review, publish the repository and only then open the official form in a normal browser session where the user can see the page and enter account-specific information.
