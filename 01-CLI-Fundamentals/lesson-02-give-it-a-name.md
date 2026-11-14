# 02: Give It a Name

## Overview

Configure a descriptive hostname on a Cisco IOS switch and verify the change using the running configuration.

## Topology

One switch connected to an admin PC and a test PC through GigabitEthernet0/1 and GigabitEthernet0/2.

## Configuration

```text
Switch> enable
Switch# configure terminal
Switch(config)# hostname Branch-SW1
Branch-SW1(config)# exit
Branch-SW1# show running-config
```

## Commands

| Command | Purpose |
| --- | --- |
| `enable` | Enter privileged EXEC mode |
| `configure terminal` | Enter global configuration mode |
| `hostname Branch-SW1` | Set the switch hostname |
| `exit` | Return to privileged EXEC mode |
| `show running-config` | Inspect the active configuration |

## Verification

The CLI prompt changed from `Switch` to `Branch-SW1`, confirming the hostname update. The running configuration included:

```text
hostname Branch-SW1
```

## Key Takeaways

- A hostname makes a device easier to identify during configuration and troubleshooting.
- The CLI prompt reflects the configured hostname.
- `show running-config` displays the active configuration.
- A running configuration change is not necessarily saved for the next reboot; saving requires a separate command such as `copy running-config startup-config`.
