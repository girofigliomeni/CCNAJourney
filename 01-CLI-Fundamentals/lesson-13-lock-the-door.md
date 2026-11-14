# 13: Lock the Door

## Overview

Secure privileged EXEC access and the physical console on a Cisco IOS switch by configuring an enable secret and console line authentication.

## Topology

A switch connected to an admin PC (`192.168.1.10`) through GigabitEthernet0/1 and a test PC (`192.168.1.20`) through GigabitEthernet0/2.

## Configuration

```text
Switch> enable
Switch# configure terminal
Switch(config)# enable secret <enable-secret>
Switch(config)# line console 0
Switch(config-line)# password <console-password>
Switch(config-line)# login
Switch(config-line)# end
Switch# exit
Switch> enable
Password:
Switch#
```

## Commands

| Command | Purpose |
| --- | --- |
| `enable secret` | Set a secret for access to privileged EXEC mode |
| `line console 0` | Enter configuration mode for the local console line |
| `password` | Set the console line password |
| `login` | Require password authentication when connecting through the console |
| `end` | Return directly to privileged EXEC mode |
| `exit` | Leave the current EXEC mode |

## Verification

After returning to user EXEC mode, entering `enable` prompted for the configured secret. Console line 0 was configured to require a password on new console sessions.

## Key Takeaways

- Privileged EXEC access and console access are separate authentication controls.
- `enable secret` protects access to privileged EXEC mode and is preferred over the legacy `enable password` command.
- A console password alone does not enforce authentication until `login` is configured on the line.
- `line console 0` configures physical console access, not remote VTY access.
