eucalyptus-configureOSG
=======================

Role to configure Eucalyptus Networking for EDGE

Requirements
------------

Eucalyptus Cloud up and running with admin credentials

Role Variables
--------------

| Parameter | Required | Default | Description
|--- |--- |--- |---
| osg_properties | Yes | [] | List containing the properties name and values for your OSG
| name | Yes | <property name> | Name of the property
| value | Yes | None | Value of the property


Dependencies
------------

- JohnPreston.eucalyptus-credentials

Example Playbook
----------------

```
- hosts: clc
  roles:
  - JohnPreston.eucalyptus-configureNetwork
  vars_files:
  - availability_zones.yml

```

The Availability Zone config file should be :

```

instance_dns_servers:
- "10.1.1.254"

instance_dns_domain: eucalyptus.internal

pub_ips:
- "10.104.6.1-10.104.6.30"

clusters:
 - {"Name": "az-01", "MacPrefix": "d0:0d",
   "Subnet":
     { "Name": "172.33.0.0",
       "Subnet": "172.33.0.0",
       "Netmask": "255.255.0.0",
       "Gateway": "172.33.255.253"},
       "PrivateIps": ["172.33.1.1-172.33.5.253"]}
[```

License
-------

BSD

Author Information
------------------

John Preston [John Mille]

