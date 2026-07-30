# Legacy

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
