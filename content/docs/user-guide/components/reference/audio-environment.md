---
description: ' Use the Audio Environment component to set up a default environment
  for an entity in Open 3D Engine. '
title: Audio Environment
---

{{< preview-migrated >}}

The **Audio Environment** component provides access to features of the [Audio Translation Layer \(ATL\)](/docs/user-guide/interactivity/audio/default-controls.md) environments\. Environments are used to apply environmental effects such as reverb or echo\.

![\[Image NOT FOUND\]](/images/user-guide/component/audio/component-audio-environment1.png)

## Audio Environment Properties {#component-audio-environment-properties}

The **Audio Environment** component has the following property:

**Default Environment**
Enter the name of the audio environment to use by default when setting amounts\.

## EBus Request Bus Interface {#component-audio-environ-ebusrequest}

Use the following request functions with the EBus interface to communicate with other components of your game\.

For more information about using the Event Bus \(EBus\) interface, see [Working with the Event Bus \(EBus\) system](/docs/user-guide/engine/ebus/_index.md)\.

### SetAmount {#environ-audio-ebus-setamount}

Sets the amount of environmental **'send'** to apply to the default environment, if set\.

**Parameters**
`amount` - Float value of the amount to set

**Return**
None

**Scriptable**
Yes

### SetEnvironmentAmount {#environ-audio-ebus-setenvironmentamount}

Sets the amount of environmental **'send'** to apply to the specified environment\.

**Parameters**
`environmentName` - Name of ATL Environment to set an amount on
`amount` - Float value of the amount to set

**Return**
None

**Scriptable**
Yes