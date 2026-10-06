# Awesome OSINT — Spain 🇪🇸

[![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> Company search, beneficial ownership and court search resources for Spain.
> Curated for investigators, journalists, compliance analysts and researchers.

Spain is unusual, and most guides get it wrong. **There is no free public company-of-record lookup.** The commercial registry is a network of provincial registries whose documents are sold per item, and the free public surface is a **gazette** — the BORME — which publishes every incorporation, appointment, capital change and dissolution the day it is registered.

That inverts the normal research method. **You do not look a Spanish company up; you reconstruct it from its publication trail.** Directors are not a field you read — they are the sum of appointment and revocation events published over time.

Court research runs the opposite way: CENDOJ gives free full-text access to the judgments of every collegiate court in the country, and the insolvency register is free and national.

*All links verified 2026-09-18.*

---

## Contents

- [Start here: the 60-second triage](#start-here-the-60-second-triage)
- [Identifiers: NIF, CIF, NIE and why they matter](#identifiers-nif-cif-nie-and-why-they-matter)
- [Company registry — official](#company-registry--official)
- [Understanding BORME](#understanding-borme)
- [The acts that matter, and what they tell you](#the-acts-that-matter-and-what-they-tell-you)
- [Company search — third party](#company-search--third-party)
- [Beneficial ownership](#beneficial-ownership)
- [Listed companies and significant shareholdings](#listed-companies-and-significant-shareholdings)
- [Courts — judgments and case law](#courts--judgments-and-case-law)
- [Courts — filings, notices and edicts](#courts--filings-notices-and-edicts)
- [Insolvency](#insolvency)
- [Other registers: property, assets, associations](#other-registers-property-assets-associations)
- [Cross-jurisdiction datasets](#cross-jurisdiction-datasets)
- [Worked workflows](#worked-workflows)
- [Practical notes and pitfalls](#practical-notes-and-pitfalls)
- [Contributing](#contributing)

---

## Start here: the 60-second triage

1. **[Registro Mercantil Central](https://www.rmc.es/)** — confirm the exact *denominación social*. Punctuation matters; get it right before anything else.
2. **[BORME](https://www.boe.es/diario_borme/)** — search the name; pull the full act history.
3. **[libreBORME](https://libreborme.net/)** — same data, structured, with **reverse officer lookup** the official source does not offer.
4. **[Registro Público Concursal](https://www.publicidadconcursal.es/)** — free insolvency check by name or NIF.
5. **[CENDOJ](https://www.poderjudicial.es/search/indexAN.jsp)** — free full-text judgment search.

Five free checks, no account, no fee. Only then consider a paid *nota simple* from Registradores.

---

## Identifiers: NIF, CIF, NIE and why they matter

The **NIF** (*Número de Identificación Fiscal*, formerly CIF for entities) is the natural join key across every Spanish source. It is a letter plus eight characters, and **the letter encodes the legal form** — which tells you what kind of entity you are dealing with before you read anything else.

| Letter | Entity type |
|---|---|
| `A` | Sociedad Anónima (S.A.) |
| `B` | Sociedad de Responsabilidad Limitada (S.L.) |
| `C` | Sociedad Colectiva |
| `D` | Sociedad Comanditaria |
| `E` | Comunidad de Bienes |
| `F` | Sociedad Cooperativa |
| `G` | Asociación / Fundación |
| `H` | Comunidad de Propietarios |
| `J` | Sociedad Civil |
| `N` | Entidad extranjera (foreign entity) |
| `P` | Corporación Local |
| `Q` | Organismo público |
| `R` | Congregación o institución religiosa |
| `S` | Órgano de la Administración |
| `U` | Unión Temporal de Empresas (UTE) |
| `V` | Otros tipos no definidos |
| `W` | Establecimiento permanente de entidad no residente |

Natural persons use a **DNI** (8 digits + check letter) or, for foreign nationals, a **NIE** (`X`, `Y` or `Z` + 7 digits + check letter).

**The catch: BORME does not publish the NIF.** On the free surface, the exact *denominación social* as printed in the announcement (`TELEFÓNICA, S.A.`) is effectively the identifier. Third-party providers supply the NIF, and it is what lets you pivot to tax, property and court sources.

## Company registry — official

- **[BORME — Boletín Oficial del Registro Mercantil](https://www.boe.es/diario_borme/)** — the official commercial gazette, published daily except Saturdays, Sundays and Madrid public holidays. Free, full archive, PDF and XML per announcement. **The primary free source for Spanish corporate events.**
- **[Registro Mercantil Central (RMC)](https://www.rmc.es/)** — the central registry. Free company **name** availability search and certification. Use it to pin the exact legal name; the underlying documents are provincial.
- **[Registradores / Colegio de Registradores](https://www.registradores.org/)** — the paid document service: *notas simples*, full mercantile extracts (*nota informativa*), filed annual accounts (*cuentas anuales*), and the *informe mercantil*. Per-item fees, account required.
- **[Open Data Registradores](https://opendata.registradores.org/)** — downloadable statistical datasets and microdata from the registry network. Bulk analysis, not per-company lookup.
- **Provincial Mercantile Registries** — the actual registries of record, one per province (Madrid, Barcelona, Valencia, etc.). Documents are filed and held provincially; the RMC is an index and name-reservation body, not a document repository.

## Understanding BORME

BORME is split into sections, and knowing which one you are reading is half the skill.

| Section | ID form | Contains |
|---|---|---|
| **BORME-A** | `BORME-A-YYYY-NNN-PP` | **Actos inscritos** — the per-province stream of registered acts: incorporations, appointments, revocations, capital changes, dissolutions. *The company history.* |
| **BORME-C** | `BORME-C-YYYY-NNNNN` | **Anuncios y avisos legales** — merger and spin-off notices, capital reduction announcements, general meeting convocations, global asset transfers. *The statutory announcements.* |

Both are free, both are archived, and both are retrievable as PDF and XML.

**Section A is the workhorse.** Every act is a dated delta against a company. Pull the full A-stream for a company and replay it oldest-first and you have reconstructed the board, the capital history and the corporate events — the closest thing Spain offers to a company profile.

**Section C catches the structural events.** Merger, spin-off and global-transfer notices name **several companies in one announcement**, and a single C-announcement is frequently the only free evidence linking two entities.

## The acts that matter, and what they tell you

When replaying a BORME-A stream, these are the act types worth flagging:

| Spanish act | Meaning | Why it matters |
|---|---|---|
| `Constitución` | Incorporation | Founding date; multi-founder incorporations list the *Socios* |
| `Nombramientos` | Appointments | Names directors, administrators, *apoderados* |
| `Ceses/Dimisiones` | Cessations / resignations | The other half of the board delta — **without these you will over-count directors** |
| `Revocaciones` | Revocation of powers | Often precedes a dispute |
| `Apoderamiento` | Grant of power of attorney | Names people with authority who are *not* directors |
| `Ampliación de capital` | Capital increase | May name subscribers; debt-to-equity conversions name creditors |
| `Reducción de capital` | Capital reduction | Distress signal when combined with losses |
| `Declaración de unipersonalidad` | Sole-shareholder declaration | **Effectively names the owner** |
| `Pérdida del carácter de unipersonalidad` | Loss of sole-member status | Ownership changed |
| `Cambio de denominación social` | Name change | Essential for following an entity through time |
| `Cambio de domicilio social` | Registered office change | Province change moves the registry file |
| `Fusión` / `Escisión` | Merger / spin-off | Names counterparties |
| `Transformación` | Change of legal form | S.L. ↔ S.A. |
| `Disolución` / `Extinción` | Dissolution / termination | End of life |
| `Reactivación` | Reactivation | Company brought back |
| `Cierre provisional de hoja registral` | **Provisional closure of the registry sheet** | **Strong distress signal** — the registry sheet is closed for failure to deposit annual accounts. A company in this state cannot file further acts. |

`Cierre provisional de hoja registral` is the single most under-used red flag in Spanish corporate OSINT. It is published, free, and means the company has stopped complying.

## Company search — third party

These fill the gap the official surface leaves — they parse BORME and sell or give away a company-shaped view of it.

- **[libreBORME](https://libreborme.net/)** — open-source project that parses BORME into a queryable **company-and-officer graph**. The closest thing Spain has to a free structured registry, and critically it supports **reverse officer lookup** — find every company a person has been appointed to. No official Spanish source does this.
- **[eInforma (Informa D&B)](https://www.einforma.com/)** — the largest Spanish business information provider. Company reports, financials, BORME act history, credit risk. Free basic identification, paid reports. Covers roughly 8.2 million Spanish economic agents.
- **[Axesor](https://www.axesor.es/)** — mercantile reports, filed financial statements, solvency ratings.
- **[Iberinform (Crédito y Caución)](https://www.iberinform.es/)** — company reports, directories, payment-behaviour data.
- **[Empresite (El Economista)](https://empresite.eleconomista.es/)** — free directory covering over 3 million Spanish companies. Good for name-to-NIF resolution.
- **[DatosCif](https://www.datoscif.es/)** — free company profiles with BORME announcement history. Solid free first pass.
- **[Infonif](https://infonif.economia3.com/)** — financial and commercial data on Spanish companies.

## Beneficial ownership

Spain's beneficial ownership information sits in the **Registro de Titularidades Reales**, and it is **not openly accessible**.

- Access is limited to AML-obliged entities and to requesters who can demonstrate a legitimate interest. There is no public REST API and no open lookup.
- The restriction follows the CJEU judgment in *WM and Sovim SA v Luxembourg Business Registers* (Joined Cases C-37/20 and C-601/20), which held that fully public UBO registers are a disproportionate interference with privacy rights.
- **[Open Ownership — jurisdiction map](https://www.openownership.org/en/map/)** — current comparative position.

**What you can reconstruct instead.** Spain publishes far more corporate-control data through BORME than most closed-UBO jurisdictions:

- **Sole-shareholder events** — *unipersonalidad* declarations and changes. Where a company is single-member, the gazette effectively names the owner.
- **Capital movements** — increases and reductions, including debt-to-equity conversions, often naming subscribing parties.
- **Mergers, spin-offs and global asset transfers** — participating and recipient entities named.
- **Partner entries and exits** — under LSC Arts. 346 and 350, and on *reactivación*.
- **Share transfers** — *transmisión*, *adjudicación*, *donación*, *sucesión*, *pignoración*, *embargo*.
- **Multi-founder incorporations** — the *Constitución* act and SLP transformations can carry a full *Socios* list.

**What you cannot get:** the full share register. The *Libro Registro de Socios* (S.L.) and *Libro de Acciones Nominativas* (S.A.) are company-held, never filed, and not recoverable from open sources. Replaying gazette acts gives you **control events, not a complete cap table**.

## Listed companies and significant shareholdings

For listed issuers, Spain is genuinely transparent — and this is the biggest blind spot in most Spain guides.

- **[CNMV — Comisión Nacional del Mercado de Valores](https://www.cnmv.es/)** — the securities regulator. Its public registers carry:
  - **Participaciones significativas** — significant shareholding notifications. Holders crossing statutory thresholds must disclose, and the register is **free and searchable**. This is real ownership data, publicly available, for listed Spanish companies.
  - **Directors' dealings** — *operaciones de directivos*.
  - **Información privilegiada / otra información relevante** — inside information and other material disclosures.
  - **Registro de entidades** — authorised investment firms, fund managers (SGIIC), collective investment schemes.
- **[Bolsas y Mercados Españoles (BME)](https://www.bolsasymercados.es/)** — the exchange operator; listing data and issuer information.
- **[Banco de España](https://www.bde.es/)** — registers of credit institutions, payment institutions and foreign-exchange bureaux.

If a Spanish company of interest sits under a listed parent, go to CNMV before BORME.

## Courts — judgments and case law

- **[CENDOJ — Buscador de Jurisprudencia](https://www.poderjudicial.es/search/indexAN.jsp)** — the judgment search of the Consejo General del Poder Judicial. Free, full text, covering the **Tribunal Supremo, Audiencia Nacional, Tribunales Superiores de Justicia and Audiencias Provinciales**. The single most important Spanish court tool.
- **[Consejo General del Poder Judicial (CGPJ)](https://www.poderjudicial.es/)** — the judiciary's portal: court structure, recent significant rulings, and the route into CENDOJ.
- **[Tribunal Constitucional — Buscador de Jurisprudencia](https://hj.tribunalconstitucional.es/)** — constitutional court judgments, a **separate database** searched separately. Easy to miss.
- **[European e-Justice — Spanish case law](https://e-justice.europa.eu/topics/legislation-and-case-law/national-case-law/es_en)** — orientation to what the Spanish databases contain and how they are structured.

### Searching CENDOJ well

- **Use ECLI.** Spanish judgments carry a European Case Law Identifier (`ECLI:ES:TS:2024:1234`). It is the cleanest way to cite and retrieve a specific judgment.
- **Know the court codes.** `TS` Tribunal Supremo, `AN` Audiencia Nacional, `TSJ` + region, `APX` Audiencia Provincial.
- **The Audiencia Nacional is where the big cases are.** It has jurisdiction over major economic crime, corruption, organised crime and terrorism. For corporate wrongdoing, search `AN` specifically.
- **Search in the regional language too.** Judgments from Catalonia, the Basque Country, Galicia and Valencia may be written in Catalan, Basque, Galician or Valencian. CENDOJ's full-text search is literal.

## Courts — filings, notices and edicts

- **[Sede Judicial Electrónica](https://sedejudicial.justicia.es/)** — the Ministry of Justice electronic court office. Most case-specific functions require a digital certificate or Cl@ve identity.
- **[BOE — Boletín Oficial del Estado](https://www.boe.es/)** — beyond BORME, the BOE carries **judicial edicts and public summonses** where a party could not be served personally. Free and searchable. An edict naming a company or individual is evidence of proceedings even when no judgment exists.
- **Tablón Edictal Judicial Único (TEJU)** — the single judicial edict board, published through the BOE. Useful for finding proceedings against parties who could not be located.

## Insolvency

- **[Registro Público Concursal](https://www.publicidadconcursal.es/)** — the official public insolvency register, run by the Colegio de Registradores under the Ministry of Justice. **Free.** Search by **debtor name or NIF**, or by insolvency administrator.

It covers insolvency declarations, procedural milestones, the register of qualified insolvency administrators, and — importantly — **disqualified directors** arising from insolvency proceedings. Regulated by Article 198 of the Insolvency Law.

This is one of the few Spanish sources where a NIF search works directly and returns a definitive answer. Run it on every Spanish entity in a due diligence.

## Other registers: property, assets, associations

- **[Sede Electrónica del Catastro](https://www.sedecatastro.gob.es/)** — the cadastre. Free search of property by address or cadastral reference, giving surface area, use, construction year and cadastral value. It does **not** name the owner publicly, but it establishes that a property exists and its characteristics.
- **Registro de la Propiedad** — the land registry, via [Registradores](https://www.registradores.org/). A *nota simple* names the owner and any charges. Paid, per property.
- **Registro de Bienes Muebles** — movable assets register: vehicles, aircraft, vessels, industrial machinery, and chattel mortgages. Also via Registradores.
- **Registro de Fundaciones** and **Registro Nacional de Asociaciones** — foundations and associations, which carry `G` NIFs and are frequently used alongside commercial structures.
- **[VIES VAT number validation](https://ec.europa.eu/taxation_customs/vies/)** — confirms a Spanish VAT number is valid and active EU-wide. Free, instant, and a quick sanity check on a claimed NIF.

## Cross-jurisdiction datasets

- **[OpenCorporates](https://opencorporates.com/companies/es)** — normalised Spanish company records; useful for pivoting between jurisdictions.
- **[OCCRP Aleph](https://aleph.occrp.org/)** — aggregated registries, leaks, court records and procurement data.
- **[ICIJ Offshore Leaks](https://offshoreleaks.icij.org/)** — Spanish individuals and companies appear across the offshore leak datasets.
- **[OpenSanctions](https://www.opensanctions.org/)** — sanctions, PEP and watchlist data with entity resolution.
- **[datos.gob.es](https://datos.gob.es/)** — the national open data catalogue; procurement, subsidies and sectoral registers.

---

## Worked workflows

### A. "I have a Spanish company name"

1. [RMC](https://www.rmc.es/) — pin the exact *denominación social*, including punctuation.
2. [BORME](https://www.boe.es/diario_borme/) — pull the complete act history; replay oldest-first.
3. [libreBORME](https://libreborme.net/) — same data structured, plus officer graph.
4. [DatosCif](https://www.datoscif.es/) or [Empresite](https://empresite.eleconomista.es/) — recover the **NIF**.
5. [Registro Público Concursal](https://www.publicidadconcursal.es/) — insolvency check by NIF.
6. [CENDOJ](https://www.poderjudicial.es/search/indexAN.jsp) — litigation history.
7. Paid: [Registradores](https://www.registradores.org/) *nota simple* and filed accounts if the matter justifies it.

### B. "I need to know who owns it"

1. Is any group entity **listed**? → [CNMV participaciones significativas](https://www.cnmv.es/) — real, free ownership data.
2. Search the BORME-A stream for `Declaración de unipersonalidad` — if single-member, the owner is named.
3. Look for `Ampliación de capital` acts naming subscribers, and `Constitución` acts listing *Socios*.
4. Check Section C merger and spin-off notices for parent/affiliate names.
5. Accept that a full cap table is not obtainable from open sources.

### C. "Reconstruct the board"

1. Pull every `Nombramientos` **and** every `Ceses/Dimisiones` act.
2. Sort ascending by publication date.
3. Apply appointments and removals in order. The residue is the current board.
4. Cross-check against a commercial provider — they do this reconstruction for you, and disagreements usually indicate a missed act.
5. Note `Apoderamiento` separately: attorneys hold authority without being directors.

### D. "Is this company in trouble?"

- `Cierre provisional de hoja registral` in BORME — accounts not deposited.
- Entry in [Registro Público Concursal](https://www.publicidadconcursal.es/).
- `Reducción de capital` following losses.
- Judicial edicts in the [BOE](https://www.boe.es/).
- Litigation in [CENDOJ](https://www.poderjudicial.es/search/indexAN.jsp).

---

## Practical notes and pitfalls

**Get the punctuation right.** `TELEFÓNICA, S.A.` and `TELEFONICA SA` are not the same string to these systems. Accents, commas and periods all matter. Pin the name at the RMC first.

**Reconstruct, do not look up.** The current board is the sum of published deltas, not a field you can read. Missing the `Ceses` acts is the most common error in Spanish corporate research and produces boards two or three times too large.

**CENDOJ anonymises natural persons.** Individuals' names are redacted in published judgments under data-protection rules. **Company names generally survive.** Plan name-based searching around that — you will find the company, not the individual.

**Provincial fragmentation is real.** Documents live at the provincial registry. A company that moved its *domicilio social* between provinces has its file split, and older documents remain at the former registry.

**Regional languages.** Filings and judgments from Catalonia, the Basque Country, Galicia and Valencia may be in Catalan, Basque, Galician or Valencian. Search the regional term as well as the Castilian one.

**Two surnames.** Spanish personal names carry paternal and maternal surnames. Registry and court entries may use one, both, or reorder them. Search combinations.

**BORME is daily, not real-time.** It publishes Monday to Friday excluding Madrid public holidays. An act registered today may appear days later — absence of a recent act is not evidence it did not happen.

**Beneficial ownership is genuinely closed.** No amount of BORME work substitutes for the UBO register. Be explicit in your reporting about what is inferred from control events versus what is verified ownership.

---

## Contributing

Pull requests welcome. Please keep to the scope — company search, beneficial ownership and court search — and for each addition state what the resource actually returns, whether it is free, and in what language. Anything requiring a digital certificate, Cl@ve identity or a paid account should say so.

Corrections to act-type terminology, BORME section conventions or CNMV register names are especially welcome.

## License

[CC0 1.0 Universal](../LICENSE) — public domain dedication. The linked resources remain subject to their own terms.

## Disclaimer

Every resource listed here is publicly accessible. This list is for lawful research, journalism, due diligence and compliance. Spanish judgments are anonymised for a reason; respect data-protection law when handling personal data from any of these sources.
