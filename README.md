# Stellar Analytics

Free, multi-tenant web and API analytics for projects building on Stellar, run as a shared service for the Stellar Community Fund (SCF).

Status: proposal stage. Walnut is applying to the SCF RFP [Web and API Analytics for Stellar Ecosystem Projects](https://stellar.gitbook.io/scf-handbook/scf-awards/build-award/rfp-track#current-open-rfps). No code yet. This repository will hold the whole system once work starts.

## What it will do

- **Web analytics** built on [Umami](https://umami.is): a cookie-free, version-pinned tracker. Page views, unique visitors, referrers, session duration, bounce rate, country and device.
- **API analytics**: tenants dual-export OpenTelemetry. The SCF collector keeps only counters and histograms in PostgreSQL (request volume, status codes, p50/p95 latency per normalized route).
- **Dashboards**: a private view per project and a global view for SCF operators, plus operator API keys.
- **Privacy**: GDPR without opt-in. No cookies, no personal data stored, EU data residency.

## Planned layout

One monorepo with the application code, infrastructure as code, deployment docs, operator runbooks, tenant onboarding guide, tests, privacy and security docs, and monitoring.

## License

[MIT](LICENSE)

Built by [Walnut](https://www.walnut.dev).
