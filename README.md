# MongoDB-Kubernetes-Persistant-Storage for development
This repository provides basic MongoDB Kubernetes settings with Persistance Storage for development purposes. I found it hard to find an easy 
Kubernetes specification to run and test MongoDB with persistant storage. 

Easy to use commands to get your MongoDB running in Kubernetes with persistant storage in matter of seconds.  

## How to add to your minikube or Kubernetes?
 

(Note for specifying your own data path clone the repo and specify your data path in the localstoragevolume.yml file. The current data path might not give you persistance)

### Set the secrets for MongoDB: `admin`, `admin` (Note this is not Secure, and should not be used in production environments!!). 
Do you want to change the credentials?

`echo -n '<your password or username>' | base64` and paste this into the mongodb-secret.yml file (Requires you to clone this repo)

`kubectl create -f https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/mongodb-secret.yml`


### Set Kubernetes persistant storage:

`kubectl apply -f https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/localstoragevolume.yml`

### Set Kubernetes claim storage:

`kubectl apply -f https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/storageclaim.yml`

### Run the Mongo service:

`kubectl apply -f https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/mongoDB.yml`

