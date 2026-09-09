# TechStyle Online Shop

A fashion e-commerce app for developers. Built with Python Flask + SQLite.

## Quick Start

**macOS / Linux**

```bash
./run_dev.sh
```

**Windows (PowerShell)**

```powershell
powershell -ExecutionPolicy Bypass -File .\run_dev.ps1
```

This creates a virtual environment, installs dependencies, seeds the database, and starts the dev server.

Open http://localhost:5001

## Project Overview

TechStyle is a Flask-based eCommerce platform used as a practical DevOps modernization project.

The goal of the project is to transform a traditional monolithic application into a modern DevOps-driven platform using:

- Git & GitHub Flow
- CI/CD Pipelines
- Automated Testing
- Docker
- AWS
- Monitoring
- Infrastructure as Code

## Project Structure

```text
techstyle/
├── app.py
├── seed_data.py
├── requirements.txt
├── templates/
├── static/
└── README.md

### Manual setup (without the script)

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python seed_data.py
python app.py
```

**Windows (PowerShell)**

```powershell
# The app expects a /tmp folder for the database (see Notes) — create it first.
# Use the drive your repo lives on, e.g. D:\tmp if you work from D:.
mkdir C:\tmp -Force

python -m venv .venv          # falls "python" nicht gefunden wird: py -3 -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python seed_data.py
python app.py
```

> Wenn PowerShell die Aktivierung blockiert (`... cannot be loaded because running scripts is disabled`):
> `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` ausführen und den Befehl wiederholen.

## Deploy to Production

```bash
./deploy.sh
```

Make sure `~/.ssh/techstyle_prod.pem` exists and the server IP in `deploy.sh` is correct.

## Features

- Product catalogue (20 items, multiple categories)
- Session-based shopping cart
- Checkout (no real payment)
- Admin panel at /admin

## Notes

- Database is stored at `/tmp/techstyle.db` — the path is hardcoded in `app.py` and `seed_data.py`
- **Windows:** there is no `/tmp`, so Python resolves that path to `C:\tmp\techstyle.db` (the `tmp`
  folder on the drive you are working from). If the folder is missing, both `seed_data.py` and
  `app.py` abort with `sqlite3.OperationalError: unable to open database file`. `run_dev.ps1`
  creates the folder for you; for the manual setup create it yourself with `mkdir C:\tmp -Force`.
- Run `python seed_data.py` again to reset products, or delete the DB file for a fresh start
  (`rm /tmp/techstyle.db` / `del C:\tmp\techstyle.db`) — activate the venv first
- Admin panel has no login — it's fine for now


