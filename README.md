# ansible-role-containerd

Install containerd

## Install

```shell
ansible-galaxy role install git+https://github.com/sergelogvinov/ansible-role-containerd.git,main
```

## Usage

```yaml
# builder.yaml

- hosts: all
  roles:
    - ansible-role-containerd
```

```yaml
# group_vars/all.yaml

containerd_mirrors:
  - domain: k8s.gcr.io
    endpoints:
      - https://registry.k8s.io
      - https://k8s.gcr.io
  - domain: docker.io
    endpoints:
      - https://registry.ipv6.docker.com
      - https://registry-1.docker.io
```

```shell
ansible-playbook -Dv -i inventories/hosts.ini builder.yaml
```
