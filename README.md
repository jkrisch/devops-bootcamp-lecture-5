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

git remote add origin https://<my-gh-token>@github.com/jkrisch/devops-bootcamp-lecture-5.git

git commit -m "initial commit"
git push -u origin master
