# Awesome OSINT — Hong Kong 🇭🇰

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search and court search resources for the Hong Kong SAR.

Hong Kong publishes a great deal and charges for most of it. The Companies Registry runs a free open-data feed of live entities and a paid per-item search for everything that matters — directors, secretaries, charges, filings. The courts, by contrast, are genuinely open: the Judiciary's Legal Reference System carries full-text judgments back to 1946, free.

The jurisdiction's defining research quirk is that the single richest corporate-network resource is not a government service at all.

This list covers **three things: finding companies, identifying who is behind them, and finding court records.**

*All links verified 2026-09-18.*

## Contents

- [Company registry — official](#company-registry--official)
- [Listed companies and regulated entities](#listed-companies-and-regulated-entities)
- [Company search — third party](#company-search--third-party)
- [Beneficial ownership](#beneficial-ownership)
- [Courts — judgments and case law](#courts--judgments-and-case-law)
- [Courts — cause lists and filings](#courts--cause-lists-and-filings)
- [Insolvency, bankruptcy and winding-up](#insolvency-bankruptcy-and-winding-up)
- [Practical notes](#practical-notes)
- [Contributing](#contributing)

## Company registry — official

- [Companies Registry](https://www.cr.gov.hk/) — the statutory registry. Start here for what is searchable and what each search costs.
- [CR e-Services Portal / ICRIS](https://www.e-services.cr.gov.hk/) — the live search system. Relaunched 27 December 2023 as the "Revamped ICRIS", replacing the 18-year-old AQUA-based system. Free basic search by company name or CR number / UBI returns status, entity type and incorporation date. A paid company particulars search (around HK$22) returns directors, company secretary, registered office and issued share capital.
- [CR Open Data](https://data.cr.gov.hk/) — the free daily-rebuilt dataset of company names, business registration numbers and registered office addresses, published under the Hong Kong PSI open-data scheme. Bulk-friendly and free, but **live entities only**.
- [How to obtain company information](https://www.cr.gov.hk/en/services/obtain-company-info.htm) — the Registry's own breakdown of free versus paid search routes, including the on-site Public Search Centre.

## Listed companies and regulated entities

- [HKEXnews](https://www.hkexnews.hk/) — statutory filings of every Hong Kong listed issuer: annual reports, circulars, and — critically — disclosure of interests filings showing substantial shareholders and director dealings. Free, full archive.
- [SFC Public Register of Licensed Persons and Registered Institutions](https://apps.sfc.hk/publicregWeb/) — every licensed corporation and individual, their responsible officers, licence conditions and disciplinary history. Free.

## Company search — third party

- [Webb-site](https://webb-site.com/) — the indispensable one. A non-profit database built from 1998 covering Hong Kong listed-company directors and boards, CCASS holdings, SFC licensees, members of statutory and advisory bodies, the judiciary, and solicitors — cross-linked into a navigable people-and-companies graph. It does what no official Hong Kong source does: **reverse lookup by person**. Founded by David Webb (1965–2026); the database and its mirrors remain online.
- [Webb-site Database mirror](https://webb-database.com/dbpub/) — mirror of the Webb-site database interface.
- [check-site.ai](https://www.check-site.ai/) — successor platform built on the Webb-site system, searching companies, directors, CCASS holdings and SFC licensees.

## Beneficial ownership

Hong Kong has **no public beneficial ownership register**, and the gap is structural rather than a matter of access fees.

- Every Hong Kong company must keep a **Significant Controllers Register (SCR)** — but it keeps it **at its own registered office**. The Companies Registry does not collect it, does not hold it, and does not publish it.
- Only competent authorities can compel inspection of an SCR. There is no public dataset, no legitimate-interest route, and nothing to query.
- Failure to maintain an SCR is an offence, but enforcement is not visible in a searchable public register.

**What to use instead:**

- [HKEXnews — disclosure of interests](https://www.hkexnews.hk/) — for **listed issuers**, the Securities and Futures Ordinance Part XV regime requires substantial shareholders (5%+) and directors to disclose their interests and changes to them. This is the single richest open ownership source in Hong Kong, and it is free and fully archived.
- [Webb-site](https://webb-site.com/) — cross-links listed-company directors, boards and CCASS holdings into a people-and-companies graph, enabling the reverse lookup no official source offers.
- **CCASS holdings** — the Central Clearing and Settlement System participant holdings show which brokers and custodians hold a listed stock. Nominee-level, not beneficial-level, but it reveals concentration and movement.
- [SFC Public Register](https://apps.sfc.hk/publicregWeb/) — responsible officers and licensed representatives, which links individuals to regulated corporations.

For a private Hong Kong company with no listed parent, beneficial ownership is generally **not recoverable from open sources**. Court filings and filings made by affiliates in more transparent jurisdictions are the realistic routes.

## Courts — judgments and case law

- [Legal Reference System (LRS)](https://legalref.judiciary.hk/lrs/common/ju/judgment.jsp) — the Judiciary's official judgment database. Court of Final Appeal, Court of Appeal, Court of First Instance, Competition Tribunal, District Court, Family Court and Lands Tribunal, from 1946–48 and 1966 onwards. Searchable by case number, neutral citation, party name or reported citation, with English, Traditional Chinese and bilingual versions. Free.
- [HKLII — Hong Kong Legal Information Institute](https://www.hklii.hk/) — free full-text search across every Hong Kong court and tribunal at once, plus legislation. Often faster and better-indexed than the official LRS for keyword work.
- [HKLII databases index](https://www.hklii.hk/databases) — what HKLII actually holds, court by court, with coverage dates.
- [Judiciary — Judgments and Legal Reference](https://www.judiciary.hk/en/judgments_legal_reference/index.html) — the Judiciary's landing page for judgments, law reports and the library collections.

## Courts — cause lists and filings

- [Judiciary](https://www.judiciary.hk/) — court structure, daily cause lists, practice directions and registry contacts.
- [e-Courts / iCMS](https://www.judiciary.hk/en/e_courts/index.html) — the integrated Court Case Management System. Progressively rolled out across the High Court, District Court, Magistrates' Courts and Small Claims Tribunal since 2022. **Unregistered members of the public may use it to search filed documents open to public inspection and to search cause books** — one of the few routes to case-level data without a practitioner account.

## Insolvency, bankruptcy and winding-up

- [Official Receiver's Office](https://www.oro.gov.hk/) — administers compulsory winding-up and personal bankruptcy.
- [Search on Bankruptcy, IVA and Compulsory Winding-up records](https://www.oro.gov.hk/eng/our_services/electronic_services/compulsory.html) — the online search. Establishes whether a person is bankrupt or facing a petition, or a company wound up or facing one. Around HK$80 per request.
- [Compulsory winding-up and bankruptcy statistics](https://www.oro.gov.hk/eng/statistics/compulsory_winding_up_and_bankruptcy/stat.php) — aggregate trend data, free.

## Practical notes

**Identifier.** Since 27 December 2023 the 8-character **Business Registration Number (BRN)** issued by the Inland Revenue Department is the Companies Registry's primary identifier, replacing the legacy CR number. Usually 8 digits (`79510969`), with leading zeros significant on pre-2000 entities (`09748794`), and `C` + 7 digits for companies limited by guarantee (`C0523371`).

**The open data feed hides the dead.** `data.cr.gov.hk` publishes **live entities only** — struck-off, wound-up and dissolved companies are simply absent. An entity missing from the free feed is not proof it never existed; it is often proof it is gone. Dissolved-company history requires the paid e-search surface.

**Name search is begins-with, not contains.** The free name search matches from the start of the name, and only against the local-company endpoint. Registered non-Hong Kong companies are reachable **by identifier only** — you cannot find a foreign branch by name on the free surface.

**Foreign-company registration dates mislead.** For a registered non-local company, the date shown is the date of Hong Kong registration, not incorporation in the home jurisdiction. Do not report it as an incorporation date.

**Directors are not free, and controllers are not public at all.** Director and company-secretary records are sold per item. The Significant Controllers Register (SCR) is kept by each company **at its registered office** — the Registrar does not collect it, and no public dataset exists. Only competent authorities can compel inspection. For listed issuers, use HKEXnews disclosure-of-interests filings instead; for anyone else, Webb-site is usually the only open route.

**Charges are filed but paywalled.** Registered charges exist in the register and are retrievable only as paid image downloads.

**Bilingual search is two searches.** Company names and judgments exist in English and Traditional Chinese, and the systems match literally. Run both forms — a Chinese-only trading name will not surface on an English query.

**Winding-up records have gaps.** The Official Receiver does not hold records of **voluntary** liquidations, and the computer system does not cover compulsory cases closed before 1984.

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and in which languages. Links that require a practitioner login or a paid account should say so.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.
