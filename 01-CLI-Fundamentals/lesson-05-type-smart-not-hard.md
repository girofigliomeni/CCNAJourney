# 05: Type Smart, Not Hard

## Overview

Use Cisco IOS command shortcuts to work more efficiently, including command abbreviations, Tab completion, and command history.

## Topology

A switch connected to an admin PC (`192.168.1.10`) on GigabitEthernet0/1 and a test PC (`192.168.1.20`) on GigabitEthernet0/2.

## Commands

```text
Switch> en
Switch# exit
Switch> enable
Switch# sh st
Switch# show startup-config
Switch# configure terminal
Switch(config)# interface g0/1
Switch(config-if)# interface g0/2
```

| Command or shortcut | Purpose |
| --- | --- |
| `en` | Abbreviation for `enable` |
| Tab | Complete a command when the entered prefix is unambiguous |
| `sh st` | Ambiguous abbreviation; IOS requires more characters |
| `sh start` | Abbreviation for `show startup-config` |
| Up arrow | Recall the previous command |
| `int g0/2` | Short form of `interface GigabitEthernet0/2` |

## Key Concepts

### Command abbreviations

IOS accepts shortened commands when enough characters are supplied to uniquely identify a command. An ambiguous abbreviation is rejected until more characters are entered.

### Tab completion

Tab can complete a command or keyword when the current input has a unique match.

### Command history

The Up arrow recalls earlier commands, which can then be edited rather than retyped.

### Startup configuration

The startup configuration is the saved configuration used when the device boots. It can be inspected with `show startup-config`. Saving the active configuration requires a command such as `copy running-config startup-config`.

## Result

Completed the lab successfully, including command abbreviation, Tab completion, command history, and interface-mode navigation.

## Practice

Entered privileged EXEC mode using a shortened command, explored abbreviated `show` commands, and navigated into interface configuration mode.
