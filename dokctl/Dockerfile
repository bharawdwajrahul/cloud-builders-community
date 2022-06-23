# Use the official lightweight Python image.
# https://hub.docker.com/_/python
FROM debian:bullseye
#FROM 3.10.5-bullseye

MAINTAINER Rahul V Bharadwaj <bharadwajrahul17@google.com>

# Install Dependencies.
RUN apt update -y
#RUN apt-get install python3 -y
RUN apt install -y \
  git \
  wget \
  curl \
  unzip \
  lib32stdc++6 \
  libglu1-mesa \
  python3 \
  python3-pip

#RUN add-apt-repository ppa:deadsnakes/ppa

#RUN apt install python3.10
# Allow statements and log messages to immediately appear in the Knative logs
ENV PYTHONUNBUFFERED True

#RUN pip install .
RUN pip install ocpp

RUN pip install websockets

ENV OCPP_ROOT="/opt"
RUN git clone https://github.com/mobilityhouse/ocpp -b 0.15.0 "${OCPP_ROOT}"
CMD exec python3 $OCPP_ROOT/examples/v201/central_system.py
#RUN python3 $OCPP_ROOT/examples/v201/central_system.py
# Copy local code to the container image.
#ENV APP_HOME /app
#WORKDIR $APP_HOME
#COPY . ./

# Install production dependencies.
#RUN pip install --no-cache-dir -r requirements.txt

# Run the web service on container startup. Here we use the gunicorn
# webserver, with one worker process and 8 threads.
# For environments with multiple CPU cores, increase the number of workers
# to be equal to the cores available.
# Timeout is set to 0 to disable the timeouts of the workers to allow Cloud Run to handle instance scaling.
#CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 main:app
