Ansible Role: proxmox_ldapauth
=========

Adds LDAP-authentication for Proxmox VE.

Requirements
------------

None

Role Variables
--------------
Available variables are listed below. See [defaults/main.yml](defaults/main.yml):

    ldap_server1: "ldap1.example.com"

FQDN or IP address of the LDAP server.

    ldap_server2: "ldap2.example.com"

FQDN or IP address of the fallback LDAP server.

    ldap_port: "636"

The port which LDAP server listens. The default port for LDAP over SSL is 636. The default insecure TCP port is 389.

    ldap_secure: "1"

In case of LDAP over SSL set value to `1`.

    ldap_base_dn: "ou=people,dc=example,dc=com"

LDAP base distinguished name where to search user entries during authentication.

    ldap_user_attr: "uid"

A user attribute in the LDAP.

    ldap_bind_dn: "cn=bind,dc=example,dc=com"

It is the user name configured for LDAP authentication.

    ldap_bind_pass: "password"

It is the password of bind_dn entry configured for LDAP authentication.

    default_auth: "1"

Set LDAP authentication default in Proxmox VE web-management interface.

Dependencies
------------

None

Example Playbook
----------------

    - hosts: proxmox-servers
      vars_files:
        - vars/proxmox-servers.yml
      roles:
         - { role: vhaidamaka.proxmox_ldapauth }

Inside `vars/proxmox-servers.yml` rewrite default role variables.

License
-------

MIT

Author Information
------------------

Vadym Haidamaka vadym.haidamaka@gmail.com
