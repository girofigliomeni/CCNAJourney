# 17: Exam - SSH Into the Switch

## Overview

Configure secure remote management on a Cisco IOS switch using SSH, a local administrator account, and a management IP address.

## Topology

| Device | Interface | IP address |
| --- | --- | --- |
| Admin PC | Ethernet | 192.168.1.10 |
| SW1 | VLAN 1 | 192.168.1.1/24 |

The Admin PC connects to switch port GigabitEthernet0/1.

## Configuration

### Device identity and authentication

```text
Switch> enable
Switch# configure terminal
Switch(config)# hostname SW1
SW1(config)# ip domain-name ccna.lab
SW1(config)# username admin privilege 15 password <password>
SW1(config)# enable secret <secret>
```

### RSA keys

```text
SW1(config)# crypto key generate rsa modulus 2048
```

RSA keys establish the cryptographic identity required for SSH on the switch.

### Management interface

```text
SW1(config)# interface vlan 1
SW1(config-if)# ip address 192.168.1.1 255.255.255.0
SW1(config-if)# no shutdown
```

### VTY access

```text
SW1(config)# line vty 0 4
SW1(config-line)# login local
SW1(config-line)# transport input ssh
SW1(config-line)# end
```

`login local` uses the configured local account for authentication. `transport input ssh` permits SSH while excluding Telnet on the selected VTY lines.

## Verification

```text
SW1# show running-config
SW1# write memory
```

From the Admin PC, connect using SSH:

```text
ssh admin@192.168.1.1
```

After authentication, the remote session opens on `SW1`.

## Key Takeaways

- A hostname and domain name are prerequisites for generating RSA keys on this IOS setup.
- SSH provides encrypted remote terminal access.
- An SVI with an IP address allows in-band management of the switch.
- `login local` authenticates against the local user database.
- `transport input ssh` disables Telnet access on the selected VTY lines.
- Save the running configuration to retain the management settings after a restart.

> **Security note:** The lab uses `username ... password` to create the account. On production devices, prefer `username ... secret` and current SSH algorithms supported by the platform.
