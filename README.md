[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)
# DEPRECATED/LOOKING FOR MAINTAINERS -> archived

[![Actions Status - Master](https://github.com/juju4/ansible-tailon/workflows/AnsibleCI/badge.svg)](https://github.com/juju4/ansible-tailon/actions?query=branch%3Amaster)
[![Actions Status - Devel](https://github.com/juju4/ansible-tailon/workflows/AnsibleCI/badge.svg?branch=devel)](https://github.com/juju4/ansible-tailon/actions?query=branch%3Adevel)

# Tailon install

This role will install [Tailon](https://github.com/gvalkov/tailon), a web tail utility in Go.

Be aware that this program maintenance state is uncertain. A notable updated was done in Oct 2024 after about 6 years of inactivity.
Systemd is used to harden settings (restrict syscalls, namespaces, IP acl, cgroups limits) and avoid running unwanted commands like.
```
tailon[33674]: 2020/01/01 19:54:33 Running command: [grep --text --line-buffered --color=never -e $(whoami)]
```

# Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.10-2.18

### Operating systems

Tested on Ubuntu 24.04, 22.04, 20.04, Centos/Rockylinux 9.

## Example Playbook

Just include this role in your list.
For example

```
- host: all
  roles:
    - juju4.tailon
```

## Continuous integration

This role has a travis config leveraging molecule for testing.

Once you ensured all necessary roles are present, You can test with:
```
$ pip install molecule docker
$ molecule test
$ MOLECULE_DISTRO=ubuntu:24.04 molecule test --destroy=never
```

## Troubleshooting & Known issues

N/A

## License

BSD 2-clause
