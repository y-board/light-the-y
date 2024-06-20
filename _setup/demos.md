---
layout: page
toc: false
title: "Demos"
indent: 0
number: 3
icon: fa-solid fa-gamepad-modern
---

We have created several demo applications that you can use to explore the capabilities of the Y-Board. Each demo is a complete project that you can load onto the Y-Board and run. The demos are designed to be self-contained, so you can run them without needing to write any code.


The demos are stored on Github at the following link: <https://github.com/y-board/demos>

To run these on your computer, you will need to get these files on your local computer.


## Clone GitHub Repository

<details markdown="block">
<summary markdown="span">What Does This Mean?
</summary>

We've created a **code repository** that stores the demo applications. You will need to "clone" a copy of that repository onto your computer. To do so, follow the steps below for.

</details>

**Clone from VS Code**

1. Open VS Code 
    - Press the `Windows` key
    - Type `code` and press `Enter`

1. Click the "Source Control" button on the left toolbar

1. Click "Clone Repository"

1. Enter the url `https://github.com/y-board/demos.git` and hit Enter \
<img src="{% link media/vscode_gui_clone_demos.png %}" width="800" vspace="10px">

1. A window will open and ask you to select the destination folder. Make sure you click "Home" on the left hand side of the window, then click the green "Select as Repository Destination" button \
<img src="{% link media/select_destination_folder.png %}" width="800" vspace="10px">

1. When asked if you want to open the project, click "Open"



## Select and Open a Demo

Once you have the demos repository open in VS Code, you can view the structure of the project and looks at the demos available.  Once you have decided on a demo to run, you will need to open the demo folder in its own VS Code window.  Follow the steps below to do this:

1. Select the file *Explorer* button on the left toolbar
1. Expand the `y-board-v2` or `y-board-v3` folder to view the demos available for your board.
1. Note the different folders inside your board folder.  Each folder contains a separate demo application.
<img src="{% link media/demos_file_browser.png %}" width="800" vspace="10px">
1. Once you have decided on a demo to run, click *File*->*Open Folder* and select the folder for the demo you want to run.

## Running a Demo

Once you have a demo folder opened up, you can run the demo on your Y-Board.  To do so, simply click the *Upload* button as shown on the [Running Code]({% link _setup/compiling.md %}) page.
