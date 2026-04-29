# TODO — Umami-Analytics Frontend-Integration

**Status:** wartet auf Infrastruktur-Sprint (siehe `infrastruktur/runbooks/sprint-umami-analytics.md`)
**Geschätzter Aufwand:** ~30 min
**Voraussetzungen:** Umami muss live sein, dann werden zwei Werte gebraucht:
- `BACKEND_URL`: voraussichtlich `https://analytics.rc-tech-solutions.com`
- `WEBSITE_ID`: UUID, wird im Umami-Dashboard beim Anlegen der Website "RC-Tech Solutions" generiert

---

## 1. Tracking-Script in alle 16 HTML-Files einbauen

**Stelle:** im `<head>`-Block, irgendwo zwischen `<meta name="theme-color">` und dem `<style>`-Block.

**Snippet (mit Platzhaltern):**
```html
<script async defer src="https://analytics.rc-tech-solutions.com/script.js" data-website-id="WEBSITE_ID_HIER_EINSETZEN"></script>
```

**Files (16):**
- `de/index.html`, `en/index.html`
- `de/softwareentwicklung.html`, `en/software-development.html`
- `de/cloud-engineering.html`, `en/cloud-engineering.html`
- `de/ki-integrationen.html`, `en/ai-integrations.html`
- `de/compliance.html`, `en/compliance.html`
- `de/datenschutz.html`, `en/privacy.html`
- `de/impressum.html`, `en/imprint.html`
- `de/agb.html`, `en/terms.html`

**Nicht** in: `index.html` (Locale-Detector-Page, redirect-only — kein Tracking nötig)

---

## 2. Custom Events einbauen

Umami erkennt automatisch Klicks auf Elemente mit `data-umami-event="<name>"`-Attribut. Folgende Stellen markieren:

### 2.1 Hero-CTA "Erstgespräch vereinbaren"
**File:** `de/softwareentwicklung.html` (Zeile ~345)
```html
<a href="#contact" class="b1" data-umami-event="erstgespraech-cta-software">
  Erstgespräch vereinbaren
```

**File:** `en/software-development.html` (analog)
```html
<a href="#contact" class="b1" data-umami-event="discovery-cta-software">
```

### 2.2 EHB-Link auf Index-Page
**File:** `de/index.html` (Produkt-Karte)
```html
<a href="https://easyandsmartbooking.com" class="prod-link" target="_blank" rel="noopener" data-umami-event="ehb-link-index">
```

**File:** `en/index.html` (analog mit `data-umami-event="ehb-link-index-en"`)

### 2.3 Email-Click `info@rc-tech-solutions.com`
Mehrere Stellen — im Footer, Contact-Section, etc. **In allen 10 Marketing-Files** suchen und ergänzen:
```html
<a href="mailto:info@rc-tech-solutions.com" data-umami-event="email-info-click">
```

### 2.4 Service-Page-Outbound-Klicks
- Status-Page-Link im Footer: `data-umami-event="status-link-click"`
- Sub-Processor-Verweise auf Privacy: `data-umami-event="privacy-deep-link"`

### 2.5 Optional — KPI-spezifisch
- "Kontakt"-Button im Header: `data-umami-event="header-contact-click"`
- Footer-Service-Links: `data-umami-event="footer-service-click"` (mit individuellen IDs falls gewünscht)

---

## 3. Privacy-Policy Update (DE + EN)

### 3.1 DE — `de/datenschutz.html`

**Stelle:** Section §6 ("Sub-Auftragsverarbeiter") oder als neue Section §X "Reichweitenmessung" einfügen. Vorschlag:

```html
<section id="v6-analytics" class="block">
  <h2><span class="num">X.</span> Reichweitenmessung</h2>
  <p>Wir betreiben ein <strong>selbst gehostetes Analytics-Tool (Umami)</strong> auf unserer eigenen EU-Infrastruktur (Hetzner Nürnberg/Helsinki, siehe Ziff. 4). Es werden keine Cookies gesetzt, keine personenbezogenen Daten gespeichert und keine Daten an Dritte übermittelt. Erfasst werden ausschliesslich anonymisierte Aggregat-Daten:</p>
  <ul>
    <li>Aufgerufene Seiten und Verweildauer</li>
    <li>Browser- und Geräte-Typ (Desktop/Mobile/Tablet)</li>
    <li>Land der Anfrage (auf Land-Ebene, ohne IP-Speicherung)</li>
    <li>Verweisende Webseite (Referrer)</li>
  </ul>
  <p>Die Daten werden ausschliesslich zur Optimierung unserer Webseite verwendet und nach 12 Monaten automatisch gelöscht. Rechtsgrundlage: berechtigtes Interesse an Reichweitenmessung (Art. 6 Abs. 1 lit. f DSGVO / Art. 31 Abs. 1 DSG).</p>
</section>
```

**Plus:** Den bestehenden Satz in §8 (Cookies) anpassen:
> Alt: "...keine Analytics-Dienste Dritter (kein Google Analytics, Meta Pixel, etc.)..."
> Neu: "...keine Analytics-Dienste Dritter (kein Google Analytics, Meta Pixel, etc.). Für die Reichweitenmessung verwenden wir ein selbst gehostetes, cookieloses Tool (siehe Ziff. X)."

**TOC-Eintrag** in der Inhaltsübersicht ergänzen.

### 3.2 EN — `en/privacy.html`

Analoge Änderung. Vorschlag-Snippet:

```html
<section id="v6-analytics" class="block">
  <h2><span class="num">X.</span> Web Analytics</h2>
  <p>We operate a <strong>self-hosted analytics tool (Umami)</strong> on our own EU infrastructure (Hetzner Nuremberg/Helsinki, see clause 4). No cookies are set, no personal data is stored, and no data is transmitted to third parties. Only anonymised aggregate data is collected:</p>
  <ul>
    <li>Pages visited and time on page</li>
    <li>Browser and device type (desktop/mobile/tablet)</li>
    <li>Country of request (country-level, without IP storage)</li>
    <li>Referring website</li>
  </ul>
  <p>Data is used solely to optimise our website and automatically deleted after 12 months. Legal basis: legitimate interest in audience measurement (Art. 6(1)(f) GDPR / Art. 31(1) FADP).</p>
</section>
```

**Stand-Zeile** auf beiden Privacy-Files: Version + Datum hochziehen.

---

## 4. Verifikation nach Deployment

- [ ] Im Umami-Dashboard: Realtime-View zeigt Visits sobald gepullt
- [ ] Custom Events erscheinen in der Events-Section nach Click-Tests
- [ ] Privacy-Policy-Update sichtbar und korrekt verlinkt
- [ ] Robots.txt-Block schliesst Tracker-Domain NICHT aus (analytics.rc-tech-solutions.com sollte erreichbar sein)
- [ ] Auf einem AdBlocker-aktiven Browser-Profil getestet — sollte trotzdem tracken (Umami umgeht die meisten Blocker, weil es nicht in den Blocklists ist)

---

## 5. Backend-URL einsetzen — Such-und-Ersetz

Sobald BACKEND_URL und WEBSITE_ID bekannt sind, einfaches Find-and-Replace:

```bash
# In allen 16 HTML-Files:
# Suchen: WEBSITE_ID_HIER_EINSETZEN
# Ersetzen: <UUID aus Umami-Dashboard>
```

Wenn BACKEND_URL anders als geplant ist (z.B. nicht `analytics.rc-tech-solutions.com`):
```bash
# Suchen: https://analytics.rc-tech-solutions.com/script.js
# Ersetzen: https://<echte-url>/script.js
```
