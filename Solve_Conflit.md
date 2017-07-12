In linea di principio, e' **facile**:

* git stesso ti dira' quali file con e' riuscito a mergiare perche' ci sono conflitti

* apri quei file e cerca **HEAD** (HEAD sarebbe cio' che c'e' adesso nel branch di approdo su cui vuoi mergiare, tendenzialmente diverso da cio' che c'e' nel branch che stai chiedendo di mergiare). In quei punti git ti propone le due versioni confliggenti. 

* scegli quale vuoi tenere e fixa il codice

* A questo punto, gli devi dire "Ho risolto i conflitti, tutto ok" e per farlo

* **git add dei file che hai modificato**
Se non lo fai e provi direttamente a committare, ti dara' questo messaggio:
```
error: 'commit' is not possible because you have unmerged files.
```
* **git commit** (SENZA MESSAGGIO)
* Si aprira' (con qualche editor, tipo __nano__) una pagina di dialogo
* **Ctrl + X** e passa la paura ; oppure se e' quella merda di vim **ESC :q**

* Ora puoi andare avanti, cambiare branch, fare tutto cio' che vuoi con git
