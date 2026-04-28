---
titel: Konsistenz-Korrekturen vor Anwalts-Termin 4. Mai 2026
datum: 2026-04-28
zweck: Dokumentation der Vorab-Korrekturen an AGB / Datenschutz / Webseite, die zwischen V2.1 (Bedrock-Stand) und V2.2 (Konsistenz-Korrekturen) eingearbeitet wurden — Diskussionsgrundlage für den Anwalts-Termin
status: 🟡 VORAB-UMGESETZT (passwortgeschützte Seiten — endgültiger Sign-Off folgt am 4.5.)
---

# Konsistenz-Korrekturen vor Anwalts-Termin 2026-05-04

## Hintergrund

Bei einer internen Konsistenz-Prüfung am 28. April 2026 wurden mehrere Inkonsistenzen zwischen den öffentlichen Webseiten-Aussagen (RC-Tech-Webseite, EHB-Marketing-Seite) und den Compliance-Vorgaben aus dem Anwalts-Briefing 2026-05-04 identifiziert. Da die Seiten passwortgeschützt sind (kein öffentlicher Zugriff), wurden die Korrekturen vorab eingespielt — Sign-Off folgt am Anwalts-Termin.

## Zusammenfassung der Änderungen

| Bereich | Datei(en) | Änderung |
|---|---|---|
| RC-Tech Webseite (Hauptseite) | `de.html`, `en.html`, `fr.html`, `it.html`, `es.html`, `sr.html` | "Internationale Kunden — USA, EU, Schweiz" entfernt → "Europäische Kunden — Schweiz, EU, Liechtenstein" |
| RC-Tech Webseite (Hauptseite) | `de.html`, `en.html`, `fr.html`, `it.html`, `es.html`, `sr.html` | Neue Service-Card "KI-Integration" als 7. Service ergänzt |
| RC-Tech AGB | `agb.html` §1 | **Räumlicher Geltungsbereich:** US-Kunden-Ausschluss als eigener Absatz aufgenommen (Versicherungs-Auflage) |
| RC-Tech AGB | `agb.html` §3 | Leistungsbereich "KI-Integration" als eigener Bullet aufgenommen |
| RC-Tech AGB | `agb.html` §10 | Anthropic als Sub-AVV via AWS Bedrock qualifiziert (kein eigenständiger Drittanbieter mehr) |
| RC-Tech AGB | `agb.html` §13 | Subunternehmer-Klausel um AVV-Hinweis und Widerspruchsrecht (Art. 28 DSGVO) ergänzt |
| RC-Tech AGB | `agb.html` §3 (Iteration 2, V2.4) | KI-Integration provider-agnostisch formuliert: AWS Bedrock EU bevorzugt für Eigenprodukte, bei Kundenprojekten projekt-individuell (z. B. Bedrock EU, Azure OpenAI EU, Vertex AI EU, lokale Modelle) |
| RC-Tech AGB | `agb.html` Stand-Zeile | V2.1 → V2.3 → **V2.4**, Datum 26.4. → 28.4. |
| RC-Tech Webseite | `de/en/fr/it/es/sr.html` Service-Card (Iteration 2) | Tag-Liste auf "LLMs · EU-Hosting · Workflow-Audit · DSGVO" neutralisiert (Claude/Bedrock raus). "Mehr erfahren →"-Link auf `ki-integrationen.html` ergänzt. CSS für `.svc-link` hinzugefügt. |
| RC-Tech Webseite | `de/en/fr/it/es/sr.html` Footer (Iteration 2) | KI-Integration als Eintrag in Services-Footer-Block ergänzt (sprachspezifisch übersetzt) |
| RC-Tech Landingpage | `ki-integrationen.html` Stack-Sektion (Iteration 2) | Vier KI-Modell-Optionen statt nur Claude: Claude (Bedrock-EU bevorzugt), OpenAI über Azure EU, Gemini über Vertex EU, lokale/Open-Source-Modelle |
| RC-Tech Landingpage | `ki-integrationen.html` Hero-Trust-Zeile (Iteration 2) | "AWS Bedrock EU-Region" → "EU-Hosting für Modelle und Daten" / "Modell-Wahl projekt-individuell" |
| Cleanup | `agb.pdf`, `datenschutz.pdf` | **Gelöscht** (waren V2.0-Stände vom 24.4., nicht synchron mit HTML — Quelle der Wahrheit ist das HTML) |
| Firmenunterlagen-Snapshots | `Firmenunterlagen/Recht/Compliance/Webseiten/STALE-NOTICE-2026-04-28.md` | **Neu:** STALE-Notiz über veraltete Snapshot-PDFs in den Firmenunterlagen — diese müssen vor 4.5. mit dem PDF-Generator regeneriert werden |
| RC-Tech Datenschutz | `datenschutz.html` §6 | Hinweis auf produktspezifische Sub-Auftragsverarbeiter (Twilio, Google, Microsoft, Meta, fiskaly) für EHB-Kontext ergänzt |
| RC-Tech Datenschutz | `datenschutz.html` Stand-Zeile | V2.1 → V2.2, Datum 26.4. → 28.4. |
| RC-Tech Webseite (NEU) | `ki-integrationen.html` | **Neu erstellt:** Standalone-Landingpage für KI-Integration als Vorbereitung der späteren Domain-Redirects (ai-integrationen.ch, ki-integrationen.ch, ai-hilfe-schweiz.ch, ki-hilfe-schweiz.ch). Aktuell verlinkt im Footer der Hauptseite, noindex/nofollow/noarchive aktiv. |
| EHB Marketing-Seite | `easyandsmartbooking-webseite/src/pages/marketing/TermsPage.tsx` §1 | **Räumlicher Ausschluss:** US-Kunden-Klausel ergänzt (analog zu RC-Tech §1) |
| EHB Marketing-Seite | `easyandsmartbooking-webseite/src/pages/marketing/TermsPage.tsx` §10 | Drittanbieter-Liste konsistent auf alle relevanten Anbieter erweitert (AWS, Anthropic, Hetzner, IONOS, Twilio, fiskaly) |
| EHB Marketing-Seite | `easyandsmartbooking-webseite/src/pages/marketing/TermsPage.tsx` Stand-Zeile | V3 → V3.2 |
| EHB Marketing-Seite | `easyandsmartbooking-webseite/src/pages/marketing/PrivacyPage.tsx` §2 | "Kein Profiling"-Aussage präzisiert auf Art. 22 DSGVO; Customer-Brain als Mensch-im-Loop transparent benannt (Konsistenz mit §13) |
| EHB Marketing-Seite | `easyandsmartbooking-webseite/src/pages/marketing/PrivacyPage.tsx` Stand-Zeile | V3 → V3.2 |

## Detaillierte Änderungen

### 0) RC-Tech AGB §1 + EHB AGB §1 — US-Kunden-Ausschluss

**Hintergrund:** Die Schweizer Berufs-/Cyber-Versicherung verbietet US-Kunden als Vertragspartner (Klage-Risiko). Bisher stand das nirgends in den AGB — nur die Webseiten-Aussage wurde in V2.2 angepasst. In V2.3 (RC-Tech) bzw. V3.2 (EHB) ist der Ausschluss jetzt vertraglich verankert.

**RC-Tech AGB §1, neuer Absatz vor "Abweichende Bedingungen":**
> **Räumlicher Geltungsbereich:** RC-Tech bedient keine Kunden mit Sitz oder Rechtsform in den Vereinigten Staaten von Amerika (USA). Bestellungen oder Anfragen aus den USA werden nicht angenommen; ein Vertragsverhältnis kommt in diesem Fall nicht zustande.

**EHB AGB §1, analoger Absatz:**
> Räumlicher Ausschluss: Die Plattform und alle damit verbundenen Dienstleistungen werden Kunden mit Sitz oder Rechtsform in den Vereinigten Staaten von Amerika (USA) nicht angeboten. Registrierungen oder Bestellungen aus den USA werden nicht angenommen; ein Vertragsverhältnis kommt in diesem Fall nicht zustande.

**Anwalts-Termin nicht mehr nötig** für diese Klausel — die Versicherungsauflage ist Fakt, der Anwalt würde nur formulieren. Wir tragen die Klausel selbst ein und lassen den Anwalt am 4.5. nur die Formulierung gegenprüfen.

### A) RC-Tech Webseite — US-Kunden-Bezug entfernt

**Hintergrund:** Die Schweizer Cyber-/Betriebsversicherung verbietet US-Kunden als Vertragspartner (Klage-Risiko). Die bisherige Bewerbung von US-Kunden auf der Webseite stand im Widerspruch zur internen No-US-Customers-Policy (Memory `project_no_us_customers_policy.md`).

**Vorher** (z. B. `de.html:425`):
```html
<div class="exp-cat">Internationale Kunden</div>
<div class="exp-desc">USA, EU, Schweiz — SLA-basierte Hosting-Verträge, Multi-Currency Billing</div>
```

**Nachher:**
```html
<div class="exp-cat">Europäische Kunden</div>
<div class="exp-desc">Schweiz, EU, Liechtenstein — SLA-basierte Hosting-Verträge, mehrsprachig (DE/EN/FR/IT/ES)</div>
```

Analog in allen 6 Sprachversionen (de/en/fr/it/es/sr) jeweils sprachgerecht übersetzt.

### B) RC-Tech Webseite — KI-Integration als 7. Service-Card

**Hintergrund:** Die Über-uns-Section beschreibt zwar wie wir intern mit KI arbeiten ("KI ist unser Kaffee"), die Service-Section nennt aber bisher keine KI-Integration als Kunden-Leistung — Mismatch zur tatsächlichen Geschäftsstrategie.

Eine neue Service-Card mit Sparkles-Icon wurde nach "Beratung & Architektur" ergänzt:

- **Titel:** KI-Integration / AI Integration / Intégration IA / Integrazione IA / Integración de IA / AI integracija
- **Beschreibung:** "LLMs in echte Workflows integrieren. Mit Datenschutz-Architektur, EU-Hosting und nachvollziehbaren Ergebnissen. Pragmatisch und auf Dauer wartbar."
- **Tags:** Claude · Bedrock-EU · Workflow-Audit · DSGVO

### C) RC-Tech AGB §3 — KI-Integration als Leistung aufgenommen

**Vorher:** Aufzählung Softwareentwicklung / Cloud-Infrastruktur / SaaS-Hosting / Beratung / Wartung & Support.

**Nachher:** Neuer Bullet zwischen "Beratung" und "Wartung":
> **KI-Integration:** Einbindung von Large-Language-Modellen (LLMs) in bestehende Workflows, Prompt-Engineering, Datenschutz-Architektur, Anbindung über AWS Bedrock in der EU-Region `eu-central-1`

### D) RC-Tech AGB §10 — Anthropic-Qualifizierung in der Drittanbieter-Liste

**Vorher:** "Drittanbieter (Hetzner, IONOS, Infomaniak, Gcore, Stripe, AWS, Anthropic, SMS-Provider etc.)"

Anthropic war hier als eigenständiger Drittanbieter gelistet — das passte nicht zur §14-Aussage "kein direkter Datenfluss in die USA" nach Bedrock-EU-Umstellung.

**Nachher:** "Drittanbieter und ihre Sub-Auftragsverarbeiter (insbesondere Hetzner, IONOS, Infomaniak, Gcore, Stripe, AWS Europe SARL inkl. der über AWS Bedrock bezogenen KI-Modelle der Anthropic PBC, SMS- und E-Mail-Provider)"

### E) RC-Tech AGB §13 — Subunternehmer-Klausel um AVV-Hinweis ergänzt

**Hintergrund:** Art. 28 Abs. 2 DSGVO verlangt bei Auftragsverarbeitung eine Vorab-Information bei Wechsel von Sub-Auftragsverarbeitern mit Widerspruchsrecht. Die ursprüngliche Klausel deckte nur den allgemeinen Werkvertrags-Fall ab.

**Ergänzter Absatz:**
> Soweit im Rahmen der vertraglichen Leistungen personenbezogene Daten im Auftrag des Kunden verarbeitet werden (Auftragsverarbeitung gemäss Art. 28 DSGVO bzw. Art. 9 DSG), erfolgt der Einsatz und Wechsel von Sub-Auftragsverarbeitern nach Massgabe des jeweiligen Auftragsverarbeitungsvertrags (AVV). RC-Tech informiert den Kunden vorab über geplante Änderungen am Bestand der Sub-Auftragsverarbeiter und räumt ihm die Möglichkeit zum Widerspruch innerhalb einer angemessenen Frist ein.

### F) RC-Tech Datenschutz §6 — Hinweis auf produktspezifische Sub-Prozessoren

**Hintergrund:** Auf der Dachseite (RC-Tech) sind nur 8 Sub-Prozessoren gelistet, im Anwalts-Briefing aber 14 (inkl. Twilio, Google, Microsoft, Meta, fiskaly — diese sind EHB-spezifisch). Damit ein Kunde nicht den Eindruck einer unvollständigen Liste bekommt, wurde am Ende von §6 ein Verweis auf produktspezifische AVVs ergänzt.

**Ergänzter Absatz:**
> **Hinweis zu produktspezifischen Sub-Auftragsverarbeitern:** Für einzelne Dienstleistungen und Produkte (insbesondere die SaaS-Plattform EasyAndSmartBooking) können weitere Sub-Auftragsverarbeiter zum Einsatz kommen, etwa für SMS-/E-Mail-Versand (z. B. Twilio Inc., Irland), Kalender-Synchronisation (Google Ireland, Microsoft Ireland), Messaging (Meta Platforms Ireland) oder Fiskal-Signaturen (fiskaly GmbH, Wien). Die jeweils aktuelle und produktspezifische Liste wird im zugehörigen Auftragsverarbeitungsvertrag (AVV) und in der Datenschutzerklärung des betreffenden Produkts offengelegt.

### G) EHB AGB §10 — Drittanbieter-Liste konsistent gemacht

**Hintergrund:** §6 listet korrekt AWS, Anthropic, Hetzner, IONOS und alle anderen Sub-Prozessoren — §10 erwähnte aber nur "Stripe, SMS-Provider" als Haftungs-Ausschluss-Kandidaten. Inkonsistent: Ein Kunde könnte argumentieren, ein AWS-Ausfall sei nicht von der Befreiung gedeckt.

**Vorher:** "Schäden die durch Drittanbieter (z.B. Stripe, SMS-Provider), höhere Gewalt oder unsachgemässe Nutzung..."

**Nachher:** "Schäden, die durch Drittanbieter und ihre Sub-Auftragsverarbeiter (insbesondere Hetzner Online GmbH, IONOS SE, Infomaniak Network SA, Gcore S.à r.l., AWS Europe SARL inkl. der über AWS Bedrock bezogenen KI-Modelle der Anthropic PBC, Stripe Payments Europe Ltd., Twilio Inc. und weitere SMS-/E-Mail-Provider, fiskaly GmbH), durch höhere Gewalt oder durch unsachgemässe Nutzung..."

### H) EHB Datenschutz §2 — Customer-Brain-Konsistenz

**Hintergrund:** §2 sagte absolut "Wir nutzen Daten nicht für Profiling" — §13 beschreibt aber das Customer-Brain (KI-gestützte CRM-Profil-Zusammenfassung). Drift 2.4 aus den Anwalts-Konsistenz-Hinweisen 2026-05-04.

**Vorher:** "Wir verkaufen keine Daten. Wir nutzen Daten nicht für Profiling oder Werbe-Targeting."

**Nachher:** "Wir verkaufen keine Daten und nutzen sie nicht für Werbe-Targeting. Eine automatisierte Entscheidungsfindung mit rechtlicher oder ähnlich erheblicher Wirkung im Sinne von Art. 22 DSGVO findet nicht statt. Die KI-gestützte CRM-Profil-Zusammenfassung («Customer-Brain», siehe Ziff. 13) liefert pseudonymisierte Hinweise für das Salon-Personal als Mensch-im-Loop — die finale Entscheidung trifft stets eine natürliche Person, kein automatisierter Beschluss."

## Was am 4.5. mit dem Anwalt zu klären ist

1. **Art. 22 DSGVO und Customer-Brain:** Die neue §2-Formulierung schliesst Art. 22 explizit aus, weil eine natürliche Person die Empfehlung verwendet. Anwalt soll bestätigen, ob das ausreicht oder ob eine zusätzliche Einwilligung erforderlich ist.
2. **US-Kunden-Klausel — formale Gegenprüfung:** Klausel in §1 (RC-Tech und EHB) ist eingebaut. Anwalt soll nur Formulierung und Platzierung absegnen; die Auflage selbst kommt nicht von ihm.
3. **Sub-Auftragsverarbeiter-Wechsel-Mechanik (RC-Tech AGB §13):** Die Frist für Widerspruch ist als "angemessene Frist" formuliert — Anwalt kann konkretisieren (z. B. 30 Tage).
4. **Konsistenz Subprozessor-Liste:** RC-Tech Datenschutz §6 verweist auf produktspezifische AVVs für die zusätzlichen 6 Anbieter. Anwalt soll bestätigen, ob das transparenz-rechtlich ausreichend ist (Art. 13 DSGVO).
5. **EHB §13 listet 7 Use-Cases — Audit identifiziert 14:** Bestehende offene Drift 2.2, in dieser Iteration nicht angefasst (gehört in Anwalts-Diskussion).
6. **CLOUD-Act-Risiko bei US-Konzern-Töchtern:** Stripe Ireland, Twilio Ireland, Google Ireland, Microsoft Ireland, Meta Ireland — alle EU-Vertragspartner, aber US-Konzern-Mütter. Anwalts-Frage 4 im Briefing 2026-05-04, ob SCCs ausreichen oder ob TIA pro Anbieter dokumentiert werden muss.

## Workflow nach 4.5.

1. Anwalts-Korrekturen (falls vorhanden) einarbeiten
2. Stand-Zeile umstellen auf *"Stand: 4. Mai 2026 · Version 2.3 (kanzleigeprüft)"* für RC-Tech bzw. *"Version 3.2 (kanzleigeprüft)"* für EHB
3. Snapshots in `Quellen/Recht/Compliance/Webseiten/` erneut spiegeln
4. Alte PDFs (`agb.pdf`, `datenschutz.pdf` im Repo-Root vom 24.4., V2.0-Stand) aus aktuellem HTML neu drucken oder löschen
5. CHANGELOG-Datei archivieren in `_archive/2026-04-Konsistenz-Sprint/`

## Nicht in dieser Iteration umgesetzt (bewusst offen für Anwalts-Diskussion)

- Drift 2.2 (EHB §13 listet nur 7 von 14 KI-Use-Cases)
- Drift 2.3 (DPF-Restbehandlung — bereits in V2.1/V3 mit Bedrock weitgehend gelöst)
- AVV-Diff-Korrekturen A/B/C/D (sind im AVV-Vorschlag, nicht in den öffentlichen Webseiten-Texten)

## Landingpage `ki-integrationen.html` — Vorbereitung Domain-Redirects

Die neue Standalone-Landingpage liegt im Repo-Root als `ki-integrationen.html`. Sie ist im Stil der Hauptseite gehalten (gleiche Typografie, gleiche Farb-Palette, Sparkles-Akzent für KI), aber fokussiert auf eine Single-Purpose-Erzählung:

- Hero mit klarer Positionierung
- Sechs Use-Case-Cards (Chatbot, Übersetzungen, Dokument-Analyse, Workflow-Automation, Wissens-Suche, Code-Assistenz)
- Vier-Schritte-Prozess (Audit → Pilot → Integration → Betrieb)
- Stack-Sektion (Claude über AWS Bedrock EU + EU-Hosting-Stack)
- Drei "Warum"-USPs (Engineering-Fokus, EU-First, Transparenz)
- Kontakt-CTA + Footer mit Verlinkung zur Hauptseite

**Status:** Datei ist live im Repo, aktuell durch das Repository-weite Fort-Knox-Setup geschützt (noindex/nofollow/noarchive Meta-Tags).

**Geplante Domain-Strategie (nicht Teil dieser Iteration):**
Sobald die GmbH notariell beglaubigt und das Fort-Knox-Setup aufgehoben ist, sollen die folgenden Domains via 301-Redirect auf `https://rc-tech-solutions.com/ki-integrationen.html` umgeleitet werden:

- `ai-integrationen.ch`
- `ki-integrationen.ch`
- `ai-hilfe-schweiz.ch`
- `ki-hilfe-schweiz.ch`

Übersetzungen (EN/FR/IT/ES/SR) werden nachgezogen, sobald der DE-Inhalt finalisiert ist. Bis dahin nur DE-Version aktiv.

## Iteration 10 — Service-Landingpages + Dropdown-Menu (29.04. nachts)

Strategische Erweiterung umgesetzt: 3 neue Service-Landingpages plus Dropdown-Navigation.

**Neue Landingpages (DE-Master, andere Sprachen folgen nach Inhalts-Sign-off):**

| Page | URL | Living-Proof-Story |
|---|---|---|
| Compliance &amp; Datenschutz | `/compliance.html` | Eigene RC-Tech-Datenschutzerklärung als Beispiel |
| Softwareentwicklung | `/softwareentwicklung.html` | EHB als Showcase (220+ Features, Multi-Tenant, KI) |
| Cloud Engineering | `/cloud-engineering.html` | Eigener EU-Stack-Aufbau (Hetzner, Infomaniak, IONOS, Gcore) |

**Pricing-Anker auf jeder Landingpage:**
- Compliance: Audit ab CHF 6&apos;000 / Template-Pack ab CHF 3&apos;500 / Spot-Beratung CHF 240/h
- Softwareentwicklung: Discovery ab CHF 1&apos;800
- Cloud Engineering: Migration-Assessment ab CHF 3&apos;800 / Migration Klein 8-15k / Mid 20-50k

**Hauptseite-Updates (alle 6 Sprachen):**
- Service-Cards mit "Mehr →"-Links zu allen 4 Service-Landingpages (Software, Cloud, KI, Compliance)
- Beratung &amp; Architektur, SaaS-Hosting, Wartung &amp; Support bleiben Service-Cards ohne Detail-Page (überschneiden sich, sind self-contained, oder gehören zu Saasiro-Stealth)
- Top-Menu Dropdown: Services ▾ → Software / Cloud / KI / Compliance / "Alle Services im Überblick"
- Mobile-Burger: flache Liste mit Section-Headers
- Footer-Services-Block: alle 4 Landingpages + Beratung-Anker

**Tech:**
- CSS-only Dropdown (Hover + Focus, keine JS), keyboard-accessible
- sitemap.xml um 3 neue URLs erweitert
- CHANGELOG dokumentiert Iteration 10

**Ehrlich-Bremsen-Notiz:**
4 Landingpages (mit KI-Integration) statt ursprünglich diskutierten 6. Beratung &amp; Architektur als Anker-Section auf Hauptseite (überschneidet sich mit anderen Services). Tech-DD bleibt opportunistisch, ohne eigene Page. Buchungssystem-Beratung: weggelassen (potenzieller COI mit EHB-Marke).

## Iteration 9 — SEO-Phase-A + Cloud Engineering Rename + Landingpage-Briefing (29.04. nachts)

Strategische Erweiterung: Service-Landingpages für SEO. Recherche durch interne Strategie-Dokumente (Consulting-Strategie 2026, Marketing-Fahrplan 2026) ergab klare Service-Mappings und Pricing-Bereiche.

**Phase A SEO-Basics umgesetzt** (alle 6 Sprachen + KI-Landingpage):
- Meta-Description sprachgerecht erweitert (war zu generisch)
- Keywords-Tags
- canonical URLs
- hreflang Cross-Linking aller Sprachversionen
- Open Graph Tags (Social-Sharing für LinkedIn/Twitter/WhatsApp)
- Twitter Card Tags
- JSON-LD Schema.org (Organization + ProfessionalService auf de.html als Master)
- Service-Schema auf ki-integrationen.html
- sitemap.xml erstellt mit allen URLs + hreflang-Mapping
- robots.txt mit Sitemap-Referenz erweitert (bleibt Fort-Knox bis Launch)

**Cloud Engineering Rename**:
- "Cloud-Infrastruktur" → "Cloud Engineering" in allen 6 Sprach-HTMLs (Service-Card + Expertise-Section + Footer)
- AGB §3: Bullet umbenannt + um "Migration auf EU-Provider" erweitert
- ki-integrationen.html Footer: ebenfalls umbenannt
- AGB §1 Geltungsbereich: "Cloud-Infrastruktur" → "Cloud Engineering"

**Landingpage-Briefing erstellt** (`BRIEFING-Landingpages-2026-04-28.md`):
- Service-Mapping (Webseite-Cards ↔ Consulting-Strategie Service-Lines)
- 4 vorgeschlagene Landingpages (Softwareentwicklung, Cloud Engineering, Beratung & Architektur, Compliance) mit Strukturvorschlag und Pricing-Hinweisen aus Recherche
- Konkrete Briefing-Fragen (A1-A4, B1-B4, C1-C4, D1-D4) für Inhalts-Erstellung
- Strategische Fragen (E: Buchungssystem-Beratung als 5. Page? F: Tech-DD eigene Page? G: Menu Dropdown vs. Anker?)

EHB-SEO-Basics noch ausstehend — wird nach User-Feedback zu den Landingpages gemacht.

## Iteration 8 — Detail-Audit-Fixes (28.04. spät nachts, Audit-Pass)

Systematischer Audit gegen fünf Kriterien (DSGVO / Schweizer Recht / Behauptung-vs-Wissen / EHB-RC-Tech-Trennung / Doku-Konsistenz). Sechs Fixes identifiziert und eingebaut:

**Iteration 8 — Änderungen:**

| Bereich | Datei | Änderung |
|---|---|---|
| RC-Tech AGB §4 | `agb.html` | Fester Stundensatz CHF 160 entfernt → "projekt-individuell vereinbarte Stunden- oder Tagessätze gemäss Einzelvertrag oder aktuellem Angebot". Beratungssätze sind nicht standardisiert |
| RC-Tech AGB §14 | `agb.html` | Restrukturiert von 2 auf **3 Wege** (analog zu Datenschutz §14): 14.1 Pair-Programming, 14.2 Eigene SaaS-Produkte, 14.3 NEU: Kundenprojekte mit projekt-individueller Modell-Wahl |
| RC-Tech AGB | `agb.html` Stand-Zeile | V2.6 → **V2.7** |
| RC-Tech Datenschutz §4 | `datenschutz.html` | "Sämtliche Haupt-Anbieter ISO 27001 zertifiziert" → präzise: "Wesentliche Infrastruktur-Anbieter (Hetzner, Infomaniak, IONOS, AWS) sind ISO/IEC 27001 zertifiziert. Weitere Sub-Auftragsverarbeiter erfüllen branchenübliche Standards" — keine Pauschal-Behauptung mehr |
| RC-Tech Datenschutz §10 | `datenschutz.html` | Neuer Geltungsbereich-Absatz am Anfang: TOM gelten für produktive SaaS-Plattformen, NICHT für die statische rc-tech-solutions.com-Webseite (für die gelten TLS/HSTS aus §7 und Server-Log-Anonymisierung aus §12) |
| RC-Tech Datenschutz §14.1 | `datenschutz.html` | DPF-Wording robuster gegen Wegfall: SCCs sind primäre Rechtsgrundlage, DPF nur "soweit aufrechterhalten" als zusätzlich. Bei Schrems-III-Wegfall fällt die Datenschutzerklärung nicht in sich zusammen |
| RC-Tech Datenschutz | `datenschutz.html` Stand-Zeile | V2.5 → **V2.6** |
| EHB AGB §4 | `TermsPage.tsx` | "Stripe, Inc. bzw. verbundene Gesellschaft" → "Stripe Payments Europe Ltd. (Dublin, Irland) bzw. verbundene EU-Gesellschaft" — konsistent zu §6, kein versehentlicher US-Datenfluss-Eindruck |
| EHB AGB | `TermsPage.tsx` Stand-Zeile | V3.4 → **V3.5** |

**Was im Audit als sauber bestätigt wurde** (keine Änderung nötig):
- Subprozessor-Liste vollständig und gruppiert (V2.5 §6)
- Aufbewahrungsfristen sauber differenziert (6 Kategorien)
- IP-Modelle (3 Stufen) konsistent
- Haftungs-Klausel mit Erfüllungsgehilfen-Anerkennung (V2.6)
- Customer-Brain als Mensch-im-Loop / Art. 22 DSGVO
- US-Kunden-Ausschluss in beiden AGB §1
- Voice Agent als "in Vorbereitung" markiert
- Querverweise (6.2, 4, 14, 6.6) funktionieren alle
- EHB ↔ RC-Tech sauber getrennt (Eigenprodukt vs. Dachfirma)
- Zukunftsklauseln in §6.6 (RC-Tech) und §6/§13 (EHB) → erlauben neue Produkte/Subprozessoren ohne AGB-Update

**Audit-Bestätigung:**
1. ✅ DSGVO-konform — alle Verarbeitungs-Tätigkeiten dokumentiert mit Rechtsgrundlagen
2. ✅ Schweizer Recht — kein Verstoss gegen OR Art. 100 (zwingend), Art. 101 (Erfüllungsgehilfe), revDSG
3. ✅ Wissen statt Behauptung — pauschale Aussagen präzisiert, ISO-27001-Behauptung auf belegbare Anbieter beschränkt
4. ✅ EHB ↔ RC-Tech Trennung — Eigenprodukt-Klausel in §1, drei KI-Wege in §14
5. ✅ Interne Doku — CHANGELOG + STALE-NOTICE führen den vollständigen Audit-Trail

## Iteration 7 — Haftungs-Klausel + Mobile-Header (28.04. ganz spät nachts)

Zwei Themen vom finalen Sichten:

1. **§10 Haftungs-Klausel war juristisch zu pauschal:** Aussage *"haftet nicht für Schäden durch Drittanbieter und ihre Sub-Auftragsverarbeiter"* widerspricht zwingendem Schweizer Recht (OR Art. 101, Erfüllungsgehilfen-Haftung) sowie DSGVO Art. 28 Abs. 4. Vor Gericht wäre die Klausel teilweise unwirksam und hätte die ganze §10 angreifbar gemacht.

2. **Mobile-Bug auf RC-Tech:** Top-Menü blieb beim Scrollen oben kleben — Abstand zwischen Menü und Top-Inhalt nervig auf Mobile. EHB hat das saubere Hide-on-Scroll-Verhalten, RC-Tech nicht.

**Iteration 7 — Änderungen:**

| Bereich | Datei | Änderung |
|---|---|---|
| RC-Tech AGB §10 | `agb.html` | **Haftungs-Klausel neu strukturiert:** Sorgfalts-Klausel ("RC-Tech wählt und überwacht mit der Sorgfalt eines erfahrenen IT-Anbieters") + Erfüllungsgehilfen-Anerkennung (Art. 28 DSGVO + Art. 101 OR) — Schutz bleibt für höhere Gewalt, unverschuldete Drittanbieter-Ausfälle, eigenständige Vertragsverhältnisse (Stripe), unsachgemässe Nutzung |
| RC-Tech AGB | `agb.html` Stand-Zeile | V2.5 → **V2.6** |
| RC-Tech Header | `de/en/fr/it/es/sr.html` + `ki-integrationen.html` | CSS `transition:transform .4s ease` + `.nav-hidden` Klasse; Scroll-Listener im JS-Block — Header verschwindet beim Runterscrollen, kommt zurück beim Hochscrollen oder am Top |
| EHB AGB §10 | `TermsPage.tsx` | Analog zur RC-Tech-Anpassung: Sorgfalts-Klausel + Erfüllungsgehilfen-Anerkennung; expliziter Hinweis auf Art. 100 OR (zwingende Mindesthaftung) im ersten Absatz |
| EHB AGB+Datenschutz | `TermsPage.tsx` + `PrivacyPage.tsx` Stand-Zeile | V3.3 → **V3.4** |

**Hinweis:** Die neue Haftungs-Klausel macht uns NICHT haftbarer — wir haften gesetzlich ohnehin so. Sie macht uns nur unangreifbarer vor Gericht, weil sie nicht mehr versucht, zwingendes Recht auszuhebeln.

## Iteration 6 — IP-Modelle + Schnittstellen-Klarstellung (28.04. nachts)

Drei Themen aus dem laut-denken über die Geschäftsbeziehung:

1. **§8 Geistiges Eigentum war zu eng:** Die alte Formulierung gab nur ein Modell ("nicht-ausschliessliches Nutzungsrecht") und liess offen, was passiert wenn ein Kunde Exklusivität oder vollständiges Eigentum will. Bei einem Werkvertrag/Auftrag im individuellen Software-Bereich ist das ein häufiger Streitpunkt am Projektende. Drei branchenübliche Modelle (Standard / Exklusiv-Lizenz / Eigentums-Übergang) bringen Klarheit ins Angebot — der Kunde sieht von Anfang an, was Standard ist und was kostet extra.

2. **Hintergrund-IP nicht geschützt:** Das alte §8 sicherte unsere "vorbestehenden Rechte" nur implizit. Bei einem strikten Modell-C-Vertrag (Eigentums-Übergang) hätte ein Kunde theoretisch argumentieren können, alle wiederverwendbaren Bausteine zu vereinnahmen. Mit explizitem §8.1 (Hintergrund-IP) ist das geklärt.

3. **Open-Source-Klausel fehlte komplett:** Moderne Software enthält IMMER OSS-Bestandteile (React, Node, Postgres-Treiber, etc.). Ohne Klausel könnten wir versehentlich versprechen, was wir gar nicht halten können. Mit §8.4 ist das explizit geregelt.

4. **Landingpage Schnittstellen-Realität:** Stage 2 (Tiefe Integration) und Audit-Step setzen voraus, dass die bestehende Kundensoftware Schnittstellen hat (APIs, Webhooks, DB-Zugriff). Das war implizit, ist jetzt explizit — verhindert falsche Erwartungen.

5. **Landingpage Infrastruktur-Block zu starr:** Wirkte, als gäbe es nur unseren Eigen-Stack. Bei Kundenprojekten ist Hosting projekt-individuell (auf unserem Stack, in Kunden-Cloud, On-Premise). Saubere Trennung jetzt: Eigen-Stack, Kundenprojekt-Optionen, verbindliche Standards für alle.

**Iteration 6 — Änderungen:**

| Bereich | Datei | Änderung |
|---|---|---|
| RC-Tech AGB §8 | `agb.html` | **Vollständig restrukturiert** in 4 Unter-Sektionen: 8.1 Vorbestehende Rechte (Hintergrund-IP), 8.2 Projektspezifische Arbeitsergebnisse mit drei Modellen (a) Standard-Nutzungsrecht / (b) Exklusiv-Lizenz / (c) Eigentums-Übergang, 8.3 Kunden-Inhalte, 8.4 Open-Source-Komponenten |
| RC-Tech AGB | `agb.html` Stand-Zeile | V2.4 → **V2.5** |
| Landingpage Stack | `ki-integrationen.html` | Infrastruktur-Block neu strukturiert: Eigen-Stack-Items markiert, Kundenprojekt-Optionen erwähnt (Azure/AWS/Google/On-Premise), Standards "verbindlich für alle Projekte" hervorgehoben |
| Landingpage Drei Tiefen Stage 2 | `ki-integrationen.html` | Schnittstellen-Voraussetzung explizit benannt; neuer Listenpunkt "Anbindung an bestehende Kundensoftware via REST/GraphQL/Webhook" |
| Landingpage Audit-Step | `ki-integrationen.html` | Schnittstellen-Frage in den Audit aufgenommen ("Welche Schnittstellen zur bestehenden Software sind verfügbar?") |

**Konzept der drei IP-Modelle:**
- **Modell A (Standard, im Preis enthalten):** Nicht-ausschliessliches Nutzungsrecht — Kunde nutzt unbefristet, RC-Tech kann Patterns wiederverwenden
- **Modell B (Aufpreis, im Einzelvertrag verhandelbar):** Exklusiv-Lizenz für 12-24 Monate — wir bauen nichts Vergleichbares für Wettbewerber
- **Modell C (Aufpreis, im Einzelvertrag verhandelbar):** Vollständiger Eigentums-Übergang am projektspezifischen Code — RC-Tech verzichtet auf Wiederverwendung; Wartungs-Zugriffsrecht muss explizit geregelt werden

In den AGB stehen **keine konkreten Aufpreise** — diese werden im Einzelvertrag verhandelt (üblich: Pauschal-Aufschlag 20-50% auf Projekt-Honorar je nach Modell).

## Iteration 5 — Subprozessor-Vollständigkeit + Landingpage-Erweiterung (28.04. nachts)

Zwei Themen kamen beim erneuten Durchlesen hoch:

1. **Subprozessor-Liste in RC-Tech §6 unvollständig:** Die EHB-spezifischen Sub-AV (Twilio, SMTP, Google Ireland, Microsoft Ireland, Meta Ireland, fiskaly) waren nur im "Hinweis"-Absatz namentlich erwähnt mit Verweis auf den AVV. Da §5 aber explizit EHB als Auftragsverarbeitungs-Tätigkeit von RC-Tech beschreibt, sollten sie auch in §6 konkret aufgeführt sein — sonst entsteht eine Lücke gegenüber Art. 13 DSGVO (Empfänger-Information). **Fix:** §6 ist jetzt vollständig mit Gruppierung in 6 Unter-Sektionen (6.1–6.6).

2. **KI-Landingpage zu use-case-zentriert:** Die Landingpage zeigte 6 Use-Case-Cards, erklärte aber nicht auf hoher Ebene, was KI-Integration eigentlich heisst — und die Brücke zu "massgeschneiderter Software" (= Software-Engineering von Grund auf) fehlte. Ein nicht-technischer Entscheider hatte keinen klaren Einstieg in die Skala der Möglichkeiten.

**Iteration 5 — Änderungen:**

| Bereich | Datei | Änderung |
|---|---|---|
| RC-Tech Datenschutz §6 | `datenschutz.html` | **Vollständig restrukturiert** in 6 Unter-Sektionen: 6.1 Plattform-Infrastruktur (Hetzner, Infomaniak, IONOS, Gcore, BetterStack), 6.2 Zahlungsabwicklung (Stripe), 6.3 KI-Inferenz (AWS Europe SARL mit Anthropic als Sub-AVV), 6.4 EHB-spezifisch (Twilio, SMTP, Google IE, Microsoft IE, Meta IE, fiskaly), 6.5 Webseite (Google Fonts), 6.6 Aktualität (Update-Mechanismus mit Widerspruchsrecht) |
| RC-Tech Datenschutz | `datenschutz.html` Stand-Zeile | V2.4 → **V2.5** |
| KI-Landingpage | `ki-integrationen.html` | Neue Section "Was wir damit konkret meinen" zwischen Hero und Use-Cases — drei Absätze in zugänglicher Sprache, erklärt Dokumentensuche, Vektorisierung/Indexierung und Workflow-Automation ohne Buzzword-Bingo |
| KI-Landingpage | `ki-integrationen.html` | Neue Section "Drei Tiefen der Integration" zwischen Use-Cases und Process — Stufe 1 (Workflow-Automation, 2-4 Wo), Stufe 2 (Tiefe Integration mit RAG/Vektorisierung, 2-3 Mo), **Stufe 3 (Massgeschneiderte Software** mit Link auf `de.html#services` — Brücke zu Software-Engineering-Service) |
| KI-Landingpage | `ki-integrationen.html` | Use-Cases #3 (Dokument-Analyse) und #5 (Wissens-Suche) geschärft — semantische Suche, RAG, Vektorisierung explizit benannt aber im Kontext erklärt |

## Iteration 4 — Eigenprodukt-Trennung + Zukunftsklausel (28.04. ganz spät)

Nach weiterer Sichtung wurden zwei strukturelle Lücken erkannt:

1. **RC-Tech vs. EHB nicht klar genug getrennt:** EHB ist ein Eigenprodukt aus eigenem Haus, kein gewhitelabeltes Drittanbieter-Tool. Diese Information stand zwar implizit in §1, aber nicht prominent. Bei einem Audit oder einer Kanzleiprüfung wäre das eine erste Frage.

2. **Keine Zukunftsklausel:** Die KI-Use-Case-Listen in EHB §6 (AGB) und §13 (Datenschutz) waren Momentaufnahmen. Wenn der Voice Agent live geht oder neue KI-Funktionen kommen, müssten die AGB jedes Mal angepasst werden. Eine generische "Wir dokumentieren neue Funktionen vorab in der Datenschutzerklärung"-Klausel löst das.

**Iteration 4 — Änderungen:**

| Bereich | Datei | Änderung |
|---|---|---|
| EHB AGB §1 | `TermsPage.tsx` | "Eigenes Software-Produkt aus dem Hause der RC-Tech Solutions GmbH ... kein gewhitelabeltes Drittanbieter-Produkt" — explizite Eigenprodukt-Klarstellung |
| EHB AGB §6 | `TermsPage.tsx` | Voice Agent als zukünftige KI-Funktion ergänzt; Zukunftsklausel am Ende: neue Funktionen werden in der Datenschutzerklärung dokumentiert, kein erneuter AGB-Update bei jeder Erweiterung nötig |
| EHB Datenschutz §13 | `PrivacyPage.tsx` | Eigenprodukt-Hinweis am Anfang; Voice Agent als Use-Case Nr. 8 mit Status "in Vorbereitung"; Zukunftsklausel am Ende mit Verweis auf Architektur-Leitfaden (Bedrock EU + Datenminimierung + Mensch-im-Loop) |
| RC-Tech Datenschutz §14 | `datenschutz.html` | Restrukturiert von 2 auf **3 KI-Wege**: 14.1 Pair-Programming, 14.2 EHB-Eigenprodukt, **14.3 NEU: Kundenprojekte (modell-agnostisch)**, 14.4 Transparenz Art. 50 (vorher 14.3), 14.5 NEU: Zukunftsklausel |
| RC-Tech Datenschutz | `datenschutz.html` Stand-Zeile | V2.3 → **V2.4** |

**Konzept:** Die drei Wege auf RC-Tech-Seite sind jetzt sauber separiert:
- **Pair-Programming** = Anthropic-direkt für RC-Tech-eigene Code-Entwicklung (kein Kundendaten-Bezug)
- **EHB als Eigenprodukt** = Bedrock-EU als feste Architektur-Wahl
- **Kundenprojekte (Beratung/KI-Integration)** = projekt-individuell, im jeweiligen AVV geregelt — diese Datenschutzerklärung gilt nicht für Kundenprojekte, sondern nur für RC-Tech selbst

## Iteration 3 — Aufbewahrungsfristen + Anthropic-Konsistenz (28.04. spät)

Nach weiterer Sichtung kamen zwei Detail-Probleme an die Oberfläche:

1. **EHB §6 listete Anthropic noch als direkten US-Drittanbieter** — das war vor der Bedrock-Umstellung korrekt, ist seit V3 aber inkonsistent zu §13 ("Anthropic agiert als Sub-Auftragsverarbeiter im Rahmen der AWS-Marketplace-Subscription ohne direkten Datenfluss in die USA"). **Fix:** §6 listet jetzt AWS Europe SARL als Vertragspartner, Anthropic explizit als Sub-AVV.

2. **Aufbewahrungsfristen vermischten Buchhaltung mit Backup-Retention** — der alte §10 (EHB) und §12 (RC-Tech) suggerierten "10 Jahre Buchhaltung" pauschal, ohne klar zu trennen zwischen:
   - operativen Plattform-Daten (Vertragsdauer + 30 Tage)
   - Backup-Snapshots auf IONOS (rolling 30 Tage, automatisch überschrieben)
   - Buchhaltungs-Belegen in der Buchhaltung (10 Jahre OR/HGB)
   - KI-Inferenz (nicht persistiert)
   
   **Fix:** Beide §10 (EHB) und §12 (RC-Tech) zeigen jetzt explizit fünf bis sechs Datenkategorien mit eigenen Fristen. Das war datenschutzrechtlich nicht zwingend falsch, aber missverständlich — und ein Auditor hätte zu Recht nachgefragt.

**Zusätzliche Änderungen aus Iteration 3:**

| Bereich | Datei | Änderung |
|---|---|---|
| EHB Datenschutz | `PrivacyPage.tsx` §6 | Anthropic-Eintrag korrigiert: AWS Europe SARL als Vertragspartner, Anthropic als Sub-AVV |
| EHB Datenschutz | `PrivacyPage.tsx` §10 | Aufbewahrungsfristen in 6 Datenkategorien aufgeteilt |
| EHB AGB+Datenschutz | `TermsPage.tsx` + `PrivacyPage.tsx` Stand-Zeile | V3.2 → **V3.3** |
| RC-Tech Datenschutz | `datenschutz.html` §12 | Aufbewahrungsfristen in 6 Datenkategorien aufgeteilt (analog EHB) |
| RC-Tech Datenschutz | `datenschutz.html` Stand-Zeile | V2.2 → **V2.3** |

## Iteration 2 — Konsolidierung am Abend des 28.04.

Nach erstem Sichten kamen drei Wünsche dazu:

1. **Sauber konsolidieren** — alte Stände entsorgen, eine Quelle der Wahrheit
2. **Landingpage findbar machen** — vorher nirgends verlinkt, jetzt in Service-Card und Footer
3. **Provider-Agnostik** — RC-Tech als Dachfirma ist nicht auf Claude festgelegt; bevorzugt für Eigenprodukte (EHB), bei Kundenprojekten modell-/anbieter-individuell

Änderungen aus Iteration 2 sind in der Tabelle oben kenntlich gemacht. EHB-Texte wurden in Iteration 2 nicht mehr angefasst — dort ist die Bedrock-EU-Wahl eine bewusste Architektur-Entscheidung für das eigene Produkt und bleibt fest.

## Datei-Inventar dieser Iteration

```
rc-tech-solutions-webseite/
├── agb.html                                            (V2.1 → V2.7)
├── datenschutz.html                                    (V2.1 → V2.6)
├── de.html, en.html, fr.html, it.html, es.html, sr.html (KI-Integration-Service + No-US + Landingpage-Link + neutrale Tags)
├── ki-integrationen.html                                (NEU — Landingpage, Stack-Sektion provider-agnostisch)
├── CHANGELOG-2026-04-28-Konsistenz-Korrekturen.md       (NEU)
├── agb.pdf                                              (GELÖSCHT — V2.0-Altstand, nicht synchron)
└── datenschutz.pdf                                      (GELÖSCHT — V2.0-Altstand, nicht synchron)

easyandsmartbooking-webseite/src/pages/marketing/
├── TermsPage.tsx                                       (V3 → V3.5)
└── PrivacyPage.tsx                                     (V3 → V3.4)

Firmenunterlagen/Recht/Compliance/Webseiten/
└── STALE-NOTICE-2026-04-28.md                           (NEU — Snapshots veraltet, vor 4.5. regenerieren)
```

---

**Erstellt:** 2026-04-28
**Verantwortlich:** Robert Camathias, Geschäftsführer RC-Tech Solutions GmbH
**Review-Termin:** 2026-05-04 (Anwalts-Termin)
