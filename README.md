# [bootstrap](#bootstrap)

Prepare your system to be managed by Ansible.

![gitlab](https://gitlab.collegiseducation.com/ansible/ansible-role-bootstrap/badges/main/pipeline.svg)
## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://gitlab.collegiseducation.com/dustinliddick/ansible-role-bootstrap/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  # This role installs packages using the `raw` module and needs to connect as
  # `root`. (`sudo` is not available before bootstrapping.) All tasks in the
  # role have `become` set to `no`, so you can use either `no` or `yes` for
  # `become`, the role will not use become (so `sudo`) for any task.
  become: yes  # `no` will also work.
  # This role installs python, gathering facts can't be done before `python` is
  # installed. This role runs the `setup` module, so facts will be available
  # after running the role.
  gather_facts: no

  roles:
    - role: dustinliddick.bootstrap
```

Also see a [full explanation and example](https://dustinliddick.nl/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://gitlab.collegiseducation.com/dustinliddick/ansible-role-bootstrap/blob/master/defaults/main.yml):

```yaml
---
# defaults file for bootstrap

# Do you want to wait for the host to be available?
bootstrap_wait_for_host: no

# The number of seconds you want to wait during connection test before failing.
bootstrap_timeout: 3

# Tell the role to "become" or not.
bootstrap_become: yes
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://gitlab.collegiseducation.com/dustinliddick/ansible-role-bootstrap/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://dustinliddick.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/dustinliddick/ansible-role-bootstrap/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/dustinliddick):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/repository/docker/dustinliddick/alpine/general)|all|
|[EL](https://hub.docker.com/repository/docker/dustinliddick/enterpriselinux/general)|all|
|[Fedora](https://hub.docker.com/repository/docker/dustinliddick/fedora/general)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://gitlab.collegiseducation.com/dustinliddick/ansible-role-bootstrap/issues)

## [License](#license)

[Apache-2.0](https://gitlab.collegiseducation.com/dustinliddick/ansible-role-bootstrap/blob/master/LICENSE).

## [Author Information](#author-information)

[dustinliddick](https://dustinliddick.nl/)

Please consider [sponsoring me](https://gitlab.collegiseducation.com/sponsors/dustinliddick).
