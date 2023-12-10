# README

This is a small Ruby on Rails 7 blog app with SQLite for k8s testing purposes

```
sudo docker build . -t mb:v1
docker run -d --env SECRET_KEY_BASE=some_random_secure_key_there mb:v1
```
