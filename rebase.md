```
[17:17:46] Vittorio Raoul Tavolaro: git rebase -i master
[17:17:55] Vittorio Raoul Tavolaro: c'e` un caveat
[17:18:05] Vittorio Raoul Tavolaro: rebase prova a mergiare commit per commit
[17:18:18] Giuseppe Fasanella: cioe' tu dici, prima di fare la pull request
[17:18:22] Giuseppe Fasanella: faccio il rebase
[17:18:40] Vittorio Raoul Tavolaro: quindi se c'e` un file che confligge, che viene modificato da piu` di un tuo commit, ad ogni commit ti chiedera` di fixare il conflitto
[17:18:54] Vittorio Raoul Tavolaro: quindi se vuoi fare rebase devi fare dei commit pseudo-furbi
[17:18:55] Vittorio Raoul Tavolaro: si`
[17:19:04] Vittorio Raoul Tavolaro: prima della PR fai rebase del master
[17:19:16] Vittorio Raoul Tavolaro: e ti pigli tutti gli sviluppi del master nel tuo branch stocazzo
[17:19:23] Vittorio Raoul Tavolaro: -i ti fa fare il rebase interattivo
[17:19:36] Vittorio Raoul Tavolaro: che e` un pochino guidato e ti dice cosa fare con i conflitti
[17:19:50] Vittorio Raoul Tavolaro: sostanzialmente:
- risolvi il conflitto
- fai git add del file incriminato
- fai git rebase --continue
[17:20:37] Vittorio Raoul Tavolaro: hai anche la possibilita` di cambiare la history dei tuoi commit per la PR
[17:21:28] Vittorio Raoul Tavolaro: quando inizi il rebase, puoi riordinare i commit (credo), radunare multipli commit in uno solo o fare una cosa che si chiama "squash commit" che non mi ricordo come funziona
```
