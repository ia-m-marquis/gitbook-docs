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

## Flags

As flags are&#x20;

## Schematic Pages

There are different main page groups, that all have different specific purposes. Each Group may be connected to a type from the following table. This allows you to build granularity within the design.

Group + Group Specific Type (Optional) + Stage (Optional) + Location (Optional)

<table><thead><tr><th width="118">Group</th><th width="333">Group Specific Type (Optional)</th><th>Associated functionalities</th></tr></thead><tbody><tr><td>UI</td><td>UCI, <a data-footnote-ref href="#user-content-fn-1">XK</a>, <a data-footnote-ref href="#user-content-fn-2">VC</a>, Wallpanels</td><td>UCI interfaces, XK-Keypanels and other control interfaces</td></tr><tr><td>Video</td><td><a data-footnote-ref href="#user-content-fn-3">BMD</a>, <a data-footnote-ref href="#user-content-fn-4">MN</a>, Cameras, Displays, Recording</td><td>Video routers, cameras, displays</td></tr><tr><td>Audio</td><td><a data-footnote-ref href="#user-content-fn-5">Show Relay</a>, Recording</td><td>Audio mixers, amps, audio device control, audio test tools</td></tr><tr><td>Cuelights</td><td></td><td>Cuelight connectors, cuelight logics</td></tr><tr><td>System</td><td></td><td>Licensing, global default controls, system mute, status readout</td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

For constructing specific page names, the following table shall be used for orientation. The naming convention for pages is **Title Case**.

| Group (+  Group Specific Type) | Stage (Optional) | Location (Optional) |
| ------------------------------ | ---------------- | ------------------- |
| UI                             | KH[^6]           | Desk[^7]            |
| Video                          | GH[^8]           | FoH[^9]             |
| Audio                          | WB[^10]          | Studio              |
| Cuelights                      |                  | SW[^11]             |
| System                         |                  |                     |

### Examples

* UI UCI KH Desk
  * UCI for the stage managers desk of the small stage (Kleines Haus).
* UI XK KH Desk
  * XK Keypanel for the stage managers desk of the small stage (Kleines Haus).
* Audio GH Desk
  * Audio processing for the stage managers desk of the large stage (Großes Haus).
* Video BMD
  * BMD video switching for the entire venue (not specific to a stage).
* System
  * All components associated with the core and global controls.





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
