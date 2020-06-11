[![Build Status](https://travis-ci.org/nl2go/ansible-role-kafka.svg?branch=master)](https://travis-ci.org/nl2go/ansible-role-kafka)
[![Ansible Galaxy](https://img.shields.io/badge/role-nl2go.kafka-blue.svg)](https://galaxy.ansible.com/nl2go/kafka/)
[![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/nl2go/ansible-role-kafka)](https://galaxy.ansible.com/nl2go/kafka)

# Ansible Role: Apache Kafka

An Ansible Role that manages installation and configuration of [Apache Kafka](https://kafka.apache.org/).

Kafka heavily depends on zookeeper which is not part of this role. To install zoopeeper we recommend the nl2go [zookeeper role](https://github.com/nl2go/ansible-role-zookeeper): 

## Role Variables

Available variables listed and described along with default values in `defaults/main.yml`.

## Dependencies

- [nl2go.openjdk](https://galaxy.ansible.com/nl2go/openjdk)

## Example Playbook

    - hosts: all
      roles:
        - nl2go.kafka
      vars:
        kafka_zookeeper_connection_hosts:
          - my.zookeeper.host:2181

## Set up monitoring for Kafka

For enabling monitoring via JMX you have to create an environment file and set the environment variables used in the kafka startup script like this:

```
JMX_PORT=1099
KAFKA_JMX_OPTS="-Dcom.sun.management.jmxremote -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false"
```

This file needs to be referenced in the `kafka_environment_file` then. Here is an example playbook:

    - hosts: all
      roles:
        - nl2go.kafka
      vars:
        kafka_environment_file: /etc/kafka/custom.env

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
