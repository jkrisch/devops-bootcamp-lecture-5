# Tasks for Exercise 5

## 0 Clone Git Repo

- clone repo
  - git clone https://gitlab.com/devops-bootcamp3/node-project 

- remove references and metadata for local repo
  - git rm .git -Rf

- initialize repo
  - git init
  - git add .
  - git config user.name Jonas
  - git config user.email (my-emailaddress)
  - git remote add origin https://<my-gh-token>@github.com/jkrisch/devops-bootcamp-lecture-5.git
  - git commit -m "initial commit"
  - git push -u origin master

## 1 Package NodeJS App

- go to app dir
- package project (npm pack)

## 2 Create a new server

- Create server either via portal or via api
```
TOKEN=<your digitalocean TOKEN>
curl -X POST -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer '$TOKEN'' \
    -d '{"name":"bootcamp-chapter-5",
        "size":"s-1vcpu-512mb-10gb",
        "region":"fra1",
        "image":"ubuntu-22-10-x64",
        "vpc_uuid":"f265ac76-f85c-4c38-867f-0d79fecaec30",
        "ssh_keys":[<your_id for the ssh key (can be retrived via ssh api endpoint)>],
        "user_data":"#!/bin/bash\napt -y update\napt -y install npm nodejs"}' \
    "https://api.digitalocean.com/v2/droplets"
```
via user data we can pass the commands to install npm and nodejs automatically during VM creation

## 3 Prepare server to run Node App

this has already been done via the curl command see above

## 4 Copy App and package.json

On local host execute
scp package.json root@<vm_ip>:/root
scp bootcamp-node-project-1.0.0.tgz root@<vm_ip>:/root

## 5 Run Node App

- first ssh on the remote host
- unpack the tarball
  - tar vzxf /root/bootcamp-node-project-1.0.0.tgz
- run npm unpack
- then start the app via node server.js & (ampersand to run it detached)

## Access from browser - configure firewall

- open port 3000 on firewall (via portal or api)
