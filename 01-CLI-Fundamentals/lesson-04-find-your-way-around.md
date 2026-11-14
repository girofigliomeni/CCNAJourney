# 04: Find Your Way Around

## Overview

Navigate Cisco IOS configuration modes, including global configuration, interface configuration, and VLAN configuration.

## Topology

One switch connected to an admin PC and a test PC.

## Commands

```text
Switch> enable
Switch# configure terminal
Switch(config)# interface g0/1
Switch(config-if)# exit
Switch(config)# exit
Switch# configure terminal
Switch(config)# vlan 10
Switch(config-vlan)# exit
Switch(config)# exit
Switch#
```

| Command | Purpose |
| --- | --- |
| `enable` | Enter privileged EXEC mode |
| `configure terminal` | Enter global configuration mode |
| `interface g0/1` | Enter interface configuration mode for GigabitEthernet0/1 |
| `vlan 10` | Enter VLAN 10 configuration mode |
| `exit` | Return to the previous command mode |

## Key Concepts

- **Privileged EXEC (`Switch#`)** provides access to administrative and diagnostic commands.
- **Global configuration (`Switch(config)#`)** is used for device-wide configuration.
- **Interface configuration (`Switch(config-if)#`)** is used to configure a specific interface.
- **VLAN configuration (`Switch(config-vlan)#`)** is used to configure a VLAN.
- The CLI prompt identifies the current mode.
- `exit` moves up one level in the command hierarchy. Multiple `exit` commands may be required to return to privileged EXEC mode.

## Result

Navigated between interface and VLAN configuration modes and returned to privileged EXEC mode.
