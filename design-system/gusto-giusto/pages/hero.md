# Hero — Override di pagina

> **PROGETTO:** Gusto Giusto OOO
> **Tipo:** Landing / sezione di apertura (above the fold)
>
> ⚠️ Le regole qui sovrascrivono `../MASTER.md`. Sono documentate solo le deviazioni;
> per tutto il resto vale il Master. Palette e font restano quelli di brand.

---

## Obiettivo
Primo impatto forte e raffinato: comunicare in pochi secondi *"DMC italiano premium,
B2B, per tour operator russofoni, ciclo completo"*. Composizione editoriale, calma, costosa.

## Layout
- **Split editoriale** su 2 colonne (≈1.15fr / 1fr) su desktop, **1 colonna** sotto 900px.
- Colonna sinistra = contenuto (eyebrow → H1 → sub → CTA → proof strip).
- Colonna destra = pannello **navy immersivo** con **glass hero-card** che fluttua.
- Min-height `100vh`, padding `130px 48px 80px` (desktop) / `100px 24px 60px` (mobile).

## Trattamento visivo
- Fondo crema con **pannello navy** sul lato destro (45% desktop / fascia bassa su mobile).
- **Glow oro radiale** morbido + texture finissima (low-opacity) per profondità — niente rumore invadente.
- **Hairline oro** verticale come separatore editoriale tra le colonne.
- Glass card: crema translucida + `backdrop-filter: blur`, bordo oro 1px, ombra `--shadow-xl`.
- **Emblema anfora = logo esistente** (immagine già presente nel nav, riusata via clone JS).
  **NON ridisegnare il logo.** Va trattato come marchio premium dentro la card.

## Tipografia (override)
- H1: `clamp(46px, 5.4vw, 82px)`, line-height 1.04, enfasi `<em>` corsivo oro.
- Eyebrow con piccolo trattino/linea oro iniziale.

## Proof strip (nuovo, opzionale)
3 dati **fattuali** (nessun prezzo): _20 regioni · 5 linee di prodotto · RU·IT·EN_.
Numerali in Cormorant oro, label Inter uppercase. Coerenti con i dati già presenti nel sito.

## Movimento (riusa l'intro esistente)
- Mantenere l'introduzione `.anim.intro-ready` (logo, eyebrow, H1, sub, CTA, card)
  con stagger e `cubic-bezier(0.22,0.61,0.36,1)`.
- Hover card `translateY(-4px)` + ombra profonda.
- Tutto dentro `@media (prefers-reduced-motion: no-preference)`.

## Vincoli da non rompere
- Menu sticky 5 voci + scroll, hamburger mobile, toggle lingua RU/EN, apertura PDF: invariati.
- Ogni testo nuovo della hero ha chiavi `data-i18n` in **RU ed EN**.
- CTA primaria: "Перейти к программам / Explore Programmes" (scroll a `#programmes`).
- CTA secondaria: "Запросить B2B-доступ / Request B2B Access" (`openModal('b2b')`).
