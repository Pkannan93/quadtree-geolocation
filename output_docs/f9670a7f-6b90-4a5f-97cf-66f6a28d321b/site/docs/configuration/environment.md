# Environment — canvas-repo-31uxk3fo

No settings-class fields or env-var references detected. We scan for Pydantic `BaseSettings` subclasses, `pydantic-settings` v2 classes, `@dataclass` settings, generic `Settings` / `Config` classes, plus raw `os.getenv` / `process.env` reads and `.env.example` documented defaults. If your service reads config through another mechanism (e.g. a YAML loader), it won't appear in the typed table — the `operations/environments.md` page captures those raw reads instead.
