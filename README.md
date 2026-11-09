# intern0

Moves Datadog dashboards and monitors to Dash0.

Web version: https://dash0-migrator.vercel.app

![intern0 migrating a Datadog dashboard and monitor to Dash0](intern0-demo.svg)

## Installation

Python 3.9 or later.

```
uv tool install git+https://github.com/eric134422/intern0     # or: pipx install git+https://github.com/eric134422/intern0
intern0 migrate            # add --dry-run to only preview, nothing is sent
```

The first run opens your browser twice: sign in to Datadog and later to Dash0. Click allow so the migrator can move dashboards and alerts.

## Files

```
pyproject.toml               makes intern0 an installable command
intern0-demo.svg             the picture above
intern0/
├── cli.py                   intern0: sign-ins, picking, plan, import
└── converter/
    ├── datadog_to_perses.py     Datadog dashboard → Dash0 dashboard (Perses)
    ├── monitors_to_dash0.py     Datadog monitor → Dash0 alert (Prometheus rule)
    └── datadog_metrics.csv.gz   type and unit of 36,948 Datadog metrics, used by both
```
