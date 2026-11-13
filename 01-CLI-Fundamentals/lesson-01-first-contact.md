# Lesson 1: First Contact

| Field | Details |
| --- | --- |
| Platform | SwitchLab |
| Level | Beginner |
| Status | Completed (4/4 objectives shown) |
| Evidence | Screen recording, November 13, 2026 |

## Objective

Become familiar with the Cisco IOS command-line interface by moving from user EXEC mode to privileged EXEC mode, using context-sensitive help, and entering global configuration mode.

## Topology

A SWITCH connects an ADMIN PC and a TEST PC through interfaces G0/1 and G0/2. Both interfaces were shown connected. This lab focuses on CLI navigation, not modifying the network topology.

## Commands observed

```text
Switch> enable
Switch# ?
Switch# configure terminal
Switch(config)#
```

- `enable` enters privileged EXEC mode (`Switch#`).
- `?` lists commands available in the current context.
- `configure terminal` enters global configuration mode (`Switch(config)#`).

## Verification

The recording shows all four SwitchLab objectives completed and the lab completion dialog. The visible terminal prompt confirms entry into global configuration mode. No additional device configuration or connectivity tests are claimed.

## Findings

The Cisco IOS prompt indicates the current command mode. Context-sensitive help helps discover valid commands without memorizing every option.

## Evidence notes

Based on the submitted 55-second screen recording. Only visibly supported actions and outcomes are documented.
