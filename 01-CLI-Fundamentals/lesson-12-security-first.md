# 12: Security First

## Overview

Protect access to privileged EXEC mode by configuring an enable password and verifying that authentication is required when moving from user EXEC mode.

## Topology

A switch connected to an admin PC (192.168.1.10) on GigabitEthernet0/1 and a test PC (192.168.1.20) on GigabitEthernet0/2.

## Configuration

```text
Switch> enable
Switch# configure terminal
Switch(config)# enable password <password>
Switch(config)# end
Switch# exit
Switch> enable
Password:
Switch#
```

The lab uses `CCNA` as the enable password. The placeholder above avoids reproducing the credential as a reusable configuration example.

## Verification

After returning to user EXEC mode, the `enable` command prompted for a password. Entering the configured password restored access to privileged EXEC mode.

## Key Takeaways

- `enable password` requires authentication before entering privileged EXEC mode.
- `exit` from privileged EXEC mode returns to user EXEC mode.
- `enable password` does not provide strong protection for the stored credential.
- **`enable secret` is preferred** for production configurations because it stores a hashed secret rather than the legacy enable password.
- Privileged access should be restricted to authorized administrators.
