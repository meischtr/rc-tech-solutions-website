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
| RC-Tech AGB | `agb.html` Stand-Zeile | V2.1 → V2.3, Datum 26.4. → 28.4. |
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

## Datei-Inventar dieser Iteration

```
rc-tech-solutions-webseite/
├── agb.html                                            (V2.1 → V2.3)
├── datenschutz.html                                    (V2.1 → V2.2)
├── de.html, en.html, fr.html, it.html, es.html, sr.html (KI-Integration-Service + No-US)
├── ki-integrationen.html                                (NEU — Landingpage)
├── CHANGELOG-2026-04-28-Konsistenz-Korrekturen.md       (NEU)

easyandsmartbooking-webseite/src/pages/marketing/
├── TermsPage.tsx                                       (V3 → V3.2)
└── PrivacyPage.tsx                                     (V3 → V3.2)
```

---

**Erstellt:** 2026-04-28
**Verantwortlich:** Robert Camathias, Geschäftsführer RC-Tech Solutions GmbH (i. Gr.)
**Review-Termin:** 2026-05-04 (Anwalts-Termin)
