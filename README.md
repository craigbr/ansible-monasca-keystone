#Monasca Keystone
Performs some Keystone setup for Monasca

This role adds one or more users/tenants/roles to Keystone, as specified in keystone_users:

```
keystone_users:
  monasca-agent:
    password: some-password
    tenant: some-tenant
    role: monasca-agent
```
It also creates a Monasca endpoint in keystone.

Override default variables as necessary:
  - `keystone_url`
  - `keystone_admin_token`
  - `keystone_endpoint` `host` (the hostname or IP address of the Monasca API server)

##Requirements
- Server running OpenStack Keystone
- Hostname or IP of Monasca API server

##Optional

##License
Apache

##Author Information
David Schroeder

Monasca Team email monasca@lists.launchpad.net
