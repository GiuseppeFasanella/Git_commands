ssh keys are used to deal with different local users, all of them pushing on a remote repository of github

They also have the big advantage that you don't have to type username and passwd every time you push, so:

******************************************************************

`ssh-keygen -t rsa -C “mail”`

Dai un nome alla chiave che ti identifichi( esempio giuseppe_Amerigo_rsa )

Metti chiave pubblica e privata, giuseppe_Amerigo_rsa.pub e giuseppe_Amerigo, in ~/.ssh

Apri la chiave pubblica e copia tutto

Incolla il contento su gitHub (Accounti settings, SSH Keys)

A questo punto devi istruire ssh

ssh-add ~/.ssh/giuseppe_Amerigo_rsa

crea un config file

touch ~/.ssh/config

Nel config file scrivi:
*****************************************************
Host github.com

HostName github.com

User git

IdentityFile ~/.ssh/giuseppe_Amerigo
****************************************************
Now, if you:

git remote add origin git@github:wherever/repo.git

the user "giuseppe" is associated to the hostname "github" and via the corresponding ssh key it's done. You have now to put your passwd only once in 24 h

******************************************************
******************************************************

If you have another user_name and you want to push under that name

Host github_me2

Hostname github.com

User git

IdentityFile ~/.ssh/anotherUser_Amerigo


Now, if you:

git remote add myorigin git@github-me2:wherever/repo.git

You will push using the ssh associated to the second user
