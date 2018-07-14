[![CircleCI](https://circleci.com/gh/bitnami/bitnami-docker-python/tree/master.svg?style=shield)](https://circleci.com/gh/bitnami/bitnami-docker-python/tree/master)

# What is Python?

> Python is a programming language that lets you work quickly and integrate systems more effectively

[python.org](https://www.python.org/)

# TL;DR;

```bash
$ docker run -it --name python bitnami/python
```

## Docker Compose

```bash
$ curl -sSL https://raw.githubusercontent.com/bitnami/bitnami-docker-mariadb/master/docker-compose.yml > docker-compose.yml
$ docker-compose up -d
```

# Why use Bitnami Images?

* Bitnami closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Bitnami images the latest bug fixes and features are available as soon as possible.
* Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* Bitnami images are built on CircleCI and automatically pushed to the Docker Hub.
* All our images are based on [minideb](https://github.com/bitnami/minideb) a minimalist Debian based container image which gives you a small base container image and the familiarity of a leading linux distribution.

# Supported tags and respective `Dockerfile` links

* [`3-ol-7`, `3.6.5-ol-7-r19` (3/ol-7/Dockerfile)](https://github.com/bitnami/bitnami-docker-python/blob/3.6.5-ol-7-r19/3/ol-7/Dockerfile)
* [`3-debian-9`, `3.6.5-debian-9-r9`, `3`, `3.6.5`, `3.6.5-r9`, `latest` (3/Dockerfile)](https://github.com/bitnami/bitnami-docker-python/blob/3.6.5-debian-9-r9/3/Dockerfile)
* [`3-debian-8`, `3.6.5-debian-8-r70` (3/debian-8/Dockerfile)](https://github.com/bitnami/bitnami-docker-python/blob/3.6.5-debian-8-r70/3/debian-8/Dockerfile)
* [`2-ol-7`, `2.7.15-ol-7-r20` (2/ol-7/Dockerfile)](https://github.com/bitnami/bitnami-docker-python/blob/2.7.15-ol-7-r20/2/ol-7/Dockerfile)
* [`2-debian-9`, `2.7.15-debian-9-r9`, `2`, `2.7.15`, `2.7.15-r9` (2/Dockerfile)](https://github.com/bitnami/bitnami-docker-python/blob/2.7.15-debian-9-r9/2/Dockerfile)
* [`2-debian-8`, `2.7.15-debian-8-r62` (2/debian-8/Dockerfile)](https://github.com/bitnami/bitnami-docker-python/blob/2.7.15-debian-8-r62/2/debian-8/Dockerfile)

Subscribe to project updates by watching the [bitnami/python GitHub repo](https://github.com/bitnami/bitnami-docker-python).


# Get this image

The recommended way to get the Bitnami Python Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bitnami/python).

```bash
$ docker pull bitnami/python:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/bitnami/python/tags/) in the Docker Hub Registry.

```bash
$ docker pull bitnami/python:[TAG]
```

If you wish, you can also build the image yourself.

```bash
$ docker build -t bitnami/python https://github.com/bitnami/bitnami-docker-python.git
```

# Entering the REPL

By default, running this image will drop you into the Python REPL, where you can interactively test and try things out in Python.

```bash
$ docker run -it --name python bitnami/python
```

# Configuration

## Running your Python script

The default work directory for the Python image is `/app`. You can mount a folder from your host here that includes your Python script, and run it normally using the `python` command.

```bash
$ docker run -it --name python -v /path/to/app:/app bitnami/python \
  python script.py
```

## Running a Python app with package dependencies

If your Python app has a `requirements.txt` defining your app's dependencies, you can install the dependencies before running your app.

```bash
$ docker run --rm -v /path/to/app:/app bitnami/python pip install -r requirements.txt
$ docker run -it --name python -v /path/to/app:/app bitnami/python python script.py
```

or using Docker Compose:

```
java:
  image: bitnami/java:latest
  command: "sh -c 'pip install -r requirements.txt && python script.py'"
  volumes:
    - .:/app
```

**Further Reading:**

  - [python documentation](https://www.python.org/doc/)
  - [pip documentation](https://pip.pypa.io/en/stable/)

# Maintenance

## Upgrade this image

Bitnami provides up-to-date versions of Python, including security patches, soon after they are made upstream. We recommend that you follow these steps to upgrade your container.

### Step 1: Get the updated image

```bash
$ docker pull bitnami/python:latest
```

or if you're using Docker Compose, update the value of the image property to `bitnami/python:latest`.

### Step 2: Remove the currently running container

```bash
$ docker rm -v python
```

or using Docker Compose:

```bash
$ docker-compose rm -v python
```

### Step 3: Run the new image

Re-create your container from the new image.

```bash
$ docker run --name python bitnami/python:latest
```

or using Docker Compose:

```bash
$ docker-compose up python
```

# Contributing

We'd love for you to contribute to this Docker image. You can request new features by creating an [issue](https://github.com/bitnami/bitnami-docker-python/issues), or submit a [pull request](https://github.com/bitnami/bitnami-docker-python/pulls) with your contribution.

# Issues

If you encountered a problem running this container, you can file an [issue](https://github.com/bitnami/bitnami-docker-python/issues). For us to provide better support, be sure to include the following information in your issue:

- Host OS and version
- Docker version (`docker version`)
- Output of `docker info`
- Version of this container (`echo $BITNAMI_IMAGE_VERSION` inside the container)
- The command you used to run the container, and any relevant output you saw (masking any sensitive
information)

# License

Copyright (c) 2018 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
