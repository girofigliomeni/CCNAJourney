# 01: First Contact

## Overview

Introduction to the Cisco IOS command-line interface (CLI), including command modes and context-sensitive help.

## Topology

A switch connected to an admin PC and a test PC through interfaces G0/1 and G0/2.

## Commands

```text
Switch> enable
Switch# ?
Switch# configure terminal
Switch(config)#
```

| Command | Purpose |
| --- | --- |
| `enable` | Enter privileged EXEC mode |
| `?` | Display available commands in the current mode |
| `configure terminal` | Enter global configuration mode |

## Key Concepts

Cisco IOS uses different command modes to separate monitoring and configuration tasks:

- **User EXEC (`Switch>`)**: Basic commands and limited access.
- **Privileged EXEC (`Switch#`)**: Additional diagnostic and administrative commands.
- **Global configuration (`Switch(config)#`)**: Device-wide configuration commands.

The CLI prompt indicates the active mode. Context-sensitive help can be used to discover available commands and syntax.

## Result

Successfully navigated from user EXEC mode to privileged EXEC mode and then to global configuration mode.
