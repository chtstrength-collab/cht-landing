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
| `images/` | Logo, favicon, anteprima social e foto prima/dopo |
| `fonts/` | Font Montserrat ospitato sul sito (più veloce e senza invio dati a Google) |

Puoi modificare tutto direttamente da GitHub: apri il file, clicca sull'icona della **matita** (Edit), cambia e poi premi **Commit changes**. Dopo 1-2 minuti il sito si aggiorna.

## Cambiare i testi

Apri `index.html` e cerca la frase da cambiare (Ctrl+F / Cmd+F nel browser). Ogni sezione è segnata da un commento:

- `<!-- 1. HERO -->` titolo e sottotitolo
- `<!-- 2. TI RICONOSCI? -->`
- `<!-- 3. I 3 ERRORI -->`
- `<!-- 4. COME FUNZIONA -->`
- `<!-- 5. STORIE VERE -->`
- `<!-- 6. FAQ -->` ogni domanda è un blocco `<details>…</details>`: copialo per aggiungerne una
- `<!-- 7. CTA FINALE -->`

Cambia solo il testo tra i tag (`<p>testo</p>`), non i tag stessi.
La parola viola sottolineata nei titoli è quella dentro `<span class="kw">…</span>`.

Il titolo e la descrizione che compaiono su Google e nelle anteprime social sono in alto, nelle righe `<title>`, `description`, `og:title` e `og:description`.

## Cambiare le foto prima/dopo

Nella cartella `images/` ci sono 4 segnaposto:

- `alessandro-prima.jpg`, `alessandro-dopo.jpg`
- `alessia-prima.jpg`, `alessia-dopo.jpg`

Su GitHub: entra in `images/` → **Add file → Upload files** → carica le tue foto **con lo stesso identico nome** (sovrascrivono i segnaposto) → **Commit changes**.

Consigli: formato verticale 4:5 (es. 800×1000 px), JPG sotto i 200 KB (puoi comprimerle gratis con squoosh.app). Usa solo foto per cui hai il consenso scritto della persona.

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
