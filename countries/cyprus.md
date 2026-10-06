# Awesome OSINT — Cyprus 🇨🇾

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search, beneficial ownership and court search resources for the Republic of Cyprus.

Cyprus is the most open of the European offshore-adjacent jurisdictions on the corporate side and one of the most awkward on the court side. The company register is genuinely free and public — name, number, registered office, **and officers**, with filed documents previewable — which puts it ahead of Ireland, Spain, Luxembourg and most of the Crown Dependencies. The beneficial ownership register went the other way: public access was switched off in January 2023 and has not come back.

Court research is dominated by a single non-governmental site, and most of it is in Greek.

*All links verified 2026-09-18.*

## Contents

- [Company registry — official](#company-registry--official)
- [Regulated entities and listed companies](#regulated-entities-and-listed-companies)
- [Beneficial ownership](#beneficial-ownership)
- [Courts — judgments and case law](#courts--judgments-and-case-law)
- [Courts — filings and case management](#courts--filings-and-case-management)
- [Insolvency](#insolvency)
- [Practical notes](#practical-notes)
- [Contributing](#contributing)

## Company registry — official

- [DRCOR eFiling — Public Search](https://efiling.drcor.mcit.gov.cy/DrcorPublic/SearchForm.aspx?sc=0&cultureInfo=en-AU) — **the primary tool, free, no account.** Search by company name or HE registration number. Returns status, registered office, directors and secretary, and lets you preview the filed document index. English and Greek interfaces.
- [Department of Registrar of Companies and Intellectual Property](https://www.companies.gov.cy/) — the department itself. Renamed from DRCOR to DRCIP in 2021; the e-filing URL and older filings still carry the legacy DRCOR initials, so both acronyms refer to the same body.
- [eSearch in Business Entity's Registry](https://www.companies.gov.cy/en/21-eservices/esearch-in-business-entity-s-registry) — the department's own guidance on the search service and what each result field means.

## Regulated entities and listed companies

- [CySEC — Regulated Entities](https://www.cysec.gov.cy/en-GB/entities/) — the Cyprus Securities and Exchange Commission register: investment firms (CIFs), fund managers, administrative service providers, crypto-asset service providers, with licence status and regulatory announcements. Free. Cyprus is a major CIF domicile, so this is high-value.
- [Cyprus Stock Exchange](https://www.cse.com.cy/) — listed issuers, announcements and disclosures.

## Beneficial ownership

- [UBO Register — Beneficial Owner](https://ubo.meci.gov.cy/) — the Cyprus register of beneficial owners.

**Public access ended on 3 January 2023**, following the CJEU judgment in *WM and Sovim SA v Luxembourg Business Registers* (Joined Cases C-37/20 and C-601/20). Access is now limited to obliged entities performing customer due diligence and to government authorities. There is no open lookup and no legitimate-interest portal for the general public.

Filing obligations continue and are strict, which matters for OSINT indirectly — non-compliance is itself a public signal:
- Declaration due within **90 days** of incorporation.
- Changes must be filed within **45 days**.
- **Annual confirmation between 1 October and 31 December**, required even where nothing has changed.
- Penalties since December 2024: €100 on the first day, €50 per day thereafter, capped at €5,000, charged to the company rather than its directors.

The threshold for a reportable beneficial owner is a natural person holding more than 25% of shares or voting rights, or otherwise exercising control.

## Courts — judgments and case law

- [CyLaw](https://www.cylaw.org/) — **the primary case-law resource**, and it is not a government site. Run by the Cyprus Institute of Legal Information since 2002. Holds all Supreme Court judgments **from 1883 onwards**, plus Supreme Constitutional Court, Administrative Court and Court of First Instance decisions, Competition Commission decisions, consolidated and original legislation, and the civil procedure rules. Free.
- [CyLaw — advanced search](https://cylaw.org/advanced-en.html) — the English-language advanced search form. The interface and most content are Greek, but the search engine accepts English keywords, and **Supreme Court judgments from 1970 to 1988 are available in English**.
- [Supreme Court of Cyprus](https://www.supremecourt.gov.cy/) — the official judiciary site. Court structure, judicial appointments, procedural information. A legacy Lotus Notes application; navigation is poor and it is not a practical full-text search tool. Use CyLaw for judgments.
- [CommonLII — Cyprus](http://www.commonlii.org/cy/) — Commonwealth Legal Information Institute mirror of selected Cypriot material. Thin, but sometimes surfaces things CyLaw's interface buries.

## Courts — filings and case management

- [iJustice](https://ijustice.judicial.gov.cy/) — the judiciary's e-filing and case-register portal, used for electronic filing and for communication between lawyers, registrars and judges. **Practitioner or party access; not a public search tool.** Note that it may be unreachable from outside Cyprus.

eJustice covers all District Court jurisdictions but excludes the Criminal Court, Juvenile Court, Military Court, the Supreme Court's appellate jurisdiction, and the Administrative Court of International Protection.

## Insolvency

- [Department of Insolvency](https://www.insolvency.gov.cy/) — under the Ministry of Energy, Commerce and Industry. Maintains and publishes the national insolvency registers: bankruptcies, compulsory liquidations and voluntary liquidations. Searchable by debtor name or registration ID.

Company windings-up are also reported into the Business Register, so a dissolved or liquidating company will show in the DRCOR search as well — cross-check both.

## Practical notes

**Identifier.** The registration number is an `HE` prefix plus digits (`HE123456`) for companies. Other prefixes exist for other entity types — partnerships and business names use their own series. Keep the prefix; the bare number is ambiguous.

**Officers are free here.** Unlike Ireland, the Cayman Islands or Hong Kong, the Cyprus public search returns **directors and the company secretary at no cost**. This is the jurisdiction's single most useful OSINT property, and it is the reason a Cyprus entity in a chain is often the most tractable link in it.

**But nominees are pervasive.** Cyprus has a large administrative-service-provider industry, and the named directors and shareholders of a Cyprus holding company are frequently nominees supplied by a corporate service provider. Free officer data is not ownership data. Treat repeated director names across unrelated companies as a service-provider fingerprint, not a business relationship — and note that identifying the provider is often more informative than the nominee.

**Two languages, two spellings.** Company names and judgments exist in Greek and English, and transliteration is inconsistent (`Andreou` / `Andreou`, `Χ` rendered as `Ch`, `H` or `X`). Search both scripts and more than one transliteration.

**Court restructuring changed the hierarchy.** Since the 2023 reform Cyprus runs first-instance District Courts, a dedicated **Court of Appeal** as the principal appellate court for civil and commercial judgments, and a **Supreme Constitutional Court** for further appeals on limited leave. Older material refers to a single Supreme Court handling appeals — the citation structure in pre-reform judgments reflects the old system.

**Greek is the working language of the courts.** Judgments after 1988 are overwhelmingly in Greek. Machine translation handles the substance reasonably but mangles party names; verify names against the register rather than the translation.

**Filed documents are indexed, not always delivered.** The free search shows what has been filed and lets you preview much of it. Certified copies and certificates such as a Certificate of Good Standing carry a fee.

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and in which language. Anything requiring a practitioner login or an obliged-entity account should say so.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.
