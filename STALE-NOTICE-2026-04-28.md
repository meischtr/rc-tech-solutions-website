---
titel: Snapshot-Stale-Hinweis 2026-04-28
zweck: Markiert die PDFs in diesem Ordner als veraltet — der aktuelle Stand auf der Webseite ist neuer
gültig_ab: 2026-04-28
gültig_bis: bis Snapshots regeneriert
---

# ⚠️ STALE-Hinweis — Snapshots in diesem Ordner sind veraltet

## Was ist veraltet

| Datei | Snapshot-Stand | Aktueller Stand auf Webseite |
|---|---|---|
| `agb-rc-tech.pdf` | V2.1 (26.04.2026) | **V2.9 (28.04.2026)** |
| `datenschutz-rc-tech.pdf` | V2.1 (26.04.2026) | **V2.7 (28.04.2026)** |
| `impressum-rc-tech.pdf` | V1.0 | unverändert |
| `EHB/agb-easyandsmartbooking.pdf` | V2 (24.04.2026) | **V3.5 (28.04.2026)** |
| `EHB/datenschutz-easyandsmartbooking.pdf` | V2 (24.04.2026) | **V3.4 (28.04.2026)** |

## Was sich seit V2.1 / V3 geändert hat

Konsistenz-Korrekturen vom 28.04.2026 (vor Anwalts-Termin 04.05.2026), in elf Iterationen:

**RC-Tech AGB (V2.1 → V2.9):**
- §1: US-Kunden-Ausschluss als räumlicher Geltungsbereich (Versicherungs-Auflage); Service-Aufzählung auf 4 Säulen reduziert (Softwareentwicklung, Cloud Engineering, KI-Integration, Compliance)
- §3: 4 Bullet-Points statt 7 — Wartung als Teil von Cloud Engineering, Discovery als Teil von Softwareentwicklung, KI-Integration provider-agnostisch (AWS Bedrock EU bevorzugt für Eigenprodukte, bei Kundenprojekten projekt-individuell)
- §4: Stundensätze projekt-individuell (CHF 160 fix entfernt)
- §8: **Vollständig restrukturiert** in 4 Unter-Sektionen — drei IP-Modelle (Standard-Nutzungsrecht / Exklusiv-Lizenz / Eigentums-Übergang), Hintergrund-IP geschützt, Open-Source-Komponenten geregelt
- §10: Erfüllungsgehilfen-Haftung Art. 101 OR + zwingende Mindesthaftung Art. 100 OR + vollständige Subprozessor-Liste im Carve-Out (fiskaly, Google IE, Microsoft IE, Meta IE, Twilio)
- §13: Subunternehmer-Klausel um AVV-Hinweis und Widerspruchsrecht (Art. 28 DSGVO) ergänzt
- §14: 3 KI-Wege parallel zu Datenschutz strukturiert
- Hero-Subtitle: 4-Säulen-Aufzählung statt "Cloud-Hosting, Beratung"

**RC-Tech Datenschutz (V2.1 → V2.7):**
- §4: Hosting-Provider sauber von KI-Inferenz getrennt (AWS Europe SARL ist §6.3, nicht §4)
- §5: Section-Titel und Text auf "eigene SaaS-Produkte" (statt "SaaS-Hosting-Plattform")
- §6: **Vollständig restrukturiert** in 6 Unter-Sektionen — alle Subprozessoren konkret gelistet inkl. EHB-spezifische (Twilio, SMTP, Google IE, Microsoft IE, Meta IE, fiskaly), gruppiert nach Einsatzbereich
- §10: TOM-Scope-Klärung
- §12: Aufbewahrungsfristen in 6 Datenkategorien aufgeteilt (operativ, Backup, Logs, Kontakt, Buchhaltung, KI-Inferenz) — saubere Trennung Buchhaltungs-Belege (10 Jahre) vs. Backup-Snapshots (rolling 30 Tage)
- §14: 3-Wege-Struktur (14.1 Pair-Programming Anthropic-USA SCC+DPF, 14.2 EHB-Eigenprodukt AWS Bedrock EU, 14.3 Kundenprojekte modell-agnostisch, 14.4 Transparenz Art. 50 EU AI Act, 14.5 Zukunftsklausel)

**EHB AGB (V2 → V3.5):**
- §1: US-Kunden-Ausschluss + EHB als Eigenprodukt aus eigenem Haus
- §4: Stripe Payments Europe Ltd. Dublin als Payment-Subprozessor
- §6: KI-Architektur als bewusste Eigenproduktwahl, Voice Agent als zukünftige Funktion erwähnt, Zukunftsklausel; **vier Zielsprachen (EN/FR/IT/ES)** ausgehend von Deutsch (Konsistenz mit Privacy §13)
- §10: Drittanbieter-Liste konsistent zu §6 erweitert; Erfüllungsgehilfen-Haftung Art. 101 OR

**EHB Datenschutz (V2 → V3.4):**
- §2: Profiling-Aussage präzisiert auf Art. 22 DSGVO + Customer-Brain transparent benannt
- §6: Anthropic-Eintrag korrigiert (AWS Europe SARL als Vertragspartner, Anthropic als Sub-AVV)
- §10: Aufbewahrungsfristen in 6 Datenkategorien aufgeteilt
- §13: Eigenprodukt-Hinweis, 8 KI-Use-Cases dokumentiert, Voice Agent als Use-Case Nr. 8 (in Vorbereitung), Zukunftsklausel

Vollständiger Diff im Webseiten-Repo: `rc-tech-solutions-webseite/CHANGELOG-2026-04-28-Konsistenz-Korrekturen.md` (Iterationen 1–11)

## Quelle der Wahrheit

Aktuell und massgeblich ist das HTML/TSX im Webseiten-Repo:

```
rc-tech-solutions-webseite/
├── agb.html                    (V2.5)
├── datenschutz.html            (V2.5)
├── impressum.html              (V1.0)
└── ki-integrationen.html       (NEU — KI-Landingpage)

easyandsmartbooking-webseite/src/pages/marketing/
├── TermsPage.tsx               (V3.3)
└── PrivacyPage.tsx             (V3.3)
```

## Was zu tun ist vor 4. Mai 2026

1. **PDF-Generator anwerfen** (Pfad laut README: `tools/pdf-gen/`) und alle 5 betroffenen PDFs neu erzeugen — auf dem aktuellen V2.4 / V3.2 Stand.
2. Diese `STALE-NOTICE-2026-04-28.md` löschen, sobald die Snapshots aktualisiert sind.
3. Den Anwalt am 04.05. auf den aktuellen Stand briefen — die Konsistenz-Korrekturen vom 28.04. sind bereits eingearbeitet, der Sign-Off bezieht sich auf V2.7 (RC-Tech AGB) / V2.6 (RC-Tech Datenschutz) / V3.5 (EHB AGB) / V3.4 (EHB Datenschutz), **nicht** auf V2.1 / V3.

## Warum nicht direkt löschen

Die alten PDFs zeigen einen historischen Snapshot-Stand und können bis zur Regenerierung als Vergleichs-Referenz nützlich sein. Sobald die neuen Snapshots da sind, sollten die alten ersetzt werden — danach gibt es wieder genau eine Quelle der Wahrheit pro Dokument.
