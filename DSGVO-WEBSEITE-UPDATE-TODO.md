# DSGVO-Webseiten-Update — RC-Tech Solutions Marketing-Webseite

**Stand:** 🟡 VORAB-UMGESETZT 2026-04-26 — Anwalts-Sign-Off ausstehend (Termin 4.5.2026)
**Hinweis:** Auf Wunsch von Roebi vorzeitig in HTML-Master eingespielt, weil die Seiten passwortgeschützt sind und keine Öffentlichkeit erreichen. Diskussionsgrundlage zum Anwalts-Termin ist nun der **bedrock-eingearbeitete** HTML-Stand (V2.1), nicht mehr der Vor-Bedrock-Stand (V2.0) aus den am 24.4. gedruckten PDFs.
**Verantwortlich:** RC-Tech-Webseiten-Agent (eigene Session)
**Nach Anwalts-Sign-Off zu tun:** Stand-Hinweis von "zur Kanzlei-Prüfung 4. Mai 2026 vorgesehen" auf "kanzleigeprüft" umstellen, Snapshots erneut spiegeln, ggf. Anwalts-Korrekturen einarbeiten.

---

## Kontext

Am 2026-04-26 wurde im EASB-Backend die Migration auf **AWS Bedrock EU** (`eu-central-1` Frankfurt) und **BYOK-Removal** (Plattform-Key only) durchgeführt. Die RC-Tech-Webseite (Datenschutz + AGB) erwähnt Anthropic in zwei Kontexten:

1. **EASB-Plattform-Funktionen** (Buchungs-Chatbot, Übersetzungen) — laufen ab Migration über AWS Bedrock EU → Texte müssen angepasst werden
2. **Eigene Entwicklungs-Tools** (Claude Code als Pair-Programming-Tool für RC-Techs Code) — bleibt Anthropic-direkt, weil keine Kundendaten reingehen → Texte müssen die Differenzierung klar machen

→ Updates müssen vor 1.6.2026-CH-Launch live sein.

## Wartet auf

**Anwalts-Sign-Off am 4.5.2026.** Vor dem Termin keine Änderungen am HTML-Master vornehmen.

## Betroffene Files

📄 `rc-tech-solutions-webseite/datenschutz.html` — §7 (Subprozessor) + §14 (KI-Einsatz)
📄 `rc-tech-solutions-webseite/agb.html` — §14 (KI-Werkzeuge in Beratung)

## Zentrale Differenzierung (Konzept)

RC-Tech nutzt Claude über **zwei verschiedene Wege**, die in den Texten klar getrennt werden müssen:

| Weg | Zweck | Provider | DSGVO-Status |
|---|---|---|---|
| **A. Eigene Entwicklung** | Claude Code als Pair-Programming-Tool für RC-Techs eigenen Code | Anthropic-direkt (`api.anthropic.com`) | OK — keine Kundendaten an KI, Bestand-AVV §12.5 + Tools-Datenschutz |
| **B. EASB-Plattform-Funktionen** | Buchungs-Chatbot, Übersetzungen, CRM-Summary etc. für Salons | AWS Bedrock EU `eu-central-1` (AWS Europe SARL) | EU-Datenresidenz garantiert — kein Drittland-Transfer |

**Kein BYOK** mehr für EASB-Tenants (Plattform-Key only). Eigene Entwicklung ist davon nicht betroffen.

---

## Datenschutz §7 — Subprozessor-Liste anpassen

### Aktuelle Erwähnung (Stand 2026-04-26)

```html
<p><strong>Anthropic PBC</strong> (San Francisco, USA) — KI-gestützte Funktionen
(Buchungs-Chatbot, Übersetzungen, Infrastruktur-Monitoring). Datenminimierung:
nur Vornamen, Service-Texte, aggregierte Metriken; keine Kontakt- oder
Zahlungsdaten. Rechtsgrundlage: berechtigtes Interesse (Art. 6 Abs. 1 lit. f
DSGVO) bzw. Vertragserfüllung. Transfer-Mechanismus: EU–US Data Privacy
Framework (DPF) sowie Standardvertragsklauseln (SCCs).</p>
```

### Vorschlag neue Fassung

```html
<p><strong>AWS Europe SARL</strong> (Luxemburg) — Hosting der KI-Inferenz für
Claude-Modelle der Anthropic PBC über AWS Bedrock in der EU-Region
<code>eu-central-1</code> (Frankfurt am Main). Verwendung in den RC-Tech-eigenen
SaaS-Plattformen (insbesondere EasyAndSmartBooking) für Buchungs-Chatbot,
Übersetzungen, CRM-Profil-Zusammenfassung, Admin-Support und KI-gestützte
Texterstellung. Datenminimierung gemäss Art. 5 Abs. 1 lit. c DSGVO ist
code-seitig implementiert. Die KI-Inferenz erfolgt vollständig innerhalb der
AWS-EU-Region — kein Drittland-Transfer im Sinne von Art. 44 DSGVO. Anthropic
PBC (San Francisco, USA) agiert als Sub-Auftragsverarbeiter im Rahmen der
AWS-Marketplace-Subscription ohne direkten Datenfluss in die USA. Rechtsgrundlage
des AVV: AWS-Kundenvereinbarung mit integriertem GDPR Data Processing Addendum
und Standardvertragsklauseln (SCCs).</p>
```

---

## Datenschutz §14 — KI-Einsatz neu strukturieren

### Aktuelle Fassung

Zu lange — beschreibt nur EASB-Buchungs-Chatbot mit DPF-Hinweis und Plan-B Bedrock.

### Vorschlag neue Struktur

Neue §14 in zwei klar getrennten Teilen:

**§14.1 Eigene Entwicklungs-Tools (Claude Code als Pair-Programming)**

```html
<h3>14.1 Einsatz von KI als Entwicklungs-Werkzeug</h3>
<p>RC-Tech Solutions setzt zur Erbringung von Softwareentwicklungs- und
Beratungsleistungen KI-gestützte Werkzeuge ein, insbesondere Claude Code
(Anthropic PBC, USA) als Pair-Programming-Tool. Dabei werden ausschliesslich
RC-Tech-eigene Code-Bestände, Dokumentation und Architektur-Konzepte verarbeitet.
<strong>Vertrauliche Kundendaten werden nicht an diese Entwicklungs-KI
übermittelt.</strong> Sämtliche KI-generierten Arbeitsergebnisse werden vor
Auslieferung an den Kunden manuell geprüft, getestet und freigegeben. Bei
Beratungs- oder Review-Aufträgen, bei denen KI-Unterstützung mit Kundendaten
sinnvoll ist, wird die Datenübertragung vorab mit dem Kunden abgestimmt und
vertraglich geregelt.</p>
```

**§14.2 KI-Funktionen in eigenen SaaS-Plattformen**

```html
<h3>14.2 KI-Funktionen in den RC-Tech-eigenen SaaS-Plattformen (EasyAndSmartBooking)</h3>
<p>KI-gestützte Funktionen in den RC-Tech-eigenen SaaS-Plattformen, insbesondere
auf EasyAndSmartBooking (Buchungs-Chatbot, Übersetzungen in fünf Sprachen,
CRM-Profil-Zusammenfassung mit Pseudonymisierung, Admin-Support mit
PII-Sanitizer, Bewertungs-Moderation, KI-gestützte Texterstellung), nutzen die
Claude-Modelle der Anthropic PBC bezogen über <strong>AWS Bedrock in der
EU-Region <code>eu-central-1</code> (Frankfurt am Main)</strong>.
Vertragspartner: <strong>AWS Europe SARL (Luxemburg)</strong>. Die KI-Inferenz
erfolgt vollständig innerhalb der AWS-EU-Region — Daten verlassen das EU/EWR-Gebiet
nicht. Anthropic PBC agiert als Sub-Auftragsverarbeiter über AWS Bedrock ohne
direkten Datenfluss in die USA.</p>

<p>Datenminimierung gemäss Art. 5 Abs. 1 lit. c DSGVO ist code-seitig implementiert
(Vornamen-Reduktion, Pseudonymisierung im CRM-Profil, Allergien-Ausschluss aus
Chatbot-Prompt, Pre-Save-Sanitizer im Admin-Support-Chat). Endkunden können den
KI-Chatbot per Opt-Out deaktivieren (Art. 21 DSGVO Widerspruchsrecht).
KI-Funktionen werden ausschliesslich über die Plattform-Konfiguration des
Anbieters bereitgestellt — eine Hinterlegung eigener KI-API-Schlüssel durch
Tenants ist nicht möglich.</p>
```

**§14.3 Transparenz EU AI Act**

```html
<h3>14.3 Transparenz nach Art. 50 EU AI Act</h3>
<p>Endkunden werden bei jeder Chatbot-Interaktion erkennbar darauf hingewiesen,
dass sie mit einem automatisierten System kommunizieren. Der Buchungs-Chatbot
ist funktional auf Terminbuchung und Dienstleistungs-Auskünfte beschränkt und
gibt ausdrücklich keine medizinische, gesundheitsbezogene, diagnostische oder
therapeutische Beratung. Eine Einstufung als Hochrisiko-KI im Sinne von
Annex III AI Act liegt nicht vor.</p>

<p>Eine automatisierte Entscheidungsfindung mit rechtlicher Wirkung im Sinne
von Art. 22 DSGVO findet nicht statt. Die CRM-Profil-Zusammenfassung
(Customer-Brain) liefert pseudonymisierte Empfehlungen für das Salon-Personal —
die Verwendung erfolgt durch das Personal als Mensch-im-Loop, kein
automatisierter Beschluss.</p>
```

---

## AGB §14 — KI-Werkzeuge in Beratung anpassen

### Aktuelle Fassung — bleibt grossteils

Die AGB beschreiben **Beratungsleistungen** von RC-Tech, nicht die EASB-Plattform für Endkunden. Hier wird Claude für eigene Entwicklung genutzt → keine Drittland-Diskussion nötig (keine Endkunden-Daten).

**Empfehlung Anwalts-Frage am 4.5.:** Soll die AGB §14 nur den Entwicklungs-Tool-Aspekt behandeln und für SaaS-Plattform-KI auf die Datenschutzerklärung verweisen?

### Vorschlag minimale Anpassung

```html
<p>RC-Tech setzt zur Erbringung von Softwareentwicklungs- und Beratungsleistungen
KI-gestützte Werkzeuge ein, insbesondere Modelle der Anthropic PBC (Claude Code
als Pair-Programming-Tool). <strong>Vertrauliche Kundendaten werden im
Entwicklungsprozess grundsätzlich nicht an externe KI-Dienste übermittelt.</strong>
Sämtliche KI-generierte Arbeitsergebnisse werden vor der Auslieferung an den
Kunden manuell geprüft, getestet und freigegeben.</p>

<p>KI-gestützte Produkt-Funktionen innerhalb der von RC-Tech betriebenen
SaaS-Plattformen (z. B. Buchungs-Chatbot auf EasyAndSmartBooking) erfolgen
über AWS Bedrock in der EU-Region <code>eu-central-1</code> (AWS Europe SARL,
Luxemburg) — Details siehe Datenschutzerklärung Ziff. 14. Die betreffenden
Systeme erfüllen die Transparenzpflichten nach Art. 50 der Verordnung
(EU) 2024/1689 (EU AI Act).</p>

<p>RC-Tech verarbeitet keine besonderen Kategorien personenbezogener Daten
im Sinne von Art. 9 DSGVO im Rahmen der KI-gestützten Funktionen. Eine
Hochrisiko-KI im Sinne von Annex III AI Act liegt nicht vor.</p>
```

---

## Aktion nach Anwalts-Sign-Off

### 1. Vorschlags-Texte ggf. anpassen

Falls Anwalt Korrekturen verlangt: Vorschläge in diesem File erst aktualisieren, dann ins HTML umsetzen.

### 2. datenschutz.html anpassen

- §7 (Subprozessor-Liste): Anthropic-Eintrag durch AWS Europe SARL ersetzen
- §14 (KI-Einsatz): in §14.1 + §14.2 + §14.3 umstrukturieren

### 3. agb.html anpassen

- §14 (KI-Werkzeuge): Differenzierung Beratungs-Tool vs. SaaS-Plattform-KI klar machen

### 4. impressum.html — keine Änderungen nötig

### 5. Stand-Datum aktualisieren

In datenschutz.html und agb.html den Stand-Hinweis ändern auf "Stand: [Anwalts-Sign-Off-Datum] · kanzleigeprüft".

### 6. Build + Deploy

(Der RC-Tech-Webseite-Build-Prozess ist nicht TSX wie EASB, sondern direkt HTML — siehe `rc-tech-solutions-webseite/package.json`. Falls Build-Skript: ausführen.)

### 7. Snapshot-Update in Quellen/

Nach erfolgreichem Deploy:

📄 **Files in Quellen/ aktualisieren:**
- `Quellen/Recht/Compliance/Webseiten/agb-rc-tech.html`
- `Quellen/Recht/Compliance/Webseiten/datenschutz-rc-tech.html`
- `Quellen/Recht/Compliance/Webseiten/README.md` (Stand-Datum aktualisieren)

### 8. Dieses TODO-File als "umgesetzt" markieren

Header-Status aktualisieren auf "✅ UMGESETZT [Datum]".

## Zugehörige Dokumente

- 📄 EASB-Vorschlag: `Quellen/Recht/Compliance/Webseiten/EHB/Vorschlag-AGB-Privacy-Bedrock-Anpassung-2026-04-26.md`
- 📄 AWS-Bedrock-Setup: `Quellen/Infrastruktur/AWS-Bedrock-Setup-Anleitung-2026-04-26.md`
- 📄 Subprozessor-Liste v3.1: `Quellen/Recht/Compliance/Subprozessoren-Liste-2026-05-04.md`
- 📄 Anwalts-Briefing: `Quellen/Recht/Compliance/Anwalts-Briefing-2026-05-04.md`

## Memory-Verweise

- `project_ki_provider_strategie.md` — plattform-weite Bedrock-Strategie
- `project_ehb_to_easb_rename.md` — falls EASB-Naming auch hier konsequent durchziehen (Memory-Hinweis: aktuell teilweise EHB im Text)

## Anwalts-Frage am 4.5.

Bei dem 2026-05-04 Termin sollten zusätzlich diese RC-Tech-spezifischen Punkte geklärt werden:

1. **Ist die Differenzierung Beratungs-KI vs. SaaS-Plattform-KI in den Texten ausreichend klar?**
2. **Soll AGB §14 Verweis auf Datenschutz §14 enthalten oder beide Bereiche selbst beschreiben?**
3. **Wie wird "Vertrauliche Kundendaten werden nicht an Entwicklungs-KI übermittelt" haftungsmässig formuliert?** (Garantie vs. Bemühens-Pflicht)

## Rollback-Plan

Falls Probleme nach Deploy: Git-Revert auf Stand vor Update, Re-Deploy. Backwards-Compatibility ist gegeben (reine Text-Updates ohne Funktional-Änderung).
