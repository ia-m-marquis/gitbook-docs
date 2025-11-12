---
description: >-
  The X-Stage Routing Matrix Plugin for Q-SYS enables remote control and
  visualization of other Q-SYS components and plugins in a scrollable matrix
  format.
---

# Routing Matrix Plugin

## Features

* **Remote Control**: Manage and control Q-SYS components from a unified matrix interface.
* **Component Selection**: Easily select and switch between available Q-SYS components dynamically.
* **Matrix Sizing**: Configure viewport matrix input/output sizes and total input/output sizes in the properties to match your requirements.
* **Customizable Matrix UI**: Besides actual matrix input/output size, various aspects like text color and crosspoint button size can be set in the properties.
* **Dynamic Offsets**: Dynamically change input/output offsets for your selected component.
* **Disable Pins**: Enable/disable individual inputs and outputs, so they can't be used within the matrix view.
* **Visual Feedback**: Matrix movement faders, index indicators, and status reporting.
* **Matrix Markers**: Markers are available to visually highlight one input and output in the matrix to reduce user errors.
* **Standalone Call Mode**: Activates a call mode for advanced group/destination routing.

## Installation

1. Copy the `X-Stage Routing Matrix Plugin.qplugx` file into your `Documents/QSC/Q-Sys Designer/Plugins` folder.
2. Open your Q-SYS Design in Q-SYS Designer and drag'n drop the Plugin from the Schematic Elements into your Design.
3. Enable Script Access in the properties tab of the X-Stage License Module Plugin.
4. Use a valid X-Stage License within the X-Stage License Module (not required when emulating).
5. Enable Script Access for all components, you want to control.

## Usage

### Properties

* **Modes**
  * **Call Mode**: Activates the standalone call mode of this plugin (_WARNING: This generates many controls_)
* **I/O**
  * **Total Inputs**: The maximum amount of inputs that can be controlled.
  * **Total Outputs**: The maximum amount of outputs that can be controlled.
* **Matrix**
  * **Matrix Inputs**: The amount of inputs that are shown within the matrix viewport (x-Axis).
  * **Matrix Outputs**: The amount of outputs that are shown within the matrix viewport (y-Axis).
  * **Matrix Button Size**: The pixel size of each crosspoint of the matrix.
  * **Matrix Icon Color**: The hex color of the matrix text labels and icons.
  * **Matrix Reverse Assigned States**: Inverts the states of the red and green index controls (bright/dim).

### Pages

* **Setup**: Select the component to control and control the input/output offsets.
* **Inputs and Outputs**: View and edit all input/output names. The "|"-character can be used for CR.
* **Matrix**: Actual routing matrix. This page could be draged onto a UCI. X-Stage CSS classes are automatically applied to those controls.
* **About**: Licensing and usage information.

### Pins

* `Call Mode` - Available, when the standalone _Call Mode_ is activated
  * `Call Mode/Destinations/n` - Explained under _Call Mode_. n: input index
  * `Call Mode/Groups/n` - Explained under _Call Mode_. n: input index
  * `Call Mode/Destinations JSON` - Explained under _Call Mode_
* `Inputs`
  * `Inputs/n Disable` - Disables this input in the matrix view. n: input index
  * `Inputs/n Index` - Input index string. n: input index
  * `Inputs/n Name` - Input name string. n: input index
* `Matrix`
  * `Matrix/Crosspoints/nxm` - Currently visible matrix crosspoint button state. \[n: input index] x \[m: output index m]
  * `Matrix/Input Index Button/n` - Button state of the input buttons, that are used for setting markers. n: input index
  * `Matrix/Input Index Indicator/n` - Indicator state of the input index highlighting (input used/unused). n: input index
  * `Matrix/Input Name Button/n` - Button state of the matrix input name buttons, that are shown as texts. n: input index
  * `Matrix/Output Index Button/n` - Button state of the output buttons, that are used for setting markers. n: output index
  * `Matrix/Output Index Indicator/n` - Indicator state of the output index highlighting (output used/unused). n: output index
  * `Matrix/Output Name Button/n` - Button state of the matrix output name buttons, that are shown as texts. n: output index
  * `Matrix/Input Fader` - Fader value/position of the matrix input movement slider/fader
  * `Matrix/Input Next` - Button state of the matrix input movement button to the right
  * `Matrix/Input Previous` - Button state of the matrix input movement button to the left
  * `Matrix/Inputs Current Button` - Button state of the input names button, that displays the currently visible inputs as text
  * `Matrix/Output Fader` - Fader value/position of the matrix output movement slider/fader
  * `Matrix/Output Next` - Button state of the matrix output movement button to the right
  * `Matrix/Output Previous` - Button state of the matrix output movement button to the left
  * `Matrix/Outputs Current Button` - Button state of the output names button, that displays the currently visible outputs as text
* `Outputs`
  * `Outputs/n Disable` - Disables this output in the matrix view. n: output index
  * `Outputs/n Index` - Output index string. n: output index
  * `Outputs/n Name` - Output name string. n: output index
* `Component Input Offset` - Value of the currently used input offset
* `Component Output Offset` - Value of the currently used output offset
* `Selected Component` - The currently selected component as a string
* `Status` - The current status of the plugin as a string

## Available Components/Modes

### Matrix Mixer (Q-SYS Component)

**Setup**

In the properties tab of the matrix mixer component, enable `Script Access` and enter a `Code Name`. Additionally, enable `Crosspoint Mute Controls` in the properties tab of that matrix mixer component.

**Usage**

When `Crosspoint Mute Controls` are enabled for the selected matrix mixer, this plugin can control and monitor all crosspoint input/output mutes. Additionally the input and output labels (names) are also controllable via this plugin. In this mode, the index indicators (green/red) of the matrix do not show, whether or not an input or output is used/assigned. This is due to performance constraints.

### Hi-App Plugin (X-Stage Plugin)

**Setup**

In the properties tab of the hi-app plugin component, enable `Script Access` and enter a `Code Name`.

**Usage**

This plugin can control routing assignments of hi-app inputs and outputs. Additionally the input and output labels (names) are also controllable via this plugin. In this mode, the index indicators (green/red) of the matrix show, what input or output is used/assigned.

### Call Plugin (X-Stage Plugin)

**Setup**

In the properties tab of the call plugin component, enable `Script Access` and enter a `Code Name`. Repeat this step for your projects PA-Router.

**Usage**

This plugin can be used to assign different PA zones of your PA-Router to any available call group of the call plugin. In this mode, the index indicators (green/red) of the matrix show, whether or not a group or zone is used/assigned.

### Call Mode (Standalone)

**Setup**

Enable `Call Mode` in the properties tab to activate logic based advanced group/destination routing. This generates additional controls for call groups and destinations.

**Usage**

In this mode, the call groups are displayed as "outputs" and the call destinations as "inputs".

After selecting call destinations for a call group inside the matrix (by setting crosspoints), the `Call Mode/Groups/n` pins can be used, to activate a call group. All selected destinations of the activated groups then output a true value via the `Call Mode/Destinations/n` pins. Also, the `Call Mode/Destination JSON` pin then outputs a JSON string, that shows all call destinations as a key-value table with the call destination indices as the key and the active call group indices as values in the value table.

Example:

```
  [
      [1,2],  -- Call Destination: 1      -- Call Groups Active: 1 and 2
      [1],    -- Call Destination: 2      -- Call Groups Active: 1
      [2],    -- Call Destination: 3      -- Call Groups Active: 2
      [],     -- Call Destination: 4      -- Call Groups Active: none
      []      -- Call Destination: 5      -- Call Groups Active: none
  ]
```

## Release Notes

See ReleaseNotes.md for version history and changes.

## License & Usage

The use of this plugin is only permitted with the explicit permission of Industrial Arts GmbH.

## Support

For questions or support, contact the developer:

* **Developer**: Moses Marquis ([m.marquis@industrial-arts.de](mailto:m.marquis@industrial-arts.de))
* **Product Owner**: Pirmin Punke ([p.punke@industrial-arts.de](mailto:p.punke@industrial-arts.de))

***

Industrial Arts GmbH © 2025. All rights reserved.
