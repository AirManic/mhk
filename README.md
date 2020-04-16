[![Build Status](https://travis-ci.com/nickrusso42518/mhk.svg?branch=master)](https://travis-ci.com/nickrusso42518/mhk)

# Cisco Temporary Field Hospital (TFH)
Experimental script to build configurations for all devices in the kit.

After running the script, the `telephony_prefix` specified for each
node definition is represented by a subdirectory in `outputs/`. Within
that subdirectory are the configuration files in a given SHK. There is
one hub per hospital that aggregates SHK connections, so there is no
need for a list-like structure for input data. Each kit also have a
basic `readme.txt` output file that reflects back important data,
such as the telephony prefix, subnets, and individual IP addresses.

Given this `inputs.yml` file:
```
---
hub:
  dmvpn_source:
    interface: GigabitEthernet0/0/0
    ipv4:
      addr: 192.0.2.1
      netmask: 255.255.255.0
      nhop: 192.0.2.2
  bgp:
    local_asn: 65001
    hospital_peer: 192.0.2.129
    hospital_asn: 65002

tfh:
  - telephony_prefix: 101
    ipv4_network: 192.168.0.0/22
    domain_name: hospital.com
    dmvpn_target: tfhhub.hospital.com
    index_offset: 0
  - telephony_prefix: 102
    ipv4_network: 192.168.4.0/22
    domain_name: hospital.com
    dmvpn_target: 192.0.2.1
    index_offset: 0
...
```

You will see this result in the file system:
```
$ tree outputs/
outputs/
|-- 101
|   |-- asw1.txt
|   |-- asw2.txt
|   |-- asw3.txt
|   |-- asw4.txt
|   |-- asw5.txt
|   |-- dsw.txt
|   |-- readme.txt
|   |-- rtr.txt
|   `-- wlc.txt
|-- 102
|   |-- asw1.txt
|   |-- asw2.txt
|   |-- asw3.txt
|   |-- asw4.txt
|   |-- asw5.txt
|   |-- dsw.txt
|   |-- readme.txt
|   |-- rtr.txt
|   `-- wlc.txt
`-- hub.txt
```

There is also a `tfh_configs.zip` file that is automatically created as
an additional artifact from the script. This improves config portability.
