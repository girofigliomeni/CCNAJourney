# 07: Make and Undo

## Overview

Create and remove VLANs on a Cisco IOS switch using configuration commands and the `no` prefix.

## Topology

A switch connected to an admin PC (192.168.1.10) through GigabitEthernet0/1 and a test PC (192.168.1.20) through GigabitEthernet0/2.

## Configuration

### Create VLANs

```text
Switch> enable
Switch# configure terminal
Switch(config)# vlan 10
Switch(config-vlan)# vlan 20
Switch(config-vlan)# exit
Switch(config)# exit
Switch# show vlan brief
```

The VLAN table listed VLAN 10 (`VLAN0010`) and VLAN 20 (`VLAN0020`) as active.

### Remove VLANs

```text
Switch# configure terminal
Switch(config)# no vlan 10
Switch(config)# no vlan 20
Switch(config)# exit
Switch# show vlan brief
```

## Verification

The final `show vlan brief` output no longer listed VLANs 10 or 20. VLAN 1 and the reserved default VLANs (1002–1005) remained.

## Key Takeaways

- `vlan <id>` creates a VLAN and enters VLAN configuration mode.
- `no vlan <id>` removes the specified VLAN.
- `show vlan brief` displays VLAN IDs, names, status, and port membership.
- The `no` prefix is used throughout IOS to remove or reverse configuration commands.
- Verify configuration changes before moving to the next task.
