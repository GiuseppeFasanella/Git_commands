Point is: I am not sure what `git add .` does. 

* With a proper .gitignore (or more than one, with a .gitignore in each directory) I think `git add .` should work properly.

Anyway, a practical way to do it is:

git ls-files --modified | xargs git add