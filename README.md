# README

This is a small Ruby on Rails 7 blog app with SQLite for k8s testing purposes

## Basic Docker
```
sudo docker build . -t mb:v1

key=$(head -c 100 /dev/urandom | LC_ALL=C tr -dc 'a-zA-Z0-9~!@#$%^&*_-' | fold -w 24 | head -n 1)
docker run -d --env SECRET_KEY_BASE=$key mb:v1
```

### K8S

* this command will create pod, deployment, secret and configmap in k8s
this concept not covers real security 
```
head -c 100 /dev/urandom | LC_ALL=C tr -dc 'a-zA-Z0-9~!@#$%^&*_-' | fold -w 48 | head -n 1 | base64 | kubectl create secret generic microblog-key-base --from-literal=secret=-

kubectl apply -f deployment.yaml
```

* This command line will add port forwaring to application to your host, in Docker-Desktop case, as example
```
kubectl port-forward microblog-app 32000:3000
```

* This a sript which also create a port forward and move it to background
```
sh k8s-port-forward.sh &
```

* This will delete all previously created things
```
kubectl delete -f deployment.yaml
```
