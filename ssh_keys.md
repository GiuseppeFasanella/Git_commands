ssh keys are used to deal with different local users, all of them pushing on a remote repository of github

They also have the big advantage that you don't have to type username and passwd every time you push, so:

**Una chiave ssh puo' pushare su un solo account github**

******************************************************************
`cd ~/.ssh`

`ssh-keygen -t rsa -C “mail”`

Dai un nome alla chiave che ti identifichi( esempio giuseppe_Amerigo_rsa )

Troverai chiave pubblica e privata, giuseppe_Amerigo_rsa.pub e giuseppe_Amerigo in ~/.ssh

Apri la chiave pubblica e copia tutto

Incolla il contento su gitHub (Account -> settings -> SSH Keys)

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

Addendum (questo ha correttamente funzionato):
#when prompted enter `id_rsa_user1` as filename
ssh-keygen -t rsa

# ~/.ssh/config
Host user1-github
HostName github.com
Port 22
User git
IdentityFile ~/.ssh/id_rsa_user1

#check original remote origin url
git remote -v
origin git@github.com:user1/my-repo.git

#change it to use your custom `user1-github` hostname
git remote rm origin
git remote add origin git@user1-github:user1/my-repo.git

