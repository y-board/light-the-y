---
layout: page
toc: false
title: "Software Setup"
indent: 0
number: 1
icon: fa-solid fa-computer
---

## Install VS Code

### Install VS Code on Linux

1. Open the "Ubuntu Software" Application
    - Press the `Windows` key
    - Type `ubuntu software` and press `Enter`

1. Search for "Visual Studio Code" and install the application shown here:
    <img src="{% link media/vs_code_appstore.png %}" width="800" vspace="10px">

1. Once VS Code is done installing, launch it.

### Install VS Code on Windows

1. First go [download VS Code](https://code.visualstudio.com/download).

1. Click on the Windows installer.
    <img src="{% link media/vs_code_download_windows.png %}" width="800" vspace="10px">

1. Go to files on your computer and double click on the VS Code setup file you just downloaded.

1. Follow the steps of the installer.

1. Once VS Code is done installing, launch it.

### Install VS Code on Mac

1. First go [download VS Code](https://code.visualstudio.com/download).

1. Click on the Mac installer.
    <img src="{% link media/vs_code_download_mac.png %}" width="800" vspace="10px">

1. Go to files on your computer and double click on the VS Code setup file you just downloaded.

1. Follow the steps of the installer.

1. Once VS Code is done installing, launch it.

## Install PlatformIO Extension in VS Code

1. Within VS Code, click the "Extensions" button on the left toolbar:
    <img src="{% link media/extensions_button_vscode.png %}" width="800" vspace="10px">

1. Search for "Platform IO" and install the one that looks like this:
<img src="{% link media/platformio_extension.png %}" width="800" vspace="10px">

## Clone GitHub Repository

<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseGitCloneExplanation" role="button" aria-expanded="false" aria-controls="collapseGitCloneExplanation">
    What Does This Mean?
  </a>
</p>
<div class="collapse" id="collapseGitCloneExplanation">
  <div class="card card-body">
    <p>
        We've created a <strong>code repository</strong> that will get your board ready to program and provide you with a place to write your code. You will need to "clone" a copy of that repository onto your computer. To do so, follow the steps below for <em>one</em> of the two options (Clone from VS Code recommended).
    </p>
  </div>
</div>

**Clone from VS Code**

1. Open VS Code 
    - Press the `Windows` key
    - Type `code` and press `Enter`

1. Click the "Source Control" button on the left toolbar

1. Click "Clone Repository"

1. Enter the url `https://github.com/byu-cpe/y-badge-code.git` and click "Clone from URL" \
<img src="{% link media/vscode_gui_clone.png %}" width="800" vspace="10px">

1. A window will open and ask you to select the destination folder. Make sure you click "Home" on the left hand side of the window, then click the green "Select as Repository Destination" button \
<img src="{% link media/select_destination_folder.png %}" width="800" vspace="10px">

1. When asked if you want to open the project, click "Open"

**Clone from the Terminal**

1. Open a new instance of the "Terminal" application
    - Press the `Windows` key
    - Type `terminal` and press `Enter`

1. Type `git clone https://github.com/byu-cpe/y-badge-code.git` and press `Enter`

1. Type `code y-badge-code` and press `Enter`