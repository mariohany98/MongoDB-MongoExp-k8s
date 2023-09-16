# MongoDB-MongoExp-k8s

# Project Overview

In this project, I have created a Kubernetes environment with two distinct pods:

1-MongoDB Pod: This pod hosts a MongoDB database instance. It is responsible for storing and managing data.

2-Mongo Express Pod: This pod hosts a MongoDB Express web application. It provides a user-friendly interface to interact with the MongoDB database.

# Architecture

![Screenshot 2023-09-16 175735](https://github.com/mariohany98/MongoDB-MongoExp-k8s/assets/143083001/fc25afde-765c-44ae-bb01-f6f5c007bbbb)

My project's architecture involves the following components:

* Pods: I've setup two pods, each running in its own container:

  - mongodb pod: Contains the MongoDB database instance.

  - mongoexpress pod: Hosts the MongoDB Express web application.
  
* Services: Kubernetes Services allow communication between pods:

  - mongodb service: Exposes the MongoDB pod for communication.

  - mongoexpress service: Enables access to the MongoDB Express web app.
 
* Secrets: Secrets securely store sensitive information. I utilized secrets to store MongoDB credentials and access them within the pods.

* ConfigMaps: ConfigMaps hold configuration data. I've used ConfigMaps to provide the MongoDB Express pod with the MongoDB service URL.

Note: If you want to change the MongoDB user and password, ensure to modify them in the secret.yaml file. Don't forget to encode the username and password.

# Getting Started

1-Clone this repository to your local machine:

git clone https://github.com/mariohany98/MongoDB-MongoExp-k8s.git

2-Install the app using helm

helm install appv1 /path/to/repo/mongoDB-mongoExp-chart

3-Use the following command to retrieve the URL to access the app

minikube service mongo-express-service --url
