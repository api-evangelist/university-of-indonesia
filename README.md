# University of Indonesia (university-of-indonesia)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

University of Indonesia (Universitas Indonesia, UI) is a public research university in Depok and Jakarta, the highest-ranked university in Indonesia. This repository catalogs UI's public, machine-readable developer/API footprint as an [APIs.json](http://apisjson.org) profile.

- APIs.json: https://raw.githubusercontent.com/api-evangelist/university-of-indonesia/refs/heads/main/apis.yml
- Run with Naftiko: https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=university-of-indonesia-api-evangelist&utm_content=repo

## Type

- **Class:** university (`x-type: university`)
- **Category:** Public Research University
- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Who operates what

A university is a federation of buyers, not a producer, so every surface below carries an
`x-operator` in `apis.yml` saying **who runs the thing**, alongside the usual `method:` provenance
saying how we came to hold the artifact.

| Surface | Host | Operator | Why |
|---|---|---|---|
| UI API Gateway (Kong Enterprise 3.3.1.0) | api.ui.ac.id | `institution` | ui.ac.id, no CNAME, 152.118.148.211 inside UI's own APNIC block 152.118.0.0/16 (INDONESIAUNI-ID) |
| SSO UI (Apereo CAS) | sso.ui.ac.id | `institution` | ui.ac.id, no CNAME, 152.118.148.213, self-hosted open-source CAS |
| EMAS2 (Moodle Web Services + LTI 1.3) | emas2.ui.ac.id | `institution` | ui.ac.id, no CNAME, 152.118.24.145, self-hosted Moodle |
| LONTAR Library OPAC | lib.ui.ac.id | `institution` | ui.ac.id, no CNAME, 152.118.147.93; lontar.ui.ac.id redirects here |
| UI Scholars Hub OAI-PMH | scholarhub.ui.ac.id | `tenant` | **CNAME → dcuischolarhub.bepress.com**; OAI adminEmail dc-support@elsevier.com |
| UI Research Portal (Elsevier Pure) | scholar.ui.ac.id | `tenant` | **CNAME → ui.elsevierpure.com**; response header `x-product: Pure Portal` |
| Crossref member 4386 | api.crossref.org | `registry` | Membership, prefix 10.7454, 12,754 DOIs — a fact about UI, not a UI contract |
| ROR 0116zj450 | api.ror.org | `registry` | Identifier registry UI is registered in |

**Two CNAME tenancies are the headline finding.** Both `scholarhub.ui.ac.id` and
`scholar.ui.ac.id` sit on the university's own registrable domain, so any host-based ownership
check reads them as UI's own engineering. They are not. `scholar.ui.ac.id/ws/api/openapi.yaml`
serves Elsevier's generic **Pure API** OpenAPI 3.0.1 — 827 paths, `info.contact.email`
`pure-support@elsevier.com`, `servers: [{url: /ws/api}]` (relative, therefore invisible to a
host-based check). **That contract is deliberately not stored in this repository.** The tenancy is
recorded; the contract belongs in Elsevier's own profile.

## APIs

- **UI API Gateway (Kong Enterprise)** — `api.ui.ac.id`, institution-operated. HTTP 401
  `{"message":"Unauthorized"}` on every probed path including `/docs` and `/openapi.json`.
- **SSO UI (CAS Single Sign-On)** — `sso.ui.ac.id/cas/login`, institution-operated, live. No public
  developer docs; `/cas/idp/metadata` and `/cas/oidc/.well-known/openid-configuration` return the
  login HTML with 200 (soft-200, not metadata).
- **EMAS2 Learning Platform** — institution-hosted Moodle. `/webservice/rest/server.php` →
  `moodle_exception` / `invalidtoken`; `/login/token.php` → `missingparam`; `/mod/lti/auth.php` →
  a populated LTI 1.3 OIDC authorization form.
- **UI Scholars Hub OAI-PMH** — bepress Digital Commons tenant. 115 sets, 9 metadata prefixes.
- **UI Research Portal (Elsevier Pure)** — Pure tenant. `/ws/oai` OAI-PMH with an OpenAIRE CERIF
  1.2 profile; `/ws/api` serves Elsevier's contract (not saved here).
- **LONTAR Library OPAC** — institution-operated; human-facing only, no machine surface found.
- **Crossref Member 4386** and **ROR 0116zj450** — registry memberships.

## Conformance (Kin Score `education` regime)

[conformance/university-of-indonesia-conformance.yml](conformance/university-of-indonesia-conformance.yml)
— every entry probed, positives and negatives alike.

- `lti` — **yes**, institution (EMAS2 Moodle LTI 1.3 platform endpoint)
- `oai-pmh` — **yes**, tenant (both providers are vendor-operated on UI hostnames)
- `crossref` — **yes**, registry (member 4386, prefix 10.7454)
- `datacite`, `shibboleth`, `saml`, `orcid`, `scim`, `oneroster`, `ed-fi`, `caliper`, `qti` — no,
  each with the negative probe that established it

## Why this profile is thin

`x-coverage: gated / auth_required`. UI runs real machine surfaces on its own network and publishes
a contract for none of them. There is no developer portal, API reference, OpenAPI, key issuance or
client registration anywhere on `ui.ac.id`, and none has been generated to stand in for one.

## Plans

- [plans/university-of-indonesia-plans-pricing.yml](plans/university-of-indonesia-plans-pricing.yml)

## Rate Limits

- [rate-limits/university-of-indonesia-rate-limits.yml](rate-limits/university-of-indonesia-rate-limits.yml)

## FinOps

- [finops/university-of-indonesia-finops.yml](finops/university-of-indonesia-finops.yml)

## Timestamps

- **Created:** 2026-06-03
- **Modified:** 2026-09-01

## Common Properties

- Website: https://www.ui.ac.id/
- LinkedIn: https://www.linkedin.com/school/university-of-indonesia/
- Authentication (CAS SSO): https://sso.ui.ac.id/cas/login
- ResearchRepository: https://scholarhub.ui.ac.id/ and https://scholar.ui.ac.id/
- LibraryCatalog: https://lib.ui.ac.id/
- Conformance, DomainSecurity, Plans, RateLimits, FinOps and Review pointers (see above and
  [review.yml](review.yml))

## Notes

- **Superseding the June 2026 note about geofencing.** `www.ui.ac.id`, `lib.ui.ac.id` and
  `lontar.ui.ac.id` all answer. `www.ui.ac.id` sits behind an F5 Shape/TSPD JavaScript
  interstitial that returns HTTP 200 with a bot-defense body for **every** path — `/robots.txt`,
  `/llms.txt`, `/.well-known/security.txt` and invented paths all "succeed" — so no status code
  from that host was treated as evidence for or against anything.
- One dead pointer was removed: `https://sso.ui.ac.id/account/node/3` returns HTTP 503.
- `data.ui.ac.id` answers HTTP 200 with `<h1>Website Disabled</h1>` on Apache 2.2.3 / PHP 5.2.9.
  It is not an open-data portal and no `OpenData` pointer is asserted.
- `academic.ui.ac.id` (SIAK-NG, the student information system; `siakng.ui.ac.id` CNAMEs to it) has
  no public A record and does not resolve from the open internet.
- No official University of Indonesia GitHub organization exists. `github.com/universitas-indonesia`
  and `github.com/University-of-Indonesia` both have 0 public repositories; everything else found
  is faculty, lab or student-society work, so no `GitHubOrganization` pointer is asserted.
- Indonesia has no eduGAIN member federation and no `*.ac.id` entityID appears in the eduGAIN
  entity aggregate (10,615 entities), so there is no identity-federation surface to record.
- No specification has been fabricated or generated for any of these surfaces.

## Maintainers

- Kin Lane — kin@apievangelist.com
