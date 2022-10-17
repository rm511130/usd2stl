# usd2stl
- (Headless) Blender Python Script for converting a [USD file](https://graphics.pixar.com/usd/release/usdfaq.html) into STL format
- Proof of Concept Code by rmeira@physna.com
- 10/14/2022

## Combined purposes:
   1. Convert a single USD file into STL
   2. Convert all subcomponents of a USD file into STLs

## Requires: 
   - [Blender 3.3 or later](https://www.blender.org/download/)
   - Code will be executed as headless / background service
   - Windows OS (MacOS will follow soon)

## Command Syntax:

```
blender.exe -b -P usd2stl.py -- -i <sample.usd> -o output <output-directory> -s <single.stl>
```

- The <sample.usd> file is typically made up of many objects with 3D meshes. 
- The usd2stl.py script will:
     - typically output one STL per object found in the <sample.usd> file. 
     - append .stl to the object names it finds in the <sample.usd> file. 
     - also export the union of all the .stl files as a <single.stl> file.
- The <sample.usd> and <single.stl> placeholders correspond to file-path and file-name.
- The <output-directory> placeholder corresponds to a file-path of an existing directory.
 
## How to execute:

### PowerShell Example:

```
C:> cd "C:\Program Files\Blender Foundation\Blender 3.3"
C:\Program Files\Blender Foundation\Blender 3.3> .\blender.exe -b -P "C:\Users\Ralph\Python\usd2stl.py" -- -i "C:\\Users\\Ralph\\3D Objects\\Human Pixar Woman\\HumanFemale.usd" -o "C:\\Users\\Ralph\\3D Objects\\Human Pixar Woman\\output" -s "C:\\Users\\Ralph\\3D Objects\\Human Pixar Woman\\HumanFemale.stl"
```
### Where:
```
-b = background or headless

-P = Python

Python Script = "C:\Users\Ralph\Python\usd2stl.py" 

-- = subsequent parameters are inputs for the Python code

-i = input USD file name and location
     Example of USD file name and location = "C:\\Users\\Ralph\\3D Objects\\Human Pixar Woman\\HumanFemale.usd" 

-o = output directory where all USD subcomponents will be saved as STL files
     Example of output directory: "C:\\Users\\Ralph\\3D Objects\\Human Pixar Woman\\output" 

-s = file name and location of single STL file conversion from USD file
     Example of Single STL file name and location: "C:\\Users\\Ralph\\3D Objects\\Human Pixar Woman\\HumanFemale.stl"
```

### Notes:
       - Directories referred to in "-i", "-o" and "-s" must already exist
       - Note the need for double backslashes when passing parameters to the Python code
 
## The output on the PowerShell Console will look something like this:

```       
Blender 3.3.1 (hash b292cfe5a936 built 2022-10-05 00:49:25)
Read prefs: C:\Users\Ralph\AppData\Roaming\Blender Foundation\Blender\3.3\config\userpref.blend
USD import of 'C:\Users\Ralph\3D Objects\Human Pixar Woman\HumanFemale.usd' took 53.7 ms
Blender quit
```

# Step-by-Step Tutorial _(work in progress)_

This tutorial will show you how to use this tool to convert a USD file into STL format

### 1. Download examples of USD files from: https://graphics.pixar.com/usd/release/dl_downloads.html#assets

![](./images//Pixars_USD_Kitchen.gif)

In the example above, `kitchen_set.zip` is being downloaded to my `C:\Users\Ralph\Downloads` directory.

### 2. Unzip the contents of the `Kitchen_set.zip` file and place them in a directory of your choosing:

When openning the `Kitchen_set.zip` file, you will see a directory structure that looks like this:

![](./images//KitchenUnzipped.png)

Take these files and place them in a directory of your choosing. In this tutorial we will place the files under `C:\Users\Ralph\3D Objects\Kitchen from Pixar`





