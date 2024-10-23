# Revolution Robotics LDraw
The repository stores all the LDraw & CAD resources for robot modelling in Stud.io

# Disclaimer
There's now two versions from the Revolution Robotics Challenge kit.
- **Version 1**: from 2018 to 2024-06 (`white` Brain with `red` motors and `white, blue and yellow` plastic parts)
- **Version 2**: from 2024-06 (`dark gray` Brain with `purple` motors and `gray, purple, green and yellow` plastic parts)

Because of the colour change, the Stud.io resources needed to be separated as well. folder BUT `setting up your machine is also different`. Simply put, Stud.io is serving our need but is not a great software (*this is a common strong opinion by the team*). For the gray Brain we needed to change core application files instead of the user-specific ones, because the very same code works in the core and doesn't work in the user lib. Bummer!

Use the parts fitting your model version and don't forget to change the setup if you need to fall back to older models.

# Version 2 (latest): from 2024-06
## Setup Bricklink Stud.io for build instruction creation
1. We use **BrickLink LEGO Studio** for the build instructions. Download it here: https://www.bricklink.com/v3/studio/download.page
2. **Install & Start** the Studio app for the first time to initialise folders
3. After the first successful start close Studio
4. Locate the **core application folder**
    - Mac: `/Applications/Studio 2.0/`
    - Win: `C:\Program Files\Studio 2.0\`
5. You need to **define the kit colors** for the instruction maker. 
    - Locate the `StudioColorDefinition.txt`
        - Mac: `/Applications/Studio 2.0/data`
        - Win: `C:\Program Files\Studio 2.0\data`
            - *TIP*: use VSCode for editing, when saving, it auto suggests Save as Admin when saving failed due to permissions
    - Create a backup from the file (e.g.: `StudioColorDefinition-orig.txt`)
    - Add these lines to the end OR symlink the file provided from this repository.
```txt
3000	3000	3000	3000	RR V2 Gray	RR V2 Gray	RR V2 Gray	RR V2 Gray	#253746	1	Solid Colors	1	o		47,21,0,73	Revolution Robotics
3001	3001	3001	3001	RR V2 Yellow	RR V2 Yellow	RR V2 Yellow	RR V2 Yellow	#FFD700	1	Solid Colors	1	o		0,16,100,0	Revolution Robotics
3002	3002	3002	3002	RR V2 Green	RR V2 Green	RR V2 Green	RR V2 Green	#44D62C	1	Solid Colors	1	o		68,0,79,16	Revolution Robotics
3003	3003	3003	3003	RR V2 Purple	RR V2 Purple	RR V2 Purple	RR V2 Purple	#5F259F	1	Solid Colors	1	o		40,77,0,38	Revolution Robotics
```

6. You need to define the same colours for eyesight to be able to create the renders from the instruction maker. 
    - Locate the `settings_v1.xml`
        - Mac: `/Applications/Studio 2.0/PhotoRealisticRenderer/mac/`
        - Win: `C:\Program Files\Studio 2.0\PhotoRealisticRenderer\win\64\`
    - Create a backup from the file (e.g.: `settings_v1-orig.xml`)
    - Add these lines BEFORE the Solid-WHITE section OR symlink the file provided file from this repository.
```xml
<!-- REVOLUTION ROBOTICS SOLID COLORS -->
  <material displacement_method="bump" heterogeneous_volume="False" name="SOLID-RR_V2_GRAY" use_local_tuning="False" use_mis="True" use_transparent_shadow="True" volume_interpolation_method="linear" volume_sampling_method="multiple_importance">
    <shader>
      <group group_name="SOLID-GROUP" name="SOLID-GROUP">
        <input name="BaseColor" type="color" />
        <input name="SubsurfaceColor" type="color" />
        <output name="Shader" type="closure" />
      </group>
      <!-- This would be the RGB for #253746 BUT on render colours are more washed out, so we increase the saturation/brightness manually -->
      <!-- <color name="RGB" value="0.1450980392 0.2156862745 0.2745098039" /> -->
      <!-- This is the RGB value for #141E27 -->
      <color name="RGB" value="0.078 0.118 0.153" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="BaseColor" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="SubsurfaceColor" />
      <connect from_node="SOLID-GROUP" from_socket="Shader" to_node="Output" to_socket="Surface" />
    </shader>
  </material>
  <material displacement_method="bump" heterogeneous_volume="False" name="SOLID-RR_V2_YELLOW" use_local_tuning="False" use_mis="True" use_transparent_shadow="True" volume_interpolation_method="linear" volume_sampling_method="multiple_importance">
    <shader>
      <group group_name="SOLID-GROUP" name="SOLID-GROUP">
        <input name="BaseColor" type="color" />
        <input name="SubsurfaceColor" type="color" />
        <output name="Shader" type="closure" />
      </group>
      <!-- Yellow is kept untouched at #253746 -->
      <color name="RGB" value="1.0 0.8431372549 0.0" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="BaseColor" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="SubsurfaceColor" />
      <connect from_node="SOLID-GROUP" from_socket="Shader" to_node="Output" to_socket="Surface" />
    </shader>
  </material>
  <material displacement_method="bump" heterogeneous_volume="False" name="SOLID-RR_V2_GREEN" use_local_tuning="False" use_mis="True" use_transparent_shadow="True" volume_interpolation_method="linear" volume_sampling_method="multiple_importance">
    <shader>
      <group group_name="SOLID-GROUP" name="SOLID-GROUP">
        <input name="BaseColor" type="color" />
        <input name="SubsurfaceColor" type="color" />
        <output name="Shader" type="closure" />
      </group>
      <!-- This would be the RGB for #44D62C BUT on render colours are more washed out, so we increase the saturation/brightness manually -->
      <!-- <color name="RGB" value="0.2666666667 0.8392156863 0.1725490196" /> -->
      <!-- This is the RGB value for #3CC326 -->
      <color name="RGB" value="0.235 0.765 0.149" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="BaseColor" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="SubsurfaceColor" />
      <connect from_node="SOLID-GROUP" from_socket="Shader" to_node="Output" to_socket="Surface" />
    </shader>
  </material>
  <material displacement_method="bump" heterogeneous_volume="False" name="SOLID-RR_V2_PURPLE" use_local_tuning="False" use_mis="True" use_transparent_shadow="True" volume_interpolation_method="linear" volume_sampling_method="multiple_importance">
    <shader>
      <group group_name="SOLID-GROUP" name="SOLID-GROUP">
        <input name="BaseColor" type="color" />
        <input name="SubsurfaceColor" type="color" />
        <output name="Shader" type="closure" />
      </group>
      <!-- This would be the RGB for #5F259F BUT on render colours are more washed out, so we increase the saturation/brightness manually -->
      <!-- <color name="RGB" value="0.3725490196 0.1450980392 0.6235294118" /> -->
      <!-- This is the RGB value for #341458 -->
      <color name="RGB" value="0.204 0.078 0.345" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="BaseColor" />
      <connect from_node="RGB" from_socket="Color" to_node="SOLID-GROUP" to_socket="SubsurfaceColor" />
      <connect from_node="SOLID-GROUP" from_socket="Shader" to_node="Output" to_socket="Surface" />
    </shader>
  </material>
  <!-- /REVOLUTION ROBOTICS SOLID COLORS -->
```

7. Add the Stud.io **User data** to its place
    - Locate the `User data folder`
        - Mac: `~/.local/share/Stud.io/`
        - Win: `%LOCALAPPDATA%\Stud.io\`
    - Symlink or Copy the content of **Stud.io-user-resources**

See full setup example commands below

## Full setup examples
### Mac
- In this MAC example I store this repository under `/Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw`
1. Core application files
    - **Make backups**: 
        - `mv /Applications/Studio\ 2.0/data/StudioColorDefinition.txt /Applications/Studio\ 2.0/data/StudioColorDefinition-orig.txt`
        - `mv /Applications/Studio\ 2.0/PhotoRealisticRenderer/mac/settings_v1.xml /Applications/Studio\ 2.0/PhotoRealisticRenderer/mac/settings_v1-orig.xml`
    - **Symlink**
        - `ln -s /Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw/Stud.io-core-resources/mac/data/* /Applications/Studio\ 2.0/data/`
        - `ln -s /Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw/Stud.io-core-resources/mac/PhotoRealisticRenderer/mac/* /Applications/Studio\ 2.0/PhotoRealisticRenderer/mac/`
2. User specific files
    - **Delete existing resources**: `rm -rf /Users/laszlobekessy/.local/share/Stud.io/CustomParts/ && rm -rf /Users/laszlobekessy/.local/share/Stud.io/Instruction/`
    - **Symlink for all items**: `ln -s /Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw/Stud.io-user-resources/* /Users/laszlobekessy/.local/share/Stud.io/`



# Version 1: from 2018 to 2024-06
## Setup Bricklink Stud.io for build instruction creation
1. We use **BrickLink LEGO Studio** for the build instructions. Download it here: https://www.bricklink.com/v3/studio/download.page
2. **Install & Start** the Studio app for the first time to initialise folders
3. After the first successful start close Studio
4. Add the Stud.io **User data** to its place
    - Locate the `User data folder`
        - Mac: `~/.local/share/Stud.io/`
        - Win: `%LOCALAPPDATA%\Stud.io\`
    - Symlink or Copy the content of **Stud.io-user-resources**

See full setup example commands below

## Full setup examples
### Mac
- In this MAC example I store this repository under `/Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw`
    - **Delete existing resources**: `rm -rf /Users/laszlobekessy/.local/share/Stud.io/CustomParts/ && rm -rf /Users/laszlobekessy/.local/share/Stud.io/Instruction/ && rm -rf /Users/laszlobekessy/.local/share/Stud.io/CustomColors/`
    - **Symlink for all items**: `ln -s /Users/laszlobekessy/Dev/steamacademy/revolution-robotics-ldraw/Stud.io-user-resources/v1-from-2018-to-2024-06/* /Users/laszlobekessy/.local/share/Stud.io/`

---

Notes:

Inside `Stud.io-user-resources` there is a `Bucket/Folders` folder, and it contains the lists for both our Revolution Robotics Part collection and their respective counts, I also put here our LEGO Spike Prime and Spike Essential kits, so all assets used by STEAM academy is in one place.

Studio's format for parts collection is not documented anywhere however it's pretty straight forward from looking at an example:

Header:
```txt
~*RR_v2    <- name of the list
17         <- have no clue
-1         <- always -1 for some reason
```

From there tuples indexed 0, 1, 2, 4 piece description follows
```txt
0 67351c01.dat             <- filename (this is a LEGO)
1 Electric Powered HUB     <- description
2 15                       <- color index
4 1                        <- number of pieces in set
0 ct2x2.dat                         <- filename (this is RR)
1 Connector Tangential with Pins    <- description
2 3001                              <- our special colors!
4 12                                <- number of pieces in set
...
```
