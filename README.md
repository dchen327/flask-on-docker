# Overview
## About
This repo containerizes a Python Flask app with Postgres -- it has separate development and production Docker Compose files. Gunicorn and Nginx are used to handle static/media files. The root `/` returns a hello world message as JSON, whereas `/upload` allows for uploading a file to be displayed at `/media/filename.ext`. By default, port 1026 is used.

## Upload Demo
![demo.gif](https://github.com/dchen327/flask-on-docker/blob/master/demo.gif?raw=true)

# Build Instructions
## Development
Spin up containers and build image
```docker compose up -d --build```
Create database table
```docker compose exec web python manage.py create_db```
Remove volumes and containers (when done using)
```docker compose down -v```

## Production
Spin up containers and build image
```docker compose -f docker-compose.prod.yml up -d --build```
Create database table
```docker compose -f docker-compose.prod.yml exec web python manage.py create_db```
Remove volumes and containers (when done using)
```docker compose -f docker-compose.prod.yml down -v```


