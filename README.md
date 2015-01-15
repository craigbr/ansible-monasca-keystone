#Monasca Keystone
Performs some Keystone setup for Monasca

This role adds one or more users/projects/roles to Keystone, as specified in keystone_users:

```
keystone_users:
  monasca-agent:
    password: some-password
    project: some-project
    role: monasca-agent
```
It also creates a Monasca endpoint in keystone.

Override default variables as necessary:
  - `keystone_url` The url to connect to keystone with, must be a v2 endpoint
  - `keystone_admin_token`
  - `monasca_api_url` The url of the monasca api to be registered as the service endpoint in keystone

As of this writing the [keystone-user](https://github.com/ansible/ansible-modules-core/blob/devel/cloud/openstack/keystone_user.py) module
does not support keystone v3 so the service endpoint script is also written to keystone v2.

##Requirements
- Server running OpenStack Keystone
- Hostname or IP of Monasca API server

##Optional

##License
Apache

##Author Information
David Schroeder

Monasca Team email monasca@lists.launchpad.net
