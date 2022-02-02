# Dokerfile: OracleLinux-8 for Molecule CI 

[![Build](https://github.com/darexsu/docker-oraclelinux-8/actions/workflows/build.yml/badge.svg)](https://github.com/darexsu/docker-oraclelinux-8/actions/workflows/build.yml)

OracleLinux-8 for Ansible Playbooks testing

### Example molecule.yml
```yaml
---
dependency:
  name: galaxy
driver:
  name: docker
platforms:
  - name: instance
    image: "darexsu/molecule-oraclelinux-8:latest"
    command: ${MOLECULE_DOCKER_COMMAND:-""}
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
    privileged: true    
provisioner:
  name: ansible
  playbooks:
    converge: converge.yml
```
