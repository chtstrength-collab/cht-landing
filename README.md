# CHT – Landing page coaching online

Landing page per le campagne Instagram/Facebook di **CHT – Competitive Human Training**.
Un solo obiettivo: far prenotare la chiamata conoscitiva gratuita su WhatsApp.

Indirizzo pubblico (dopo aver attivato GitHub Pages):
**https://chtstrength-collab.github.io/cht-landing-/**

## Cosa c'è dentro

| File / cartella | A cosa serve |
| --- | --- |
| `index.html` | La landing page (testi, stile e codice sono tutti qui dentro) |
| `privacy.html` | Informativa privacy e cookie |
| `images/` | Logo, favicon, anteprima social, la tua foto (`coach.webp`) |
| `images/prima-dopo/` | Foto prima/dopo dei clienti |
| `fonts/` | Font Montserrat ospitato sul sito (più veloce e senza invio dati a Google) |

Puoi modificare tutto direttamente da GitHub: apri il file, clicca sull'icona della **matita** (Edit), cambia e poi premi **Commit changes**. Dopo 1-2 minuti il sito si aggiorna.

## Cambiare i testi

Apri `index.html` e cerca la frase da cambiare (Ctrl+F / Cmd+F nel browser). Ogni sezione è segnata da un commento:

- `<!-- 1. HERO -->` titolo e sottotitolo
- `<!-- 2. TI RICONOSCI? -->`
- `<!-- 3. I 3 ERRORI -->`
- `<!-- 4. COME FUNZIONA -->`
- `<!-- 4b. CHI SONO -->`
- `<!-- 5. STORIE VERE -->`
- `<!-- 6. FAQ -->` ogni domanda è un blocco `<details>…</details>`: copialo per aggiungerne una
- `<!-- 7. CTA FINALE -->`

Cambia solo il testo tra i tag (`<p>testo</p>`), non i tag stessi.
La parola viola sottolineata nei titoli è quella dentro `<span class="kw">…</span>`.

Il titolo e la descrizione che compaiono su Google e nelle anteprime social sono in alto, nelle righe `<title>`, `description`, `og:title` e `og:description`.

## Aggiungere la tua foto (sezione "Chi sono")

Su GitHub: entra in `images/` → **Add file → Upload files** → carica la tua foto chiamandola esattamente **`coach.webp`** → **Commit changes**.

- Formato verticale 4:5 (es. 800×1000 px), meglio sotto i 200 KB.
- Finché il file non c'è, al suo posto compare il segnaposto "LA TUA FOTO QUI".
- Hai un JPG? Convertilo gratis in WebP con squoosh.app (scegli "WebP" in basso a destra).
- I testi di "Chi sono" sono in `index.html`, nel blocco `<!-- 4b. CHI SONO -->`.

## Foto prima/dopo (striscia che scorre)

La striscia di card scorre da sola, si ferma quando ci passi sopra con il mouse o la tocchi, e su telefono si può scorrere col dito. Chi ha attivato "riduci movimento" sul telefono la vede ferma e la scorre a mano.

**Aggiungere un cliente (2 passaggi):**

1. Carica le due foto in `images/prima-dopo/` (Add file → Upload files), es. `marco-prima.webp` e `marco-dopo.webp`. Verticali 4:5, es. 800×1000 px.
2. In `index.html` cerca `var PRIMA_DOPO = [` e aggiungi UNA riga, copiando una di quelle esistenti:

```js
  { nome: 'Marco', prima: 'marco-prima.webp', dopo: 'marco-dopo.webp', frase: 'Il risultato in una riga.' },
```

Attenzione: ogni riga finisce con una virgola, tranne l'ultima. Usa le virgolette semplici `'…'`; se nella frase serve un apostrofo scrivi `\'` (es. `'L\'ha fatto'`).

- Le prime due righe sono già pronte per Alessandro e Alessia: carica `alessandro-prima.webp`, `alessandro-dopo.webp`, `alessia-prima.webp`, `alessia-dopo.webp`.
- Le righe "Nome cliente 3…6" sono segnaposto: sostituiscile con clienti veri o cancellale **prima di usare la pagina nelle ads**.
- Per togliere un cliente cancella la sua riga.
- La velocità si cambia in `var VELOCITA_STRISCIA = 28;` (numero più basso = più lento).
- Usa solo foto e risultati veri, con il consenso scritto della persona.

Le storie di Alessandro e Alessia restano anche come testo nella sezione "Storie vere".

## Cambiare il numero WhatsApp o il messaggio

In `index.html` cerca `393336445066` e sostituiscilo **in tutti i punti** (sono 5) con il nuovo numero: prefisso `39` + numero, senza `+`, spazi o trattini.

Il messaggio precompilato è il testo dopo `?text=`, con gli spazi scritti come `%20` e la virgola come `%2C`.

## Attivare il Meta Pixel

1. In `index.html` cerca `var META_PIXEL_ID = '';`
2. Inserisci il tuo ID tra le virgolette, es. `var META_PIXEL_ID = '123456789012345';`
3. Commit.

Da quel momento compare il banner cookie: il Pixel si carica **solo** se il visitatore clicca "Accetta". Vengono tracciati `PageView` e `Contact` (click su un pulsante WhatsApp). Nel footer appare anche "Preferenze cookie" per cambiare scelta.

## Logo, colori, anteprima social

- `images/logo-cht.png` versione per sfondo scuro; `images/logo-cht-originale.png` il file originale.
- `images/og-image.jpg` (1200×630) è l'immagine che appare quando condividi il link.
- I colori sono all'inizio del blocco `<style>` in `index.html` (`--bg`, `--brand`, `--accent`…).

## Pubblicare con GitHub Pages

Settings → Pages → *Build and deployment* → Source: **Deploy from a branch** → Branch: **main**, cartella **/ (root)** → **Save**.
