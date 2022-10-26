
# Interactive Switches

Interactive Switches is an Unreal Engine asset package that allows you to create and customize a lighting system using variety of lighting sources and meshes. The included Switch Plates and Switches are able to be operated independently and can be 'wired' to as many lights as needed, including varying component types, emulating that found in a real world room/environment.

https://www.unrealengine.com/marketplace/en-US/product/interactive-switches

---------------------
 * Technical Information
 * First Steps/Setup
 * How to Create a Compatible Light
 * How to Configure Your Light Switch
 * How to Use Your Light Switch

TECHNICAL INFORMATION
=====================
    Features:
        Fully Configurable and Customizable
        Imitate real-life light switch functionality
	    Interaction system with post-process outline functionality;
	    Includes two classic switch types, with each plate supporting up to 4 switches;
	    Each switch is capable of supporting multiple light actors and multiple light types;
	    Clean and Organized Blueprints with Functionality Comments:
	    Parent Blueprint for crafting additional environment lights;
	    Master Blueprints for Switch Plates and Independent Light Switches;
	    Example Blueprints of controllable environment lights;

    Components:
        Number of Blueprints: 8
        Number of Blueprint Interfaces: 1
        Number of Blueprint Game Modes: 1
        Number of Blueprint Characters: 1
        Number of Unique Meshes: 25
        Number of Materials and Material Instances: 27
        Number of Material Functions: 3
        Number of Textures: 55
        Texture Resolutions: 1024x1024 / 2048x2048

    Input: Keyboard, Mouse
    Supported Development Platforms: Windows, Mac


FIRST STEPS/SETUP
=================
- Blueprint functions required for Interaction/Object Outlines are contained within BP_FirstPerson_EXAMPLE

- you will need to copy and/or merge these to your own character when integrating with an existing project.

- **(Required)** In Project Settings, under Engine/Input, implement an 'action mapping' named "Use", this can be bound to any key of your choice.
 	
	![picture](http://img.retrohazard.com/qvkfjh.png)

- **(Required)** In Project Settings, under Engine/Collision, create a 'New Object Channel' named "Interactable" with 'Default Response' set to "Block"
	
	![picture](http://img.retrohazard.com/cwh1cz.png)

- **(Optional)** To Enable the Object Outline, in your Post Process Volume, attach the Post Process Material "MI_Outliner"
	
	![picture](http://img.retrohazard.com/hsjpfg.png)

HOW TO CREATE A COMPATIBLE LIGHT
================================
    Refer to the included example Light BPs if you are unsure of the setup process below.

1. Locate the BP_Light_Master Blueprint

![picture](https://img.retrohazard.com/ifnf64.png)

2. Right Click and choose 'Create Child Blueprint Class'

![picture](https://img.retrohazard.com/qc7xe2.png)

3. Add any necessary Static Meshes, Light Sources, Audio Components, etc. to your new blueprint. 

![picture](https://img.retrohazard.com/j2bf3m.png)        

	The names of these components do not matter as far as the light switch functionality is concerned

4. Switch to the Construction Script tab of your Blueprint.     

![picture](https://img.retrohazard.com/blsl22.png)   

	**(REQUIRED)** Ensure that the 'Parent: Construction Script' node is present. If this node is not implemented, your lights will not automatically be tagged.

5. Make any desired changes to the Construction Script FOLLOWING the execution pin from the 'Parent: Construction Script'

![picture](https://img.retrohazard.com/cy9wzy.png) 

6. Switch to the Event Graph tab of your Blueprint.

![picture](https://img.retrohazard.com/brke90.png)

	**(OPTIONAL)** If your light requires changes to be made when the light changes states, such as materials or sounds, you can implement the Event "UpdateOnStateChange" and customize as needed.

![picture](http://img.retrohazard.com/wvj5ah.png)

HOW TO CONFIGURE YOUR LIGHT SWITCH
==================================
1. Place your new light actor within your level.

![picture](https://img.retrohazard.com/sarvyh.png)

2. (Optional) Set Light Status

![picture](https://img.retrohazard.com/tqtdcl.png)

3. Add a light switch to your level by placing the BP_SwitchPanel actor in your scene.

![picture](https://img.retrohazard.com/88q1o3.png)

![picture](https://img.retrohazard.com/i12gwc.png)

4. Configure your Switch Settings

![picture](https://img.retrohazard.com/wx7ycr.png)

Choose the number of switches required and style/type.


![picture](https://img.retrohazard.com/v8fe5y.png)

Add Element(s) to the assignment variable.


![picture](https://img.retrohazard.com/bq9ngs.png)

Pick a Light Actor from your scene and assign the switch number (0 - 3)

![picture](https://img.retrohazard.com/3ic1dm.png)


		    Multiple light actors can be attached to a single light switch, however... 
		    NOTE: In order to attach a light actor to this asset, it MUST be a Child Blueprint Class of BP_Light_Master.

![picture](https://img.retrohazard.com/yb17qy.png)
	
	
HOW TO USE YOUR LIGHT SWITCH
============================
1. Play your level in the selected Viewport (or PIE window), aim at a light switch, and use the key which you bound earlier to your "Use" action mapping.
    
    If you've configured everything correctly, the switch should highlight/outline (if Post Process Materials were enabled), and when interacting, the switch and associated light(s) should toggle between an ON/OFF state, as well as execute any additional code you implemented in your Child classes.

![picture](https://img.retrohazard.com/akoabf.png)

![picture](https://img.retrohazard.com/reuu31.png)
