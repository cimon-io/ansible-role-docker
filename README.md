Docker role
=========

An Ansible Role that installs docker ce.

Requirements
----------------

None.

Role Variables
----------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
docker_user: "deploy"

docker_storage_driver: ""
docker_storage_opt: "[]"

docker_host: "[]"
docker_dns: "[]"
docker_dns_opt: "[]"

docker_cert_path: "~/.docker"
docker_tls: "false"
docker_tlscacert: "{{ docker_cert_path }}/ca.pem"
docker_tlscert: "{{ docker_cert_path }}/cert.pem"
docker_tlskey: "{{ docker_cert_path}}/key.pem"

docker_cacert_file: ""
docker_cert_file: ""
docker_key_file: ""

docker_state: "present"
docker_version: "17.12*"
docker_service_enabled: yes

docker_requirements:
  - apt-transport-https
  - ca-certificates
  - curl
  - gnupg2
  - software-properties-common

docker_gpg_key_url: "https://download.docker.com/linux/{{ ansible_distribution|lower }}/gpg"
docker_repository: "deb [arch=amd64] https://download.docker.com/linux/{{ ansible_distribution|lower }} {{ ansible_distribution_release }} stable"
```

Dependencies
----------------

None.

Example Playbook
----------------

Example:

    - hosts: dockerhost
      roles:
         - role: docker

License
-------

MIT

