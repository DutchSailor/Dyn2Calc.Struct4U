# Dyn2Calc.Xframe3d
Library for interoperability between Autodesk Revit,Dynamo and Xframe3d

Export a Revit-model to XFrame3d
Import a Revit-model from XFrame3d

https://www.struct4u.com/xframe3d/?lang=en 

![Image](Dyn2CalcXframe3DImage.png)

## Version
0.0.1 alpha released on 21-03-2020. Work in progress

## Installation
Installation will be possible via the dynamo built-in package manager.

## Dynamo, Revit-version
The current nodes are tested with Revit 2020.2 and Dynamo 2.x
It had not been tested with older or newer versions of Revit and Dynamo.

## Material on this repository
-Directory supportfiles contains files with families to use with the nodes and example files.
-Directory nodes contains the versions of the package and the actual nodes


## Status

### Revit to Xframe3D

#### Implemented
* Project information
* Nodes, beams, columns, braces
* Grids X,Y,Z
* Recognition of steelsections with 4 different type of nameconventions.
* Recognition of rectangle concrete sections and wood sections

#### To be implemented
* Plates
* Rebar
* Buildup Sections
* Non rectangular concrete and wood sections
* Materials
* Supports
* Intelligent analytical node merging within a certain distance
* Steelconections
* Recognize section location(top, middle, bottom)

### Xframe3D to Revit

#### Implemented
* Grids X Y Z
* Nodes, beams, columns, braces
* All XML-information as lists in Dynamonodes
* Example of place piles based on support location

#### To be implemented:
* Plates
* Rebar
* Recognition of section and load family into project
* Buildup Sections
* Non rectangular concrete and wood sections
* Materials
* Intelligent analytical node merging
* Steelconections


## Recognition of sections

### Steel
They are based on a mapping table with 4 kind of sectionnames. The node looks to the typename of the Structural Column of Structural Framing and will try to match this with a Xframe Steelsection. If there is none the profile will be a HEM1000.

### Wood
The dynamonode will look to a typename starting with a Abbrevation. By Example 'HB'. Within the family the 'Section Shape'-parameter should be used. The standard parameters 'Width' and 'Height' will be used to extract the width and the height of the section.

### Concrete
Same story as wood



