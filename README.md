# Overview
## About
This repo containerizes a Python Flask app with Postgres -- it has separate development and production Docker Compose files. Gunicorn and Nginx are used to handle static/media files. The root `/` returns a hello world message as JSON, whereas `/upload` allows for uploading a file to be displayed at `/media/filename.ext`.

## Upload Demo

# Build Instructions
