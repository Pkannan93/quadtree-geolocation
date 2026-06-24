# Geospatial indexing and visualization (quadtree-based location services) Documentation — Secrets & config inventory

Three signals from the secrets/config scanner plugin (R3 Sprint A, F2 track 2):

1. **Environment variables** — the scanner records every `os.getenv` / `process.env.*` / `System.getenv` style call. Names captured verbatim; values are runtime, not in scope here.
2. **Suspected secret literals** — strings that match high-precision credential shapes (AWS access keys, GitHub PATs, Slack tokens, or high-entropy literals assigned to a `secret`/`token`/`api_key`-named variable). **Values are always redacted to a SHA-256 fingerprint** — we never round-trip a credential value into the report. Use the `relpath:line` citation to inspect the source.
3. **Config-file references** — calls to `load_dotenv`, `yaml.load`, Pydantic `_env_file=`, `dotenv.config({path: …})`, and a few other common loaders. Inventory of "where does config come from".

## Environment variables

_No environment-variable reads detected. Either this service uses static config (config files only), or none of the scanned languages call into `os.getenv` / `process.env` / `System.getenv`._

## Suspected secret literals

_No suspected secret literals detected. The detectors that fired this run looked for AWS access-key prefixes (`AKIA`), GitHub PAT prefixes (`gh[pousr]_`), Slack tokens (`xox[baprs]-`), and credential-named variable assignments to high-entropy literals (24+ chars from the credential alphabet). A clean scan is the expected outcome — false positives here are tolerable, but every match warrants a manual look._

## Config-file references

_No config-file references detected. Either this service uses environment variables exclusively, or its config loader is outside the scanner's coverage (Sprint B widens to Java's `Properties.load`, .NET's `IConfiguration`, K8s `valueFrom.configMapKeyRef`)._
