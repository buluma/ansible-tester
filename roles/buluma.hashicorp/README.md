# [hashicorp](#hashicorp)

Install HashiCorp products using packages.

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-hashicorp/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-hashicorp/actions)|[![gitlab](https://gitlab.com/buluma/ansible-role-hashicorp/badges/master/pipeline.svg)](https://gitlab.com/buluma/ansible-role-hashicorp)|[![quality](https://img.shields.io/ansible/quality/58209)](https://galaxy.ansible.com/buluma/hashicorp)|[![downloads](https://img.shields.io/ansible/role/d/58209)](https://galaxy.ansible.com/buluma/hashicorp)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-hashicorp.svg)](https://github.com/buluma/ansible-role-hashicorp/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.hashicorp
      hashicorp_products:
        - name: consul

    - role: buluma.hashicorp
      hashicorp_installation_method: manual
      hashicorp_products:
        - name: vault
          version: "1.9.0"
          type: ent
```

The machine needs to be prepared. In CI this is done using `molecule/default/prepare.yml`:
```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.core_dependencies
```


## [Role Variables](#role-variables)

The default values for the variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for hashicorp

# You can select how to intall hashicorp products. Choose from `package` or
# `manual`. `manual` means this role wil download from
# "https://releases.hashicorp.com/vault/".
hashicorp_installation_method: package

# You can install hashicorp products using this list.
# hashicorp_products:
#   - name: consul
#   - name: consul-template
#   - name: nomad
#   - name: packer
#   - name: terraform
#   - name: vagrant
#   - name: vault

# If you are using `manual` as the `hashicorp_installation_method`, you must
# specify the version to install.
# hashicorp_products:
#   - name: vault
#     version: "1.10.4"

# For `vault` you can choose what type you want to install, either:
# `oss` (default), `ent` or `hsm`.
# hashicorp_products:
#   - name: vault
#     type: oss
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-hashicorp/blob/main/requirements.txt).

## [Status of used roles](#status-of-requirements)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-bootstrap/badges/main/pipeline.svg)](https://gitlab.com/buluma/ansible-role-bootstrap)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Build Status GitHub](https://github.com/buluma/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions)|[![Build Status GitLab ](https://gitlab.com/buluma/ansible-role-core_dependencies/badges/main/pipeline.svg)](https://gitlab.com/buluma/ansible-role-core_dependencies)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.co.ke/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-hashicorp/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|amazon|Candidate|
|el|8|
|debian|bullseye|
|fedora|34, 35|
|ubuntu|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.



If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-hashicorp/issues)

## [License](#license)

Apache-2.0

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)
