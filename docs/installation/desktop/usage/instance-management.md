---
url: https://docs.comfy.org/installation/desktop/usage/instance-management/
title: Instance Management - ComfyUI
method: scrapling+scrapegraph
fetched_at: 2026-10-17T10:50:58.018314+00:00
---

# Instance Management - ComfyUI

> Source: https://docs.comfy.org/installation/desktop/usage/instance-management/

## On this page

  * Instance Types
  * Creating a New Instance
  * Tracking an Existing Installation
    * Detecting Your Installation
    * Setting Paths
    * Track vs Standalone
  * Launching, Stopping, and Restarting an Instance
    * Launching an Instance
    * Launching While Another Instance Is Running
    * Stopping an Instance
    * Restarting After a Crash
  * Uninstalling an Instance
  * Copying an Installation
  * Editing an Instance
  * Error State



Usage Guide

# Instance Management

Copy pageCopy page

Create, edit, rename, and delete ComfyUI instances in Comfy Desktop

Copy pageCopy page

Comfy Desktop lets you manage multiple ComfyUI instances from the Chooser view.

### 

​

Instance Types

Comfy Desktop supports four types of instances. Each type displays a distinct icon on its card and in the title bar.

Type| Icon| Description  
---|---|---  
**Standalone**|  💻| A self-contained ComfyUI instance created by Comfy Desktop. Includes bundled Python, automatic updates, and full snapshot support. This is the default when you click **New Instance**.  
**Cloud**|  ☁️| A Comfy Cloud instance. Requires a Comfy Cloud account. Cloud instances run on Comfy’s servers and are billed separately.  
**Remote**|  🌐| Connects to a ComfyUI instance running on another machine on your network. Configure the remote host and port during setup.  
**Tracked**|  —| Tracks an existing ComfyUI installation (Git clone or portable). Uses the same icon as **Standalone** — there is no separate icon for tracked instances. You manage updates manually. See Tracking an Existing Installation.  
  
The image below labels the key actions available for each instance card: ![Instance card ⋮ menu: Manage, Duplicate, Show in Folder, Export/Restore Snapshot, Uninstall](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/interface/interface_instance_menu.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=eabc491b33905fbe3b187b15191b7ecb)

  1. **New Instance** : Create a brand new ComfyUI instance. See Creating a New Instance. You can also [create an instance from a snapshot file](https://docs.comfy.org/installation/desktop/usage/snapshots#create-an-instance-from-a-snapshot-file).
  2. **⋮ Menu** : Click the three-dot icon to open the action menu for an instance.
  3. **Manage** : Open the Manage panel to configure the instance (path, launch args, model directories, environment variables). See the [Manage](https://docs.comfy.org/installation/desktop/usage/manage) page.
  4. **Restore Snapshot** : Revert the instance to a previous snapshot. See the [Snapshots](https://docs.comfy.org/installation/desktop/usage/snapshots) page.
  5. **Share** : Export a snapshot of the instance to share with others.
  6. **Copy Installation** : Duplicate an existing standalone installation with its own Python environment and custom nodes. See Copying an Installation.
  7. **Forget** : Remove the instance from the Chooser without deleting its files (equivalent to Untrack).
  8. **Uninstall** : Permanently delete the instance and all its files from disk. See Uninstalling an Instance for details on Forget and Uninstall.



## 

​

Creating a New Instance

Click the **+** card (top-left) in the Chooser view to add a new ComfyUI instance.

1

Create a New Instance

  * Windows

  * macOS

  * Linux




![The Create a New Instance wizard on Windows, annotating the name \(1\), build mode \(2\), release channel \(3\), hardware \(4\) and install location \(5\)](https://mintcdn.com/dripart/cAVuyhdaebQHS2CS/images/desktop/usage/new_install_01_settings_windows.png?fit=max&auto=format&n=cAVuyhdaebQHS2CS&q=85&s=f293743f357c88ea7639667b957053de)

![The Configure Comfy Desktop wizard on macOS, annotating the name \(1\), the Browse button \(2\), Advanced options \(3\), Standalone \(4\) and Remote Connection \(5\)](https://mintcdn.com/dripart/0w1gtsOzv5mNaeqr/images/desktop/usage/new_install_01_settings_mac.png?fit=max&auto=format&n=0w1gtsOzv5mNaeqr&q=85&s=d8228761665dace0b77d19ca2ce57a8c)

![Create a New Instance wizard on Linux: name, Public Builds, release, hardware \(AMD/NVIDIA/Intel Arc\), and install location with free space](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/new_install_01_settings_linux.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=03b4201e96f77d5ecac7d8920268992e)

  1. **Name** : The name of your instance. The default is “ComfyUI”.
  2. **Public Builds** : The recommended option. A standard ComfyUI install built for your detected hardware. Select **Managed Builds** to install a Build from one of your workspaces instead (see [Workspaces and Builds](https://docs.comfy.org/installation/desktop/usage/workspaces-and-builds#installing-a-build)), or **Remote Connection** to connect to a ComfyUI instance running on another machine.
  3. **Release** : The release channel to install. **Stable (Recommended)** is preselected.
  4. **Hardware** : Comfy Desktop detects your GPU and preselects the matching build (NVIDIA, AMD, Intel Arc (XPU), or CPU). Each option shows the ComfyUI version, the Python version, and the download size.
  5. **Install Location** : Where ComfyUI is installed. On Windows, it’s strongly recommended to use an **SSD** and avoid the root of the C: drive. The field shows free space on the drive and an install size estimate when Comfy Desktop knows it.

If free space looks low, the wizard shows a **Low Disk Space** dialog. Choose **Continue Anyway** , or cancel and pick another path.![Low Disk Space dialog showing free space versus required install size, with Cancel and Continue Anyway](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/low_disk_space_dialog.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=7306da9f6d98179436d54fa23581eb62)

2

Installing

![Installing progress: Downloading ComfyUI with percent, throughput, and remaining steps](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/new_install_02_installing.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=56f28d2fc1eb721c2ef27d4229816095)Comfy Desktop will handle the rest: downloading Python, setting up the environment, and installing ComfyUI. The progress screen shows the current step.

3

Choose a Template

![Choose a starter workflow step with Video/Image/3D/Audio tabs before install finishes](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/new_install_03_interface_template.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=c02ae0bffd0167cecf0fea20418cba79)Once the installation is complete, Comfy Desktop opens the template library where you can pick a workflow template to get started.Templates that download models need enough free space for those files. If the drive cannot hold a template’s models, the wizard blocks that choice — pick a lighter template or free space. On very small disks, the template step may be skipped entirely.

## 

​

Tracking an Existing Installation

If you already have a ComfyUI installation (either manually set up from the Git repository or downloaded as a portable version), you can add it to Comfy Desktop without creating a new one. Click **New Instance** on the Dashboard to open the installation menu, then select **Add Existing Instance**. ![Add Existing Instance](https://mintcdn.com/dripart/nieA_of_7hwqPqsM/images/desktop/usage/track_instance_01.png?fit=max&auto=format&n=nieA_of_7hwqPqsM&q=85&s=e46a37b75bfe364219e28b259001ae57)

  1. Click **New Instance** to open the installation options.
  2. Select **Add Existing Instance** to open the tracking dialog.



### 

​

Detecting Your Installation

In the tracking dialog, click **Browse** to select a ComfyUI directory. Comfy Desktop probes the folder and automatically detects the installation type. For a **Windows portable** install, the probe looks for:

  * `standalone-env` directory — the bundled Python environment
  * `ComfyUI/main.py` — the ComfyUI entry point

For a **manually cloned git repo** , the probe looks for:

  * `models/` and `user/` directories — signs of a configured ComfyUI
  * `.venv` directory — a Python virtual environment



### 

​

Setting Paths

After selecting the directory, the dialog shows the detected paths. You can adjust them if needed. ![ComfyUI directory and Python environment](https://mintcdn.com/dripart/nieA_of_7hwqPqsM/images/desktop/usage/track_instance_02.png?fit=max&auto=format&n=nieA_of_7hwqPqsM&q=85&s=1cc5306a7db7b481082b3734f39212c3)

  1. **ComfyUI Directory** : The path to the ComfyUI folder containing `main.py`. For portable installations, this is typically the folder _inside_ the portable package. 
     * Portable example: `D:\ComfyUI_windows_portable\ComfyUI`
  2. **Python Environment** : The path to the Python environment folder. Comfy Desktop detects this automatically and lets you override it if needed. 
     * Portable example: `D:\ComfyUI_windows_portable\python_embeded`
     * Git repo example: `<ComfyUI_dir>/.venv`



### 

​

Track vs Standalone

The key difference between a **Tracked** (Add Existing Instance) installation and a **Standalone** installation is how updates are managed:

Aspect| Tracked (Existing)| Standalone  
---|---|---  
**Updates**|  No automatic updates — manage ComfyUI version manually via Git| Built-in automatic updates  
**Python**|  Uses an existing Python environment (`.venv`, `python_embeded`, etc.)| Bundled Python, automatic dependency management  
**Isolation**|  Shares the existing path and environment| Fully self-contained, isolated installation  
**Snapshots**|  Not supported| Snapshot support available  
**Use case**|  Already have ComfyUI set up and customized| Fresh install from scratch  
  
> **Note:** Tracked installations use `launchMode: 'external'`. Comfy Desktop launches the existing ComfyUI process without managing it internally. Snapshots are currently supported for Standalone instances only.

## 

​

Launching, Stopping, and Restarting an Instance

↩ Back to overview

### 

​

Launching an Instance

Click an instance card in the Chooser to launch it. While ComfyUI starts, the window shows the startup progress, then the ComfyUI interface once the server is ready.

### 

​

Launching While Another Instance Is Running

When you launch a local instance while another local instance is running or starting, Comfy Desktop shows an **An instance is already running** dialog that lists the instances it would stop:

  * **Close & Launch**: stops the listed instances, then launches the one you picked.
  * **Run All** : launches the new instance alongside the running ones.

Dismiss the dialog to cancel the launch. Restarting an instance never shows this dialog. To stop seeing it, turn off **Warn before running multiple instances** in [Desktop Settings → Preferences](https://docs.comfy.org/installation/desktop/usage/settings#preferences).

### 

​

Stopping an Instance

Select **Stop** from the instance card’s ⋮ menu. The ComfyUI server stops and the window stays open with a **ComfyUI is stopped** card. Select **Relaunch ComfyUI** to start the server again, or **Return to Dashboard** to go back to the Chooser.

### 

​

Restarting After a Crash

If ComfyUI fails to start or exits unexpectedly, the window stays open with a card describing what happened:

  * **ComfyUI could not start** : the instance did not start.
  * **ComfyUI exited unexpectedly** : the process stopped. When Comfy Desktop can read it, the card also shows the exit code, or the signal that ended the process.

On Windows, a crash can report a memory access violation and note that some Microsoft Visual C++ Redistributable files appear to be missing. Expand the card’s logs for details, then select **Restart ComfyUI** to launch again, or **Back** to return to the dashboard. If ComfyUI stops because it cannot open the asset database it keeps inside the installation, the error it stops with explains the reason instead of only reporting an exit code:

  * **Another ComfyUI is using this installation’s database** : close that ComfyUI (or the app that started it), or give one of them its own database location with the `--database-url` startup argument.
  * **Any other database failure** , from one locked by another program to one written by a newer version of ComfyUI or impossible to create in that folder: the message names the file and the fix, and ends with the option to start the instance without the asset system, by adding `--disable-assets` to its startup arguments.



## 

​

Uninstalling an Instance

↩ Back to overview When you want to remove an instance, the three-dot menu offers two options depending on whether you want to keep the files or delete everything. ![Forget vs Uninstall](https://mintcdn.com/dripart/nieA_of_7hwqPqsM/images/desktop/usage/instance_uninstall.png?fit=max&auto=format&n=nieA_of_7hwqPqsM&q=85&s=eb59cb4e1ee479602cecf8847b94b6e1)

  1. **Forget / Untrack** : Removes the instance from the Chooser list without deleting any files. The installation folder and all its data remain on disk. Use this when you just want to clean up the list but might need the instance again later.
  2. **Uninstall / Delete** : Permanently removes the installation and all its files from disk. Model files in shared directories are not affected.

The name you see in the menu depends on the instance type: **Forget** appears for standalone installations (untrack doesn’t apply because standalone installs are local), while **Untrack** appears for installations that were adopted or added manually. Both do the same thing: remove the instance from the list without deleting its files.

## 

​

Copying an Installation

↩ Back to overview You can duplicate an existing standalone installation by right-clicking its card and selecting **Copy Installation**. This creates a copy with:

  * A new Python environment
  * The same ComfyUI version
  * Its own custom node setup

You’ll be prompted to enter a name for the new installation before the copy starts.

## 

​

Editing an Instance

↩ Back to overview In the **Manage** panel for an instance, you can:

  * Change the installation path
  * Adjust launch arguments
  * Modify model directories
  * Update environment variables

Open the **Manage** panel by right-clicking the instance card and selecting **Manage**.

## 

​

Error State

If an installation encounters a problem, a warning indicator appears on its card. Right-click the card and select **Dismiss Error** to clear the error state. If the issue persists, check the logs at the [Data Locations](https://docs.comfy.org/installation/desktop/usage/settings#data-locations).

Was this page helpful?

YesNo

[Suggest edits](https://github.com/comfy-org/docs/edit/main/installation/desktop/usage/instance-management.mdx)[Raise issue](https://github.com/comfy-org/docs/issues/new?title=Issue%20on%20docs&body=Path:%20/installation/desktop/usage/instance-management)

[Using Comfy DesktopPrevious](https://docs.comfy.org/installation/desktop/usage/overview)[Workspaces and ComfyUI Builds in Comfy DesktopNext](https://docs.comfy.org/installation/desktop/usage/workspaces-and-builds)

⌘I

[ComfyUI home page![light logo](https://mintcdn.com/dripart/WCFdTagRdhtvk9-o/logo/light.svg?fit=max&auto=format&n=WCFdTagRdhtvk9-o&q=85&s=ec112de87239058f5a931a7e4b594965)![dark logo](https://mintcdn.com/dripart/QzWbjSCBG7w61rR3/logo/dark.svg?fit=max&auto=format&n=QzWbjSCBG7w61rR3&q=85&s=62b4d879fb3aadbd7a468d1539032d6f)](https://docs.comfy.org/)

[github](https://github.com/Comfy-Org/ComfyUI)[x](https://x.com/ComfyUI)[discord](https://discord.com/invite/comfyorg)[youtube](https://www.youtube.com/@comfyorg)

Resources

[installation](https://docs.comfy.org/installation/system_requirements)[Tutorials](https://docs.comfy.org/tutorials/basic/text-to-image)[Development](https://docs.comfy.org/development/overview)

Products

[Features](https://www.comfy.org/?utm_source=docs)[Gallery](https://www.comfy.org/gallery?utm_source=docs)[Download](https://www.comfy.org/download?utm_source=docs)

Company

[About](https://www.comfy.org/about?utm_source=docs)[Careers](https://www.comfy.org/careers?utm_source=docs)[Terms of Service](https://www.comfy.org/terms-of-service?utm_source=docs)[Privacy Policy](https://www.comfy.org/privacy-policy?utm_source=docs)

[github](https://github.com/Comfy-Org/ComfyUI)[x](https://x.com/ComfyUI)[discord](https://discord.com/invite/comfyorg)[youtube](https://www.youtube.com/@comfyorg)

[Powered byThis documentation is built and hosted on Mintlify, a developer documentation platform](https://www.mintlify.com?utm_campaign=poweredBy&utm_medium=referral&utm_source=dripart)
