# Intro to Docker

This repo was created to introduce developers to docker.

# Requirements

The following is required to run any of the files or steps in the repo:

1. Python3
2. Docker

# Project Structure

The repo's layout looks like the following:

- `images`: The docker image definitions.
- `sample-app`: The sample python HTTP server.
- `compose`: The docker compose files.

# Running the Sample App

Python is needed to run the sample app provided.  This is a very simple HTTP server created using [Flask](https://flask.palletsprojects.com/).  Run the following commands to run the server locally:

```cmdline
# Create a new virtual environment to isolate python project changes
python -m venv ./ENV/

# Activate the virtual environment
./ENV/Script/activate
# For linux
# source ./ENV/bin/activate

# Install sample app dependencies
pip install ./sample-app

# Run the server
python sample-app/app/main.py
```

# Building the Dockerfiles

To build the dockerfiles, run the following:

```cmdline
# Build the docker image
docker build -t sample-app:{type} . -f ./images/Dockerfile.{type}

# Run the docker image
docker run sample-app:{type}
```

`type` in this context refers to the kind of docker file in the directory (such as `simple`).

# Running the Compose Files

To run the compose files, run the following:

```cmdline
docker compose -f ./compose/docker-compose.{type}.yml {cmd}
```

Where `type` is the kind of compose file in the directory (such as `simple`) and `cmd` is a docker compose command (such as `up`, `down`, `build`, etc).
