# 03: Learning From Errors

## Overview

Use Cisco IOS error messages to identify invalid syntax, complete unfinished commands, and understand which commands are available in each configuration mode.

## Topology

One switch connected to an admin PC and a test PC through GigabitEthernet0/1 and GigabitEthernet0/2.

## Commands

```text
Switch# show running-config
Switch# configure terminal
Switch(config)# hostname
% Incomplete command.
Switch(config)# hostname Sandbox-SW1
Sandbox-SW1(config)# do show running-config
```

| Command or response | Purpose |
| --- | --- |
| `show running-config` | Display the active device configuration |
| `hostname` without a value | Demonstrate an incomplete command |
| `hostname Sandbox-SW1` | Supply the required hostname argument |
| `do show running-config` | Run a privileged EXEC command from configuration mode |

## Key Concepts

### Invalid commands

A mistyped or unrecognized command produces an error. The `^` marker points to where IOS could not interpret the input. Correct the syntax and try again.

### Incomplete commands

Some commands require additional arguments. For example, `hostname` must be followed by a name.

### Command modes

Commands are available in different IOS modes. The `do` prefix allows supported EXEC commands to run without leaving configuration mode.

## Key Takeaways

- IOS error messages provide useful guidance for correcting commands.
- Command syntax and the current CLI mode both determine whether a command succeeds.
- Incomplete commands can be corrected by supplying the required arguments.
- `do` is useful for checking configuration while making changes.
