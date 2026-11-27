# IM*MEDIA · Agente per i case study (demo)

Project work del **Gruppo 2** · Master AI per il Marketing · brief "Processo ed efficienza".
Tutti i dati sono **simulati**.

Un agente Claude Code che accompagna un case study da quando il progetto si chiude fino alla bozza pronta per il cliente. Tu fai il PM: l'agente legge i materiali, fa solo le domande necessarie, scrive le bozze, segnala i blocchi e tiene memoria di quello che è successo.

**Come provarlo:** leggi [COME_PROVARE.md](COME_PROVARE.md). Il modo più veloce è aprire questo repository su [claude.ai/code](https://claude.ai/code) e scrivere:

```
Il progetto A29 è chiuso, prepariamo il case
```

## Cosa c'è dentro
- `CLAUDE.md` · chi è l'agente e le regole che valgono sempre
- `.claude/skills/case-study-immedia/SKILL.md` · il percorso del case, passo per passo
- `memoria.md` · la memoria dell'agente (processo generale + storico dei case)
- `notifiche-PM.md` · gli avvisi dell'agente al PM
- `casi/A29/` · i materiali del case di prova; le bozze finiscono in `casi/A29/bozze/`
- `_reset/` · le copie iniziali, per ripartire da zero in locale
