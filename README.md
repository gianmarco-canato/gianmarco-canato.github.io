# gianmarco-canato.github.io

Sito statico: solo HTML e CSS, nessun programma da installare.

## Come è fatto

Tutte le pagine usano lo stesso sistema, "due canali":

- in alto un **nastro blu** con parole che scorrono (`<div class="tape">`);
- sotto, **due colonne** (`<section class="twin">`):
  - a sinistra `<div class="left">`: cos'è la pagina (nome, titolo, scheda, prossima data…). Resta ferma mentre scorri;
  - a destra `<div class="right">`: il contenuto, a blocchi uno sotto l'altro.

Sul telefono le due colonne diventano una sola e la colonna sinistra va in cima.

```
index.html                 home: nome verticale + schede dei lavori
works.html                 indice di tutti i lavori
work-*.html                una pagina per ogni lavoro
work-template.html         MODELLO da duplicare per un lavoro nuovo
research.html              domanda di ricerca, progetto, concetti, pubblicazioni
agenda.html                prossima data + date future e passate
about.html                 ritratto, bio, insegnamento, formazione, contatti
style.css                  TUTTO l'aspetto grafico (un solo file, con indice all'inizio)
img/                       le immagini (da creare quando metti la prima foto)
```

Header e footer sono ripetuti uguali in ogni pagina. Se cambi un link nel menu
o l'email, cambialo in tutte: in VS Code usa **Cerca e sostituisci in tutti i file**
(`Ctrl+Shift+H` su Windows, `Cmd+Shift+H` su Mac).

## Operazioni frequenti

**Aggiungere un lavoro**
1. Duplica `work-template.html` e rinominalo (es. `work-nuovo-progetto.html`).
2. Cambia numero, titolo, scheda tecnica, nastro, testi e media (le istruzioni sono nei commenti `<!-- -->`).
3. In `works.html` copia una riga `<li>…</li>`, aggiorna link e testi, e aggiorna il numero grande a sinistra.
4. In `index.html` copia un blocco `<a class="card">…</a>`.
5. Sistema i link "Next work" in fondo alle pagine dei lavori.
6. I lavori sono numerati dal più recente: un lavoro nuovo diventa 01 e gli altri scalano.

**Aggiungere una data**: in `agenda.html` copia un `<li>…</li>` in cima a "Upcoming".
Aggiorna anche la prossima data a sinistra e il nastro. Quando una data è passata, spostala sotto "Past".

**Mettere un'immagine al posto di un segnaposto**
1. Metti il file in `img/` (JPG, lato lungo circa 1600–2000 px, sotto 500 KB).
2. Sostituisci `<div class="media r-land ph" data-label="…"></div>`
   con `<div class="media r-land"><img src="img/nome-file.jpg" alt="descrizione breve"></div>`
   (tieni la classe del formato: `r-wide`, `r-land`, `r-tall` o `r-square`).

**Il ritratto**: salva la foto come `img/portrait.jpg` e segui il commento in `about.html`.

**Incorporare video e audio**: su YouTube, Vimeo, Bandcamp o SoundCloud cerca
"Condividi" → "Incorpora" e prendi l'indirizzo dentro `src="…"`.
Nelle pagine dei lavori i commenti mostrano dove incollarlo.

**Cambiare il nastro**: il testo è scritto tre volte di seguito (tre `<span>` uguali), così il nastro non resta mai vuoto. Cambialo in tutti e tre.

**Cambiare colori, font o grana**: tutto all'inizio di `style.css`, sezione 1.

**Dopo aver cambiato `style.css`**: in tutte le pagine aumenta il numero in
`style.css?v=3` (→ `?v=4`, ecc.). Così i browser scaricano subito la versione nuova.
Con Cerca e sostituisci in tutti i file è un'operazione sola.

## Vedere il sito prima di pubblicarlo

In VS Code, con l'estensione **Live Server**: clic destro su `index.html` → "Open with Live Server".
La pagina si ricarica da sola a ogni salvataggio.

## Pubblicare

In VS Code, pannello **Source Control** (icona a ramo, `Ctrl+Shift+G`):
1. prima di modificare, clicca **Sync Changes** per scaricare eventuali modifiche fatte altrove;
2. scrivi una frase nel campo messaggio (es. "aggiunta data 12 dicembre");
3. clic su **Commit**;
4. clic su **Sync Changes**.

Dopo uno o due minuti le modifiche sono online su https://gianmarco-canato.github.io
