# 10: Test 1 - Investigate

## Overview

Investigate a switch with an incorrect hostname, missing VLANs, and a disabled interface. Inspect the existing configuration, restore the required settings, and save the changes.

## Topology

A branch switch with an admin PC connected to GigabitEthernet0/0 and a desk PC connected to GigabitEthernet0/1. GigabitEthernet0/3 was administratively disabled.

## Investigation

```text
Wrong-Host> enable
Wrong-Host# show running-config
Wrong-Host# show vlan brief
Wrong-Host# show interfaces status
```

Initial checks identified:

- Hostname set to `Wrong-Host`.
- VLANs 10, 20, and 30 missing.
- GigabitEthernet0/3 administratively disabled.

## Configuration

```text
Wrong-Host# configure terminal
Wrong-Host(config)# hostname Branch-SW1
Branch-SW1(config)# vlan 10
Branch-SW1(config-vlan)# vlan 20
Branch-SW1(config-vlan)# vlan 30
Branch-SW1(config-vlan)# exit
Branch-SW1(config)# interface g0/3
Branch-SW1(config-if)# no shutdown
Branch-SW1(config-if)# exit
Branch-SW1(config)# exit
```

## Verification and Save

```text
Branch-SW1# show running-config
Branch-SW1# show vlan brief
Branch-SW1# show interfaces status
Branch-SW1# write memory
```

The hostname was corrected, VLANs 10, 20, and 30 were created, and GigabitEthernet0/3 transitioned to an up state. The updated configuration was saved.

## Key Takeaways

- Inspect the running configuration, VLAN table, and interface states before changing a device.
- Use `hostname` to correct device identification.
- Create VLANs with `vlan <id>` and restore administratively disabled interfaces with `no shutdown`.
- Verify each change and save the configuration with `write memory` (or `copy running-config startup-config`).
