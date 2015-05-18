ghost
=========

Installs Ghost blogging server as a service.

Requirements
------------

Debian or Ubuntu

Role Variables
--------------

```yaml
ghost_version: '0.6.2'
ghost_env_vars:
  NODE_ENV: production

ghost_public_hostname: 'http://blog.example.com'
ghost_bind_address: "0.0.0.0"
ghost_port: 2368
ghost_allow_filestorage: true
ghost_compress: false # favor nginx compression
ghost_forceAdminSSL: true

ghost_mail:
  transport: SMTP
  options:
    host: YOUR-SES-SERVER-NAME
    port: 465
    service: SES
    auth:
      user: 'YOUR-SES-ACCESS-KEY-ID'
      pass: 'YOUR-SES-SECRET-ACCESS-KEY'
```

Dependencies
------------

* gotansible.runit
* gotansible.nodejs

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: gotansible.ghost, ghost_public_hostname: lovemyblog.com }

License
-------

MIT

Author Information
------------------

Created by Franklin Wise in Santa Monica, CA.
