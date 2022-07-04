[![CI](https://github.com/de-it-krachten/ansible-role-sslh/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-sslh/actions?query=workflow%3ACI)


# ansible-role-sslh

Manages sslh


## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- OracleLinux 8
- AlmaLinux 8
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 35
- Fedora 36

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Should sslh be activated
sslh_active: true

# native SSLH port
sslh_port: 443

# Port to forward ssh traffic to
sslh_ssh_port: 22

# list of packages to install
sslh_packages:
  - sslh

# service name
sslh_service: sslh
</pre></code>

### vars/family-RedHat.yml
<pre><code>
# sslh configuration
sslh_config: /etc/sslh.cfg
</pre></code>

### vars/family-Debian.yml
<pre><code>
# sslh configuration
sslh_config: /etc/sslh/sslh.cfg
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'sslh'
  hosts: all
  vars:
    sslh_fqdn: server.example.com
  tasks:
    - name: Include role 'sslh'
      include_role:
        name: sslh
</pre></code>
