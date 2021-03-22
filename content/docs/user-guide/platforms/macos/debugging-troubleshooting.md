---
description: ' Debug your macOS application using Xcode and O3DE source code. Troubleshoot
  the various steps to build assets, shaders, and your macOS application. '
title: macOS Debugging and Troubleshooting
weight: 500
---

{{< preview-migrated >}}

|  |
| --- |
| This feature is in [preview](/docs/userguide/ly-glos-chap#preview) release and is subject to change\.  |

O3DE provides full access to the source code, which allows you to debug your macOS application using Xcode without additional O3DE\-specific steps to follow\. For information about debugging and profiling your macOS application, see [Debugging](https://developer.apple.com/support/debugging/) in the official Apple developer documentation\.

**Unable to see activity in the shader compiler window**
You must connect to the shader compiler on your PC in order to compile the subset of shaders required by your game, on demand\. To verify that your app has connected correctly and obtained all shaders, you can view the output in the shader compiler window\. If you still do not see any activity in the window, please check your setup by following the instructions on the [Building Shaders for macOS Games](/docs/user-guide/platforms/macos/shaders-building.md) page\.

Cleaning the project does not create a full rebuild of the macOS application

O3DE uses a custom build step to generate the final executable and temporary C\+\+ object files, which output to the `\BinTemp\darwin_x64_debug` or `\BinTemp\darwin_x64_profile` directory where you installed O3DE\. Unlike a regular Xcode project, in order to create a full rebuild of the macOS application, you must manually delete the contents of the output folder or run one of the following Waf commands from a Terminal window:
+ To build debug, run the following command: `lmbr_waf.sh clean_darwin_x64_debug`
+ To build profile, run the following command: `lmbr_waf.sh clean_darwin_x64_profile`
+ To build release, run the following command: `lmbr_waf.sh clean_darwin_x64_release`

**Observed frame rate varies greatly**
While running your application, the observable frame rate can vary depending on the build \(debug or profile\) you are running and whether you are connected to the Xcode debugger\. To display the frame rate in the upper right corner of the screen, set the `r_DisplayInfo` configuration variable to **1** or higher\. When your Xcode project is generated, the default build scheme is set up for debugging\. If you want to test or profile your application's speed, we recommend that you [edit your active scheme](https://developer.apple.com/library/mac/recipes/xcode_help-scheme_editor/Articles/SchemeDialog.html) to run a profile build\. Deselect **Debug executable**\.