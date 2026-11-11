# Repository guidance

- This repository contains only public catalogue distribution materials and documentation. Keep it independent from `nmsinventory` and `nmsinventory-scraper`.
- Never copy or publish private scraper source code, credentials, or secrets here.
- Treat the shared contract in the application repository's `docs/DATA_CONTRACT.md` and the project's master specification as requirements. Resolve changes across all three repositories; do not silently invent fields or formats.
- The agreed primary source is `https://nms.source.gs/`. Do not use NMS Handbook. Any crawling belongs to the private scraper and must be restricted to the agreed source website.
- Do not add catalogue data, images, or release assets until source material is validated and redistribution permission and attribution requirements are verified.
- Do not guess stack limits. Preserve unknown or unverified values as such.
- Planned releases use a version manifest, checksums, release notes, provenance/attribution, catalogue data, and permitted image assets. Exact schemas and conventions remain undecided.
- Keep secrets, API keys, credentials, private user data, and local environment files out of Git.
- Do not mark data, a package, or a release milestone complete without validation and tests. Update `docs/PROGRESS.md` when work changes.

