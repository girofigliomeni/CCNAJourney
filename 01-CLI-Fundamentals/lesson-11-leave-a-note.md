# 11: Leave a Note

## Overview

Configure a Cisco IOS message-of-the-day (MOTD) banner, verify that it appears when entering a new CLI session, and inspect the active configuration.

## Topology

A switch connected to an admin PC (`192.168.1.10`) through GigabitEthernet0/1 and a test PC (`192.168.1.20`) through GigabitEthernet0/2.

## Configuration

```text
Switch> enable
Switch# configure terminal
Switch(config)# banner motd # Authorized Access Only - Branch Office #
Switch(config)# end
Switch# exit
```

The `#` characters delimit the banner text; they are not part of the displayed message.

## Verification

Return to user EXEC mode to trigger the banner on the next login, then re-enter privileged EXEC mode and inspect the running configuration:

```text
Switch> enable
Switch# show running-config
```

The MOTD banner was configured with the text:

```text
Authorized Access Only - Branch Office
```

## Key Takeaways

- `banner motd` defines a message displayed when users connect to the device.
- The delimiter marks the beginning and end of the banner text.
- `end` returns directly to privileged EXEC mode from configuration mode.
- `show running-config` verifies the active banner configuration.
- A banner can communicate an access warning before a user enters privileged mode.
