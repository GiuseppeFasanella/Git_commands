Ho una cartella `My_dir` con un file dentro `file.txt` e voglio mettere questa cartella su github

* Creo una repository remota su github da Browser con il suo bel `README.md`

* Nella cartella My_dir faccio `git init`

* A questo punto devo associare la repository locale appena creata con git init con la repository remota. E' qui che puo' succedere una tragedia

* git remote add origin git@github.....

**Procedura corretta**
* git pull (Subito, prima di tutto il resto. Cosi' sostanzialmente ti compare in locale README.md)
* git add file.txt
* git commit -m "file added"
* git push origin master



**Errore grave da non fare**

Supponiamo che non fai `git pull` subito, prima ancora di fare add, puo' accadere questo

* git add file.txt
* git commit -m "file added"
* git push origin master

E non te lo fa fare: perche' la repository remota ha README.md dentro che My_dir non ce l'ha.

Allora, tu dici `"Beh, faccio git pull"`. E' qui che sei fregato perche' lui allinea My_dir alla repository remota, la quale contiene solo README.md ! Il risultato e' che perdi file.txt in My_dir. Questo perche' hai fatto add prima.


