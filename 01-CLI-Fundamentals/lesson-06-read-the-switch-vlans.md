# 06: Read the Switch - VLANs

## Overview

Inspect VLAN membership on a Cisco switch and administratively disable an interface.

## Topology

A switch connects two end devices:

| Device | Switch port | VLAN |
| --- | --- | --- |
| HR Workstation | GigabitEthernet0/1 | 20 (HR) |
| Sales Laptop | GigabitEthernet0/2 | 10 (SALES) |

## Configuration and Verification

```text
CorpSwitch> enable
CorpSwitch# show vlan brief
CorpSwitch# configure terminal
CorpSwitch(config)# interface g0/1
CorpSwitch(config-if)# shutdown
```

### VLAN Membership

`show vlan brief` lists VLAN IDs, names, statuses, and assigned switch ports.

| VLAN | Name | Ports |
| --- | --- | --- |
| 1 | default | Gi0/3, Gi0/4 |
| 10 | SALES | Gi0/2 |
| 20 | HR | Gi0/1 |

### Administratively Disable an Interface

The `shutdown` command disables the selected interface:

```text
CorpSwitch(config)# interface g0/1
CorpSwitch(config-if)# shutdown
```

The switch reports that GigabitEthernet0/1 changed state to administratively down. To re-enable the interface, use `no shutdown` from interface configuration mode.

## Key Takeaways

- VLANs logically separate devices on a switch.
- `show vlan brief` provides a quick view of VLAN-to-port assignments.
- `shutdown` disables an interface without removing its configuration.
- An administratively disabled port does not forward traffic until it is re-enabled.
