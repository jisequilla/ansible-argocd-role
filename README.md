# Role argocd

The role argocd will install argocd in a Kubernetes cluster, and deploy a root application which will be in charge of deploying new application in gitops mode.

## Requirements

To run this playbook it is necesary to run it in a host machine wich has access to a kuberntes cluster, it has kubectl installed and helm installed. To be able to run this playbook first must install it depenencies.

To install dependencies run:

```
ansible-galaxy collection install kubernets.core
```

or create a **requirements.yaml** file for your playbooks

```
---
roles:
  - src: git+https://github.com/jisequilla/ansible-argocd-role.git
    version: develop
    name: argocd

collections:
- name: kubernetes.core
  version: 2.2.2

```

and run:

```
ansible-galaxy install -r requirements.yaml
```

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

TBD

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

This rolehas a dependency from **kubernetes.core** module

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: argocd

## License

BSD
