# Simulatore Cambio Fornitore Energia

Applicazione web per simulare il passaggio a un nuovo operatore elettrico e calcolare il risparmio annuo sulla bolletta.

## Struttura

```
simulatore-cambio-fornitore-energia/
├── index.html              # Applicazione completa (HTML + CSS + JS)
├── netlify.toml            # Configurazione Netlify (headers sicurezza)
├── robots.txt              # Configurazione SEO crawler
├── sitemap.xml             # Mappa del sito
├── README.md               # Documentazione
└── docs/                   # Documenti di riferimento
    ├── octopus.pdf         # Esempio bolletta Octopus Energy
    ├── hera.pdf            # Esempio bolletta Hera STG
    └── confronto_energia.xlsx  # Foglio calcolo confronto tariffe
```

## Funzionalità

- Wizard guidato in 4 step
- Confronto: operatore attuale vs nuovo operatore
- Database 23+ operatori con auto-compilazione prezzi
- Supporto Mercato Libero e Servizio Tutele Graduali (STG)
- Calcolo dettagliato: energia, rete, oneri, accise, IVA
- Risparmio annualizzato con barre comparative
- Design responsive (mobile-first)
- Dark theme con effetto glassmorphism

## Formula di Calcolo

```
Totale = (Energia + Commercializzazione + Rete + Quota Fissa + Quota Potenza + Accise) × (1 + IVA)

dove:
- Energia = consumo_kWh × prezzo_energia
- Commercializzazione = quota_venditore × mesi
- Rete = consumo_kWh × costi_rete_oneri
- Quota Fissa = quota_fissa_ARERA × mesi
- Quota Potenza = potenza_kW × quota_potenza_ARERA × mesi
- Accise = consumo_kWh × aliquota_accise
- IVA = 10% (uso domestico)
```

## Parametri ARERA (default)

| Parametro | Valore | Note |
|-----------|--------|------|
| Rete + Oneri | 0,044845 €/kWh | Costi passanti, uguali per tutti |
| Quota fissa | 9,45 €/mese | Costi fissi di rete |
| Quota potenza | 2,106667 €/kW/mese | Dipende dalla potenza impegnata |
| Accise | 0,0227 €/kWh | Imposta erariale (>3kW residenti) |
| IVA | 10% | Uso domestico |

## Operatori Inclusi

Octopus Energy, Enel Energia, Eni Plenitude, A2A Energia, Edison Energia, Sorgenia, Hera Comm, Iren Mercato, Acea Energia, NeN, Pulsee, Wekiwi, E.ON Energia, Illumia, Fastweb Energia, Dolomiti Energia, ENGIE Italia, Alperia, Duferco Energia, Etruria Luce e Gas, Estra Energie, Optima Italia, Sinergas

## Tecnologie

- HTML5 + CSS3 + JavaScript vanilla (ES5/ES6)
- Nessuna dipendenza esterna (solo Google Fonts)
- Analytics: GoatCounter (privacy-friendly, no cookie)
- Hosting: Netlify

## SEO e PWA

- Meta tags completi (title, description, keywords)
- Open Graph e Twitter Cards
- Schema.org structured data (WebApplication)
- PWA meta tags per installazione mobile
- Canonical URL configurato

## Sviluppo Locale

```bash
# Opzione 1: Python
python -m http.server 8000

# Opzione 2: Node.js
npx http-server

# Opzione 3: Aprire direttamente
open index.html
```

## Disclaimer

I prezzi delle offerte sono indicativi (dicembre 2025) e potrebbero variare. Verifica sempre sul sito ufficiale dell'operatore prima di sottoscrivere un contratto.

I costi di rete, oneri di sistema, accise e IVA sono regolati da ARERA e sono uguali per tutti i fornitori.

## Licenza

MIT - Usa liberamente per scopi personali o commerciali.
