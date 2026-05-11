# Final-Review Report

Stand: 11. Mai 2026 · Vor Deploy auf petsch-digital.com

## Check 1: Interne Links

✅ Alle internen Links zeigen auf existierende Files und Anchor.

- `/sprint.html`, `/plus.html`, `/system.html`, `/datenschutz.html`, `/impressum.html`, `/` (index): alle Dateien vorhanden
- `/assets/css/style.css` und `/assets/Fonts/Geist/Geist-Regular.ttf`: vorhanden und über HTTP erreichbar
- Anker `#main` (Skip-Link) auf allen sechs Pages vorhanden
- Hub-Anker `#angebote`, `#ueber`, `#kontakt` auf index.html vorhanden
- Sprint/Plus/System-Anker `#kontakt` (Final-CTA) lokal vorhanden; `/#ueber` und `/#kontakt` von Stufen-Pages und Legal-Pages aus zeigen korrekt auf Hub-Anker
- `#mOverview` Anker in datenschutz.html: vorhanden in der Inhaltsübersicht und in der Body-Section

## Check 2: Externe Links mit target="_blank" + rel="noopener"

⚠️ **6 Treffer ohne `target="_blank"` und `rel="noopener"`**: das Prighter-Trust-Badge-Image-Wrapping-`<a>` im Footer auf allen sechs Pages.

```
plus.html:292:        <a href="https://app.prighter.com/portal/15539856848">
index.html:231:       <a href="https://app.prighter.com/portal/15539856848">
impressum.html:98:    <a href="https://app.prighter.com/portal/15539856848">
system.html:305:      <a href="https://app.prighter.com/portal/15539856848">
datenschutz.html:348: <a href="https://app.prighter.com/portal/15539856848">
sprint.html:288:      <a href="https://app.prighter.com/portal/15539856848">
```

Der Caption-Link „powered by Prighter" hat dagegen korrekt `target="_blank" rel="noopener"`. Das ist konsistent zum Prighter-Original-Snippet — Branchenüblich ist es, den Badge im selben Tab zu öffnen. **Empfehlung:** Tab-Verhalten an die anderen externen Links angleichen (siehe „Fixes vor Deploy").

Alle Tally-Links (4 pro Stufen-Page, 2 auf Hub) haben `target="_blank" rel="noopener"` korrekt gesetzt.

## Check 3: Tally-URL-Konsistenz

✅ Alle URLs an den korrekten Stellen.

**`vGExkd` (Erstgespräch):**
- index.html: Hero-Secondary + Final-CTA (2× ✓)
- sprint.html: Hero-Secondary + Final-CTA-Sublink (2× ✓)
- plus.html: Hero-Primary + Final-CTA (2× ✓)
- system.html: Hero-Primary + Final-CTA (2× ✓)

**`lbV4VW` (Sprint-Anfrage):**
- sprint.html: Hero-Primary + Final-CTA-Primary (2× ✓)
- Nirgendwo sonst — korrekt scoped auf Sprint-Page

Datenschutz und Impressum haben keine Tally-Links — korrekt.

## Check 4: Wording-Konsistenz

### Discovery-Call

⚠️ **1 echte Inkonsistenz, 6 Content-Kontext-Treffer (in Ordnung):**

| Datei:Zeile | Kontext | Beurteilung |
|---|---|---|
| index.html:186 | Hub-FAQ DSGVO: „Details im Discovery-Call" | ❌ **Marketing-Kontext — sollte `Erstgespräch` sein** |
| plus.html:64 | Nutzen-Block: „nach jedem Discovery-Call dein Briefing" | ✅ Content (Kunde's eigene Calls) |
| plus.html:108 | Muster-Card: „Discovery-Call-Vorbereitung" | ✅ Content (Kunde's Workflow) |
| system.html:102 | Beispiel-Card: „Vom ersten Lead bis zum Discovery-Call" | ✅ Content |
| system.html:119 | Beispiel-Card: „Discovery-Call-Buchungs-Link" | ✅ Content (technisch) |
| sprint.html:100 | Pain-Bullet: „Discovery-Calls dauern zu lang" | ✅ Content (Pain-Beschreibung) |
| sprint.html:104 | Muster-Card: „Du sparst Discovery-Call-Zeit" | ✅ Content |

### Workflow-Custom / Custom-Page

✅ 0 Treffer. Komplett umbenannt auf System.

### Pattern (Marketing-Kontext)

| Datei:Zeile | Kontext | Beurteilung |
|---|---|---|
| sprint.html:204 | Abgrenzung: „außerhalb LLM-Patterns" | ✅ Technisch |
| system.html:41 | Hero-Lead: „statt zum Pattern-Katalog" | ⚠️ Rhetorischer Kontrast „Pain vs. Pattern" — Stilistische Entscheidung, kein klarer Bug |

### Tool-Stack (Marketing-Kontext)

| Datei:Zeile | Kontext | Beurteilung |
|---|---|---|
| index.html:7 | Meta-Description: „auf deinem Tool-Stack gebaut" | ❌ **Marketing-Kontext — sollte umformuliert werden** |
| index.html:10 | OG-Description: gleiches Wording | ❌ **Marketing-Kontext — sollte umformuliert werden** |
| plus.html:85 | Zielgruppe-Bullet: „Du hast einen erprobten Tool-Stack" | ✅ Content (beschreibt Kunde's Setup) |

## Check 5: Pricing-Konsistenz

✅ Alle Preise konsistent:
- **Sprint 1.500 €**: Hub-Card, Sprint-Meta, Sprint-Hero, Sprint-Preis-Block — überall identisch
- **Plus 2.500 €**: Hub-Card, Plus-Meta, Plus-Hero, Plus-Preis-Block, Sprint-FAQ-Querverweis — überall identisch
- **System ab 5.000 €**: Hub-Card, System-Meta, System-Hero, System-Preis-Block, Sprint-FAQ-Querverweis — überall identisch
- **System Range 5.000–12.000 €**: System Beispiele-Cards + Preis-Block — konsistent

## Check 6: Mail-Adresse-Konsistenz

✅ Alle `mailto:`-Links zeigen auf `kontakt@petsch-digital.com`:
- impressum.html:53 (Kontakt-Block)
- datenschutz.html:75 (Verantwortlicher-Block)
- index.html:158 (Über-Sub-Block)

Zusätzlich `mailto:dsb@dsb.gv.at` in datenschutz.html:299 — österreichische Datenschutzbehörde, korrekt.

## Check 7: 30-Tage-Bugfix-Garantie

✅ Alle drei Stufen-Pages erwähnen die Garantie:
- **sprint.html**: Meta, OG, Hero-Lead, Nutzen-Block-Card 03, FAQ-2-Antwort — 5× erwähnt
- **plus.html**: „Was im Plus-Paket steckt"-Liste (Bullet 6), Ablauf-Card 05 „Bugfix-Fenster 30 Tage" — 2× erwähnt
- **system.html**: „Was im System-Paket steckt"-Liste (Bullet 7), Ablauf-Card 06 „Bugfix-Fenster 30 Tage", Preis-Block — 3× erwähnt

## Check 8: Meta-Tags

✅ Alle sechs Pages haben `<title>` und `<meta name="description">`.

| Datei | Title | Description-Länge |
|---|---|---|
| index.html | „petsch.digital — Workflows für Solopreneurs" | 111 Z. ✓ |
| sprint.html | „Workflow-Sprint — Petsch Digital" | 194 Z. ✓ |
| plus.html | „Workflow-Plus — Petsch Digital" | 135 Z. ✓ |
| system.html | „Workflow-System — Petsch Digital" | 137 Z. ✓ |
| datenschutz.html | „Datenschutzerklärung — Petsch Digital" | 104 Z. ✓ |
| impressum.html | „Impressum — Petsch Digital" | 77 Z. ⚠️ **unter 100-Zeichen-Schwelle** |

Impressum ist noindex,follow — SEO-Relevanz ist eh begrenzt. Aber Brief-Threshold ist nicht erfüllt.

## Check 9: Footer-Konsistenz

✅ Alle sechs Pages haben identischen Footer-Aufbau:

| Datei | Compliance-Badge | Diensteanbieter | EU-Vertreter | DS-Link | Imp-Link |
|---|:---:|:---:|:---:|:---:|:---:|
| index.html | 1 ✓ | ✓ | ✓ | 1 ✓ | 1 ✓ |
| sprint.html | 1 ✓ | ✓ | ✓ | 1 ✓ | 1 ✓ |
| plus.html | 1 ✓ | ✓ | ✓ | 1 ✓ | 1 ✓ |
| system.html | 1 ✓ | ✓ | ✓ | 1 ✓ | 1 ✓ |
| datenschutz.html | 1 ✓ | ✓ | ✓ | 1 ✓ | 1 ✓ |
| impressum.html | 1 ✓ | ✓ | ✓ | 1 ✓ | 1 ✓ |

US-Adresse auf allen Pages in finalem 4-Zeilen-Layout (`Ste 225C, Oakland Park` / `FL 33311, USA`). Prighter-Badge erscheint sechsmal.

## Zusammenfassung

**Alle Checks bestanden:** überwiegend ja, mit drei Marketing-Wording-Bugs und zwei Minor-Issues.

### Kritische Fehler vor Deploy

Keine Fehler, die Deploy verhindern würden. Site ist funktional komplett.

### Empfohlene Fixes vor Deploy

1. **index.html:186** „Details im Discovery-Call" → „Details im Erstgespräch" (Hub-FAQ DSGVO)
2. **index.html:7 + :10** Meta- und OG-Description: „auf deinem Tool-Stack gebaut" umformulieren, z.B. „mit den Tools, die du schon nutzt"
3. **Prighter-Badge-Anchor auf allen 6 Pages**: `target="_blank" rel="noopener"` ergänzen für Konsistenz mit anderen externen Links

### Empfohlene Fixes nach Deploy (Nice-to-have)

4. **impressum.html Meta-Description** auf min. 100 Zeichen erweitern (aktuell 77, Page ist noindex aber)
5. **system.html:41 „Pattern-Katalog"** stilistisch in „Muster-Katalog" ändern für volle Konsistenz — alternativ als bewusste Rhetorik behalten

### Visuell und inhaltlich

Diese Checks bleiben Steve überlassen:
- Mobile-Responsiveness der drei Stufen-Cards auf der Hub
- Lesefluss der Sprint-FAQ und der Datenschutz-Glossar-Sektion
- Verständlichkeit der Pricing-Hinweise (Festpreis vs. Range bei System)
- Hover-States aller Buttons und Links
