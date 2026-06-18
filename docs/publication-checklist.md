# Publication Checklist

Use this before publishing or updating a public GitHub repository.

## 1. Review local files

- [ ] Read `README.md`.
- [ ] Read `SECURITY.md`.
- [ ] Confirm examples are safe to publish.

## 2. Choose public scope

- [ ] Repository name, suggested: `hermes-obsidian-project-os-template`.
- [ ] License, suggested: MIT.
- [ ] Whether to include all templates and examples in v1.
- [ ] Whether to add screenshots later. Do not add screenshots before privacy review.

## 3. Run local safety checks

Run these checks locally before any public repository creation or update. They are designed to be safe: read-only, no network, no credentials required.

```bash
cd /root/codex-for-oss-project-os-template

# File list check: review the exact files that would become public.
find . -type f | sort

# Markdown readability check: list headings and TODO-like markers for manual review.
python3 - <<'PY'
from pathlib import Path
for path in sorted(Path('.').rglob('*.md')):
    text = path.read_text(encoding='utf-8')
    print(f'\n## {path}')
    for line in text.splitlines():
        if line.startswith('#') or '<' in line or 'TODO' in line.upper():
            print(line)
PY

# Secret-pattern scan: catches common accidental credentials.
python3 - <<'PY'
from pathlib import Path
import re, sys
patterns = {
    'env assignment': re.compile(r'(?i)\b[A-Z0-9_]*(TOKEN|SECRET|KEY|PASSWORD|DSN)\s*='),
    'private key': re.compile(r'-----BEGIN [A-Z ]*PRIVATE KEY-----'),
    'api key shape': re.compile(r'sk-[A-Za-z0-9_-]{20,}'),
    'github token': re.compile(r'gh[pousr]_[A-Za-z0-9_]{20,}'),
}
allowed_placeholder_words = ('<PUBLIC_REPO_URL>', '<MAINTAINER')
failures = []
for path in sorted(Path('.').rglob('*')):
    if not path.is_file() or path.suffix not in {'.md', '.txt'}:
        continue
    text = path.read_text(encoding='utf-8', errors='ignore')
    for name, pattern in patterns.items():
        for match in pattern.finditer(text):
            line = text.count('\n', 0, match.start()) + 1
            snippet = text.splitlines()[line - 1].strip()
            if any(word in snippet for word in allowed_placeholder_words):
                continue
            failures.append((str(path), line, name, snippet))
if failures:
    for item in failures:
        print('%s:%s: %s: %s' % item)
    sys.exit(1)
print('secret-pattern scan passed')
PY
```

Manual checks after the commands:

- [ ] Confirm all `<PLACEHOLDER>` values are still placeholders, not real account data.
- [ ] Confirm no `.env`, token file, customer record, or private screenshot is present.
- [ ] Confirm the user has explicitly approved the repository name and publication scope.

## 4. Publish only after review

- [ ] Create the GitHub repository manually or with approved tooling.
- [ ] Push the reviewed files.
- [ ] Confirm the public repo renders correctly.
- [ ] Add a first issue or roadmap if desired.

## 5. Keep private planning private

- [ ] Do not commit private strategy notes, form answers, customer details, or account-specific identifiers.
- [ ] Keep non-public drafts in a private workspace, not in this public template repository.
