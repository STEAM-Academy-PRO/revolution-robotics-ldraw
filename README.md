# Revolution Robotics LDraw
The repository stores all the LDraw & CAD resources for robot modelling in Stud.io

## Setup Bricklink Stud.io for build instruction creation
1. We use **BrickLink LEGO Studio** for the build instructions. Download it here: https://www.bricklink.com/v3/studio/download.page
2. **Install & Start** the Studio app for the first time to initialise folders
    - *Note: At the very first start the app might crash, don’t worry about it. Just start it again.*
3. After the first successful start close Studio
4. Open the **Stud.io App data** location and check if exists
    - Windows: `%LOCALAPPDATA%\Stud.io\`
    - Mac: Mac: `~/.local/share/Stud.io/`
5. **Symlink (best solution) or Copy (fallback solution)** the **Stud.io App data folder** to
    - Windows: `%LOCALAPPDATA%\Stud.io\CustomParts`
    - Mac: `~/.local/share/Stud.io/CustomParts/`
    - See [full command examples below](#symlinking-examples)
6. In **Studio**
    - Custom Parts: from the dropdown on the left (by default set to Main), select Custom Parts
    - Global Style: Select it from the dropdown on the Page Design panel

## Build instruction creation & know-how
- [Notion link](https://www.notion.so/steamacademypro/Build-instructions-e2ea71c0967e452e86dd69178eddef85)

## All robot builds
- [Drive link](https://drive.google.com/drive/folders/1K5lteZ-coDv6EaQ5NzyZrNBuxguR_WlL)

## Symlinking examples
- In this MAC example I store this repository under `/Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw`. This is the path you want to replace with yours. The Stud.io app data is stored under `/Users/laszlobekessy/.local/share/Stud.io/`
    - **Delete existing resources**: `rm -rf /Users/laszlobekessy/.local/share/Stud.io/CustomParts/ && rm -rf /Users/laszlobekessy/.local/share/Stud.io/Instruction/ && rm -rf /Users/laszlobekessy/.local/share/Stud.io/CustomColors/`
    - **Symlink for all items**: `ln -s /Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw/Stud.io\ resources/* /Users/laszlobekessy/.local/share/Stud.io/`
    - If you want to use a different version of the kit, just symlink the coddect folder, e.g.: `v1-from-2018-to-2024-06`