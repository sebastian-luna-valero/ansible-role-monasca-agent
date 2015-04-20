#monasca-agent
Installs the [monasca-agent](https://github.com/stackforge/monasca-agent) part of the [Monasca](https://wiki.openstack.org/wiki/Monasca) project.
It is installs it into a virtualenv on the box.

## Requirements
- keystone_url:
- monasca_agent_user:
- monasca_agent_password:
- monasca_agent_project:

## Optional
- monasca_agent_service:
- monasca_agent_dimensions: 'role:monitoring,region:a'
- monasca_api_url: if undefined it will be pulled from the keystone service catalog.

Optionally supply monasca_checks varible which is a dictionary with each entry consisting of a plugin name followed by the
plugin config, typically with two sections init_config and instances. Refer to the specific monasca-agent plugin documentation
for more detail.

An example ssh check:

    monasca_checks:
      host_alive:
        init_config:
          ssh_port: 22
          ssh_timeout: 0.5
          ping_timeout: 1
        instances:
          - devstack:
              name: devstack
              host_name: 192.168.10.5
              alive_test: ssh

##License
Apache

##Author Information
Tim Kuhlman
Monasca Team email monasca@lists.launchpad.net
