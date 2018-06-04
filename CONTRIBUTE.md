---
title: Contribution Policy
permalink: /documentation/CONTRIBUTE.md.html
---

# Contributing to 96Boards Documentation

Thanks for stopping by to contribute the mezzanine-community repository! The following is a set of guidelines for contributing.

**NOTE: This documentation is solely for the 96Boards Documentation Repository, for filing bugs and issues about the boards themselves please refer to: [Report A Bug](Extras/Report_a_bug.md)**

## Table Of Contents

- [Bugs and Suggestions](#bugs-and-suggestions)
- [Contribution](#contribution)
  - [General Contribution and Bug-Fixes](#general-contribution-and-bug-fixes)
  - [Adding a New Guide](#adding-a-new-guide)
  - [Adding a New Boards](#adding-a-new-boards)
  - [Guidelines for submitting a Pull Request](#guidelines-for-submitting-a-pull-request)

## Bugs and Suggestions

Before attempting to fix the issue/bug on your own, it is recommended to open an issue. There are two ways of doing that:
- Using "Report an Issue" button integrated on every page of our website placed on the bottom right.

  ![Report an Issue](https://i.imgur.com/qM1bJjH.png)
- Using the [built-in issues page](https://github.com/96boards/documentation/issues) provided in this GitHub repository.

One of our maintainers will get around to your issue as soon as possible. After review, the maintainer may fix the issue on his/her own, or request the subject step in to fix the observed issue. If inclined:
- Send your edits using "Edit on GitHub" button integrated on every page of our website placed on the bottom right.

  ![Report an Issue](https://i.imgur.com/qM1bJjH.png)
- Or manually fork the repository, make said edits, and submit a [Pull Request](https://help.github.com/articles/about-pull-requests/).

Please make sure you comply with the following criteria when creating/submitting your issue:

- **Use a clear and descriptive title** for the issue to identify the problem/suggestion.
- **Describe the exact steps to reproduce the problem** in as many details as possible in the case of a problem or suggestion
- **Mention location** where was this issue is found / what will your suggestion affect.

If You need help with submitting an issue or a pull request on GitHub, take a look at our tutorial over at YouTube:
 - [Submit an issue](https://www.youtube.com/watch?v=OzitElQoHzU&index=1&list=PL-NF6S9MM_W1Lf714oYsSRIHT4bL_8P7e)
 - [Fork the Repository](https://www.youtube.com/watch?v=PXgqMPSMG-o&index=0&list=PL-NF6S9MM_W1Lf714oYsSRIHT4bL_8P7e)
 - [Send a Pull Request](https://www.youtube.com/watch?v=k4VtYyjakOw&index=3&list=PL-NF6S9MM_W1Lf714oYsSRIHT4bL_8P7e)
 - More information on [GitHub issues](https://guides.github.com/features/issues/).
 - More information on submitting a [Pull Request](https://help.github.com/articles/about-pull-requests/)
***

## Contribution

### General Contribution and Bug-Fixes:

Community contributions are always Welcome! This section is intended to help anyone interested in contributing to this repository. For quick fixes and corrections its fine just to get stuck in. On the other hand if you want to add new pages then, before you spend a long time working on it, it is a good idea to discuss your idea with the repository maintainers and community by raising a [GitHub issue](https://github.com/96boards/documentation/issues) using the guidelines mentioned above.

Either way, when you are ready to make changes, you will need to do the following (these instructions assume you are a [GitHub user](https://github.com/join):
- Send your changes using "Edit on GitHub" button integrated on every page of our website placed on the bottom right.

  ![Report an Issue](https://i.imgur.com/qM1bJjH.png)

- Manually send them using git:
  - ###### Step 1: [Fork this repository](https://help.github.com/articles/fork-a-repo/)
    - [Video Tutorial on How to Fork the Repository](https://www.youtube.com/watch?v=PXgqMPSMG-o&index=0&list=PL-NF6S9MM_W1Lf714oYsSRIHT4bL_8P7e)
  - ###### Step 2: [Make changes, commit and push to your fork](https://services.github.com/on-demand/github-cli/add-commits-git)
  - ###### Step 3: [Submit Pull Request](https://help.github.com/articles/creating-a-pull-request/)
    - [Video Tutorial on How to Send a Pull Request](https://www.youtube.com/watch?v=k4VtYyjakOw&index=3&list=PL-NF6S9MM_W1Lf714oYsSRIHT4bL_8P7e)
    - When submitting a Pull Request to the 96Boards repository, there's a check list in the [Guidelines for submitting a Pull Request](#guidelines-for-submitting-a-pull-request) section to help you.

A full fledged git and github training is available here: [GitHub On Demand Training](https://services.github.com/on-demand/)

**All 96Boards Documentations follow the markdown '.md' format unless otherwise specified.**

***

### Adding a New Guide

We encourage our community members to submit 96Boards related guides to our repository so others can benefit.

- Before getting started, it's a good idea to discuss your idea with the repository maintainers and community by raising a [GitHub issue](https://github.com/96boards/documentation/issues) using the guidelines mentioned in the [Bugs and Suggestions](#bugs-and-suggestions) section.
- Get familiar with git and GitHub following our [General Contribution and Bug-Fixes](#general-contribution-and-bug-fixes) topic.
- We use the following structure to arrange our guides:
  - ```/guides``` Generic guides that span across all 96Boards
  - ```/consumer/guides``` Edition specific guides, they may be consumer, enterprise or ie
  - ```/consumer/<board-name>/guides``` Board specific guides
- Make sure to place header section on your guides file, these headers make sure that the web page is properly generated and place at the correct location.:
  ```
  ---
  title: Guide Title
  permalink: /documentation/consumer/boardname/guide/guide-name.html
  ---
  ```
- Before submitting a Pull Request to the 96Boards repository, make sure to read and adhere to our guidelines mentioned in the [Guidelines for submitting a Pull Request](#guidelines-for-submitting-a-pull-request) section.
***

### Adding a New Boards:

If you have recently launched a new 96Boards and have to add it to the documentation repository.
- Get yourself familiar with the [General Contribution and Bug-Fixes](#general-contribution-and-bug-fixes) topic.
- Arrange your documentation material following the [Template](templates/board-template)
- Each folder/section has a README.md file that acts like the "index.html" or front page of said section of the documentation. This can be used as an index or point-of-entry for said section of the documentation.
- **Boards Folder Structure:**
  - ```<board-name/additional-docs/```:
    - ```<board-name>/additional-docs/images/```: This folder contains ALL the images that would be used throughout the documentation
      - ```<board-name>/additional-docs/images/images-board/```: Images of the board itself, preferably with transparent background. Check the [README.md](templates/board-template/additional-docs/images/images-board/README.md) in the template for details on the resolution.
      - ```<board-name>/additional-docs/images/images-hw-user-manua/l```: This folder hosts all the images related to the Hardware User Manual Docs, these may include schematics, flowcharts block diagrams etc.
      - ```<board-name>/additional-docs/images/images-logos/```: All logos related to the board, manufacturer, seller etc go in this folder.
    - ```<board-name>/build/```: This folder contains all documentation related to compiling source code related to the board. These may include Kernel, OS, Bootlaoder etc.
    - ```<board-name>/downloads/```: Instructions to download various pieces of software go here. These may include Kernel, OS, Bootlaoder etc.
    - ```<board-name>/getting-started/```: This section should be considered as a "quick start guide" and the point-of-entry for new users.
    - ```<board-name>/guides/```: All the board specific guide NOT related to installation or building go here. These may include guides like: "How to use Camera", "Enable SPI", "Wifi Setup" etc.
    - ```<boards-name>/hardware-docs/```: All documentation relating to the Hardware on the board are hosted in this folder. Most of the documentation regarding the SoC and on-board peripheral need to be added to the ```hardware-user-manual.md``` file.
    - ```<boards-name>/installation/>```: Instructions to install various pieces of software go here. These may include Kernel, OS, Bootlaoder etc.
    - ```<boards-name>/support/>```: Any information relating to finding support for your board is placed here. This may include forum links and also links to other sections of this documentation.
- Copy you board folder under the right Edition category folder
  - [Consumer Edition(CE)](consumer) ```/consumer/<board-name>/```
  - [Enterprise Edition(EE)](enterprise) ```/enterprise/<board-name>/```
  - [Internet of Things Edition(IE)](iot) ```/iot/<board-name>/```
- Send in a Pull Request

**Things To Remember: Before sending the Pull request:**
- Make sure all the .md files have the headers in place, these headers make sure that the web page is properly generated and place at the correct location.
  - All the files in the template have the headers commented out like so:
    ```
    <!---
    ---
    title: Using the boardname
    permalink: /documentation/consumer/boardname/
    ---
    -->
    ```
  - Make sure to un-comment them like so:
    ```
    ---
    title: Using the boardname
    permalink: /documentation/consumer/boardname/
    ---
    ```
  - And modify them according to your board
- Make sure to place all the images in the ```assets/images``` folder with the correct resolution as mentioned in the template.
- If your board has its guides section populated, make sure to add the board to our [guides page](guides) ```/guides/README.md```
- Before submitting a Pull Request to the 96Boards repository, make sure to read and adhere to our guidelines mentioned in the [Guidelines for submitting a Pull Request](#guidelines-for-submitting-a-pull-request) section.
- Also take a look at our [Contribution Guide](https://www.youtube.com/playlist?list=PL-NF6S9MM_W1Lf714oYsSRIHT4bL_8P7e) play-list over at YouTube for short tutorials.

***

### Guidelines for submitting a Pull Request:
- **1: Make sure you sign-off your commit and pull request:** You can add it using the git command ```$ git commit -s .``` or manually add it to your commit and pull request ```Signed-off-by: NAME <committer-email>```
- **2: Start with a one-line summary (50 characters maximum), followed by a blank line. This format is used by git and Gerrit for various displays.**
- **3: Starting on the third line, enter a longer description:** This description should focus on what issue the change solves, and how it solves it. The second part is somewhat optional when implementing new features, though desirable.
- **4: Here is an example commit message:**
  ```
  short description on first line

  more detailed description of your patch,
  which is likely to take up multiple lines.
  ```
- **5: If you are new to git:** There are some excellent guide on the internet.
  - [Getting Started - Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
  - [https://guides.github.com/activities/hello-world/](https://guides.github.com/activities/hello-world/)


***

**For any additional questions/help, please visit us in IRC Channel: #96boards**
