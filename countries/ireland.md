# Awesome OSINT — Ireland 🇮🇪

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search and court search resources for the Republic of Ireland.

Ireland is one of the more open common-law jurisdictions for corporate research: name and number searches at the company registry are free and need no account, and the courts publish written judgments and daily hearing lists on the open web. The friction is in the documents — statutory filings are priced per item, and officer data sits behind the same paywall.

This list covers **three things: finding companies, identifying who is behind them, and finding court records.**

*All links verified 2026-09-18.*

## Contents

- [Company registry — official](#company-registry--official)
- [Company search — third party](#company-search--third-party)
- [Beneficial ownership](#beneficial-ownership)
- [Other entity registers](#other-entity-registers)
- [Courts — judgments and case law](#courts--judgments-and-case-law)
- [Courts — hearing lists and case tracking](#courts--hearing-lists-and-case-tracking)
- [Insolvency and bankruptcy](#insolvency-and-bankruptcy)
- [Practical notes](#practical-notes)
- [Contributing](#contributing)

## Company registry — official

- [Companies Registration Office (CRO)](https://cro.ie/) — the statutory registry for companies, business names and limited partnerships. Start here.
- [CRO Company Search](https://cro.ie/post-registration/company-search/) — the registry's own guidance on what is searchable and what each document costs.
- [CORE — Companies Online Registration Environment](https://core.cro.ie/) — the live search and filing portal. Company name and number lookup is free without an account; submission and document purchase need a login.
- [CRO Open Services](https://services.cro.ie/) — machine-readable company and submission data, including the free company-number lookup endpoints.
- [CRO Gazette](https://cro.ie/en-ie/Publications/CRO-Gazette) — the weekly statutory gazette: incorporations, strike-off notices, dissolutions. Useful for monitoring rather than lookup.

## Company search — third party

- [Vision-Net](https://www.vision-net.ie/) — the most complete commercial layer over CRO data: full filing history, director cross-referencing, credit and insolvency flags. Name search is free, reports are paid.
- [SoloCheck](https://www.solocheck.ie/) — Irish company and director profiles with free summary data and a paid report tier.
- [Businesses.ie](https://www.businesses.ie/) — free CRO-derived company lookup. Independent of the CRO; use the official CORE search when you need the authoritative record.
- [OpenCorporates — Ireland](https://opencorporates.com/companies/ie) — normalised Irish company records, useful when you are pivoting across jurisdictions rather than working inside Ireland.

## Beneficial ownership

- [Register of Beneficial Ownership (RBO)](https://rbo.gov.ie/) — the central UBO register for Irish corporates. **Public access is restricted.** Following CJEU *WM and Sovim* (C-37/20), general public access was withdrawn; unrestricted access is limited to competent authorities and designated persons, with a restricted route for those who can show legitimate interest. Do not expect open lookup.

## Other entity registers

- [Charities Regulator — Register of Charities](https://www.charitiesregulator.ie/en/information-for-the-public/search-the-register-of-charities) — free search of registered Irish charities, including the trustees and annual reports. Many Irish NGOs are also CRO-registered companies, so cross-reference both.

## Courts — judgments and case law

- [Courts Service — Judgments](https://www2.courts.ie/Judgments) — the official judgment database. Written judgments of the Supreme Court, Court of Appeal and High Court, filterable by court, judge, and date delivered. This is the primary source.
- [BAILII — Ireland](https://www.bailii.org/ie/) — full-text searchable Irish case law, Supreme Court / High Court / Court of Criminal Appeal from 2000 with selected earlier judgments. Better full-text search than the official site; slightly behind on recency.
- [Courts.ie](https://www.courts.ie/) — the Courts Service homepage; the route into every other court service listed below.
- [Decisis](https://www.decisis.ie/) — commercial Irish law reporting, reports on every new Supreme Court, Court of Appeal and High Court judgment since 2011. Subscription.
- [IRLII — Irish Legal Information Initiative](https://www.ucc.ie/en/lawsite/irlii/) — UCC-hosted archive of selected pre-2000 Supreme and High Court decisions. **Not updated since 2017** — historical use only.

## Courts — hearing lists and case tracking

- [Legal Diary](https://legaldiary.courts.ie/) — the daily court list, updated 17:00 Monday to Friday. Covers the Supreme Court, Court of Appeal (civil and criminal), Central Criminal Court, Chancery, Commercial, Competition, Extradition, Family Law, Judicial Review and Circuit lists. The single best tool for seeing who is in court tomorrow.
- [High Court Search](https://courts.ie/high-court-search) — case tracking for High Court proceedings, covering all cases since August 1993. Search by party name or record number to establish that an action exists and follow its procedural history.
- [Courts Service Online (CSOL)](https://www.csol.ie/) — the umbrella portal: eDiary, High Court Search, eRegister, bankruptcy search, licensing, and the Legal Costs Adjudicators register.

## Insolvency and bankruptcy

- [Insolvency Service of Ireland (ISI)](https://www.isi.gov.ie/) — the statutory registers of Debt Relief Notices, Debt Settlement Arrangements, Personal Insolvency Arrangements and protective certificates. Searched jointly by first name and surname.
- [ISI — Register of Personal Insolvency Arrangements](https://www.isi.gov.ie/en/ISI/Pages/Register_PIA)
- [ISI — Register of Debt Settlement Arrangements](https://www.isi.gov.ie/EN/ISI/PAGES/REGISTER_DSA)
- Corporate insolvency (liquidation, receivership, examinership) is filed at the **CRO**, not the ISI — check the company's filing history and the CRO Gazette.

## Practical notes

**Company number format.** Numeric, 1–8 digits, no prefix (e.g. `104547`). Leading zeros are not significant. An optional suffix selects the register: `/C` for the companies register (the default) and `/B` for the business-names register — so `540274/B` is a registered business name, not a company. Business names are *not* separate legal persons; do not treat a `/B` hit as a corporate entity.

**Status vocabulary.** The CRO uses `Normal` (in good standing), `Strike off listed` (removal pending — a strong distress signal), `Receivership`, `In Liquidation`, `Externally Administered` and `Dissolved`. "Strike off listed" is the one worth alerting on: it usually means overdue annual returns.

**What costs money.** Name and number search is free. Statutory documents run roughly €3–€15 per item. **Director and secretary rosters are not on the free surface** — they come from purchased filings or from a commercial provider like Vision-Net. This is the single biggest difference from the UK, where officer data is free at Companies House.

**Annual return dates matter.** `next_ar_date` in the public record is a live compliance signal: a company well past its annual return date is heading for the strike-off list.

**Court coverage starts late.** Online written judgments effectively begin at 2001 (Supreme Court) and 2004 (High Court, Court of Criminal Appeal). Anything earlier means BAILII's selected set, IRLII's archive, or the printed reports.

**Judgments are not the whole docket.** Most Irish civil proceedings settle or resolve without a written judgment. A party absent from the judgment database may still have extensive litigation history — check High Court Search and the Legal Diary, which reflect proceedings rather than outcomes.

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and in what language. Links that require a practitioner login or a paid account should say so.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.
