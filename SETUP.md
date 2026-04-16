# Claude Session Setup

This file contains setup instructions for Claude to access the Odoo 19 developer
documentation at the start of each session.

## Odoo Documentation Repo

The full Odoo 19 developer documentation (forked from odoo/documentation) is available at:
**https://github.com/AdmaOdoo/documentation** (branch: 19.0)

## Session Initialization

At the start of any development session, paste your current PAT into this command
and run it in the bash tool to clone the documentation locally for instant file access:

```bash
git clone --depth=1 --branch 19.0 https://YOUR_PAT@github.com/AdmaOdoo/documentation.git /home/claude/odoo-docs
```

Once cloned, documentation files are readable instantly. Key paths:

| Topic | Path |
|---|---|
| Views / column_invisible / invisible | `/home/claude/odoo-docs/content/developer/reference/user_interface/view_architectures.rst` |
| ORM API / create / write overrides | `/home/claude/odoo-docs/content/developer/reference/backend/orm.rst` |
| QWeb Reports | `/home/claude/odoo-docs/content/developer/reference/backend/reports.rst` |
| Actions / button returns | `/home/claude/odoo-docs/content/developer/reference/backend/actions.rst` |
| Mixins / activity_schedule | `/home/claude/odoo-docs/content/developer/reference/backend/mixins.rst` |
| Module manifest | `/home/claude/odoo-docs/content/developer/reference/backend/module.rst` |
| Security / access rights | `/home/claude/odoo-docs/content/developer/reference/backend/security.rst` |
| Server Framework 101 | `/home/claude/odoo-docs/content/developer/tutorials/server_framework_101.rst` |

## Custom Module Repo

All custom Odoo developments live at:
**https://github.com/AdmaOdoo/AdmaDemoCustom** (branch: staging-revalve-test)

Clone command:
```bash
git clone --branch staging-revalve-test https://YOUR_PAT@github.com/AdmaOdoo/AdmaDemoCustom.git /home/claude/AdmaDemoCustom
```

## Odoo.sh Details

- Staging DB name: `admaodoo-admademocustom-staging-revalve-test-30913619`
- Shell command: `odoo-bin shell -d admaodoo-admademocustom-staging-revalve-test-30913619`
- Push to deploy: bump `version` in `__manifest__.py` (format: `19.0.X.X.X`)

## Key Development Notes

- Always check docs BEFORE writing code — prefer config over code
- `column_invisible` hides entire list column including header; `invisible` only hides cell content
- `point_id.title` is the QCP human-readable name; `point_id.name` is the sequence code
- Manifest version bump triggers auto-update on Odoo.sh push
- PAT should be provided by user at session start — never store in files
