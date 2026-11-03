# Radici di Sostenibilità — Gruppo Casalasco

Pagina web per la comunicazione e il download del **Bilancio di Sostenibilità 2025** del Gruppo Casalasco.

Artefatto del Project Work del CdS Informatica per le Aziende Digitali (L-31), Università Telematica Pegaso
Tema n. 3 "Tecnologia web per la sostenibilità d'impresa" — Traccia 17 "Sviluppo di una pagina web per il download dei report di sostenibilità di un'impresa del settore primario".

Autore: Federico Francesco Bello (matricola 0312401032)

## Contenuto del repository

```
radici-di-sostenibilita/
├── assets/
│   └── Bilancio-Sostenibilita-2025-Gruppo-Casalasco.pdf
├── .gitignore
├── README.md
├── index.html
└── style.css
```

Il progetto non usa framework, librerie JavaScript o processi di build: sono solo due file sorgente HTML e CSS più il PDF del report.

## Come eseguire la pagina

**Online:** se GitHub Pages è attivo, la pagina è visitabile all'indirizzo
`https://federicobello.github.io/radici-di-sostenibilita/`

**In locale:**

1. Scaricare il repository (pulsante *Code → Download ZIP*) oppure clonarlo:
   ```bash
   git clone https://github.com/FedericoBello/radici-di-sostenibilita.git
   ```
2. Aprire `index.html` con un qualsiasi browser moderno (Chrome, Firefox, Safari, Edge).

In alternativa, si può avviare un piccolo server locale dalla cartella del progetto:
```bash
python3 -m http.server 8000
```
e visitare `http://localhost:8000`.

L'unica risorsa esterna è il caricamento dei font da Google Fonts: senza connessione la pagina resta funzionante e usa i font di riserva (Georgia e Segoe UI / sans-serif).

## Struttura della pagina

| # | Sezione | id | Contenuto |
|---|---------|----|-----------|
| 1 | Header | — | Navigazione fissa (sticky) e pulsante di download sempre visibile |
| 2 | Hero | — | Titolo, introduzione, call-to-action, illustrazione SVG |
| 3 | Il Gruppo in numeri | `#numeri` | Dati aggregati 2025 (Highlights del Bilancio) |
| 4 | Custodi della terra | `#filiera` | Filiera agricola e Decalogo per la Sostenibilità |
| 5 | Impegno ambientale | `#ambiente` | Tabella degli indicatori ambientali 2025 |
| 6 | Scarica il Bilancio | `#download` | Download del report in PDF |
| 7 | Footer | — | Nota didattica e link rapidi |

## Funzionalità

- **Download del report:** link `<a href="assets/…pdf" download="…">`; l'attributo `download` chiede al browser di salvare il file invece di aprirlo.
- **Responsività:** layout desktop-first con due media query (900px e 560px) e dimensioni dei titoli fluide con `clamp()`.
- **Accessibilità (riferimento WCAG 2.1):**
  - link "Salta al contenuto principale", visibile al focus da tastiera;
  - HTML semantico (`header`, `nav`, `main`, `section`, `footer`, `ol`, `table` con `caption` e `scope`);
  - `aria-label` sulle due navigazioni e `aria-labelledby` sulla sezione dei numeri;
  - elementi decorativi (SVG) con `aria-hidden="true"` e `focusable="false"`;
  - titolo nascosto alla vista ma leggibile dagli screen reader (classe `.visually-hidden`);
  - focus da tastiera sempre visibile (`:focus-visible`);
  - rispetto della preferenza `prefers-reduced-motion`;
  - unità in `rem` per rispettare la dimensione del carattere impostata dall'utente;
  - attributo `lang="it"` per la corretta pronuncia degli screen reader.

## Fonte dei contenuti

Testi e dati sono tratti dal *Bilancio di Sostenibilità 2025* del Gruppo Casalasco, incluso nella cartella `assets/`. La pagina è stata realizzata a scopo esclusivamente didattico; il report resta di proprietà del Gruppo Casalasco.
