# Codebase structure

The engine's source is private; this is its top-level shape (316 tracked
files, ~30,000 lines of TypeScript plus a Python sidecar). Descriptions stay
deliberately at the "what it does" level — the how, and the module-by-module
breakdown, live in the private repo.

```
deal-engine/
├── backend/            NestJS API (:3000) — the deterministic rules core, the
│                       business modules, the AI boundary, schema + migrations,
│                       and the unit + e2e gate suites
├── frontend/           Next.js dashboard (:3001) — 12 routes plus tokenized
│                       public pages (sign, verify, deal room, payment)
├── ai-sidecar/         optional Python service — on-device transcription,
│                       voice synthesis, the PII redaction firewall with PH
│                       identifier recognizers, document sealing
├── handover/           a 10-document operations pack: setup, walkthrough, API
│                       reference, data import, testing, operations,
│                       deployment & scaling
├── sample-data/        importable demo CSV (fictional companies)
├── sbom/               software bill of materials
├── .github/            CI — real database + queue, migrations, seeds,
│                       typecheck, lint, 306 unit + 29 e2e tests on every push
├── docker-compose.yml  local infrastructure (database, queue, mail sink)
├── bootstrap.sh        clone → running system, one command
└── launch.sh           one-command start/stop of the entire stack
```

## The numbers behind the tree

| | |
|---|---|
| 316 tracked files | ~30,000 lines of TypeScript + a Python sidecar |
| 82 REST endpoints | across 14 backend modules |
| 20 tables · 21 migrations | row-level security enforced on every tenant table |
| 306 unit + 29 e2e tests | including six always-green architectural gates |
| 12 dashboard routes | plus tokenized public pages (sign, verify, deal room, payment) |
| 2 commands to run | verified end-to-end from a fresh clone |

*Source access and live demos available on request — see the
[README](README.md).*
