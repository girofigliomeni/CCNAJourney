# 14: Where is the Remote

## Overview

Configure virtual terminal (VTY) lines on a Cisco IOS switch to require a password for remote terminal sessions.

## Topology

A switch connected to an admin PC (`192.168.1.10`) through GigabitEthernet0/1 and a test PC (`192.168.1.20`) through GigabitEthernet0/2.

## Configuration

```text
Switch> enable
Switch# configure terminal
Switch(config)# line vty 0 4
Switch(config-line)# password <vty-password>
Switch(config-line)# login
```

## Commands

| Command | Purpose |
| --- | --- |
| `line vty 0 4` | Select virtual terminal lines 0 through 4 |
| `password` | Set a shared line password |
| `login` | Require line-password authentication for VTY access |

## Key Concepts

- VTY lines are used for remote terminal sessions rather than physical console access.
- `line vty 0 4` selects five VTY lines, numbered 0 through 4.
- The `login` command enables password checking for sessions using the configured VTY lines.
- A shared VTY password is a basic authentication method. For production devices, SSH with individual user accounts or centralized authentication is preferable.
- VTY authentication alone does not establish network reachability or enable secure remote transport.

## Result

Configured VTY lines 0 through 4 with a shared password and required login authentication.
