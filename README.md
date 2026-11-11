# Internet Archive APIs — Postman Collection

This Postman collection (format v2.1) has 21 requests for **[archive.org](https://archive.org)** and the **Wayback Machine**. It covers metadata search, **full-text (OCR) search inside millions of scanned books and microfilm**, genealogy collections (Allen County Public Library and US census microfilm), item metadata, text downloads, IIIF manifests and Wayback snapshots.

**Import link** (Postman → Import → Link):
```
https://raw.githubusercontent.com/mikeyeves/Internet-Archive-API-Postman/main/Internet_Archive_API.postman_collection.json
```
You don't need a key or an environment file to read data.

## Folders
| Folder | Requests | Notes |
|---|---|---|
| ★ Search (metadata) | 7 | Advanced search; collections for genealogy, Allen County Public Library and US census microfilm; date range; subject; browse a collection |
| ★ Full-text search | 3 | Search the OCR text of every book with highlighted snippets; exact phrase; the Scrape API for deep paging |
| Items, text & images | 8 | Metadata, file list, OCR text, file download, **search inside one book** (server, directory and file are filled in automatically), IIIF manifest, thumbnail |
| Wayback Machine | 3 | Closest snapshot, list of all captures, open a snapshot |

The search requests include **Visualizer** tables with thumbnails, links and highlighted OCR snippets.

## Tested at build time
- Collection sizes: `genealogy` 20,979 items, `allen_county` 83,250, `us_census` 24,320.
- Full-text search: `Bukovsky` matched **4,858 pages**; `"Gross Betschkerek"` matched **83**.
- Books mentioning Banat dated 1800–1925: 41. The metadata, OCR text download and IIIF manifest requests all returned 200.
- Wayback availability and the list of captures (`delpher.nl`) both worked.

## Notes
- The full-text endpoint (`/services/search/beta/page_production/`) is the one the archive.org website itself uses. It works, but the Internet Archive labels it **beta**, so it may change.
- Allen County Public Library and FamilySearch-digitized books are often only in the full-text index, not in titles or descriptions. Try full-text search for surnames.
- Please be gentle: use the Scrape API for bulk harvests and avoid rapid repeat calls.

## Related collections
[DPLA](https://github.com/mikeyeves/DPLA-API-Postman) · [Library of Congress](https://github.com/mikeyeves/Library-of-Congress-API-Postman) · [FamilySearch](https://github.com/mikeyeves/FamilySearch-API-Postman)

*Unofficial. Not affiliated with the Internet Archive.*
