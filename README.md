#Monasca Keystone
Performs some Keystone setup for Monasca.
The role requires python-keystoneclient and by default will use the version installed in the Monasca virtualenv.
This role adds one or more users/projects/roles to Keystone, as specified in keystone_users:

```
keystone_users:
  - username: monasca-agent
    password: some-password
    project: some-project
    role: monasca-agent
```
It also creates a Monasca endpoint in keystone.

Override default variables as necessary:
  - `keystone_url` The url to connect to keystone with
  - `monasca_api_url` The url of the monasca api to be registered as the service endpoint in keystone

Keystone Authentication:
There are two ways to authenticate to Keystone:

1: Use an Admin Token by setting `keystone_admin_token`
2: Use an Admin User and Password by setting `keystone_admin`, `keystone_admin_password` and `keystone_admin_project`

The variables are mutually exclusive, only one set can be defined.

Keystone SSL:
If the keystone server is using a self-signed SSL certificate, the variable `keystone_admin_cacert` can be used to specify a cacert so that SSL authentication will succeed. If the correct cacert is already on the remote system, the variable `keystone_local_cacert` can be used to give its location.

As of this writing the [keystone-user](https://github.com/ansible/ansible-modules-core/blob/devel/cloud/openstack/keystone_user.py) module
does not support a `cacert` parameter so it is not used.

##Requirements
- Server running OpenStack Keystone
- Hostname or IP of Monasca API server

##Optional

##License
Apache

##Author Information
David Schroeder

Monasca Team email monasca@lists.launchpad.net
