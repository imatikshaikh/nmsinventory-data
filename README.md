# No Man's Sky Inventory Manager catalogue data

This independent public repository is planned to distribute validated, versioned catalogue packages for the No Man's Sky Inventory Manager. It is not the application repository and must not contain the private scraper.

## Status

Documentation and bootstrap only. No catalogue data, images, package, or GitHub Release has been created. Redistribution permissions have not yet been fully verified; do not publish source material or images until the relevant rights and attribution requirements are confirmed.

## Planned release contents

A release uses versioned GitHub Releases and provides `manifest.json`, the shared versioned JSON catalogue, release notes, SHA-256 checksums and file sizes, source/attribution information, and an optional image package only when redistribution is permitted. The application imports JSON into logically separate catalogue tables in its SQLite database; the release is not an application database.

Catalogue content version, catalogue schema version, and manifest format version are distinct. See [`docs/RELEASE_FORMAT.md`](docs/RELEASE_FORMAT.md) and the canonical `nmsinventory/docs/DATA_CONTRACT.md` in the application repository for the shared record contract. Exact schema details, versioning/compatibility policy, image layout/formats, and signing remain pending decisions.

## Shared contract and source

The application consumes published releases from this repository and must work offline with its last installed catalogue. The private scraper prepares candidate packages; the application does not depend on it.

The agreed primary source is `https://nms.source.gs/`. Do not use NMS Handbook. The scraper is restricted to the agreed source website. The shared contract requires immutable UUID IDs, separate recipe records, package-relative image references, provenance, and explicit validation states. Numeric stack limits are published only when verified. Retired items retain their IDs. These requirements do not claim source fields have been inspected.

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
