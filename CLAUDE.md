# Gusto Giusto — Sito B2B (regole di progetto)

Sei l'assistente di sviluppo per il sito vetrina B2B di Gusto Giusto OOO,
una DMC italiana premium per tour operator russofoni. Il sito è un singolo
file `index.html` (più la cartella `pdf/` con i documenti scaricabili).

## Regole tecniche
- Tutto deve restare in UN SOLO file `index.html` autoconsistente (CSS e JS
  inline). Non creare file separati, non aggiungere dipendenze esterne nuove.
- Il sito è bilingue RU/EN tramite attributi `data-i18n`. Ogni testo nuovo va
  aggiunto in ENTRAMBE le lingue (oggetto i18n `ru` e `en`).
- Non rompere la struttura esistente: navigazione, toggle lingua, sezioni.
- I bottoni dei PDF puntano a file nella cartella `pdf/` con nomi esatti
  (es. `pdf/GG_GROUP_01_Tuscany.pdf`). Non rinominare i link senza motivo.
- Dopo ogni modifica, verifica che il file sia valido e che la pagina si apra.

## Brand
- Palette: Navy #1B2A40, Cream #F5EDD6, Gold #C9A84C.
- Font: Cormorant Garamond (titoli) + Inter (testo).
- Tono: sobrio, premium, professionale. Niente effetti volgari o caotici.

## Regole commerciali (IMPORTANTI, non violare mai)
- L'azienda è sempre "Gusto Giusto OOO" o "Gusto Giusto". Mai suffissi italiani
  tipo "S.r.l.".
- Sede: "Mosca e San Pietroburgo".
- Mai mostrare prezzi degli upsell o costi netti/fornitori. I prezzi si
  indicano solo come "от/from".
- Il vaporetto a Venezia (incluse le escursioni alle isole della laguna) NON è
  mai incluso: è sempre pagato sul posto dal cliente.
- Non menzionare mai AIS, associazioni di sommelier o ruoli in esse.

## Come lavorare
- Prima di modificare, spiega in breve cosa cambierai e aspetta conferma.
- Puoi proporre e applicare in autonomia miglioramenti coerenti col brand e
  con un sito turistico premium (animazioni, micro-interazioni, struttura),
  ma sempre a piccoli passi e spiegando prima cosa cambi.
- Procedi a piccoli passi. Modifiche pulite, commentate dove utile.
- Quando aggiungi animazioni, mantienile eleganti e leggere (fade/slide morbidi),
  performanti, senza appesantire il caricamento.
