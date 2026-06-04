# University of Indonesia (university-of-indonesia)

University of Indonesia (Universitas Indonesia, UI) is a public research university in Depok and Jakarta, ranked **#206 in the QS World University Rankings 2025** and the highest-ranked university in Indonesia. This repository catalogs UI's public, machine-readable developer/API footprint as an [APIs.json](http://apisjson.org) profile.

- APIs.json: https://raw.githubusercontent.com/api-evangelist/university-of-indonesia/refs/heads/main/apis.yml
- Run with Naftiko: https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=university-of-indonesia-api-evangelist&utm_content=repo

## Type

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

Education, Higher Education, University, Indonesia, Research, Repository, OAI-PMH, Authentication

## APIs

- **UI Scholars Hub OAI-PMH** — OAI-PMH 2.0 metadata-harvesting interface for the UI Scholars Hub institutional research repository (Digital Commons / bepress). Verified live.
  - Docs: https://scholarhub.ui.ac.id/
  - Base URL: https://scholarhub.ui.ac.id/do/oai/
- **SSO UI (CAS Authentication)** — University-wide Single Sign-On (Sistem Akun UI) using the CAS protocol. Login endpoint reachable; integration gated, no public developer portal.
  - Docs: https://sso.ui.ac.id/account/node/3

## Plans

- [plans/university-of-indonesia-plans-pricing.yml](plans/university-of-indonesia-plans-pricing.yml)

## Rate Limits

- [rate-limits/university-of-indonesia-rate-limits.yml](rate-limits/university-of-indonesia-rate-limits.yml)

## FinOps

- [finops/university-of-indonesia-finops.yml](finops/university-of-indonesia-finops.yml)

## Timestamps

- **Created:** 2026-06-03
- **Modified:** 2026-06-03

## Common Properties

- Website: https://www.ui.ac.id/
- LinkedIn: https://www.linkedin.com/school/university-of-indonesia/
- Authentication (SSO/CAS): https://sso.ui.ac.id/
- Plans, RateLimits, FinOps, and Review pointers (see above and [review.yml](review.yml))

## Notes

- The UI Scholars Hub OAI-PMH endpoint was verified live (HTTP 200, valid OAI-PMH 2.0 Identify response, repositoryName "UI Scholars Hub").
- sso.ui.ac.id was confirmed as a CAS Single Sign-On service; no public, self-service developer documentation or API keys were found.
- No official API Evangelist-style GitHub organization was found for the university; only unofficial community projects exist, so no GitHub common property is asserted.
- Several institutional domains (www.ui.ac.id, lib.ui.ac.id, lontar.ui.ac.id) appear geofenced and did not resolve from the review environment; they are known to be live. No endpoints were fabricated.

## Maintainers

- Kin Lane — kin@apievangelist.com
