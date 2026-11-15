# 16: Test 2 - Access Review Before Go-Live

## Overview

Review and secure administrative access to a Cisco IOS switch before handoff. Configure console authentication, require local user authentication for remote VTY sessions, and save the updated configuration.

## Topology

| Device | Connection | Address |
| --- | --- | --- |
| Lobby-SW1 | Switch | — |
| Staff laptop | GigabitEthernet0/1, VLAN 10 | 192.168.10.10 |
| Guest kiosk | GigabitEthernet0/2, VLAN 20 | 192.168.20.20 |

## Configuration

Access privileged EXEC mode using the existing enable password, then enter global configuration mode.

```text
Lobby-SW1> enable
Password:
Lobby-SW1# configure terminal
Lobby-SW1(config)# line console 0
Lobby-SW1(config-line)# password <console-password>
Lobby-SW1(config-line)# login
Lobby-SW1(config-line)# line vty 0 4
Lobby-SW1(config-line)# login local
```

The existing local user account is used for VTY authentication rather than configuring a shared VTY line password.

## Verification and Save

```text
Lobby-SW1(config-line)# end
Lobby-SW1# show running-config
Lobby-SW1# copy running-config startup-config
```

Confirm that console line 0 uses password-based login and VTY lines 0 through 4 use `login local`. Save the running configuration to preserve these settings across a reboot.

## Key Takeaways

- `line console 0` configures access through the physical console.
- `password` and `login` together enforce console line authentication.
- `line vty 0 4` selects the remote terminal lines.
- `login local` authenticates VTY sessions against locally configured user accounts.
- Reviewing the running configuration and saving it are separate steps.
- For production remote management, use SSH and appropriately secured user credentials.
