# Tasks for Exercise 5

## 0 Clone Git Repo

- clone repo
git clone https://gitlab.com/devops-bootcamp3/node-project 

- remove references and metadata for local repo
git rm .git -Rf

- initialize repo
git init
git add .
git config user.name Jonas
git config user.email (my-emailaddress)

git remote add origin https://<mygh-token>@gitlab.com/devops-bootcamp3/node-project 

git commit -m "initial commit"
git push -u origin master
