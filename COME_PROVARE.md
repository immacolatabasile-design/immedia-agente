# Come provare l'agente IM*MEDIA per i case study

> Demo del project work del **Gruppo 2** (Master AI per il Marketing, brief "Processo ed efficienza").
> Tutti i dati sono **simulati**. Durata della prova: circa 15 minuti.

## Cos'è
Un agente che accompagna un case study da quando il progetto si chiude fino alla bozza pronta per il cliente. Tu fai il **PM** dell'agenzia: l'agente legge i materiali, ti fa solo le domande necessarie, scrive le bozze, ti avvisa dei problemi e ricorda cosa è successo.

Non c'è un file da aprire con un doppio clic: l'agente è questa cartella, e si avvia con **Claude Code**.

---

## Opzione GitHub · Claude Code sul web (niente da installare, consigliata)

### Cosa ti serve
- Un account **Claude Pro o Max**.
- Un account **GitHub**, aggiunto come collaboratore del repository (chiedilo a chi l'ha creato).

### Passi
1. Vai su **https://claude.ai/code** e, la prima volta, collega il tuo account GitHub (ti guida la pagina).
2. Scegli il repository dell'agente IM*MEDIA e apri una **nuova sessione**.
3. Scrivi:
   ```
   Il progetto A29 è chiuso, prepariamo il case
   ```
4. **Rispondi come PM** (vedi il copione più sotto).
5. **Guarda cosa ha scritto** l'agente: le modifiche ai file (`notifiche-PM.md`, `memoria.md`, `casi/A29/bozze/`) compaiono nella sessione, e puoi chiedergli "mostrami la bozza" o "mostrami le notifiche".

### Ripartire da zero
Apri una **nuova sessione**: riparte dallo stato iniziale del repository. Le prove di ognuno restano sul proprio branch e non toccano quelle degli altri. Se l'agente ti propone di unire le modifiche al branch principale (`main`), **non farlo**: `main` deve restare pulito per chi prova dopo.

---

## Opzione A · Con Claude Code sul tuo PC (agente completo)

### Cosa ti serve
- **Claude Code** installato. Istruzioni ufficiali: https://code.claude.com/docs
- Un account **Claude Pro o Max** (oppure una chiave API).
- Sul PC aziendale l'installazione potrebbe essere bloccata dall'IT: in quel caso usa l'opzione B.

### Passi
1. **Scompatta** lo zip dove vuoi, per esempio sul Desktop, oppure scarica il repository da GitHub (pulsante verde **Code → Download ZIP**). Otterrai la cartella dell'agente.
2. **Apri il terminale nella cartella.**
   - Windows: apri la cartella in Esplora file, clicca sulla barra dell'indirizzo, scrivi `powershell` e premi Invio.
   - Mac: tasto destro sulla cartella → Servizi → "Nuovo terminale nella cartella".
3. **Avvia l'agente** scrivendo:
   ```
   claude --permission-mode acceptEdits
   ```
   (Con solo `claude` funziona lo stesso: ti chiederà il permesso ogni volta che deve scrivere un file.)
4. **Fai partire il case** scrivendo:
   ```
   Il progetto A29 è chiuso, prepariamo il case
   ```
5. **Rispondi come PM.** L'agente ti propone opzioni A, B, C: puoi rispondere con la lettera o con una frase. Se non sai cosa dire, usa il copione qui sotto.
6. **Guarda cosa ha scritto** l'agente, aprendo i file con un qualsiasi editor di testo:
   - `notifiche-PM.md` · gli avvisi al PM (blocchi, segnalazioni, info);
   - `memoria.md` · sezione 2, lo storico del case e le eccezioni;
   - `casi/A29/bozze/` · case study, post social, messaggio e sollecito per il cliente.

### Ripartire da zero
Il modo più semplice: cancella la cartella e **scompatta di nuovo lo zip**.
In alternativa: copia il contenuto di `_reset/` sopra la cartella principale (sovrascrivendo) e svuota `casi/A29/bozze/`.

---

## Opzione B · Senza Claude Code (su claude.ai, versione ridotta)
1. Su claude.ai crea un nuovo **Progetto**.
2. Nelle **istruzioni del progetto** incolla il contenuto di `CLAUDE.md` e poi quello di `.claude/skills/case-study-immedia/SKILL.md` (la cartella `.claude` può essere nascosta: su Windows attiva "Visualizza → Elementi nascosti").
3. Nei **file del progetto** carica `memoria.md`, `casi/A29/A29_brief_di_avvio_SIMULATO.md` e `casi/A29/A29_report_ADV_gen-giu_2026_SIMULATO.md`.
4. Apri una chat nel progetto e scrivi: `Il progetto A29 è chiuso, prepariamo il case`.

Differenza: qui l'agente **non può scrivere file**. Memoria, notifiche e bozze compaiono solo in chat. L'intervista e i controlli funzionano uguale.

---

## Copione del PM (per arrivare in fondo in ~15 minuti)
Le lettere delle opzioni possono cambiare da una prova all'altra: scegli quella che corrisponde al senso della risposta, oppure scrivi la frase.

| Quando l'agente chiede… | Rispondi |
|---|---|
| Come gestire i **due approvatori** | Ognuno approva la parte e i social del proprio brand; le parti comuni (identità A29, hub) le approvano entrambi. |
| Quale **livello di dati** si può pubblicare | Solo variazioni percentuali, deciso con entrambi i referenti. |
| Quando è andato online l'**hub** | A gennaio 2026. |
| **Citazione** e **screenshot** | Il responsabile marketing di A29 Plus ha detto che manda la citazione, ma non è ancora arrivata. Gli screenshot li ho chiesti all'art director. |
| **Conferma dei fatti** | Confermo tutto. |
| Dopo la bozza | Il redattore ha approvato e ho inviato la mail. È passato un mese: Energy to Build ha approvato, A29 Plus non ha ancora risposto. |
| Se chiede com'è arrivato l'ok di Energy to Build | Per iscritto, numeri compresi. |
| Ultimo passo | Sono passati due mesi e A29 Plus non ha risposto. |

Puoi anche **deviare dal copione** (per esempio: "il cliente non vuole numeri", oppure "ecco la citazione: …") e vedere come reagisce.

---

## Cosa osservare
- **Prima legge, poi chiede.** Le domande devono riguardare solo ciò che nei file non c'è.
- **Blocchi.** Livello di condivisione dei dati da definire → nessun numero in bozza. Due approvatori lato cliente → blocco finché il PM non decide.
- **Eccezione ECC-01.** La decisione sugli approvatori viene registrata in `memoria.md` come eccezione valida solo per questo case.
- **Coerenza.** L'agente dovrebbe accorgersi che la data di go-live del brief (ottobre 2025, "previsto") non torna con il report.
- **Niente invenzioni.** Se manca un dato (citazione, data di pubblicazione, immagini) l'agente mette un segnaposto `[MANCA: …]` o `[IMMAGINE: …]`.
- **Materiali intatti.** Brief e report non vengono modificati.
- **Versione qualitativa.** Dopo due mesi senza ok sui numeri l'agente rifà case **e** social senza numeri.
- **Memoria.** Alla fine la sezione 1 di `memoria.md` (processo generale) resta intatta; nella sezione 2 compaiono lo storico di A29 e le lezioni, con le idee dell'agente segnate come "Proposta da valutare con il PM".

Hai notato qualcosa che non torna? Segnalalo al gruppo: è esattamente il tipo di feedback che serve.
