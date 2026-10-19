---
url: https://docs.comfy.org/installation/desktop/usage/manage/
title: Managing Installations - ComfyUI
method: scrapling+scrapegraph
fetched_at: 2026-10-19T14:35:02.392980+00:00
---

# Managing Installations - ComfyUI

> Source: https://docs.comfy.org/installation/desktop/usage/manage/

## On this page

  * The Manage Panel
    * Update Tab
    * Startup Args Tab
    * Snapshots Tab
    * Storage Tab
    * Terminal Tab
    * About Tab
  * Installation Actions



Usage Guide

# Managing Installations

Copy pageCopy page

Launch, update, snapshot, and manage your ComfyUI installations

Copy pageCopy page

## 

​

The Manage Panel

The Manage panel content varies by instance type. The screenshots on this page show a **local standalone installation**. Cloud and remote instances have fewer tabs and settings. Select **Manage** on an installation to open the settings panel. ![Manage panel for a local instance: Update, Startup Args, Snapshots, Storage, Terminal, About](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/instance_settings_00.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=08543aa6d8a03edc52880c0e0cecd1cb)

  * Open the **Chooser** view (the home screen showing all your instances)
  * Click the ⋮ icon on an instance card
  * Select **Manage** from the context menu

The panel has six tabs:

### 

​

Update Tab

![Manage Update tab: ComfyUI version, update channel, and PyTorch package](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/instance_settings_01_update.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=1577f0d4aa21028a22285ba1b2abeadf) This tab shows the current version, lets you check for updates, and configure the update channel.

  * **Version** : Shows the current installed version and whether it’s up to date.
  * **Last checked** : Displays when updates were last checked.
  * **Check for update** : Manually check for a new version.
  * **Update Channel** : Choose the update channel from the dropdown: 
    * **Stable** : Tested releases, recommended for most users. Default option.
    * **Latest on GitHub** : Newest commits from the master branch.



### 

​

Startup Args Tab

![Manage Startup Args tab for instance launch arguments and beta args](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/instance_settings_02_startup_args.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=19f6f70ddf4ab607ccb6b649ea2a7995) Configure startup CLI arguments, Manager policy, launch mode, browser cache sharing, port conflict behavior, and environment variables.

  * **Startup Arguments** : Custom CLI arguments for ComfyUI (e.g. `--listen`). Click the gear icon for categorized flags. When beta features are enabled, a **+N beta** pill next to the field lists the beta arguments Comfy Desktop added for the running session, or the ones the next launch is eligible for.
  * **Manager Security Level** : Controls which node packs ComfyUI-Manager can install for this instance. Applies the next time you launch. 
    * **Strict** : Blocks all node pack installs, updates, and uninstalls. Manager is read-only.
    * **Standard (recommended)** : Allows registered node packs. Blocks installs from unregistered sources (for example arbitrary git URLs).
    * **Relaxed** : Like Standard, but also allows unregistered-source installs while ComfyUI is only reachable from this machine. `--listen` blocks them again.
    * **Permissive** : Allows every risk tier. If ComfyUI is exposed with `--listen`, installs still require **Personal cloud** network mode.
  * **Manager Network Mode** : How Manager talks to the node registry. 
    * **Public (default)** : Uses the public registry. `--listen` blocks node pack installs at every security level.
    * **Private** : Uses a private node database you configure yourself.
    * **Offline** : No external network. Downloads are unavailable.
    * **Personal cloud** : Treats this machine as a trusted remote box and lifts the `--listen` install block. The chosen security level still applies. Only use this on a machine you control.
  * **Launch Mode** : **App window** (embedded) or **Console only** (no app window; ComfyUI runs as a console process).
  * **Browser Cache** : **Unique to this instance** or **Shared**.
  * **If Port is Busy** : **Ask what to do** , or **Use next available port (asks if —port is set)**.
  * **Environment Variables** : Add custom environment variables with the **\+ Add Variable** button.



## Startup Flags Reference

See the full list of ComfyUI startup flags available for Startup Arguments.

### 

​

Snapshots Tab

![Manage Snapshots tab listing restore points for the instance](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/instance_settings_03_snapshots.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=88bc650af81748f7ddaf889ec27ac755) View, import, export, and create snapshots. Each entry shows version changes and package statistics.

  * **Timeline** : Lists all snapshots chronologically with version changes and stats.
  * **Latest** : Shows when the most recent snapshot was taken.
  * **Import** : Import a snapshot from a file.
  * **Export All** : Export all snapshots as a backup.
  * **Create Snapshot** : Manually create a new snapshot at any time.
  * Each snapshot entry shows: 
    * Version change (e.g. `v0.20.1 → v0.24.1`)
    * Package changes
    * Node and package counts
    * **Export** and **Delete** buttons



## Complete Snapshot Management

Learn about automatic snapshots, comparison, and full snapshot management.

### 

​

Storage Tab

![Manage Storage tab for per-instance model and I/O paths](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/instance_settings_04_storage.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=193f1e10a16fca5cd4ee4962b0bb645e) Configure whether this instance uses the global shared folders, and add extra model directories that apply only to this instance.

  * **Include Shared Directories** : Toggle whether this instance scans the global shared model directories from [Desktop Settings → Storage](https://docs.comfy.org/installation/desktop/usage/settings#storage).
  * **Use Shared Input Folder** : When enabled, this instance reads input files from the global shared input folder. Disable to use this instance’s own input folder.
  * **Use Shared Output Folder** : When enabled, this instance writes generated outputs to the global shared output folder. Disable to use this instance’s own output folder.
  * **Model Directories** : Extra model directories for this instance only, searched in addition to the shared model directories.
  * **Input Directory** / **Output Directory** : This instance’s own folders when the shared toggles above are off.



### 

​

Terminal Tab

![Manage Terminal tab showing the instance console](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/instance_settings_05_console.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=42b31f1f47d7b8ae1afdd70fe8165dfa) An interactive shell in this instance’s folder. It works whether ComfyUI is running or stopped.

  * Use it to inspect startup logs, errors, and Python output.
  * Copy, paste, and select-all follow OS shortcuts. Right-click the terminal for the same actions.



### 

​

About Tab

![Manage About tab with instance paths and version details](https://mintcdn.com/dripart/N4LZwJLSpBN0lv19/images/desktop/usage/instance_settings_05_about.png?fit=max&auto=format&n=N4LZwJLSpBN0lv19&q=85&s=f3fd05eb228275ec4d03685c7922e83e) View installation details: ComfyUI version, hardware, Python and PyTorch versions, disk path, and usage.

  * **Current Version** : The installed ComfyUI version.
  * **Hardware** : Detected hardware (e.g. `Apple Silicon (MPS)`).
  * **Python** : Bundled Python version.
  * **PyTorch** : The installed PyTorch build. **Change PyTorch** switches to an official stack tested with this install type (CUDA, ROCm, Intel XPU, CPU, or Apple MPS). The rest of the environment is kept. Nightly builds are marked unstable.
  * **Location** : The full installation path on disk. Click the copy button to copy it.
  * **Disk Usage** : How much disk space the installation uses.



## 

​

Installation Actions

Right-click an installation card (or click the ⋮ icon) to access actions. See the [Instance Management](https://docs.comfy.org/installation/desktop/usage/instance-management) page for a full list of actions.

Was this page helpful?

YesNo

[Suggest edits](https://github.com/comfy-org/docs/edit/main/installation/desktop/usage/manage.mdx)[Raise issue](https://github.com/comfy-org/docs/issues/new?title=Issue%20on%20docs&body=Path:%20/installation/desktop/usage/manage)

[Model Downloads in Comfy DesktopPrevious](https://docs.comfy.org/installation/desktop/usage/downloads)[Comfy Desktop SettingsNext](https://docs.comfy.org/installation/desktop/usage/settings)

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
