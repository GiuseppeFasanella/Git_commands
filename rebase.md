```
git rebase -i master
c'e` un caveat
rebase prova a mergiare commit per commit
cioe' tu dici, prima di fare la pull request
faccio il rebase
quindi se c'e` un file che confligge, che viene modificato da piu` di un tuo commit, ad ogni commit ti chiedera` di fixare il conflitto
quindi se vuoi fare rebase devi fare dei commit pseudo-furbi
si`
prima della PR fai rebase del master
e ti pigli tutti gli sviluppi del master nel tuo branch stocazzo
 -i ti fa fare il rebase interattivo
che e` un pochino guidato e ti dice cosa fare con i conflitti
 sostanzialmente:
- risolvi il conflitto
- fai git add del file incriminato
- fai git rebase --continue
 hai anche la possibilita` di cambiare la history dei tuoi commit per la PR
quando inizi il rebase, puoi riordinare i commit (credo), radunare multipli commit in uno solo o fare una cosa che si chiama "squash commit" che non mi ricordo come funziona
```
