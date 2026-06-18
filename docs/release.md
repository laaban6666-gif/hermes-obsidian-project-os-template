# Release and ZIP Packaging Guide

This guide explains how maintainers can prepare a v0.1 documentation release and an optional `starter-vault` ZIP package. It is intentionally local-first: the commands below inspect and package files, but they do not create a GitHub Release, create a tag, push, or publish anything.

Current documented version: `0.1.0` (see `../VERSION`).

## Release goals

A v0.1 package should make it easy for users to either:

- download the repository ZIP from GitHub and open `starter-vault/` in Obsidian; or
- download a future maintainer-created `starter-vault` ZIP containing only the vault folder contents.

The release should remain public-safe, generic, and honest about what has actually been published.

## Pre-release safety checklist

Before preparing screenshots, assets, release notes, or ZIP files, review the repository for public-safety issues:

- [ ] `VERSION` contains the intended version.
- [ ] `CHANGELOG.md` describes only shipped or clearly planned content.
- [ ] `README.md` does not claim that a GitHub Release exists unless one has actually been created.
- [ ] `starter-vault/`, `templates/`, `examples/`, `docs/`, and `assets/` contain placeholders or generic content only.
- [ ] No private notes, customer data, credentials, account identifiers, production URLs, or private strategy notes are included.
- [ ] Any screenshot or visual asset is sanitized. Prefer diagrams or placeholder-only mockups over screenshots.
- [ ] The publication checklist has been reviewed: `docs/publication-checklist.md`.

## Local review commands

Run these from the repository root. They are read-only except for the optional ZIP creation step.

```bash
cd <REPO_PATH>

# Confirm the branch and working tree before packaging.
git status --short --branch

# Confirm the documented package version.
cat VERSION

# Review files that could be included in a repository ZIP.
git ls-files

# Review release documentation references.
python3 - <<'PY'
from pathlib import Path
for path in [Path('README.md'), Path('CHANGELOG.md'), Path('docs/release.md')]:
    text = path.read_text(encoding='utf-8')
    print(f'\n## {path}')
    for line in text.splitlines():
        if line.startswith('#') or 'VERSION' in line or 'CHANGELOG' in line or 'release' in line.lower():
            print(line)
PY
```

Optional secret-pattern scan for common accidental credentials:

```bash
python3 - <<'PY'
from pathlib import Path
import re, sys
patterns = {
    'env assignment': re.compile(r'(?i)\b[A-Z0-9_]*(TOKEN|SECRET|KEY|PASSWORD|DSN)\s*='),
    'private key': re.compile(r'-----BEGIN [A-Z ]*PRIVATE KEY-----'),
    'api key shape': re.compile(r'sk-[A-Za-z0-9_-]{20,}'),
    'github token': re.compile(r'gh[pousr]_[A-Za-z0-9_]{20,}'),
}
failures = []
for path in sorted(Path('.').rglob('*')):
    if '.git' in path.parts or not path.is_file():
        continue
    if path.suffix.lower() not in {'.md', '.txt', '.svg'} and path.name != 'VERSION':
        continue
    text = path.read_text(encoding='utf-8', errors='ignore')
    for name, pattern in patterns.items():
        for match in pattern.finditer(text):
            line = text.count('\n', 0, match.start()) + 1
            snippet = text.splitlines()[line - 1].strip()
            failures.append((str(path), line, name, snippet))
if failures:
    for item in failures:
        print('%s:%s: %s: %s' % item)
    sys.exit(1)
print('secret-pattern scan passed')
PY
```

## Prepare a starter-vault ZIP locally

Only run this after the safety checklist passes. This creates a local ZIP in `dist/`; it does not publish the ZIP.

```bash
cd <REPO_PATH>
VERSION="$(tr -d '\n' < VERSION)"
mkdir -p dist
python3 - <<'PY'
from pathlib import Path
from zipfile import ZipFile, ZIP_DEFLATED

version = Path('VERSION').read_text(encoding='utf-8').strip()
source = Path('starter-vault')
out = Path('dist') / f'hermes-obsidian-project-os-starter-vault-v{version}.zip'

if not source.is_dir():
    raise SystemExit('starter-vault/ not found')

with ZipFile(out, 'w', ZIP_DEFLATED) as zf:
    for path in sorted(source.rglob('*')):
        if path.is_file():
            zf.write(path, path.relative_to(source.parent))

print(out)
PY
```

Suggested local verification after ZIP creation:

```bash
python3 - <<'PY'
from pathlib import Path
from zipfile import ZipFile
version = Path('VERSION').read_text(encoding='utf-8').strip()
zip_path = Path('dist') / f'hermes-obsidian-project-os-starter-vault-v{version}.zip'
with ZipFile(zip_path) as zf:
    names = zf.namelist()
print(f'{zip_path}: {len(names)} files')
for name in names[:20]:
    print(name)
PY
```

Do not commit generated `dist/` files unless maintainers explicitly decide to track release artifacts in the repository.

## Draft release notes

A maintainer can adapt this text when a release is actually published:

```markdown
## Hermes x Obsidian Project OS Template v0.1.0

Initial public starter package for a lightweight Hermes Agent + Obsidian project workflow.

Includes:
- starter Obsidian vault;
- AI Team Room and routing notes;
- project, decision, PR readiness, AI team, and cron templates;
- sanitized examples and OSS docs walkthrough;
- privacy-safe visual tour diagrams;
- issue and pull request templates;
- release packaging documentation.

Safety note: examples are generic and placeholder-based. Review local copies before adding private data or screenshots.
```

## Publishing boundaries

This guide does **not** authorize irreversible publication steps. Before creating a tag, GitHub Release, or uploaded asset, a maintainer should explicitly approve:

- the exact version;
- the release notes;
- the files or ZIP assets to publish;
- the privacy/safety review result;
- whether generated artifacts should remain local or be uploaded to GitHub.

Use `git status --short --branch` before any publish step and never publish from a dirty working tree unless the maintainer intentionally approves that state.
