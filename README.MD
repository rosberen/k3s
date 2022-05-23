## Ansible K3s, Kubernetes cluster deployment tools

Necessary steps:

- Describe the machine names and ip addresses in the hosts.ini file '\inventory\hosts.ini'

## Available versions

    v1.17.17+k3s1
    v1.18.17+k3s1
    v1.18.20+k3s1
    v1.19.12+k3s1
    v1.20.4+k3s1
    v1.20.5+k3s1
    v1.20.8+k3s1
    v1.21.1+k3s1
    v1.21.2+k3s1
    v1.21.3+k3s1
    v1.21.4+k3s1
    v1.21.5+k3s2
    v1.22.2+k3s2
    v1.22.4+k3s1
    v1.23.3+k3s1
    v1.23.4+k3s1

## Deploy playbook
```
deploy:
  stage: deploy
  when: manual
  script:
    - ansible-playbook -u root --key-file=~/.ssh/id_rsa -i inventory/hosts.ini deploy.yaml

grade:
  stage: grade
  when: manual
  script:
    - ansible-playbook -u root --key-file=~/.ssh/id_rsa -i inventory/hosts.ini grade.yaml

reset:
  stage: reset
  when: manual
  script:
    - ansible-playbook -u root --key-file=~/.ssh/id_rsa -i inventory/hosts.ini reset.yaml
```
