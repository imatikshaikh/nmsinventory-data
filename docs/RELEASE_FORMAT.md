# Catalogue release format

## Status and shared contract

This repository packages and distributes the canonical versioned JSON catalogue contract defined in `nmsinventory/docs/DATA_CONTRACT.md` in the application repository. That contract is the single source for item, recipe, image, identifier, and validation semantics. This document describes the public release boundary and must not create a competing schema.

The private scraper may use an internal database schema of its own. Its exported JSON must conform to the shared contract. This repository receives candidate exports for review, packages approved assets, and publishes versioned GitHub Releases. The application consumes those releases only; it has no dependency on scraper code.

No catalogue data, images, package, or GitHub Release has been created. The agreed primary source is `https://nms.source.gs/`; do not use NMS Handbook. Do not imply that source fields have been inspected or verified before authorized inspection.

## Release distribution and contents

Distribute reviewed packages through versioned GitHub Releases, especially for larger binary assets. A release must provide:

- `manifest.json`.
- The canonical catalogue JSON document.
- An optional image package only when the included assets are cleared for redistribution.
- Human-readable release notes.

The canonical interchange is JSON, not a SQLite database. The application imports the JSON into separate logical catalogue tables in its own SQLite database.

### Manifest requirements

`manifest.json` follows the manifest concepts in the shared contract and includes:

- Manifest format version.
- Catalogue content version.
- Catalogue schema version.
- UTC release timestamp.
- Source and verified attribution information.
- A listing of downloadable package assets with package-relative names/paths, byte sizes, and SHA-256 checksums.
- Compatibility information when an approved compatibility policy exists.

Catalogue content version, schema version, and manifest format version are distinct. Lowercase hexadecimal is the recommended SHA-256 text encoding, pending final schema approval. The manifest does not checksum itself. Exact JSON property names, timestamp/checksum text encodings, version-numbering rules, compatibility ranges, asset names/archive layout, and release-signature policy remain pending in the application repository's `docs/DECISIONS.md`.

Image records in the catalogue use package-relative paths, not remote runtime URLs. The original source URL, provenance, media format, rights/redistribution status, and validation state are recorded separately as specified by the shared contract. An optional image archive must preserve the paths referenced by the catalogue.

## Data requirements

Conform to the shared contract for:

- Immutable UUID item and recipe IDs backed by a persistent ID registry.
- Recipes as independent records referring to item IDs.
- Image records and safe package-relative image references.
- Validation states `verified`, `unknown`, `unverified`, `incomplete`, and `conflicting`.
- Numeric stack limits only when verified, supported by evidence, and annotated with difficulty applicability only when supported.
- Provenance and relevant timestamps without inventing fields or values absent from inspected source material.
- Retired/legacy items retaining their IDs; never silently repurpose an ID.

The exact category taxonomy, source-to-contract mapping, optional/null rules, and final JSON Schema remain pending. Examples in the shared contract are illustrative, not catalogue data.

## Integrity and package validation

Before publishing a release:

1. Validate catalogue JSON against the approved schema version.
2. Check UUID uniqueness, item/recipe/image references, validation states, stack-limit rules, and retired-ID/alias consistency.
3. Check package paths for absolute paths, URL schemes, traversal, and root escapes.
4. Validate actual image bytes and media type, file sizes, image references, and archive members. Reject unsafe archive paths, symlinks, and unexpected file types.
5. Calculate SHA-256 and byte size for every listed downloadable asset and verify the produced release assets against those values.
6. Document coverage, known gaps, release changes, and required attribution in release notes/manifest.
7. Review redistribution rights and attribution for every included content and image asset. Keep confidential permission evidence private.
8. Test that the package is consumable under the shared contract before publication.

SHA-256 detects asset mismatch against the manifest; it does not by itself authenticate who produced the manifest. Whether releases require a signed manifest or trusted attestation remains an owner decision.

## Rights and release gate

Do not publish text, images, icons, or other source materials until permission has been verified for each relevant asset type and the source owner has rights to grant redistribution. Preserve required attribution and license notices. The reported permission to scrape and share is not proof that all material can be redistributed. Do not publish private permission correspondence or credentials.

The source website remains `https://nms.source.gs/`. Exact allowed origin, redirects, subdomains, and image hosts remain pending. Do not use NMS Handbook.

## Application safety

The application verifies checksums and sizes, validates schema and references, validates images and safe paths, backs up the installed catalogue, and atomically imports with rollback. Catalogue updates write only catalogue tables and must never overwrite or delete household accounts, Traveller profiles, personal inventory, locations, starships, freighters, uploaded photographs, or history. Retired IDs remain available so personal inventory references do not break.
