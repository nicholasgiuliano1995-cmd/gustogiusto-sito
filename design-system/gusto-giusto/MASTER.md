# Gusto Giusto — Design System (MASTER)

> **Source of Truth** del sistema di design del sito vetrina B2B di **Gusto Giusto OOO**,
> DMC italiana premium per tour operator russofoni.
>
> **LOGICA:** quando si costruisce una pagina specifica, controllare prima
> `design-system/gusto-giusto/pages/[nome-pagina].md`. Se esiste, le sue regole
> **sovrascrivono** questo file. Altrimenti si seguono le regole qui sotto.
>
> Generato a partire dalla skill `ui-ux-pro-max` (pattern *Storytelling + Feature-Rich*,
> stile *Liquid Glass / editorial luxury*) e **adattato al brand bloccato** definito in
> `CLAUDE.md`. Palette e font NON sono negoziabili: vincono sempre quelli del brand.

---

**Progetto:** Gusto Giusto OOO
**Categoria:** Luxury / Premium Travel (DMC B2B)
**Stack:** singolo file `index.html` autoconsistente (CSS + JS inline), bilingue RU/EN via `data-i18n`
**Mood:** sobrio, premium, editoriale, professionale — niente effetti volgari o caotici

---

## 1. Colore (palette di brand — bloccata)

| Ruolo | Token CSS | Hex | Uso |
|-------|-----------|-----|-----|
| Primario / scuro | `--navy` | `#1B2A40` | Testo titoli, superfici scure, CTA primaria |
| Navy soft | `--navy-soft` | `#2A3A52` | Stati hover/elevazioni su scuro |
| Navy deep | `--navy-deep` | `#0F1A2B` | Fondali profondi, gradienti |
| Sfondo / chiaro | `--cream` | `#F5EDD6` | Background principale |
| Cream soft | `--cream-soft` | `#FAF6E8` | Superfici alternate, card chiare |
| Cream deep | `--cream-deep` | `#EBE0C0` | Bordi morbidi su chiaro |
| Accento | `--gold` | `#C9A84C` | Dettagli, hairline, accenti tipografici |
| Gold soft | `--gold-soft` | `#D9BD6F` | Highlight, glow |
| Gold deep | `--gold-deep` | `#A88A30` | Testo oro su chiaro (contrasto AA) |
| Inchiostro | `--ink` | `#1A1A1A` | Testo corpo su chiaro |
| Muted | `--muted` | `#6B6B6B` | Testo secondario |
| Linea | `--line` / `--line-soft` | `#D9D2BC` / `#E8E2CF` | Bordi, divisori |

**Trattamento del colore**
- **Navy** = autorevolezza e profondità; usato per superfici immersive (pannello hero, sezione gruppi, footer).
- **Cream** = eleganza calda; è la "carta" del sito, lo sfondo di default.
- **Gold** = accento prezioso e parsimonioso: hairline da 1px, occhielli (`eyebrow`), numerali, micro-dettagli. **Mai** grandi campiture piene d'oro.
- Contrasto: testo corpo su crema ≥ 4.5:1 (`--ink`/`--muted`); oro su chiaro solo con `--gold-deep`; su navy usare crema, non oro pieno per testo lungo.
- Accenti funzionali (focus ring) in oro semitrasparente, sempre visibili.

## 2. Tipografia

- **Titoli:** `Cormorant Garamond` (serif editoriale) — pesi 300/400/500/600, corsivo per enfasi (`<em>` in oro).
- **Corpo / UI:** `Inter` — pesi 300/400/500/600.
- **Occhiello (`eyebrow`):** Inter 11px, `letter-spacing: 0.25em`, uppercase, colore oro.

### Scala tipografica

| Livello | Font | Dimensione | Line-height | Note |
|---------|------|-----------|-------------|------|
| Display / Hero H1 | Cormorant | `clamp(46px, 5.4vw, 82px)` | 1.04 | enfasi `<em>` corsivo oro |
| H2 sezione | Cormorant | `clamp(38px, 5vw, 58px)` | 1.1 | |
| H3 card | Cormorant | 28–32px | 1.2 | |
| H4 | Cormorant | 22–24px | 1.3 | |
| Lead / sub | Inter | 17–19px | 1.7 | colore `--muted`, max 540px |
| Body | Inter | 16px | 1.6–1.75 | |
| Small / meta | Inter | 10–13px | 1.5 | tracking ampio, uppercase per label |
| Eyebrow | Inter | 11px | 1 | `0.25em`, uppercase, oro |

Misura della riga: 60–75 caratteri desktop, 35–60 mobile.

## 3. Spaziature (ritmo 4 / 8 px)

| Token | Valore | Uso |
|-------|--------|-----|
| `--space-xs` | 4px | gap minimi |
| `--space-sm` | 8px | gap icone/inline |
| `--space-md` | 16px | padding standard |
| `--space-lg` | 24px | padding componenti |
| `--space-xl` | 32px | gap larghi |
| `--space-2xl` | 48px | margini di sezione interni |
| `--space-3xl` | 64px | padding hero/blocchi |
| Sezioni | 80–120px verticale | `padding: 120px 48px` desktop, `80px 24px` mobile |

## 4. Elevazione (ombre)

| Livello | Valore | Uso |
|---------|--------|-----|
| `--shadow-sm` | `0 1px 2px rgba(27,42,64,.06)` | lift sottile |
| `--shadow-md` | `0 14px 30px rgba(27,42,64,.14)` | card, bottoni hover |
| `--shadow-lg` | `0 20px 46px rgba(27,42,64,.18)` | card in evidenza |
| `--shadow-xl` | `0 40px 90px rgba(27,42,64,.38)` | hero-card / glass su navy |

Scala unica e coerente: niente valori d'ombra casuali.

## 5. Bottoni (`.cta`)

Stile a lettering: Inter 12px, `letter-spacing: 0.18em`, uppercase, padding `16px 32px`, freccia `→` come affordance.

- **Primaria** (`.cta.primary`): fondo navy, testo crema → hover fondo oro.
- **Outline** (`.cta.outline`): bordo navy, testo navy → hover fondo navy, testo crema.
- Transizione `0.3s cubic-bezier(0.22,0.61,0.36,1)`; hover `translateY(-2px)` + ombra md.
- `cursor: pointer`, focus ring oro visibile, touch target ≥ 44px.

## 6. Card

- **Card chiara:** fondo `--cream-soft`, hairline 1px `--gold`/`--line`, padding 40–48px, ombra `--shadow-lg/xl`.
- **Glass card (su navy):** fondo crema translucido + `backdrop-filter: blur(...)`, hairline oro, ombra `--shadow-xl` — trattamento *liquid glass* del sistema, usato con misura.
- Hover: `translateY(-4px)` + ombra più profonda; transizione 0.4s.
- Niente hover che spostano il layout circostante.

## 7. Movimento

- Micro-interazioni 150–300ms; transizioni d'ingresso/scena 400–900ms con `cubic-bezier(0.22,0.61,0.36,1)`.
- Ingresso più lento dell'uscita; stagger 30–80ms tra elementi.
- Animare solo `opacity` / `transform`. Niente reflow/CLS.
- **Rispettare sempre `prefers-reduced-motion`** (le animazioni sono già condizionate da `.anim` + media query nel sito).

## 8. Pattern di pagina

- **Storytelling + Feature-Rich**, CTA above the fold.
- Ordine: Hero → linee prodotto/feature → prove → CTA → contatti.
- Una sola CTA primaria per schermata; le secondarie subordinate.

## 9. Regole commerciali (da CLAUDE.md — invalicabili)

- Azienda sempre **"Gusto Giusto OOO" / "Gusto Giusto"**. Mai "S.r.l." o suffissi italiani.
- Sede: **"Mosca e San Pietroburgo"**.
- Mai prezzi di upsell o costi netti/fornitori: solo **"от / from"**.
- Vaporetto a Venezia (e isole della laguna): **mai incluso**, pagato sul posto.
- Mai citare **AIS** o associazioni di sommelier.

## 10. Anti-pattern (NON usare)

- ❌ Cambiare palette o font del brand.
- ❌ Oro in grandi campiture / effetti "ricchi" volgari.
- ❌ Emoji come icone (usare SVG/HTML).
- ❌ Hover che spostano il layout, transizioni istantanee, animazioni > 500ms decorative.
- ❌ Testo a basso contrasto, focus invisibili.
- ❌ File esterni o dipendenze nuove: tutto resta in `index.html`.
