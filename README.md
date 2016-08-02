# ansible-docker

Yet another role for installing Docker. So far only on Debian.

## Requirements

- apt
- python
- easy_install

## Role Variables

```yaml
# Variables as set in defaults/main.yml
docker_apt_key_id: "58118E89F3A912897C070ADBF76221572C52609D"
docker_primary_apt_key_server: "hkp://p80.pool.sks-keyservers.net:80"
docker_secondary_apt_key_server: "hkp://pgp.mit.edu:80"
docker_apt_repository: "deb https://apt.dockerproject.org/repo debian-jessie main"
docker_users:
  - docker
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: servers
  become: yes
  become_user: root
  roles:
    - { role: jzmch.ansible-docker, docker_users: [ "list", "of", "docker", "users" ] }
```

## License

BSD
