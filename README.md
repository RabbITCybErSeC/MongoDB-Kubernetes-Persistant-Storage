# MongoDB-Kubernetes-Persistant-Storage for development
This repose provides basic MongoDB Kubernetes settings with Persistance Storage for development purposes. I found it hard to find an easy 
Kubernetes specification to run and test MongoDB with persistant storage. 

Easy to use commands to get your MongoDB running in Kubernetes with persistant storage. 

## How to add to your minikube?
 

(Note for specifying your own data path clone the repo and specify your data path. The current data path might not give you persistance)

### Set the secrets for MongoDB: `admin`, `admin` (Note this is not Secure, and should not be used in production environments!!). 
Do you want to change the credentials?

`echo -n '<your password or username>' | base64` and paste this into the mongodb-secret.yml file (Requires you to clone this repo)

`https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/mongodb-secret.yaml`


### Set Kubernetes persistant storage:

`kubectl apply -f https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/localstoragevolume.yml`

### Set Kubernetes claim storage:

`kubectl apply -f https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/storageclaim.yml`

### Run the Mongo service:

`kubectl apply -f https://raw.githubusercontent.com/thehoodbuddha/MongoDB-Kubernetes-Persistant-Storage/main/mongoDB.yml`

