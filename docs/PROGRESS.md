# Catalogue data repository progress

## Current phase

**Cross-repository documentation and architecture contract synchronized.** Documentation alignment is complete; no catalogue package or release exists.

## Completed tasks

- Aligned this repository's release format, README, and Copilot guidance with the canonical versioned JSON contract in `nmsinventory/docs/DATA_CONTRACT.md`.
- Documented `manifest.json`, independent catalogue/schema/manifest-format versions, UTC release timestamp, package file sizes, SHA-256 integrity checks, provenance/attribution, separate recipe/image records, immutable UUIDs, validation states, and verified-only numeric stack limits.
- Confirmed the data repository packages reviewed scraper exports, while the application consumes published releases without depending on scraper code.
- Checked terminology and requirements against both other repositories. No contradictory requirements remain in the synchronized documentation.
- No catalogue data, images, package, or GitHub Release has been created.

## Pending tasks

- Resolve pending source-boundary, schema/taxonomy, optional/null, timestamp/checksum text encoding, image, compatibility, signature, and rights decisions listed in the canonical application decision log.
- Verify redistribution rights and attribution for every relevant content and image type before preparing or publishing assets.
- Receive an authorized, contract-conforming candidate export from the private scraper, validate it, and review it before any release.
- Test package integrity and application consumption before publishing a release.

## Decisions still required

See `nmsinventory/docs/DECISIONS.md` in the application repository for the shared pending decisions. This repository must not create a competing schema or independently settle those issues.

## Dependencies on other repositories

- **`nmsinventory` (public):** defines the canonical contract and consumes published releases.
- **`nmsinventory-scraper` (private):** may provide candidate contract-conforming JSON and permitted images after collection authorization and rights review. Never copy scraper code here.

## Next recommended action

Resolve the remaining owner decisions and rights gates. Only then authorize candidate data preparation and validate it against the shared contract; do not publish a release until review and testing are complete.
