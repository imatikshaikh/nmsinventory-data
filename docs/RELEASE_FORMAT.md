# Planned catalogue release format

## Status

This document defines the intended contents and safety requirements of a catalogue release, not a finalized file format. No data or image package is present. Exact manifest schema, file names, archive layout, serialization, versioning, and checksum details require confirmation across all three repositories before the first package is prepared.

The shared semantic contract is documented in `nmsinventory/docs/DATA_CONTRACT.md` in the application repository. Do not invent source fields or imply that the source site exposes a field before it has been verified.

## Distribution

- Publish versioned, validated catalogue packages through GitHub Releases.
- Prefer GitHub Release assets for large database and image packages instead of repeatedly adding large binary archives to Git history.
- Keep release notes and source/attribution information available with each release.
- Do not create a release until package contents, validation, and redistribution permissions have been reviewed.

## Planned package contents

Each release is intended to provide:

1. **Version manifest** — at minimum, catalogue version and release date, plus source and attribution information. The precise property names, representation, and location are not yet decided.
2. **Catalogue data** — normalized records in a machine-readable data package and/or database package. The format and exact schema are open decisions.
3. **Images** — an image archive or assets and corresponding references, only where redistribution rights are confirmed. Archive layout and reference syntax are open decisions.
4. **Checksums** — checksums covering distributed package files, so the application can verify downloads. Algorithm, encoding, and exact checksum manifest format are open decisions.
5. **Release notes** — a human-readable summary of changes, data coverage, known gaps, and relevant attribution/permission notes.

Release asset names, compression, package compatibility policy, version numbering, and signing are not specified yet. Do not treat a suggested implementation as agreed without recording a decision.

## Data expectations

Normalized records should support stable internal identifiers; item names; category/subcategory; descriptions; image/icon references; verified stack limits; available crafting/refining relationships; source URL/provenance; last-checked or updated information; and confidence/validation status.

This is a set of semantic requirements, not a claim about source website fields or a fixed JSON schema. The source is `https://nms.source.gs/`; NMS Handbook is excluded. Unknown or unverified stack limits must not be guessed. Missing, unsupported, or conflicting source information must be represented honestly according to a validation convention that remains to be decided.

## Rights, provenance, and validation gate

Before any public release:

- Verify that permission covers the specific source text, images, and other included material, and that the source owner has rights to grant it.
- Record applicable attribution and licensing information.
- Validate records and provenance; detect duplicate/conflicting records.
- Validate image references and missing/broken images.
- Produce and verify checksums for the release assets.
- Test that the package can be consumed under the agreed shared contract.

The reported permission to scrape and share is not evidence that every asset's redistribution rights have been fully checked. No release is authorized by this plan.

## Application compatibility and safety

The application downloads published packages from this repository, verifies checksums, validates and installs updates atomically with rollback, and retains the last installed catalogue for offline use. Catalogue updates must never overwrite personal account, Traveller-profile, inventory, image, or history data.

The application does not depend on the private scraper. The scraper may prepare a candidate package, but only reviewed and approved package assets belong in a public release.
