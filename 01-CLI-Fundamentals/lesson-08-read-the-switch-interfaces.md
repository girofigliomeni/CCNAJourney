# 08: Read the Switch - Interfaces

## Overview

Inspect switch interface status, distinguish administratively disabled ports from active links, and enable an interface using Cisco IOS.

## Topology

| Device | Switch interface | VLAN | Initial state |
| --- | --- | --- | --- |
| Sales desk | GigabitEthernet0/1 | 10 | Connected |
| HR jack | GigabitEthernet0/2 | 20 | Disabled; no device attached |
| Ops workstation | GigabitEthernet0/3 | 30 | Administratively down |
| Management jack | GigabitEthernet0/4 | 99 | Disabled; no device attached |

## Inspection

```text
Closet-SW2> enable
Closet-SW2# show interfaces status
Closet-SW2# show ip interface brief
```

`show interfaces status` summarizes interface names, connection status, VLAN assignment, duplex, and speed.

`show ip interface brief` displays interface IP addresses along with interface and line-protocol states.

## Configuration

Enable GigabitEthernet0/3 without changing the other disabled ports:

```text
Closet-SW2# configure terminal
Closet-SW2(config)# interface g0/3
Closet-SW2(config-if)# no shutdown
```

## Verification

After enabling GigabitEthernet0/3, the Ops workstation link became connected. GigabitEthernet0/2 and GigabitEthernet0/4 remained administratively disabled.

## Key Takeaways

- `show interfaces status` provides a compact overview of switch port state and VLAN membership.
- `show ip interface brief` distinguishes interface state from line-protocol state.
- `shutdown` administratively disables a port; `no shutdown` removes that restriction.
- An administratively enabled interface still needs a functioning physical link to become operational.
- Unused ports can remain shut down as a basic security precaution.
