**Il concetto da capire subito e':**

**1 chiave ssh e' una relazione biunivoca tra 1 utente che pusha e una repository github che riceve il push**

**chiave ssh VUOL DIRE utente <--ssh--> account github**

Le chiavi ssh possono essere usate in 2 casistiche per gestire:

1) piu' users che pushano su uno stesso github

2) Lo stesso user che pusha su diversi github account. In quest'ultimo caso, ricorda che 
**una chiave ssh puo' pushare su un solo account github al quale e' bi-univocamente legata**, percio' se un utente vuole pushare su diversi account github (come me che ho "gfasanel" e "GiuseppeFasanella") dovra' generare piu' chiavi ssh e mappare ognuna di queste con il relativo github account (ma tanto e' facile e non costa niente) 

3) Chiaro che se cominci a fare troppo chiavi ssh (come nel caso mio) mi scoccia gestirle tutte e allora niente,
non uso piu' ssh, ma faccio `git clone` con http e ogni volta che pusho mi chiede l'account su cui pushare e la 
password github di quell'account. A parte la scocciatura di dover inserire nome e password ogni volta, e' pulito.
Io uso questo 3) nei casi improbabili di pushing, ad esempio `amerigo -push-> gfasanel` (visto che ad amerigo piace
pushare su GiuseppeFasanella. Quando raramente mi e' capitato ho appunto fatto col metodo `http`

******************************************************************
```
cd ~/.ssh
ssh-keygen -t rsa -C “mail”
#Dai un nome alla chiave che la identifichi 
#( esempio giuseppe_Amerigo o meglio ancora Amerigo_GiuseppeFasanella)
#Troverai chiave pubblica e privata, giuseppe_Amerigo.pub e giuseppe_Amerigo in ~/.ssh
#Apri la chiave pubblica e copia/incolla tutto su gitHub (**Account -> settings -> SSH Keys**) 
#(attento agli "a capo" che danno problemi)
#A questo punto devi istruire ssh [anche se non lo fai funziona lo stesso]
ssh-add ~/.ssh/giuseppe_Amerigo
```
```
#crea un config file (qualora non esista gia')
touch ~/.ssh/config
#Nel config file scrivi:
*****************************************************
Host gfasanel-github.com 
#(questo e' solo un nome che gli dai tu per ricordarti a quale account github stai puntando)

HostName github.com #(questo deve essere corretto invece)

User git

IdentityFile ~/.ssh/giuseppe_Amerigo #(questo dice: la chiave giuseppe_Amerigo punta a gfasanel-github) 
****************************************************
```
Ora, se fai
```
git remote add origin git@gfasanel-github:gfasanel/repo.git
#ci sara' il corretto appaiamento tra la chiave ssh e l'account gfasanel
```

Mettiamo che hai 2 account github, il config sara' cosi'
--------------------------------------------------------------------------------------------
# ~/.ssh/config
Host user1-github
HostName github.com
Port 22
User git
IdentityFile ~/.ssh/id_rsa_user1

Host user2-github
HostName github.com
Port 22
User git
IdentityFile ~/.ssh/id_rsa_user2
---------------------------------------------------------------------------------------------

```
git remote add origin git@user1-github:user1/my-repo.git
#oppure
git remote add origin git@user2-github:user2/my-repo.git
```
E' comodo, ma c'e' la scocciatura che devi tenere tu il book-keeping, o meglio, quando fai `git remote` devi
sapere chi sei, dove vuoi pushare ecc...

io uso questo ~/.ssh/config
https://github.com/GiuseppeFasanella/Git_commands/blob/master/config
