# Docker Store
An Online Shopping website developed using Html, CSS, Bootstrap, MySQL, PHP.<br>
I have updated a large number of files to use PDO instead of mysqli. I have also included docker configuration and build files


## Features

* All forms validated on Client side using HTML5 and on Server side using PHP.
* Responsive and wepages

# Running the project

This is a fork of the original project I used as a base. So I am assuming you have docker. 
Simply adjust if you want the variables in `variables.env` file and the run the below command. 

```bash
docker build -t mysql-storedb -f dockerfile_DB .
docker build -t php-lifestylestore -f dockerfile_php-apache .
docker compose up -d
```
Then go to http://localhost:8080

Default login not available yet. Create a user and you will be good to go. 

# Running in Kubernetes

Requirements:
- A running cluster on the cloud or KIND, or Minikube for local development
- Working Kubeconfig

Run the following
```bash 
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/db-cm.yaml
kubectl apply -f k8s/secret.yaml
```

Your cluster will come up in short amount of time. 


# Helm

There is a helm chart included here for ease of use

```bash
cd life/
helm install <name> . -f values.yml
```
Wait for about a minute for everything to come up. 




## Interesting Reads

### Probes
https://srcco.de/posts/kubernetes-liveness-probes-are-dangerous.html
https://www.civo.com/learn/practical-guide-to-the-kubernetes-probes



## Project Developers

Sajal Agrawal & oldManLemon