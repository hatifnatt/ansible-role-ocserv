# Ansible Role ocserv

Ansible role to setups OpenConnect VPN Server (ocserv).

What this role can do:

* install ocserv package
* manage system service - enable / disable / start
* create ssl key and certificate from a provided data
* create main configuration file
* create ocserv passwd file for plain auth
* manage helper scripts
* manage system sysctl parameters

## Requirements

None

## Role Variables

Check out [defaults/main.yml](defaults/main.yml) and [vars_example.yml](vars_example.yml) for reference and examples.

## Dependencies

None

## Installation

### Using one liner

```bash
ansible-galaxy install git+https://github.com/hatifnatt/ansible-role-ocserv.git,a1b2c3d --name hatifnatt.ocserv --roles-path ./roles

# using commit SHA or short SHA as version
ansible-galaxy install git+https://github.com/hatifnatt/ansible-role-ocserv.git,SHA --name hatifnatt.ocserv --roles-path ./roles
```

### Using requirements.yml

Create `requirements.yml`

```yaml
- name: hatifnatt.ocserv
  src: https://github.com/hatifnatt/ansible-role-ocserv.git
  scm: git
  version: master
  # or specific commit SHA
  # version: SHA
```

Install with `ansible-galaxy`

```bash
ansible-galaxy install -r requirements.yml --roles-path ./roles
```

## Example Playbook

```yaml
---
- name: Setup OCServ
  hosts: vpn-01*
  roles:
    - role: hatifnatt.ocserv
      become: true
```

## License

MIT

## Credits

Somewhat inspired by [aprt5pr lansible-role-ocserv](https://github.com/aprt5pr/lansible-role-ocserv) role.

## TODO

* generate self signed certificates (CA and server certificates)
* create per user and per group configuration
* configure OTP / OATH
* create iptables rules ?
