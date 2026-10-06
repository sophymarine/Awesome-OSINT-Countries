# Awesome OSINT — Jersey 🇯🇪

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search, beneficial ownership and court search resources for Jersey.

Jersey is a Crown Dependency and a major trust and fund jurisdiction. It has run a **central beneficial ownership register since 1989** — decades before the concept became an international standard — and it is still not public. What is public is a free company search at the financial regulator, and an unusually good free case-law archive maintained by the Jersey Legal Information Board.

*All links verified 2026-09-18.*

## Contents

- [Company registry — official](#company-registry--official)
- [Beneficial ownership](#beneficial-ownership)
- [Courts — judgments and case law](#courts--judgments-and-case-law)
- [Insolvency and bankruptcy](#insolvency-and-bankruptcy)
- [Practical notes](#practical-notes)
- [Contributing](#contributing)

## Company registry — official

- [JFSC Companies Registry — Public Search](https://sir.jerseyfsc.org/pages/PublicSearch.aspx) — **free public search, no account.** The Jersey Financial Services Commission is both the regulator and the registrar, so one body covers company registration and financial supervision.
- [Jersey Financial Services Commission](https://www.jerseyfsc.org/) — the regulator: registry services, licensed financial services businesses, public statements and enforcement notices.
- [gov.je](https://www.gov.je/) — States of Jersey government portal; the policy and consultation material behind the registry rules lives here.

## Beneficial ownership

Jersey has maintained a **central register of beneficial ownership since 1989**, now operated by the JFSC under the Disclosure (Jersey) Law 2008 and subsequent legislation. All Jersey-incorporated entities must identify and report their beneficial owners, with **updates filed within 21 days of any change** — a notably tight deadline by international standards.

**Access is restricted** to competent authorities and to obliged entities performing customer due diligence. There is no public lookup.

The practical implication is that Jersey's data quality is high and its accessibility is low: the information exists, is current, and is verified at the point of entry by regulated trust and company service providers — you simply cannot see it.

- [JFSC guidance on beneficial owners](https://www.jerseyfsc.org/) — current guidance on the reporting obligations; search the site for "beneficial ownership".
- [Open Ownership — jurisdiction map](https://www.openownership.org/en/map/) — comparative state of play.

## Courts — judgments and case law

- [Jersey Law — Jersey Legal Information Board](https://www.jerseylaw.je/) — **the primary case-law resource.** Freely accessible content includes many **unreported judgments from 1995 onwards** and Jersey Employment and Discrimination Tribunal judgments from 2005 onwards, plus enacted Laws, the revised edition of the Laws, and unofficial English translations of some Laws originally made in French.

Registration is required for: Jersey Judgments 1950–1984, the **Jersey Law Reports from 1985 onwards** (updated quarterly), some unreported judgments, the library of legal books and texts, and annotated Laws.

- [Royal Court of Jersey](https://www.courts.je/) — the Royal Court is the principal court, sitting in various configurations (Samedi, Inferior Number, Superior Number) with Jurats as judges of fact. Court information, practice directions and sittings.
- [Judicial Committee of the Privy Council](https://www.jcpc.uk/) — final court of appeal for Jersey.

## Insolvency and bankruptcy

Jersey insolvency uses distinctive local procedures — **désastre** (declaration of an en désastre by the Royal Court, administered by the Viscount) and **winding up**. The Royal Court record confirms whether a company has been declared bankrupt and the date.

- [Viscount's Department](https://www.gov.je/) — administers désastre proceedings; search gov.je for "Viscount" and "désastre".

## Practical notes

**One body does registry and regulation.** The JFSC being both registrar and financial regulator means a single search surface covers company existence and licensed status. Check both sides — an entity may be registered but not licensed for the activity it claims.

**Customary law, French terminology.** Jersey law descends from Norman customary law. Expect French-derived terms throughout the court record: *désastre*, *dégrèvement*, *Jurats*, *Samedi*, *en désastre*, *remise de biens*. Search the French term, not an English paraphrase.

**Trusts are invisible.** Jersey is a trust jurisdiction above all, and Jersey trusts are **not registered** anywhere public. A Jersey company in a structure is frequently a trustee or an underlying company of a trust whose settlor and beneficiaries appear on no register at all. The absence of a trust register is the central limitation of Jersey OSINT.

**21-day update rule means the data is current — for those who can see it.** When you obtain beneficial ownership information through a lawful channel, it is likely to be genuinely up to date, unlike jurisdictions with annual-confirmation-only regimes.

**Judgments are the open flank.** As with the other offshore centres, litigation is where structures become visible. The free 1995-onwards unreported judgment set on jerseylaw.je is searchable by party name and is the best starting point.

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and what access it requires.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.
