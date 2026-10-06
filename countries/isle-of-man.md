# Awesome OSINT — Isle of Man 🇮🇲

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search, beneficial ownership and court search resources for the Isle of Man.

The Isle of Man is a Crown Dependency with a company registry that is free to search, an unusually informative filing index, and a court system that has published its judgments online since 2008. Beneficial ownership, as everywhere in this group, is closed.

Its distinguishing feature for researchers is the **register suffix**: a single letter on the end of every entity number tells you which statutory register the entity sits on, and therefore what kind of thing it is, before you open a single document.

*All links verified 2026-09-18.*

## Contents

- [Company registry — official](#company-registry--official)
- [Regulated entities](#regulated-entities)
- [Beneficial ownership](#beneficial-ownership)
- [Courts — judgments and case law](#courts--judgments-and-case-law)
- [Courts — the register of judgments](#courts--the-register-of-judgments)
- [Practical notes](#practical-notes)
- [Contributing](#contributing)

## Company registry — official

- [Isle of Man Companies Registry](https://services.gov.im/ded/services/companiesregistry/welcome.iom) — the statutory registry, run by the Department for Enterprise. **Free search by company name or number**, no account. Returns name, number, registry type, company type, registered office, dates of registration and incorporation, status, a presence-of-charges flag, and the filing index.
- [Companies Registry — Isle of Man Government](https://www.gov.im/categories/business-and-industries/companies-registry/) — the department's guidance pages, fees and forms.

The filing index is free to browse; **document bodies are paywalled** and purchased per filing.

## Regulated entities

- [Isle of Man Financial Services Authority](https://www.iomfsa.im/) — licensed banks, insurers, fiduciaries, fund managers and designated businesses, plus public warnings and enforcement notices.

## Beneficial ownership

- [Beneficial Ownership — Isle of Man Government](https://www.gov.im/categories/business-and-industries/companies-registry/beneficial-ownership/) — the official page on the regime.

The **Beneficial Ownership Act 2017** sets the requirements for identifying, verifying and recording the beneficial ownership of legal entities. The Isle of Man maintains a **central beneficial ownership database**, but it is **not public** — access is limited to competent authorities and to licensed corporate service providers acting in that capacity.

## Courts — judgments and case law

- [Judgments Online](https://www.judgments.im/) — **the free judgment database of the Isle of Man Courts of Justice**, launched 1 October 2008. Covers civil, criminal and appellate courts, listing judgments from **2002 onwards**, with some earlier material as PDFs. Also links to Privy Council and European Court of Human Rights judgments concerning the Isle of Man.
- [Isle of Man Courts of Justice](https://www.courts.im/) — court information, fees, forms and procedure.
- [Judicial Committee of the Privy Council](https://www.jcpc.uk/) — final court of appeal for the Isle of Man.

Paper copies of pre-2000 judgments are held at the General Registry Library and the Tynwald Library.

## Courts — the register of judgments

- [Register of Judgments and New Claims (Court Entry Books)](https://www.gov.im/about-the-government/offices/general-registry-isle-of-man-courts-and-tribunals/register-of-judgments-and-new-claims-court-entry-books/) — all judgments for claims filed after **1 September 2009** are recorded on the Register of Judgments, viewable in electronic format at the public counter of the court.
- [Registry Trust — Isle of Man](https://www.registry-trust.org.uk/court-judgments/isle-of-man) — Registry Trust maintains Isle of Man judgment records; guidance on what is held and how to obtain it.
- [TrustOnline](https://www.trustonline.org.uk/) — the public search interface over Registry Trust's judgment registers, including the Isle of Man. Paid per search.

This is a distinct record from Judgments Online: **Judgments Online carries written judgments; the Register of Judgments carries money judgments entered against parties.** A debt judgment against a company will appear on the second and usually not on the first.

## Practical notes

**Read the letter suffix first.** Every Isle of Man entity number ends in a letter identifying its statutory register, and it is mandatory in lookups — a bare number is rejected:

| Suffix | Entity type |
|---|---|
| `C` | Company under the Companies Act 1931 |
| `V` | Company under the Companies Act 2006 |
| `L` | Limited Liability Company (LLC Act 1996) |
| `F` | Foreign company (and overseas LLPs) |
| `B` | Business name |
| `M` | Foundation (Foundations Act 2011) |
| `P` | Limited Partnership (Partnership Act 1909) |
| `I` | Industrial and Provident Society |

Example: `137370C` is a 1931 Act company; `023290V` is a 2006 Act company; `031608B` is a business name and **not a legal person**.

**1931 Act versus 2006 Act matters.** The two company regimes have different disclosure and filing obligations. 2006 Act (`V`) companies are the modern, lighter-touch vehicle and are the ones you will most often meet in international structures.

**Registered agents appear on 2006 Act profiles.** `V`-suffix company profiles include a **Registered Agent** — a licensed statutory agent handling filings. The registered agent is *not* a director and *not* a shareholder, but as elsewhere offshore, the agent identifies the service provider behind the structure and clusters related entities. Other entity types omit the section.

**Officers are not public for any entity type.** Director, officer and secretary names are not publicly exposed. Change-of-director filings appear in the filing index with free metadata, but the document body is paywalled — so you can see that a directorship changed, and when, without seeing who.

**"Presence of charges" is a flag, not a list.** The profile shows a yes/no charges indicator. The charge documents themselves are paywalled, and there is no public charges register.

**An empty filing list is not an error.** A company with no filed documents has no filing index at all; that returns an empty result rather than a failure.

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and what access it requires.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.
