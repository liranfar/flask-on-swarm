## Dockerizing Flask, Nginx, Postgres on Swarm using local registry
if you are unfamiliar with configuring your local docker registry - check out [local-registry-swarm](https://github.com/liranfar/local-registry-swarm) repo.
### Usage
```
eval $(docker-machine env master)
docker build ./web -t myregistry.com:5000/flask-gunicorn:latest
docker push myregistry.com:5000/flask-gunicorn:latest
docker stack deploy -c docker-compose.yml flask-swarm
docker-compose run web /usr/local/bin/python create_db.py

```
### Resources
- [Official Docs](https://docs.docker.com/get-started/)
- [RealPython - Dockerizing flask](https://realpython.com/dockerizing-flask-with-compose-and-machine-from-localhost-to-the-cloud/)
