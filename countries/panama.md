# Awesome OSINT — Panama 🇵🇦

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search, beneficial ownership and court search resources for Panama.

Panama is the outlier in this collection. Its **Registro Público is free, online, and genuinely searchable** — you can pull incorporation deeds, directors, capital and corporate acts without a registered agent, a subscription or a legitimate-interest application. For a jurisdiction whose name became shorthand for offshore secrecy, the company layer is more open than Cayman, the BVI, Bermuda or Gibraltar.

The secrecy sits one level down. Panama's beneficial ownership system is a **private** register by statutory design, and the corporate service provider industry that builds Panamanian structures is the part that stays dark.

*All links verified 2026-09-18.*

## Contents

- [Company registry — official](#company-registry--official)
- [Company search — third party](#company-search--third-party)
- [Beneficial ownership](#beneficial-ownership)
- [Courts — judgments and case records](#courts--judgments-and-case-records)
- [Practical notes](#practical-notes)
- [Contributing](#contributing)

## Company registry — official

- [Registro Público de Panamá](https://www.registro-publico.gob.pa/) — the official public registry for companies, private interest foundations and other legal entities. **Registration is free** and, once registered, you can browse the database directly.

What you can extract: *folio*, RUC (tax identifier), registration date, related members (directors, officers, subscribers), capital, and the ability to **download public deeds** — articles of incorporation, minutes, entries and dockets for corporations and foundations. Downloading founding documents without paying a gatekeeper is rare in offshore research; use it.

## Company search — third party

- [PANADATA](https://www.panadata.net/en/organizaciones) — a searchable interface over Public Registry data, considerably easier to work with than the official portal. Also carries [Panamanian court records](https://www.panadata.net/en/expedientes_judiciales), which makes it unusual: one site covering both the corporate and judicial layers.
- [Exposing the Invisible — Panama Registry guide](https://exposingtheinvisible.org/en/databases/panama-registry/) — Tactical Tech's practical walkthrough of the registry: how to register, how the search behaves, and what the fields mean. Read this before your first search.

## Beneficial ownership

Panama's beneficial ownership system was created by **Law 129 of 17 March 2020**, establishing the *Sistema Privado y Único de Registro de Beneficiarios Finales de Personas Jurídicas* — the Private and Unique System of Registration of Beneficial Owners of Legal Persons.

The name is the point: it is **private by design**. Resident agents file beneficial ownership information for the legal persons and trusts they administer, and the **Superintendencia de Sujetos No Financieros** (Superintendence of Supervision of Non-Financial Subjects) is the supervising authority. Access is restricted; there is **no public UBO search**.

- [Transparency International — Panama corporate service providers](https://www.transparency.org/en/news/panama-corporate-service-providers-beneficial-ownership-panama-papers) — context on the gap between Panama's registration requirements and what is actually verifiable.
- [Open Ownership — jurisdiction map](https://www.openownership.org/en/map/) — current comparative position.

## Courts — judgments and case records

- [Órgano Judicial de la República de Panamá](https://www.organojudicial.gob.pa/) — the judicial branch. Supreme Court decisions, court structure and judicial information.
- **Centro de Documentación Judicial (CENDOJ Panamá)** — the judicial documentation centre, reachable from the Órgano Judicial site; holds Supreme Court and appellate decisions.
- **Registro Judicial** — the official publication of judicial resolutions.
- [PANADATA — expedientes judiciales](https://www.panadata.net/en/expedientes_judiciales) — judicial proceedings and edicts drawn from the Judicial Body, in a more tractable interface than the official portal.

All substantive material is in Spanish.

## Practical notes

**Use the free registry properly.** The combination of free registration, downloadable incorporation deeds and named directors makes Panama the most productive offshore company search in this collection. When a structure touches Panama, start there rather than treating it as a dead end.

**Directors are nominees more often than not.** Panamanian corporations require three directors, and the Panamanian service-provider industry has supplied nominee directors at scale for decades. The same handful of names recurs across thousands of companies. Treat a recurring director name as a **service-provider fingerprint** — it tells you which firm built the structure, which is real intelligence, but it does not tell you who owns it.

**Bearer shares are immobilised, not abolished.** Panama historically permitted bearer shares; they must now be held by an authorised custodian rather than circulating freely. Older structures may still reference them, and custodian records are not public.

**Private interest foundations behave differently from companies.** The *fundación de interés privado* is a Panamanian speciality used for asset holding and succession. Founding documents are registrable and obtainable from the Registro Público, but the *reglamento* — the private regulations naming beneficiaries — is not filed. You can see the foundation and not the beneficiaries.

**RUC is the join key.** The *Registro Único de Contribuyentes* number is the tax identifier and the most reliable way to match an entity across the registry, court records and third-party sources. Prefer it to the name.

**Spanish only, and names are long.** Panamanian personal names commonly carry two surnames (paternal then maternal), and registry entries may abbreviate or reorder them. Search surname combinations, not a single full-name string.

**The Panama Papers are not the registry.** Leak datasets and the Registro Público are different sources with different coverage and different reliability. Anything from a leak should be corroborated against the registry record before it is relied on.

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and in what language.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.
