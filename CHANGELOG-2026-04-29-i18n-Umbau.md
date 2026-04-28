---
titel: i18n-Subdirectory-Umbau + EN-Übersetzungen + UX-Verbesserungen
datum: 2026-04-29
zweck: Vor-Launch-Umbau auf state-of-the-art Routing-Pattern (/de/, /en/) plus Vollübersetzung aller Landingpages ins Englische
status: 🟢 UMGESETZT (alle Commits auf master gepusht, smoothere View Transitions Debug-Punkt für 2026-04-30 offen)
---

# i18n-Umbau-Session 2026-04-29

## Hintergrund

Vor Launch (nach Anwalts-Termin 4.5.2026) wurde die Webseite auf state-of-the-art Multi-Language-Routing umgestellt: Subdirectory-Pattern `/de/` + `/en/` statt der bisherigen Suffix-Variante (`de.html`, `en.html`). Begründung: Google empfiehlt Subdirectories für i18n, alle grossen Anbieter (Apple, Stripe, Microsoft) nutzen das, sauber skalierbar. Migration vor Launch ist günstig (keine Backlinks zu schützen), nach Launch teuer.

Gleichzeitig wurden alle 4 Service-Landingpages ins Englische übersetzt mit klar etabliertem Tonfall-Glossar, FR/IT/ES/SR-Hauptseiten gelöscht (Launch nur DE+EN für DACH-Fokus), Footer-Logo entfernt (war doppelt), Sprachschalter überall ergänzt, View Transitions Animation aufgewertet.

## Zusammenfassung der Änderungen

| Bereich | Datei(en) | Änderung |
|---|---|---|
| Routing | `de/`, `en/` (neu) + alle bisherigen Files verschoben | Subdirectory-Pattern für i18n |
| Sprachen | `fr.html`, `it.html`, `es.html`, `sr.html` | **Gelöscht** (Launch nur DE+EN, Git-Historie bleibt) |
| Hauptseiten | `de.html` → `de/index.html`, `en.html` → `en/index.html` | Hauptseite pro Sprache, kein Sprach-Suffix |
| Coming-Soon | `index.html` (Root) | Sprachschalter auf DE+EN reduziert, Login-Pfad sprachabhängig |
| EN-Pages (neu) | `en/compliance.html`, `en/software-development.html`, `en/cloud-engineering.html`, `en/ai-integrations.html` | Vollübersetzungen aus DE-Mastern |
| EN-Login | `en/login.html` (neu) | Englische Login-Variante mit Username/Password/Sign in |
| Slugs EN | `softwareentwicklung.html` → `software-development.html`, `ki-integrationen.html` → `ai-integrations.html` | Englische Slugs für EN-Files (SEO + UX) |
| Asset-Pfade | alle 9 DE-Files + 6 EN-Files | Absolutifiziert auf `/logo.png`, `/favicon.svg`, `/robert.jpg` mit srcset |
| hreflang | alle Marketing-Files | `de` + `en` + `x-default=de` Block in jedem File |
| Sprachschalter | 4 DE-Landingpages + Hauptseite | Im Header (`.lang-sw`-Klasse) ergänzt für Symmetrie zu EN, absolute Pfade |
| Footer | alle 10 Marketing-Files | `<img src="/logo.png">`-Image entfernt (war doppelt mit dem Bold-Text `RC-Tech Solutions GmbH`) |
| Tonfall (DE) | `de/softwareentwicklung.html` | "(kein Werbe-Sprech)" entfernt - selbstreferenziell ironisch |
| Tonfall (EN) | `en/compliance.html` + Glossar | "we run" statt "we live", "looking the other way" statt "duck", "compliance theatre" statt "bureaucracy theatre", "data protection" ohne Bindestrich, "Compliance that holds up" |
| Stack-Sync | `en/index.html` | Cloudflare → Gcore, Stripe → Prisma (Drift seit Iteration 12 korrigiert) |
| sitemap.xml | komplett neu | Alle Pfade auf `/de/` + `/en/`-Pattern, FR/IT/ES/SR raus, xhtml:link rel=alternate hreflang |
| robots.txt | unverändert | Fort-Knox-Mode bleibt während Stealth, Sitemap-Pfad konstant |
| View Transitions | alle 10 Marketing-Files | 0.2s ease → 0.35s/0.45s mit Apple-Bezier + Y-Slide + persistenter Header (rc-header) |

## Detaillierte Änderungen

### A) Subdirectory-Umbau (Commit f3cc7b0)

**Vorher:**
```
rc-tech-solutions.com/de.html
rc-tech-solutions.com/en.html
rc-tech-solutions.com/fr.html
rc-tech-solutions.com/it.html
rc-tech-solutions.com/es.html
rc-tech-solutions.com/sr.html
rc-tech-solutions.com/compliance.html
...
```

**Nachher:**
```
rc-tech-solutions.com/de/index.html
rc-tech-solutions.com/en/index.html
rc-tech-solutions.com/de/compliance.html
rc-tech-solutions.com/en/compliance.html
...
```

FR/IT/ES/SR-Hauptseiten gelöscht. EN-Hauptseite war strukturell synchronisiert mit DE-Master in Iteration 12, daher kein Inhalts-Update nötig - nur Strukturanpassung (Pfade, hreflang, Sprachschalter).

### B) Login-Hotfix (Commit 50b40ea)

JS-Redirect in `/de/login.html` zeigte nach erfolgreichem Login auf `de.html` (resolvte zu `/de/de.html`, tot). Auf `index.html` umgebogen → resolvet zu `/de/index.html`. Hotfix sofort nach Robert-Live-Test des Subdirectory-Umbaus.

### C) EN-Pilot Compliance (Commit c987025)

Vollübersetzung aus `/de/compliance.html` als Tonfall-Pilot. Robert hat ChatGPT-Feedback eingeholt mit 6 Verbesserungsvorschlägen, davon 6 angenommen mit minimalen Modifikationen (Commit 860848b):
- "stand up cleanly rather than duck" → "set it up properly instead of looking the other way"
- "We live our own compliance stack" → "We run our own compliance stack"
- "Compliance that actually holds" → "Compliance that actually holds up"
- "data-protection consulting" → "data protection consulting"
- "purely legal wording we leave to a lawyer" → "Legal sign-off stays with a lawyer"
- "No bureaucracy theatre" → "No compliance theatre"

Glossar etabliert für die restlichen EN-Files.

### D) EN-Stack-Sync (Commit 6ec0798)

EN-Hauptseite hatte noch alten Stack (Cloudflare + Stripe), DE-Master war in Iteration 12 schon auf Gcore + Prisma umgestellt. Drift korrigiert.

### E) EN-Software-Development + UX-Verbesserungen + sitemap (Commit c2299fb)

- Vollübersetzung aus `de/softwareentwicklung.html`
- Footer-Logo aus 7 Files entfernt (war optisch doppelt mit dem Brand-Text darunter)
- Sprachschalter in 4 DE-Landingpages ergänzt für Symmetrie zu EN (CSS + HTML in Header)
- "(kein Werbe-Sprech)" / "(no marketing-speak)" raus in DE+EN - selbstreferenziell ironisch (Robert hat das gecatcht: "kein werbesprech? ;)")
- sitemap.xml komplett neu auf `/de/` + `/en/`-Pattern mit xhtml:link rel=alternate hreflang

### F) EN Cloud + AI Integrations (Commit 48510dd, Subagent)

Subagent in eigenem Prozess parallel zur Hauptsession. Tonfall-Glossar gleich wie Pilot. Eigene Entscheidungen die der Subagent dokumentiert hat:
- "vapourware" UK-Schreibweise (passt zu Swiss-EU-Positionierung)
- "made in Graubünden" unübersetzt als regional reference
- "PowerPoint consulting" für "PowerPoint-Beratung" (Industry-Term)
- "no big bang" für "ohne Big-Bang" (Standard-Cloud-Migration-Term)

### G) View Transitions Upgrade (Commit dc2055c)

Vorher (zu kurz, zu hart):
```css
::view-transition-old(root){animation:vt-fade-out .2s ease both;}
::view-transition-new(root){animation:vt-fade-in .25s ease both;}
```

Nachher (Apple/Stripe-like):
```css
@keyframes vt-fade-out{from{opacity:1;transform:none;}to{opacity:0;transform:translateY(-12px);}}
@keyframes vt-fade-in{from{opacity:0;transform:translateY(12px);}to{opacity:1;transform:none;}}
::view-transition-old(root){animation:vt-fade-out .35s cubic-bezier(.4,0,.2,1) both;}
::view-transition-new(root){animation:vt-fade-in .45s cubic-bezier(.22,1,.36,1) .05s both;}
header{view-transition-name:rc-header;}
::view-transition-old(rc-header),::view-transition-new(rc-header){animation:none;}
```

Persistenter Header über `view-transition-name:rc-header` - die Top-Leiste bleibt während des Übergangs an Ort, nur der Body-Content wechselt. SPA-artiges Feeling. Auf 10 Marketing-Files (5 DE + 5 EN) per PowerShell-Sweep.

**🟡 OFFEN für 2026-04-30:** Robert merkt auf seinem Desktop Chrome keinen Unterschied. Möglicherweise Cache, Auth-Wall-Verhalten, oder Browser-Flag. Debug-Hints in Memory `project_view_transitions_debug.md`.

## Commits dieser Session

| Hash | Bereich | Beschreibung |
|---|---|---|
| `f3cc7b0` | Routing | Subdirectory-Umbau /de/-Pattern |
| `50b40ea` | Hotfix | Login-Redirect nach Subdirectory-Umbau |
| `21d2a0e` | EN-Hauptseite | Strukturanpassung an /en/-Pattern |
| `c987025` | EN-Pilot | /en/compliance.html (Tonfall-Referenz) |
| `6ec0798` | Sync | EN-Stack-Drift korrigiert |
| `860848b` | Tonfall | EN-Compliance Schliff nach Review |
| `c2299fb` | EN+UX | Software-Development + UX (Footer, Sprachschalter, sitemap) |
| `48510dd` | EN | Cloud Engineering + AI Integrations (Subagent) |
| `dc2055c` | UX | View Transitions smoother |

## Was im Repo ist (Stand Ende Session)

```
rc-tech-solutions.com/
├── index.html                          ← Coming-Soon DE+EN-Switcher (Stealth)
├── de/
│   ├── index.html                      ← Hauptseite DE
│   ├── compliance.html
│   ├── softwareentwicklung.html
│   ├── cloud-engineering.html
│   ├── ki-integrationen.html
│   ├── agb.html                        ← rechtsverbindlich (DE)
│   ├── datenschutz.html                ← rechtsverbindlich (DE)
│   ├── impressum.html
│   └── login.html
├── en/
│   ├── index.html                      ← Hauptseite EN
│   ├── compliance.html
│   ├── software-development.html       ← englischer Slug
│   ├── cloud-engineering.html
│   ├── ai-integrations.html            ← englischer Slug
│   └── login.html
├── logo.png, favicon.svg, robert.jpg + Varianten
├── robots.txt                          ← Fort-Knox bleibt während Stealth
├── sitemap.xml                         ← komplett neu auf /de/ + /en/-Pattern
└── CHANGELOG-2026-04-29-i18n-Umbau.md  ← diese Datei
```

## Was offen bleibt

1. **View-Transitions-Debug** auf Robert's Desktop Chrome (siehe Memory `project_view_transitions_debug.md` mit 9 Debug-Hints)
2. **Anwalts-Termin 4.5.2026** - nach Sign-Off Stand-Zeile auf "kanzleigeprüft", evtl. EN-Convenience-Übersetzungen für Rechtsseiten mit Disclaimer
3. **Locale-Detector** statt Coming-Soon-Page beim Launch (10-Min-Eingriff)
4. **EHB-i18n-Aufbau** mit BCP47-Pattern (eigene Session, siehe `project_ehb_i18n_strategy.md`)
5. **EHB-SEO-Basics** (Phase B aus dem SEO-Plan)
6. **PDF-Snapshots regenerieren** (User-Aufgabe, separater Workflow)
7. **Domain-Redirects** (ai-integrationen.ch etc. → 301 nach Launch)

## Why diese Session jetzt

Robert wollte vor dem Launch (geplant nach Anwalts-Termin 4.5.) sauber auf state-of-the-art Routing umstellen. Vor Launch: keine Backlinks zu schützen, robots.txt blockt eh alles. Nach Launch wäre Migration teuer. Plus: EN-Übersetzungen während Stealth-Mode bauen, dann ist beim Launch alles bereit.
