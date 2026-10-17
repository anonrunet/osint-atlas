# OSINT Atlas 2.0 — build and source audit

**Audit date:** 2026-10-17  
**Final catalog:** 421 unique URLs across 15 populated categories.

## Source verification

The legacy 588-entry catalog was checked first, then filtered and curated. Candidates were selected only when a direct HTTP GET produced a successful response; redirects were followed, and the final destination was stored for moved resources. Automated requests were rate-limited to four concurrent connections, with a one-byte Range request to avoid downloading pages.

A final pass checked every URL in the new 421-entry catalog. **421/421 returned a successful GET response** on 2026-10-17. `crt.sh` was additionally checked through its live search page after a transient timeout in the automated request. ARIN's retired interface was replaced by its current RDAP page.

The selection removes unresolved/broken entries, literal parameter placeholders, duplicate URLs, discontinued services, dating sites, low-quality people-search aggregators, and several legacy social-media tools. Redirects to canonical/current resource pages were updated. S3 bucket tools were moved out of the Dark Web category; empty/incorrect categories were removed or corrected.

### Final category counts

| Category | Sources |
|---|---:|
| Domains & DNS | 100 |
| OSINT Automation | 78 |
| Images & Reverse Image Search | 66 |
| Maps & Geolocation | 28 |
| Public Records | 27 |
| IP & Networks | 24 |
| Cloud & Infrastructure | 22 |
| Email & Accounts | 19 |
| Social Media Intelligence | 16 |
| Files & Metadata | 12 |
| Usernames & Social Networks | 9 |
| Companies & Business Records | 9 |
| Search Engines & Google Dorks | 6 |
| People Search | 3 |
| Cyber Threat Intelligence | 2 |
| **Total** | **421** |

## Functional checks

- JavaScript syntax checks passed for `app.js`, `data.js`, and `dorks.js`.
- DOM smoke test: welcome-screen entry, 36-card page, category navigation, Graph page, Dorks generation (27 topic queries), Author page, and Settings page.
- Each catalog URL is unique; every tool belongs to one of the 15 populated categories.
- Existing language/theme/settings persistence, graph/cases/provenance, Undo/Redo, report/export, and quick pivots are retained.

## Scope and limits

A successful GET confirms that the URL responded at the time of checking; it does **not** guarantee a third-party feature remains free, accepts accounts from every region, or works without JavaScript. Those limitations are described in the project README, and access/payment tags are preserved. No external service was logged into, scraped, or scanned beyond one minimal availability request per final URL.
