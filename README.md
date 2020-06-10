[![Build Status](https://travis-ci.org/nl2go/ansible-role-kafka.svg?branch=master)](https://travis-ci.org/nl2go/ansible-role-kafka)
[![Ansible Galaxy](https://img.shields.io/badge/role-nl2go.kafka-blue.svg)](https://galaxy.ansible.com/nl2go/kafka/)
[![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/nl2go/ansible-role-kafka)](https://galaxy.ansible.com/nl2go/kafka)

# Ansible Role: Apache Kafka

An Ansible Role that manages installation and configuration of [Apache kafka](https://kafka.apache.org/).

## Dependencies

- [nl2go.openjdk](https://galaxy.ansible.com/nl2go/openjdk)

## Example Playbook

    - hosts: all
      roles:
        - nl2go.kafka

## Development

Use [docker-molecule](https://github.com/nl2go/docker-molecule) following the instructions to run [Molecule](https://molecule.readthedocs.io/en/stable/)
or install [Molecule](https://molecule.readthedocs.io/en/stable/) locally (not recommended, version conflicts might appear).

Use following to run tests:

    molecule test --all

## Maintainers

- [dirkaholic](https://github.com/dirkaholic)

## License

See the [LICENSE.md](LICENSE.md) file for details.

## Author Information

This role was created in 2020 by [Newsletter2Go GmbH](https://www.newsletter2go.com/).
