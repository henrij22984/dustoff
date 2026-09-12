# dustoff

Opinionated log housekeeping tool with dry-run support

Side project, maintained when I have time.

## How to use

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Installation

```bash
pip install -r requirements.txt
python -m logwash --help
```

## What it does

- Dry-run mode shows what would happen, touches nothing
- Filter by age (--older-than) or size (--larger-than)
- Exit codes friendly for cron and CI
- Archive matched logs into a timestamped .tar.gz
- Scan directories for log files by glob pattern

## Project structure

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── bug_report.md
│   └── dependabot.yml
├── docs/
│   ├── roadmap.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   └── cli.py
├── tests/
│   └── test_cli.py
├── .gitattributes
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
├── SECURITY.md
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## License

MIT - see [LICENSE](LICENSE).
