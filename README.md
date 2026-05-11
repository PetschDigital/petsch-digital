# petsch-digital.com

Marketing-Site für Petsch Digital LLC. Vier statische Pages: Hub, Sprint-Angebot, Datenschutz, Impressum. Zielgruppe: deutsche Solopreneurs, die ChatGPT/Notion nutzen, aber keine Workflow-Klammer haben.

## Stack

Vanilla HTML + CSS. Kein Framework, kein Build-Step, kein npm. System-Font-Stack, keine externen Fonts. Deploy via Cloudflare Pages Direct-Upload.

## Lokal testen

```bash
cd /Users/steffenpetschaelis/projects/petsch-digital
python3 -m http.server 8000
```

Dann `http://localhost:8000` im Browser. Alternative falls Python nicht da ist: `npx serve .` oder `php -S localhost:8000`.

## Deploy zu Cloudflare Pages (Direct Upload)

1. Cloudflare-Dashboard öffnen → Workers & Pages → Create application → Pages → **Upload assets**
2. Project-Name: `petsch-digital`
3. Drag-and-Drop: gesamter Inhalt des Projekt-Ordners (alle `.html`, `assets/`, `_headers`)
4. Deploy site klicken
5. Custom Domain anbinden: Pages-Projekt → Custom domains → `petsch-digital.com` hinzufügen. DNS läuft schon bei Cloudflare, daher automatische CNAME-Konfiguration.

Re-Deploy: bei Inhalts-Änderungen einfach erneut Direct-Upload mit allen Files. Cloudflare ersetzt das Deployment.

## Files

```
petsch-digital/
├── index.html          Hub-Page
├── sprint.html         Sprint-Angebot (1.500€ Drei-Tage-Sprint)
├── datenschutz.html    Datenschutzerklärung (Prighter-Wording)
├── impressum.html      Impressum (DSGVO-Pflicht)
├── assets/
│   └── css/
│       └── style.css   Shared Styles, Design-Tokens
├── _headers            Cloudflare Pages Security-Header
└── README.md           Diese Datei
```

## Content-Änderungen

- **Hub-Headline / Subline**: `index.html`, Hero-Section
- **Sprint-Pattern, Pricing, FAQ**: `sprint.html`
- **Datenschutz-Wording**: `datenschutz.html` → 1:1 aus Prighter-Dashboard
- **Impressum (US-Adresse, Kontakt, Steuer-ID)**: `impressum.html` und parallel in Footer aller Pages
- **Compliance-Badge**: Footer in allen vier `.html`-Files (Snippet aus Prighter-Dashboard)
- **Design-Tokens (Farben, Spacing, Typo)**: `assets/css/style.css`, `:root`-Block oben

## Externe Links

- Discovery-Call-Form (Tally): `https://tally.so/r/lbV4VW`
- Loom-Walkthrough für Sprint-Page: folgt, später in `.loom-embed` einsetzen
