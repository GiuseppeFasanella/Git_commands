```
Allora rebase serve per avere una storia di commit pulita.
Mettiamo che hai fatto 100 piccoli commit
1-2-------100
Vuoi compattarli in 1 solo commit in cui come messaggio scrivi "Big feature addition ecc"
In questo caso è un rebase che vuoi fare. E conviene farlo in maniera interattiva.
-i: interactive.

Un esempio (che non ho fatto personalmente)
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

'''
A questo punto, supponiamo che il responsabile della repo remota abbia fatto il rebase, quindi ha cambiato la sua storia.
Se provi a pullare avrai conflitti perché le storie sono incompatibili.

Allora fai cosi':
1. commit i tuoi local changes
2. git fetch origin
3. git checkout -b new_master origin/master #Cioè prenditi il master remoto e chiamalo new_master
4. git cherry-pick ash_tag_of_latest_commit #Il che vuol dire prendi l'ultimo commit e mettilo sulla cima di new_master
5. git branch -m master old_master #cambia i nomi dei branch
6. git branch -m new_master master
'''
