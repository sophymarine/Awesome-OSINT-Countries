# Awesome OSINT — Bermuda 🇧🇲

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search, beneficial ownership and court search resources for Bermuda.

Bermuda is the insurance and reinsurance capital of the offshore world, and its research profile reflects that: the financial regulator publishes a genuinely useful free register, while the company registry and the courts lag behind. Its most important corporate records — the Supreme Court Cause Book and the Register of Judgments — are **not online at all** and must be searched in person.

Bermuda also has the newest beneficial ownership statute of the major offshore centres, in force since November 2025. It is not public either.

*All links verified 2026-09-18.*

## Contents

- [Company registry — official](#company-registry--official)
- [Regulated entities](#regulated-entities)
- [Beneficial ownership](#beneficial-ownership)
- [Courts — judgments and case law](#courts--judgments-and-case-law)
- [Courts — the records that are not online](#courts--the-records-that-are-not-online)
- [Legislation](#legislation)
- [Practical notes](#practical-notes)
- [Contributing](#contributing)

## Company registry — official

- [Registrar of Companies](https://www2.gov.bm/department/registrar-companies) — the statutory registry, under the Ministry of Finance. Company verification starts here.
- [Registrar of Companies — forms and online services](https://www.gov.bm/online-services/registrar-companies-forms) — the filing and service catalogue, and the route into the public search products.

Public company information is available through the Registrar's portal and the Bermuda Government e-services platform. Access requires a registered account, and certified documents run roughly BMD 70–300 (the Bermuda dollar is pegged 1:1 to the US dollar).

## Regulated entities

- [Bermuda Monetary Authority — Search regulated entities](https://www.bma.bm/regulated-entities) — **the most useful free search in the jurisdiction.** Every entity currently licensed or registered by the BMA: insurers and reinsurers, special purpose insurers, banks, trust companies, investment businesses, fund administrators and digital asset businesses.

A large share of Bermuda-incorporated entities are exempted companies in insurance, reinsurance and investment management, all of which sit under BMA supervision — so for the majority of Bermuda vehicles that matter, the BMA register is a better first stop than the company registry.

## Beneficial ownership

- [Beneficial Ownership Act 2025](https://www.bermudalaws.bm/Laws/Consolidated%20Law/2025/Beneficial%20Ownership%20Act%202025) — the consolidating statute, **in force 3 November 2025.** It replaced the previous patchwork regime with a single Act and created a central beneficial ownership register maintained by the Registrar of Companies.
- [Beneficial Ownership Guidance Notes (PDF)](https://www.gov.bm/sites/default/files/Beneficial-Ownership-Guidance-Notes-v1.pdf) — the government's guidance on who must file what.

Most Bermuda entities must identify and verify their beneficial owners, maintain minimum prescribed information, and **file it with the Registrar for inclusion on the central register**. The register is **not publicly accessible.**

One point of OSINT interest: sections 13 and 14 of the Act empower the Supreme Court of Bermuda to resolve disputes and rectify registers, and any person aggrieved by inclusion in or omission from a register may apply to the Court. Rectification applications are court proceedings — and court proceedings generate records.

## Courts — judgments and case law

- [Court of Appeal for Bermuda](https://www.gov.bm/court-appeal) — court information, composition and sittings.
- [Bermuda Laws Online](https://www.bermudalaws.bm/) — consolidated legislation, free.
- [Judicial Committee of the Privy Council](https://www.jcpc.uk/) — final court of appeal for Bermuda. Free and fully public.

The Bermuda judiciary publishes judgments of the Supreme Court and Court of Appeal online back to roughly 2007. Coverage before that is patchy; CariLaw and vLex Justis (both subscription) hold the deeper Commonwealth Caribbean case-law archive including Privy Council, Court of Appeal and Supreme Court material.

## Courts — the records that are not online

This is the part worth knowing, because it is easy to conclude wrongly that nothing exists.

At the **Registry of the Supreme Court**:
- The **Cause Book** records any cause of action commenced against a Bermuda company.
- The **Register of Judgments** records judgments entered against a company.

**Neither is available online.** Both must be searched in person, for a nominal fee. For due diligence on a Bermuda entity this is frequently the decisive record, and an online-only search will miss it entirely. If a matter justifies it, instruct a local agent to attend the Registry.

## Legislation

- [Bermuda Laws Online](https://www.bermudalaws.bm/) — the Companies Act 1981, the Beneficial Ownership Act 2025 and the insurance legislation are all here, free and consolidated.

## Practical notes

**Exempted companies dominate.** Most Bermuda entities of interest are "exempted" — permitted to operate from Bermuda but not to trade locally. Exempted status is normal for the jurisdiction and is not itself a red flag.

**The BMA register is the free shortcut.** Before paying for a registry search, check whether the entity is BMA-regulated. If it is, you get existence, licence class and current status for nothing.

**Segregated accounts change what "the company" means.** Bermuda makes heavy use of segregated accounts companies (SACs) and special purpose insurers, where liabilities are ring-fenced per account. The registered entity may be a shell around many economically separate cells. Identify the cell, not just the company.

**In-person records are a real gap, not an absence of litigation.** See above. Treat "no judgments found online" as unverified.

**Currency.** BMD is pegged 1:1 to USD, so quoted fees translate directly.

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and what access it requires. Records that can only be searched in person should say so explicitly; that information is as useful as a link.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.
