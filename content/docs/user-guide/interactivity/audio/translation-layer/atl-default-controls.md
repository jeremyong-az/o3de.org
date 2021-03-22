---
description: ' Create sound effects for your game project with the Audio Controls Editor
  in Open 3D Engine. '
linktitle: Default controls
title: ATL default controls
weight: 200
---

{{< preview-migrated >}}

The game uses Audio Translation Layer \(ATL\) controls to communicate with the audio middleware\. ATL controls are mapped to various data authored in the middleware's authoring tool\. This abstraction layer provides you the flexibility to change mappings quickly without updating the game's integration of controls\.

To see the list of audio control types, see [ATL Controls Pane](/docs/user-guide/interactivity/audio/atl-editor-atl-controls.md)\.

## ATL Default Controls {#audio-controls-default}

The **Audio Controls Editor** automatically creates the following ATL controls by default\. You can find the controls in the `default_controls` folder\.

![\[ATL controls that the Audio Controls Editor automatically creates by default.\]](/images/user-guide/audio/audio-atl-editor-default.png)


**Default ATL Controls**

| Name | Description |
| --- | --- |
| do\_nothing |  Trigger that is used as a blank event where `play`/`stop` trigger pairs can be assigned\. If you set `do_nothing` on the `stop` trigger, the `play` trigger does not stop automatically\.  |
| get\_focus |  Trigger that is called when the application window in O3DE Editor gains focus\.   |
| lose\_focus |  Trigger that is called when the application window in O3DE Editor loses focus\.  To disable the `get_focus` and `lose_focus` triggers, use the console command `s_IgnoreWindowFocus` = `1`\. This is useful when remote connecting Wwise Profiler so that audio continues to play while the Wwise Authoring Tool application has focus\.   |
| mute\_all |  Trigger that is called when you click **Mute Audio**, which is located on the lower menu bar of O3DE Editor\.  |
| unmute\_all |  Trigger that is called when you click **Mute Audio**, which is located on the lower menu bar of O3DE Editor\.  |
| object\_speed |  RTPC control that is updated according to the speed of the associated entity in the level\. You can enable the calculation of speed on a per entity basis with the `object_velocity_tracking` control\.   |
| object\_velocity\_tracking |  Switch that is used to enable or disable the calculation of the `object_speed` value on a per entity basis\. You do not need to connect this switch to the audio middleware because it communicates O3DE\-specific data\.   |
| ObstructionOcclusionCalculationType |  Switch that is used to set the obstruction and occlusion calculation method of an entity\. The switch state values are `Ignore`, `SingleRay`, and `MultiRay`\. You do not need to connect this switch to the audio middleware because it communicates O3DE\-specific data\.   |