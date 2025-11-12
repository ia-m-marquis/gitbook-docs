---
description: Guidelines for Q-SYS Design creation.
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Q-SYS Design Guidelines

## General

#### Language

All Q-SYS Design elements shall be written in English. This allows copy and paste of various components between international projects.

## Schematic Pages

### Naming

There are different main page groups, that all have different specific purposes. Each Group may be connected to a type from the following table. This allows you to build granularity within the design.

<table><thead><tr><th width="118">Group</th><th width="333">Group Specific Type (Optional)</th><th>Associated functionalities</th></tr></thead><tbody><tr><td>UI</td><td>UCI, <a data-footnote-ref href="#user-content-fn-1">XK</a>, <a data-footnote-ref href="#user-content-fn-2">VC</a>, Wallpanels</td><td>UCI interfaces, XK-Keypanels and other control interfaces</td></tr><tr><td>Video</td><td><a data-footnote-ref href="#user-content-fn-3">BMD</a>, <a data-footnote-ref href="#user-content-fn-4">MN</a>, Cameras, Displays, Recording</td><td>Video routers, cameras, displays</td></tr><tr><td>Audio</td><td><a data-footnote-ref href="#user-content-fn-5">Show Relay</a>, Recording</td><td>Audio mixers, amps, audio device control, audio test tools</td></tr><tr><td>Cuelights</td><td></td><td>Cuelight connectors, cuelight logics</td></tr><tr><td>System</td><td></td><td>Licensing, global default controls, system mute, status readout</td></tr></tbody></table>

For constructing specific page names, the following table shall be used for orientation. The naming convention for pages is **Title Case**.

<mark style="color:blue;">**Group**</mark>**&#x20;+&#x20;**<mark style="color:purple;">**Group Specific Type (Optional)**</mark>**&#x20;+&#x20;**<mark style="color:orange;">**Stage (Optional)**</mark>**&#x20;+&#x20;**<mark style="color:red;">**Location (Optional)**</mark>

| Group (+  Group Specific Type) | Stage (Optional) | Location (Optional) |
| ------------------------------ | ---------------- | ------------------- |
| UI                             | KH[^6]           | Desk[^7]            |
| Video                          | GH[^8]           | FoH[^9]             |
| Audio                          | WB[^10]          | Studio              |
| Cuelights                      |                  | SW[^11]             |
| System                         |                  |                     |

#### Examples

* <mark style="color:blue;">UI</mark> <mark style="color:purple;">UCI</mark> <mark style="color:orange;">KH</mark> <mark style="color:red;">Desk</mark>
  * UCI for the stage managers desk of the small stage (Kleines Haus).
* <mark style="color:blue;">UI</mark> <mark style="color:purple;">XK</mark> <mark style="color:orange;">KH</mark> <mark style="color:red;">Desk</mark>
  * XK Keypanel for the stage managers desk of the small stage (Kleines Haus).
* <mark style="color:blue;">Audio</mark> <mark style="color:orange;">GH</mark> <mark style="color:red;">Desk</mark>
  * Audio processing for the stage managers desk of the large stage (Großes Haus).
* <mark style="color:blue;">Video</mark> <mark style="color:purple;">BMD</mark>
  * BMD video switching for the entire venue (not specific to a stage).
* <mark style="color:blue;">System</mark>
  * All components associated with the core and global controls.

## Components

### Naming

The components (Script Access) names follow the name of their schematic pages + their functional name. If multiple components with the same functional names exist, they should be named after their location or if not possible, numbered consecutively.

The naming convention for the script access component names shall be **Title Case**.

**Schematic Page Name + Functional Name + Number/Location (Optional)**

#### Examples

* UI KH Desk User Management
  * User Management Plugin for the stage managers desk of the small stage (Kleines Haus).
* Video MN Hi-App
  * Hi-App Plugin for MediorNet video control.
* System Status Core-Main
  * Status component for the Main-Core.
* Audio Show Relay WB Mixer
  * Mixer component for the show relay of the workshop stage (Werkstattbühne).

## Flags

### Naming

As flag names are unique to one output pin (one output to multiple inputs), their names are associated with the component, that outputs the signal.

The naming should thereby follow the names of their output components script name + the name of the components control.

The naming convention for the flag names shall be **Title Case**.

**Component Name + Control Name**

#### Examples

* Audio Rehearsal System Mixer Input 1 Gain
  *





[^1]: XK-Keypanels

[^2]: VisualCues

[^3]: Blackmagic Design (Videohub)

[^4]: Riedel MediorNet

[^5]: DE: "Mithören"

[^6]: Small stage\
    DE: "Großes Haus"

[^7]: Stage managers desk

[^8]: Large stage\
    DE: "Großes Haus"

[^9]: Front of House

[^10]: Workshop stage\
    DE: "Werkstattbühne"

[^11]: Lighting desk\
    DE: "Stellwerk"
