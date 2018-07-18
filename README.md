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

```sh
$ workon tdhwapp
$ vagrant provision
```

Deploy application:

```sh
$ cd ansible
$ ansible-playbook -i inventory deploy.yml
```

## Checks

Java app is accessible at http://192.168.1.10:8080/hello-world?name=TEST.

Nginx reverse proxy http://192.168.1.10/hello/?name=TEST.
