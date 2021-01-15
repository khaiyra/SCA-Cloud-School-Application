# USE lightweight python 3.7 image
# https://hub.docker.com/_/python
FROM python:3.7-slim

# Copy local code to the container image
ENV APP_HOME /APP_HOME
WORKDIR $APP_HOME
COPY . ./

# Install production dependencies
RUN pip install Flask gunicorn

# Run the web service on container startup. Here, ise the gunicorn
# webserver, with one workerprocess and 8 threads
CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 app:app