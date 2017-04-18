# Unreal FootPrint Engine (Physiscs)

This Engine has been developed as a separate project in Unreal and then Migrated as a tool into the group project "Fission" as a mechanism to show 2D footprints as Players traverse different materials (Snow, Grass, Mud). More work/commits are present in the group project repos in order to optimize the engine for that project.
This project also contains a method to create 3D footprints on Snow or other granular material. This is present on a separate branch called "3D_Snow_FootPrint_Try". (Not included in the main project).

## Animation CallBacks

In order to detect the right moment and position to place the footprints I created some Notifies on some of the character's animations. These Notifies trigger events in the character's blueprint calling the FootPrints Engine.
On the Character's model 2 arrow components on the feet describe the correct orientation of the prints on the floor.

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/1_AnimBP.PNG "Screen 1")

## Materials, Surfaces, Textures

Three different materials (Snow, Grass, Wood) were created as basic textures and applied to user-defined surfaces and applied to 3 different terrains in the scene.
The footprint itself was created as a decal material with the properties seen in the picture below:

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/2_FootPrintMat.PNG "Screen 2")

## Character BluePrint and FootPrints Function

Upon receiving the trigger from the Animation Blueprint described before, the character blueprint calls on a custom-made function called "FootPrints" that detects the location, orientation and type of material the character is on and calls the respective custom-made mechanic function (SnowFootPrintMechanic, Grass, Wood).
These functions create the footprints based on the character's previous path while slowly fading the effect on the new material based on the previous material's proeprties. (E.G. white footprints on muddy area or grass area).
The pictures below show these mechanic for the snow material.
 

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/3_FootPrintEngine.PNG "Screen 3")

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/4_FootPrintsFunction.PNG "Screen 4")

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/5_FootPrintsMechanicCall.PNG "Screen 5")

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/6_FootPrintsMechanic.PNG "Screen 6")


The results are shown in the picture below. Perlin noise was added in the footprint rendering method to obtain a more unique and realistic effect for each footprint which are all different in result:

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/7_GamePlayPNG.PNG "Screen 7")

## 3D Footprints on Tesselated Material and Mesh Deformation

This part of the project was experimental and not included in the group project. It mainly involved the creation of a tesselated material for snow in order to imprint a 3D deformation and give the prints a more realistic look on soft/fluffy material like snow or loose sand.
The first step involved the modification of the snow material to create a tesselated version of it:

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/8_TesselatedSnow.PNG "Screen 8")

The FootPrints function was also modified to create 20 unique 3D footprints instances present at the same time on the material with different degrees of deformation. The material instance is now the modifed snow material composed of 2 different decals (Specular and opaque) both concurring to give the prints a 3D look.
The modified footprint function is shown below:


![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/9_FootPrintModified.PNG "Screen 9")

The results of this are shown below:

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/10_FootPrint3D1.PNG "Screen 10")

![alt text](https://github.com/eliodeberardinis/Elio_Physics_FootPrint/blob/master/Physiscs_Report_Pics/11_FootPrint3D2.PNG "Screen 11")

## Future work

Optimization of the 3D footprint with arrays and classes instead of 20 + 20 unique variables. Expand on materials. Add particle effect for snow flakes, loose sand or water splashes in mud. Improvement on the materials and lighting system to make footprints stand out more in both 2D and 3D versions.

## YouTube Video

https://youtu.be/9ETM32WaSBw
