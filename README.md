# Stellar Analytics

Free, multi-tenant web and API analytics for projects building on Stellar, run as a shared service for the Stellar Community Fund (SCF).

Status: proposal stage. Walnut is applying to the SCF RFP [Web and API Analytics for Stellar Ecosystem Projects](https://stellar.gitbook.io/scf-handbook/scf-awards/build-award/rfp-track#current-open-rfps). No code yet. This repository will hold the whole system once work starts.

## What it will do

- **Web analytics** built on [Umami](https://umami.is): a cookie-free, version-pinned tracker. Page views, unique visitors, referrers, session duration, bounce rate, country and device.
- **API analytics**: tenants dual-export OpenTelemetry. The SCF collector keeps only counters and histograms in PostgreSQL (request volume, status codes, p50/p95 latency per normalized route).
- **Dashboards**: a private view per project and a global view for SCF operators, plus operator API keys.
- **Privacy**: GDPR without opt-in. No cookies, no personal data stored, EU data residency.

## Architecture

See [docs/architecture.md](docs/architecture.md): diagram, Umami choice, tenant isolation, bot filtering, Stellar-aware path normalization, privacy, hosting, SLAs and handover.

## Planned layout

One monorepo with the application code, infrastructure as code, deployment docs, operator runbooks, tenant onboarding guide, tests, privacy and security docs, and monitoring.

```
tracker/     pinned web tracker (TypeScript, based on Umami's)
gateway/     web ingest gateway: bot filtering, IP truncation, URL scrubbing (Go)
collector/   SCF OpenTelemetry Collector build and PostgreSQL exporter (Go)
portal/      enrollment, API dashboards, operator view, API keys (Next.js)
umami/       pinned Umami release and patches
deploy/      OpenTofu, Helm chart, Docker Compose
docs/        architecture, onboarding, runbooks, privacy, security, SLA reports
tests/       isolation, load, ad-blocker and end-to-end tests
```

## License

[MIT](LICENSE)

Built by [Walnut](https://www.walnut.dev).
