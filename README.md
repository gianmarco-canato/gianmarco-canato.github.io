# gianmarco-canato.github.io

Sito statico: solo HTML e CSS, nessun programma da installare.

## Come è fatto

```
index.html                 home: apertura + galleria irregolare
works.html                 indice di tutti i lavori
work-*.html                una pagina per ogni lavoro
work-template.html         MODELLO da duplicare per un lavoro nuovo
research.html              dottorato, concetti, pubblicazioni e talk
agenda.html                date future e passate
about.html                 bio, insegnamento, formazione, contatti
style.css                  TUTTO l'aspetto grafico (un solo file)
img/                       le immagini
.nojekyll                  file vuoto: dice a GitHub di non trasformare il sito
```

Header e footer sono ripetuti uguali in ogni pagina. Se cambi un link nel menu
o l'email, cambialo in tutte: in VS Code usa **Cerca e sostituisci in tutti i file**
(`Ctrl+Shift+H` su Windows, `Cmd+Shift+H` su Mac).

## Operazioni frequenti

**Aggiungere un lavoro**
1. Duplica `work-template.html` e rinominalo (es. `work-nuovo-progetto.html`).
2. Cambia titolo, scheda tecnica, testi e media (le istruzioni sono nei commenti `<!-- -->`).
3. In `works.html` copia una riga `<li>…</li>` e aggiorna link e testi.
4. Se vuoi che compaia in home, copia un blocco `<a class="tile">…</a>` in `index.html`.

**Aggiungere una data**: in `agenda.html` copia un `<li>…</li>` in cima a "Upcoming".
Quando la data è passata, spostala sotto "Past" e aggiungi `past` alla classe: `class="row past"`.

**Mettere un'immagine al posto di un segnaposto**
1. Metti il file in `img/` (JPG, lato lungo circa 1600–2000 px, sotto 500 KB).
2. Sostituisci `<div class="media ph" data-label="…"></div>`
   con `<div class="media"><img src="img/nome-file.jpg" alt="descrizione breve"></div>`.

**Incorporare video e audio**: su YouTube, Vimeo, Bandcamp o SoundCloud cerca
"Condividi" → "Incorpora" e prendi l'indirizzo dentro `src="…"`.
Nelle pagine dei lavori i commenti mostrano dove incollarlo.

**Cambiare la galleria in home**: ogni riquadro combina queste classi:
`w-3`…`w-8` larghezza in colonne (su 12), `s-1`…`s-8` colonna di partenza,
`drop-1` `drop-2` `lift` spostamenti verticali, `r-wide` `r-land` `r-tall` `r-square` formato,
`tilt` `tilt-r` leggera inclinazione.

**Cambiare colori o font**: tutto all'inizio di `style.css`, sezione 1.

## Vedere il sito prima di pubblicarlo

Apri `index.html` con il browser (doppio clic). Oppure in VS Code installa
l'estensione **Live Server**, poi clic destro su `index.html` → "Open with Live Server":
la pagina si ricarica da sola a ogni salvataggio.

## Pubblicare

In VS Code, pannello **Source Control** (icona a ramo, `Ctrl+Shift+G`):
1. scrivi una frase nel campo messaggio (es. "aggiunta data 12 dicembre");
2. clic su **Commit**;
3. clic su **Sync Changes** (o Push).

Dopo uno o due minuti le modifiche sono online su https://gianmarco-canato.github.io
