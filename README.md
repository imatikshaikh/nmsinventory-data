# No Man's Sky Inventory Manager catalogue data

This independent public repository is planned to distribute validated, versioned catalogue packages for the No Man's Sky Inventory Manager. It is not the application repository and must not contain the private scraper.

## Status

Documentation and bootstrap only. No catalogue data, images, package, or GitHub Release has been created. Redistribution permissions have not yet been fully verified; do not publish source material or images until the relevant rights and attribution requirements are confirmed.

## Planned release contents

A release is expected to provide a version manifest, machine-readable catalogue data and/or database package, checksums, release notes, source and attribution information, and an image package/assets only when distribution is permitted. Large packages are planned for GitHub Releases rather than ongoing large binary files in Git history.

The exact file layout, schema, serialization/database format, naming, versioning, checksum algorithm, and image-reference convention remain decisions to confirm. See [`docs/RELEASE_FORMAT.md`](docs/RELEASE_FORMAT.md).

## Shared contract and source

The application consumes published releases from this repository and must work offline with its last installed catalogue. The private scraper prepares candidate packages; the application does not depend on it.

The agreed primary source is `https://nms.source.gs/`. Do not use NMS Handbook. The scraper is restricted to the agreed source website. The conceptual catalogue contract includes stable internal identifiers, item names, categories/subcategories, descriptions, image references, verified stack limits, available recipe/refining relationships, provenance, update/check information, and validation status. These concepts do not claim that corresponding source fields have been verified. Unknown stack limits must remain unknown.

See `nmsinventory/docs/DATA_CONTRACT.md` in the application repository for shared semantic requirements. Resolve exact schema and release details jointly before producing packages.

## Repository rules

- Keep this repository independent from the application and private scraper repositories.
- Do not add scraper source code or credentials.
- Do not add actual catalogue records or images until authorized and validated.
- Preserve provenance and required attribution.
- Never publish material without verifying redistribution rights.
- Keep secrets, API keys, credentials, private user data, and local environment files out of Git.
- Do not call a release or milestone complete until the package has been validated and tested.

## Progress

See [`docs/PROGRESS.md`](docs/PROGRESS.md) for the phase, pending work, dependencies, and next action.
