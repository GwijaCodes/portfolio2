# GLORIA SAIJA — UI KIT v1.0

### Sistema visivo: Industrial Brutalist × Evangelion HUD

---

## 00 / FILOSOFIA DEL SISTEMA

Questo kit governa ogni scelta visiva del portfolio. Il principio guida è il **contrasto come tensione drammatica**: testo tecnico freddo contro impatto visivo brutale. Ogni elemento comunica che chi lo ha fatto sa esattamente cosa sta facendo.

Riferimenti primari: Neon Genesis Evangelion UI, pannelli di controllo industriali anni '90, manuali tecnici militari, schermi di diagnostica macchina.

Regola principale: **nessun elemento è decorativo senza funzione apparente**. Anche gli ornamenti sembrano dati, label, output di sistema.

---

## 01 / PALETTE COLORI

```css
:root {
  /* CORE */
  --col-black: #0d0d0d; /* sfondo primario assoluto */
  --col-dark: #1a1a1a; /* superfici pannello */
  --col-panel: #252525; /* card, container */
  --col-mid: #353535; /* bordi secondari, divisori */
  --col-light: #d9d9d9; /* testo body */
  --col-white: #f0f0f0; /* testo enfatizzato */

  /* ACCENT */
  --col-yellow: #ffd02a; /* accent primario — WARNING/ACTIVE */
  --col-orange: #ff6b1a; /* accent secondario — ALERT/HOT */
  --col-red: #cc2200; /* stato ERROR/CRITICAL */
  --col-green: #39ff6e; /* stato OK/CONFIRMED (usare con parsimonia) */

  /* OVERLAY */
  --col-scan: rgba(255, 208, 42, 0.03); /* scanline layer */
  --col-glow: rgba(255, 208, 42, 0.15); /* glow diffuso */
}
```

**Regole d'uso:**

- `--col-yellow` è l'unico colore caldo dominante. Non aggiungerlo ovunque — il suo potere viene dalla rarità
- `--col-orange` e `--col-red` compaiono solo come segnale di stato, mai come decorazione
- `--col-green` è estremo: usarlo solo per conferme di azione utente (form submit, download completato)
- Lo sfondo base è sempre `--col-black`, mai grigio neutro

---

## 02 / TIPOGRAFIA

### Stack font

```css
@import url("https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;700;900&family=IBM+Plex+Mono:wght@300;400;700&display=swap");
/* Mantenere Monofonto locale per headings principali */

:root {
  --font-display: "Monofonto", monospace; /* H1 — impatto, logo, titoli sezione */
  --font-brutal: "Barlow Condensed", sans-serif; /* H2/H3 — label, nav, caps aggressive */
  --font-system: "IBM Plex Mono", monospace; /* body, dati, label tecniche, codice */
}
```

### Scale tipografica

| Token         | Font             | Size    | Weight | Transform        | Uso                        |
| ------------- | ---------------- | ------- | ------ | ---------------- | -------------------------- |
| `--t-display` | Monofonto        | 72–96px | 200    | uppercase        | Hero H1, titoli di impatto |
| `--t-heading` | Barlow Condensed | 36–48px | 900    | uppercase        | Titoli sezione (H2)        |
| `--t-label`   | Barlow Condensed | 10–12px | 700    | uppercase ls:4px | Nav, badge, tag            |
| `--t-body`    | IBM Plex Mono    | 13–15px | 300    | none             | Paragrafi, descrizioni     |
| `--t-data`    | IBM Plex Mono    | 10–11px | 400    | uppercase        | Label sistema, metadati    |
| `--t-code`    | IBM Plex Mono    | 11px    | 700    | none             | `[TAG]`, valori numerici   |

### Regole tipografiche

- I titoli H1 (`--t-display`) non hanno mai `font-weight` alto — il peso viene dalla scala, non dal grassetto
- I dati e label usano sempre `letter-spacing: 3–6px` per il ritmo meccanico
- Il body text è sempre `--col-light` su dark, mai bianco puro su nero — abbassa l'affaticamento
- Non mixare più di 2 font per sezione
- I numeri progressivi di sezione (`01 /`, `02 /`) usano sempre `--font-system` in `--col-yellow`

---

## 03 / SPAZIATURA E LAYOUT

```css
:root {
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 32px;
  --space-xl: 64px;
  --space-2xl: 128px;

  --grid-gutter: 2px; /* gutter tra pannelli — stretto, industriale */
  --panel-pad: 40px 48px; /* padding interno pannelli */
  --section-pad: 120px 10vw; /* padding sezioni */

  --max-content: 1200px;
  --col-main: minmax(0, 1fr);
}
```

**Sistema a griglia:**

- Usare CSS Grid con gap di `var(--grid-gutter)` (2px) per creare l'effetto "pannelli separati da giuntura metallica"
- Le sezioni non hanno bordi arrotondati — `border-radius: 0` sempre, salvo eccezioni esplicite
- Il layout non è mai centrato-morbido: asimmetria e offset sono preferiti

---

## 04 / BORDI E CORNER SYSTEM

Il linguaggio dei bordi è il più identitario del sistema.

```css
/* Corner cut — clip-path per angoli tagliati a 45° */
.corner-cut-sm {
  clip-path: polygon(
    8px 0%,
    100% 0%,
    100% calc(100% - 8px),
    calc(100% - 8px) 100%,
    0% 100%,
    0% 8px
  );
}
.corner-cut-md {
  clip-path: polygon(
    16px 0%,
    100% 0%,
    100% calc(100% - 16px),
    calc(100% - 16px) 100%,
    0% 100%,
    0% 16px
  );
}
.corner-cut-lg {
  clip-path: polygon(
    24px 0%,
    100% 0%,
    100% calc(100% - 24px),
    calc(100% - 24px) 100%,
    0% 100%,
    0% 24px
  );
}

/* Bordo con accent giallo — solo lato sinistro o top */
.border-accent-left {
  border-left: 2px solid var(--col-yellow);
}
.border-accent-top {
  border-top: 2px solid var(--col-yellow);
}
.border-panel {
  border: 1px solid var(--col-mid);
}
.border-active {
  border: 1px solid var(--col-yellow);
}
```

**Regole bordi:**

- I pannelli principali usano sempre `border-panel` + `corner-cut-md`
- L'accent giallo sul bordo sinistro è il segnale visivo di "elemento attivo/selezionato"
- Mai bordi su tutti e quattro i lati in giallo — troppo caotico
- I bordi grigi sono struttura; i bordi gialli sono gerarchia

---

## 05 / COMPONENTI — BOTTONI

```css
/* BASE BUTTON */
.btn {
  font-family: var(--font-brutal);
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--col-yellow);
  background: transparent;
  border: 1px solid var(--col-yellow);
  padding: 12px 24px;
  clip-path: polygon(
    8px 0%,
    100% 0%,
    100% calc(100% - 8px),
    calc(100% - 8px) 100%,
    0% 100%,
    0% 8px
  );
  cursor: pointer;
  position: relative;
  transition: none; /* NO smooth — meccanico */
}

/* HOVER — click istantaneo */
.btn:hover {
  background: var(--col-yellow);
  color: var(--col-black);
}

/* ACTIVE — feedback fisico immediato */
.btn:active {
  transform: translateY(2px);
  background: var(--col-orange);
  color: var(--col-black);
  border-color: var(--col-orange);
}

/* VARIANTE GHOST */
.btn-ghost {
  border-color: var(--col-mid);
  color: var(--col-light);
}
.btn-ghost:hover {
  border-color: var(--col-yellow);
  color: var(--col-yellow);
  background: transparent;
}

/* VARIANTE DOWNLOAD — con icona e label sistema */
.btn-download::before {
  content: "[DWN] ";
  color: var(--col-orange);
  font-size: 9px;
}
```

**Stati bottone:**
| Stato | Comportamento |
|----------|------------------------------------------|
| Default | Bordo giallo, bg trasparente |
| Hover | Fill giallo istantaneo (no transition) |
| Active | Shift Y +2px, fill arancione |
| Disabled | Bordo grigio, opacity 0.3, no cursor |
| Loading | Label sostituita da `[PROCESSING...]` |

---

## 06 / COMPONENTI — CARDS E FLIP CARDS

```css
/* PANEL BASE — usato per skill cards, project cards */
.panel {
  background: var(--col-panel);
  border: 1px solid var(--col-mid);
  clip-path: polygon(
    16px 0%,
    100% 0%,
    100% calc(100% - 16px),
    calc(100% - 16px) 100%,
    0% 100%,
    0% 16px
  );
  padding: var(--panel-pad);
  position: relative;
}

/* Label di sistema nell'angolo — identifica il pannello */
.panel::before {
  content: attr(data-label); /* es. data-label="[PRJ-001]" */
  position: absolute;
  top: 8px;
  left: 16px;
  font-family: var(--font-system);
  font-size: 9px;
  color: var(--col-yellow);
  letter-spacing: 2px;
  opacity: 0.7;
}

/* FLIP CARD — meccanico: nessuna transizione fluida */
.flip-card-inner {
  transition: transform 0.15s steps(3); /* steps() = scatto meccanico */
}

/* BACK — struttura HUD */
.flip-card-back {
  background: var(--col-black);
  border: 1px solid var(--col-yellow);
  border-left: 3px solid var(--col-yellow);
  clip-path: polygon(
    16px 0%,
    100% 0%,
    100% calc(100% - 16px),
    calc(100% - 16px) 100%,
    0% 100%,
    0% 16px
  );
}
```

---

## 07 / ELEMENTI HUD / DECORATIVI

Questi elementi sono sistematici — non casuali. Appaiono sempre con funzione di "dato di sistema".

### Scanline overlay

```css
/* Applicare su .intro o su sezioni hero */
.scanlines::after {
  content: "";
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    0deg,
    var(--col-scan) 0px,
    var(--col-scan) 1px,
    transparent 1px,
    transparent 3px
  );
  pointer-events: none;
  z-index: 10;
}
```

### Label tecniche

```html
<!-- Prefisso di sistema — usare prima di titoli sezione -->
<span class="sys-label">[SYS.02]</span>
<h2>ABOUT ME</h2>
```

```css
.sys-label {
  font-family: var(--font-system);
  font-size: 9px;
  color: var(--col-yellow);
  letter-spacing: 3px;
  opacity: 0.6;
  display: block;
  margin-bottom: 8px;
}
```

### Divisore orizzontale

```css
.divider {
  display: flex;
  align-items: center;
  gap: 16px;
  color: var(--col-yellow);
  font-family: var(--font-system);
  font-size: 9px;
  letter-spacing: 3px;
}
.divider::before,
.divider::after {
  content: "";
  flex: 1;
  height: 1px;
  background: var(--col-mid);
}
.divider::before {
  background: var(--col-yellow);
  width: 40px;
  flex: 0 0 40px;
}
```

### Numerazione sezione

```html
<div class="section-counter">
  <span class="num">02</span>
  <span class="slash">/</span>
  <span class="total">04</span>
</div>
```

```css
.section-counter {
  font-family: var(--font-system);
  font-size: 10px;
  color: var(--col-yellow);
  letter-spacing: 4px;
  opacity: 0.5;
}
```

---

## 08 / NAVIGAZIONE

La nav diventa una **top bar HUD a piena larghezza** — stile barra di stato sistema operativo industriale.

```
┌──────────────────────────────────────────────────────────────┐
│ ▶ GS.EXE    [01] ABOUT    [02] PROJECTS    [03] CONTACT  ▓▓▓ │
└──────────────────────────────────────────────────────────────┘
```

**Comportamento:**

- Altezza fissa: `40px` — compatta, non invadente
- Sticky sempre: non scompare mai, niente blur morbido — `background: var(--col-black)` pieno
- I link nav hanno prefisso numerato: `[01]`, `[02]`, `[03]`
- Hover: il testo diventa `--col-yellow`, nessuna transizione — cambio istantaneo
- Un indicatore `▓▓▓` a destra (testo ASCII) per decoration HUD
- Separatori verticali `│` tra le voci

---

## 09 / ANIMAZIONI E TRANSIZIONI

**Principio:** Le macchine non fanno ease-in-out. Si accendono. Si spostano. Si fermano.

```css
:root {
  --transition-instant: 0ms;
  --transition-snap: 80ms; /* hover istantanei */
  --transition-mech: 150ms steps(4); /* movimento meccanico a scatti */
  --transition-slow: 400ms steps(8); /* transizioni di pagina */
}
```

**Regole:**

- `transition: none` su bottoni per hover/fill — il cambio è immediato
- `steps()` invece di `ease` o `cubic-bezier` per qualsiasi movimento di elementi strutturali
- Gli unici `ease` permessi: opacità di elementi che appaiono dallo scroll (testo body)
- Nessun `transform: scale()` su hover elementi principali — spostamento Y o X sì, scala no
- Le flip cards usano `steps(3)` — tre frame visibili, come un refresh di schermo

---

## 10 / STATI DI SISTEMA

Usare queste classi/pattern per feedback utente coerenti con il linguaggio HUD:

```css
/* Stato: loading */
.state-loading::after {
  content: "[LOADING...]";
  font-family: var(--font-system);
  font-size: 10px;
  color: var(--col-yellow);
  animation: blink 800ms steps(1) infinite;
}

/* Blink cursor HUD */
@keyframes blink {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}

/* Underscore cursore su titoli attivi */
.cursor-blink::after {
  content: "_";
  animation: blink 800ms steps(1) infinite;
  color: var(--col-yellow);
}
```

**Vocabolario label:**
| Stato | Label visiva | Colore accent |
|-----------|--------------------|-------------------|
| Successo | `[OK]` | `--col-green` |
| Errore | `[ERR]` | `--col-red` |
| Loading | `[LOADING...]` | `--col-yellow` |
| Info | `[SYS]` | `--col-light` |
| Download | `[DWN]` | `--col-orange` |
| Sezione | `[SYS.01]`... | `--col-yellow` |

---

## 11 / PATTERN DI SFONDO

```css
/* Pattern griglia sottile — sfondo sezioni secondarie */
.bg-grid {
  background-image: linear-gradient(var(--col-mid) 1px, transparent 1px),
    linear-gradient(90deg, var(--col-mid) 1px, transparent 1px);
  background-size: 40px 40px;
  opacity: 0.3;
}

/* Noise texture overlay (CSS puro - approssimazione) */
.bg-noise::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  opacity: 0.4;
}
```

---

## 12 / CHECKLIST QUALITÀ

Prima di ogni modifica o aggiunta al sito, verificare:

- [ ] Il font usato è nel sistema (`--font-display`, `--font-brutal`, `--font-system`)?
- [ ] Il colore usato è una variabile del kit?
- [ ] L'elemento ha un'etichetta di sistema (`data-label`, `.sys-label`) se è un pannello?
- [ ] Le transizioni usano `steps()` o `none`? (mai `ease` su struttura)
- [ ] I bordi hanno angoli tagliati (`corner-cut`) se sono pannelli?
- [ ] La numerazione di sezione è visibile?
- [ ] Esiste versione mobile pensata per questo componente?

---

_UIKIT.md — v1.0 — Gloria Saija Portfolio System_
_Aggiornare questo file ad ogni introduzione di nuovo pattern o componente._
