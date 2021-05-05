# Bitbucket Ansible role
![Logo](logo.gif)

[![Build Status](https://travis-ci.com/idealista/bitbucket_role.png)](https://travis-ci.com/idealista/bitbucket_role)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-idealista.bitbucket_role-B62682.svg)](https://galaxy.ansible.com/idealista/bitbucket_role)



This ansible role installs Bitbucket in a Debian environment. It has been tested for the following Debian versions:

* Buster

This role has been generated using the [cookiecutter](https://github.com/cookiecutter/cookiecutter) tool, you can generate a similar role that fits your needs using the this [cookiecutter template](https://github.com/idealista/cookiecutter-ansible-role).

- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Getting Started
These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will install Bitbucket in a Debian system.

### Prerequisities

Ansible 2.9.9 version installed.

Molecule 3.x.x version installed.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver and [Goss](https://github.com/aelsabbahy/goss) as verifier.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

```
- src: idealista.bitbucket_role
  version: 2.0.0
  name: bitbucket_role
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```
---
- hosts: someserver
  roles:
    - role: bitbucket_role
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties, it is very likely that you will not need to override any variables.


### Automated Bitbucket installation

For first time installation you can define `bitbucket_setup_configuration` parameters and run playbook with `bitbucket_setup_run` variable set to `true`

``` bash
ansible-playbook bitbucket.yml -e 'bitbucket_setup_run=yes'
```

After first start configuration will be stored in database and all corresponding parameters in `bitbucket.properties` would be rewritten by Bitbucket. You don't need to use `bitbucket_setup_run` variable anymore.

[More info](https://confluence.atlassian.com/bitbucketserver/automated-setup-for-bitbucket-server-776640098.html) on automated Bitbucket installation.

## Testing

### Install dependencies

```sh
$ pipenv sync
```

For more information read the [pipenv docs](ipenv-fork.readthedocs.io/en/latest/).

### Testing

```sh
$ pipenv run molecule test 
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.9.9-green.svg)
![Molecule](https://img.shields.io/badge/molecule-3.0.4-green.svg)
![Goss](https://img.shields.io/badge/goss-0.3.16-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/bitbucket_role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

* **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/bitbucket_role/contributors) who participated in this project.

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
