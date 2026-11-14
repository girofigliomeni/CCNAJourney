# 09: Save Your Work

## Overview

Inspect the saved Cisco IOS configuration, save the active configuration to NVRAM, and verify that the startup configuration contains the latest changes.

## Topology

A Branch-SW1 switch connected to a Sales laptop (`192.168.10.10`) on GigabitEthernet0/1 and a Test PC (`192.168.1.20`) on GigabitEthernet0/2.

## Commands

```text
Branch-SW1> enable
Branch-SW1# show startup-config
Branch-SW1# copy running-config startup-config
Branch-SW1# show startup-config
```

| Command | Purpose |
| --- | --- |
| `show startup-config` | Inspect the configuration saved for the next startup |
| `copy running-config startup-config` | Save the active configuration as the startup configuration |
| `show running-config` | Inspect the currently active configuration |

## Verification

After saving, the startup configuration included the current switch settings, including:

```text
hostname Branch-SW1
vlan 10
 name SALES
!
interface GigabitEthernet0/1
 description Sales laptop
 switchport access vlan 10
!
interface GigabitEthernet0/2
 description Test PC
!
interface GigabitEthernet0/3
 shutdown
!
interface GigabitEthernet0/4
 shutdown
```

The saved configuration also included the configured SSH-only VTY transport and the message-of-the-day banner.

## Key Takeaways

- **Running configuration** is the active configuration in memory.
- **Startup configuration** is loaded when the device starts.
- Changes to the running configuration are not automatically preserved across a reboot.
- `copy running-config startup-config` saves the current state.
- Verify the startup configuration after saving to confirm that intended changes will persist.
