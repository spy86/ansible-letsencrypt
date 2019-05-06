Role ansible let's encrypt 
=========
![ansible-letsencrypt](https://img.shields.io/github/issues/spy86/ansible-letsencrypt.svg) ![ansible-letsencrypt](https://img.shields.io/github/forks/spy86/ansible-letsencrypt.svg) ![ansible-letsencrypt](https://img.shields.io/github/stars/spy86/ansible-letsencrypt.svg) ![ansible-letsencrypt](https://img.shields.io/github/license/spy86/ansible-letsencrypt.svg) ![ansible-letsencrypt](https://img.shields.io/twitter/url/https/github.com/spy86/ansible-letsencrypt.svg?style=social)

Role to install and obtain SSL certificates via Letsencrypt

Requirements
------------

None

Role Variables
--------------

- `letsencrypt_path` - Path where Certbot binary should be installed.
- `letsencrypt_staging` -  By default, this option is disabled.
- `letsencrypt_renew` - Setup automated renewal of certificates default, this option is enabled.
- `letsencrypt_email` - Email address to be used when issuing requests, default is `administrator@example.com`. You **SHOULD** customize this setting.
- `letsencrypt_domains` - List of domains to generate certificates for. 

Dependencies
------------

None

Example Playbook
----------------

```yaml
---
- hosts: servers
  remote_user: root
  roles:
   - role: ansible-letsencrypt
     vars:
        letsencrypt_staging: yes
        letsencrypt_renew: yes
        letsencrypt_email: "administrator@example.com"
     letsencrypt_domains:
        - example.com
        - www.example.com
        - ldap.example.com
        - dev.example.com
        - exchange.example.com
```

