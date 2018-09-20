# Ue4 plugin: Dedicated server house Blueprint
Documentation

## H2 Index:

1. [Project structure](#project_structure)
2. Create new house
3. Create new door or window
4. Customize house
5. Edit Tool




## Project Structure

There are 2 master blueprints, one is called <b>BP_house_root</b> and the other one <b>BP_obj_90deg</b>.<br>
The first one concerns the house itself, the other one is about components: windows or doors, all the others are children.<br>
To create a child you should right click on the master one and select "create child".<br>
<br>
![alt text](https://drive.google.com/thumbnail?id=19B7zSKrf7NQVDHbXGgHtLu6KD50QD0RG&sz=w640-h480)

![alt text](https://drive.google.com/thumbnail?id=18yqtLrhVbAGugGUejYjIduE-fsRo5bry&sz=w640-h480)
<br><br>
## Create new house
Once you have created a child from BP_house_root you should set the main mesh: in the construction script, after the "parent construction script" there is a function called "Exposed Construction" with a mesh parameter.

## Create new door or window
For this you can duplicate the existing door/window bp and change the mesh and the initial parameters (rotation, location etc), or you can create a new one from the parent, then override the "Server Request Open" event and customize it as you please.

## Customize house
After you set up the main mesh, you can add as many objects as you want, if you need more doors and windows just drag and drop the door/window blueprint into the house one, then adjust position etc.

## Edit Tool
If you want some variety of colors (for example, changing the roof's color or the door's color) you can do it in the scene by adjusting some parameters: by clicking the boolean "Use Tint?" you enable the customization. You can select a color then you can apply it to a part of the mesh (by using a texture as mask).
If you want to change the color of the tower roof, or the one of the tower's door etc, you can add the mask and the selected color into the array as you can see in this screenshots.
<br><br>
![alt text](https://drive.google.com/thumbnail?id=12JXszIC9HM6Yxt8dk1-ba5y1-s7_5SDs&sz=w1920-h1080)
![alt text](https://drive.google.com/thumbnail?id=1UkGenDdPULGTUH1LE46GCaUvCQO2eFgf&sz=w1920-h1080)
<br><br>
NB remeber to add it to the blueprint too!
<br>
![alt text](https://drive.google.com/thumbnail?id=1ZiZF8rcIpR8ty5O3uGZyy1UblY7Ihlex&sz=w1920-h1080)



## Notes
In order to build the server and test it as standalone you need two additional maps:

1- <b>Default Client level (that point at the server ip)<b>
2- <b>Transition level (loading)<b>


I added both in first version but the Ue4 Marketplace staff asked me to remove them because the [Open Level] function pointing at 127.0.0.1 was not working without a server.

