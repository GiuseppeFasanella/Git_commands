Very useful and easy:
You don't want to type the passwd every time you push, so:

ssh-keygen -t rsa -C “mail”
Dai un nome alla chiave che ti identifichi( esempio giuseppe_Amerigo_rsa )
Metti chiave pubblica e privata, giuseppe_Amerigo_rsa.pub e giuseppe_Amerigo, in ~/.ssh
Apri la chiave pubblica e copia tutto
Incolla il contento su gitHub (Accounti settings, SSH Keys)
A questo punto devi istruire ssh
ssh-add ~/.ssh/giuseppe_Amerigo_rsa
crea un config file
touch ~/.ssh/config

Nel config file scrivi:
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/giuseppe_Amerigo

E tutti gli altri che hai
Host github-2
Hostname github.com
User git
Altro IdentityFile

Quando ora scrivi github stai puntando al tuo account principale su github

ORA:
git remote add myorigin git@github-2:user/repo.git