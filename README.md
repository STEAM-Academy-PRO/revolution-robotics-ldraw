# LDrawResources
The repository stores all the LDraw & CAD resources for robot modelling

## Setup Bricklink Studio for build instruction creation
1. We use the **BrickLink LEGO Studio** for the build instructions. Download it here: https://www.bricklink.com/v3/studio/download.page
2. **Install & Start** the Studio app for the first time to initialise folders
    - *Note: At the very first start the app might crash, don’t worry about it. Just start it again.*
3. After the first successful start close Studio
4. Open the **“Custom parts”** location 
    - Windows: `%LOCALAPPDATA%\Stud.io\CustomParts`
    - Mac: Mac: `~/.local/share/Stud.io/CustomParts/`
    - *Note: Sometimes a fresh install comes without this folder and there's nothing to delete*
5. The Revolution Robotics custom models can be found in this repository: `/LDraw models`
6. **Symlink (best solution) or Copy (fallback solution)** the `parts` and `connectivity` folders to the CustomParts folder. See symlinking examples below
    - Windows: `%LOCALAPPDATA%\Stud.io\CustomParts`
    - Mac: `~/.local/share/Stud.io/CustomParts/`
7. **Symlink (best solution) or Copy (fallback solution)** the global `style file` to Studio
    - In this repository: `Studio setting/Instructions/CustomStyle/*`
    - Copy to its location on your machine:
        - Windows: `%LOCALAPPDATA%\Stud.io\Instructions/CustomStyle/*`
        - Mac: `~/.local/share/Stud.io/Instructions/CustomStyle/*`
8. In **Studio**
    - Custom Parts: from the dropdown on the left (by default set to Main), select Custom Parts
    - Global Style: Select it from the dropdown on the Page Design panel

## Build instruction creation & know-how
- [Notion link](https://www.notion.so/steamacademypro/Build-instructions-e2ea71c0967e452e86dd69178eddef85)

## All robot builds
- [Drive link](https://drive.google.com/drive/folders/1K5lteZ-coDv6EaQ5NzyZrNBuxguR_WlL)

## Symlinking examples
- In this MAC example I store this repository under `/Users/laszlobekessy/www/steamacademy/revolution-robotics-ldraw-resources`. This is the path you want to replace with yours. The custom parts are stored under ` /Users/laszlobekessy/.local/share/Stud.io/CustomParts/`
    - **Delete existing resources**: `rm -rf /Users/laszlobekessy/.local/share/Stud.io/CustomParts/ && rm -rf /Users/laszlobekessy/.local/share/Stud.io/Instruction/`
    - **Symlink for all items**: `ln -s /Users/laszlobekessy/www/steamacademy/revolution-robotics-ldraw-resources/Stud.io\ resources/* /Users/laszlobekessy/.local/share/Stud.io/`