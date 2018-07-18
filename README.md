# The Dropwizard Hello World application Development Environment

## Quickstart

Install [Vagrant](https://www.vagrantup.com/) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads).

Install [Ansible](https://www.ansible.com/), e.g. inside a Python [virtual environment](https://docs.python-guide.org/dev/virtualenvs/):

```sh
$ mkvirtualenv tdhwapp
$ pip install ansible
```

Install Ansible dependencies:

```sh
$ cd ansible
$ ansible-galaxy install -r requirements.yml
```

Provision Vagrant Development server:

```sh
$ vagrant up
```

## Standard actions

Provision Development server:

```
$ workon tdhwapp
$ vagrant provision
```
