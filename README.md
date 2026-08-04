# Legacy

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Legacy is a United States direct-to-consumer male fertility company offering at-home sperm testing and sperm cryopreservation without a clinic visit. Customers order a collection kit online, provide a sample at home, and return it by free overnight shipping to Legacy's CLIA-certified, CLEP-approved laboratory, where results appear in a private client dashboard within 48 hours of receipt.

Services span basic, standard, and advanced semen analysis (count, concentration, motility, morphology, and Halosperm sperm DNA fragmentation), STI testing, multi-year sperm storage bundles, and male fertility supplements. Legacy serves people trying to conceive and those preserving fertility ahead of a vasectomy, testosterone therapy, gender-affirming care, cancer treatment, or military deployment, and is in-network with selected insurers and employer fertility benefit programs.

- Website — https://www.givelegacy.com/
- Client portal — https://client.givelegacy.com/
- GitHub — https://github.com/givelegacy
- Backed by: bain-capital-ventures

## API surface

**Legacy publishes no public API.** There is no developer portal, no documentation, no OpenAPI description, no SDKs, and no public partner or EHR/EMR integration surface — the clinician offering is a human dashboard plus a shareable medical report, not an interop endpoint. `api.givelegacy.com` resolves but answers 503 to unauthenticated requests and is not a public surface. `apis[]` is therefore intentionally empty; the spec-derived artifacts (MCP, overlays, error catalog, conventions, data model, scopes, authentication, skills, Arazzo) are not applicable and were not fabricated.

## Artifacts

| Artifact | File | Method |
|---|---|---|
| llms.txt | `llms/legacy-llms.txt` | searched (verbatim from `/llms.txt`) |
| Well-known index | `well-known/legacy-well-known.yml` | searched — **no discovery documents published** |
| Conformance | `conformance/legacy-conformance.yml` | searched |
| Domain security | `security/legacy-domain-security.yml` | probed |

### Notable find — a real, hand-written `llms.txt`

Legacy serves a substantial first-party [`/llms.txt`](https://www.givelegacy.com/llms.txt) (`text/plain`, ~8.8 KB) explicitly authored for AI answer engines, including a "Key Facts for AI Answer Engines" section and a Common Questions block. This is the company's machine-readable surface in place of an API — a good example of a consumer-health brand optimizing for agent retrieval rather than developer integration.

### Compliance posture

Published on Legacy's own site: **CLIA ID 31D2285605**, **CLEP PFI 6002**, and a stated HIPAA-compliant posture. No SOC 2, ISO 27001, or trust center is published, and no vulnerability disclosure program or `security.txt` was found on any host.

### Well-known caveat

`client.givelegacy.com` is a Netlify-hosted single-page app whose catch-all route answers **200 with the HTML app shell for any path**, including a deliberate nonsense control path. Its `/.well-known/security.txt` and `/.well-known/openid-configuration` 200s are recorded as false positives, not as documents.
