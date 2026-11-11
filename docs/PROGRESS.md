# Catalogue data repository progress

## Current phase

**Project documentation and bootstrap.** No catalogue package or release exists.

## Completed tasks

- Confirmed this repository is an independent public catalogue-distribution repository.
- Documented the planned package contents, GitHub Releases distribution, and release safety gates.
- Documented that actual catalogue data and images have not been added.

## Pending tasks

- Agree the shared record schema, manifest, serialization/database format, versioning, checksum conventions, image references, and package compatibility with the application and scraper repositories.
- Verify redistribution rights and attribution requirements for each relevant type of source material before preparing or publishing assets.
- Receive candidate package material from the private scraper only after crawling and extraction are separately authorized and performed.
- Validate, test, document, and review the first release package before publishing.

## Decisions still required

Manifest and record schemas; stable identifiers; formats and package layout; version and asset naming rules; checksum algorithm; image packaging/reference rules; validation vocabulary; source coverage; and documented redistribution permission/licensing.

## Dependencies on other repositories

- **`nmsinventory` (public):** its application consumes the published releases; the shared contract and update compatibility must be agreed with it.
- **`nmsinventory-scraper` (private):** expected producer of candidate data and image packages. This repository must not contain scraper source code.

## Next recommended action

Agree the exact cross-repository catalogue and release contract, then establish evidence and attribution requirements for redistribution before any data or image package is prepared.

