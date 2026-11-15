# 15: Configure Your First Switch

## Overview

Apply baseline identity and access settings to a Cisco IOS switch, verify the active configuration, and save it for the next startup.

## Topology

A switch connected to an admin PC (`192.168.1.10`) through GigabitEthernet0/1 and a test PC (`192.168.1.20`) through GigabitEthernet0/2.

## Configuration

```text
Switch> enable
Switch# configure terminal
Switch(config)# hostname Floor1-SW1
Floor1-SW1(config)# enable password <enable-password>
Floor1-SW1(config)# username tech password <user-password>
Floor1-SW1(config)# line console 0
Floor1-SW1(config-line)# password <console-password>
Floor1-SW1(config-line)# login
Floor1-SW1(config-line)# line vty 0 4
Floor1-SW1(config-line)# login local
Floor1-SW1(config-line)# end
```

## Verification and Save

```text
Floor1-SW1# show running-config
Floor1-SW1# copy running-config startup-config
Floor1-SW1# show startup-config
```

The hostname changed to `Floor1-SW1`. The running configuration included the privileged EXEC password, local user, console login, and VTY local login settings. The configuration was then saved and checked in the startup configuration.

## Key Takeaways

- `hostname` sets the device name displayed in the CLI prompt.
- `enable password` controls access to privileged EXEC mode. `enable secret` is the more secure choice for production devices.
- `username ... password` creates a local account; `login local` uses that account for VTY authentication.
- Console access uses `line console 0`, `password`, and `login`.
- `copy running-config startup-config` preserves changes across a restart.
- Production deployments should use hashed local secrets and SSH for remote administration.
