# Ubuntu 16.04 LTS (Xenial) SystemD URVEBoard SDK v0.1

[![Docker Automated build](https://img.shields.io/docker/automated/cwardgar/docker-ubuntu1604-systemd.svg?maxAge=2592000
)](https://hub.docker.com/r/cwardgar/docker-ubuntu1604-systemd/)

Ubuntu 16.04 LTS (Xenial) Docker container that uses SystemD for initialization. It also includes Python 2.7 and pip,
which allows for easy installation of Ansible later.

## How to Build

This image is built on Docker Hub automatically any time the upstream OS container is rebuilt, and any time a commit
is made or merged to the `master` branch. But if you need to build the image on your own locally, do the following:

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. `cd` into this directory.
  3. Run `docker build -t ubuntu1604-systemd .`

## How to Use

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull cwardgar/docker-ubuntu1604-systemd:latest` (or use the tag you
  built earlier, e.g. `ubuntu1604-systemd`).
  3. Run a container from the image: `docker run --detach --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro
  clone147/docker-ubuntu1604-systemd:latest /lib/systemd/systemd`.
  4. "Login" to the container: `docker exec -it [container_id] bash`

## Notes

I use this image to test [nexus-IaC](https://github.com/cwardgar/nexus-IaC/blob/master/scripts/test_in_docker.sh),
particularly the Ansible playbooks. I do not bake Ansible into the image, which will make it easier to change Ansible
versions later (i.e. I won't have to modify this project's Dockerfile). That is the only major difference
between this project and [docker-ubuntu1604-ansible](https://github.com/geerlingguy/docker-ubuntu1604-ansible).

## Author

Created in 2016 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](
https://www.ansiblefordevops.com/).

Modified in 2018 by Christian Ward-Garrison.
