# README

This is a small Ruby on Rails 7 blog app with SQLite for k8s testing purposes

## Basic image
```
sudo docker build . -t mb:v1
docker run -d --env SECRET_KEY_BASE=some_random_secure_key_there mb:v1
```

### K8S


This command line will add port forwaring to application to your host, in Docker-Desktop case, as example
```
kubectl port-forward microblog-app 32000:3000
```

this a sript which also create a port forward and move it to background
```
sh k8s-port-forward.sh &
```

This will delete all previously created things
```
kubectl delete -f deployment.yaml
```
