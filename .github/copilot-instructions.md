# Repository guidance

- This is the independent public catalogue distribution repository. Keep it separate from `nmsinventory` and private `nmsinventory-scraper`; never copy or publish scraper code here.
- Use the single canonical versioned JSON contract in `nmsinventory/docs/DATA_CONTRACT.md`. Do not create a second schema. The scraper exports conforming JSON; this repository validates/packages/releases it; the application imports published releases.
- Release through versioned GitHub Releases with `manifest.json`, catalogue content/schema versions, manifest format version, UTC timestamp, source/attribution, package file sizes, and SHA-256 checksums.
- Preserve immutable UUID item/recipe IDs and the registry lifecycle. Recipes are separate records referencing item IDs. Retired IDs remain represented; do not silently reuse or remove them.
- Use package-relative image references and preserve original source URLs/provenance separately. Reject unsafe paths and archive traversal. Do not fetch arbitrary remote images as an application fallback.
- Use only validation states `verified`, `unknown`, `unverified`, `incomplete`, and `conflicting`. Never treat them as confidence scores.
- Publish numeric stack limits only when verified with evidence; include difficulty applicability only when supported. Never guess.
- The agreed primary source is `https://nms.source.gs/`. Do not use NMS Handbook. Do not claim uninspected source fields.
- Do not publish catalogue text, images, or other assets until relevant redistribution rights and attribution are verified. Keep private permission evidence out of this public repository.
- Validate JSON schema, references, package sizes, SHA-256 values, image content, and paths. SHA-256 alone does not authenticate a publisher; manifest signing/attestation remains undecided.
- Keep secrets, credentials, private user data, and local environment files out of Git and releases. Do not mark releases or implementation milestones complete without validation/testing.
- Follow `docs/RELEASE_FORMAT.md`; unresolved owner decisions are tracked in the canonical contract's linked application `docs/DECISIONS.md` and this repository's progress document.
