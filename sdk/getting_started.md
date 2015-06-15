# Getting Started
## Requirements
To visit and use virtual worlds and avatars that others have created, you need

* the [VRChat Client](http://vrchat.net/download)

If you want to build your own virtual worlds and avatars, you need

* the [VRChat Client](http://vrchat.net/download)
* the [VRChat Unity SDK](http://vrchat.net/download)
* the latest [Unity 5](http://unity3d.com/get-unity) (Personal or Professional)

## Setup a VRChat Project
Every piece of content built for VRChat will start with a VRChat Unity Project.
To create an empty VRChat project, you need to 

* Create a new Unity 5 project
* Import the latest [VRChat Unity SDK](http://vrchat.net/download)

You now have the base project for creating a virtual avatar or world.

## Create a Simple Avatar
At the core of avatar creation is a script called `VRC_AvatarDescriptor`. Every custom avatar has one of these scripts on the root game object of the avatar. It has a few properties you can tweak, but the default values are enough to build a simple avatar.

<img src="{{ asset('images/avatar_descriptor.png') }}" alt="VRChat SDK Menu" style="width:30%">

** To create a simple avatar **

* Setup a new VRChat project (see above section on setting up a VRChat Project)
* Import your rigged avatar model (non-rigged work too but won't animate)
	* For learning purposes, here's a free rigged [avatar](https://www.assetstore.unity3d.com/en/#!/content/4696).
*  Drag the `avatar prefab` into your Unity scene
*  Add a `VRC_AvatarDescriptor` onto the root of the avatar game object
	* ** Note: There are two version of each SDK script. Always use the DLL (not the c#) versions. **  
*  Export and test

See the [quickstart for avatars](http:vrchat.net/docs/sdk/quickstart/avatar) to create your first avatar.

See aVRname's [Avatar Tutorial](http://54.68.196.193/codoforum/index.php?u=/topic/38/tutorial-beginner-create-a-custom-avatar) on the forums.

## Create a Simple World
At the core of world creation is a script called `VRC_SceneDescriptor`. Every custom world has one of these scripts on the root game object of the world. It has a few properties you can tweak, but the only ones that are required for a custom world is the `Spawns` property. This property is an array of spawn points in your world. At minimum, you need to set the `Spawns` `Size` to 1 and drag a spawn transform onto the space created for the spawn.

<img src="{{ asset('images/scene_descriptor.png') }}" alt="VRChat SDK Menu" style="width:30%">

** To create a simple world **

* Setup a new VRChat project (see above section on setting up a VRChat Project)
* Build a simple Unity scene with at minimum
	* A floor with a collider
	* An empty `gameObject` to act as a spawn point
	* Do NOT include any cameras in your scene
* Create a root game object to act as the parent game object of all other game objects in your scene. 
* Add a `VRC_SceneDescriptor` onto the root game object
	* ** Note: There are two version of each SDK script. Always use the DLL (not the c#) versions. ** 
* Click on the `Spawns` property on the `VRC_SceneDescriptor` and set `Size` to 1
* Drag your spawn `gameObject` into the space provided in the `Spawns` property.
* Export and test


See the [quickstart for worlds](http://vrchat.net/docs/sdk/quickstart/world).

See the simple world youtube [tutorial](https://www.youtube.com/watch?v=vTsWj0hA6g0).

## Export Content
To test or use your custom avatar or world, you'll need to export it from your VRChat Unity project. This can be achieved by

* Selecting the root game object in the hierarchy
* Click the appropriate build option from the from the VRChat Unity menu

<img src="{{ asset('images/vrchat_build_menu.png') }}" alt="VRChat SDK Menu" style="width:30%">

### Avatars

* `Build Custom Avatar from Selection` creates a `.vrca` file which can then be imported into VRChat using the steps in the *Using Content* section. 

### Worlds
There are two options for exporting your VRChat worlds from Unity, 

* `Build Custom Scene from Selection` creates a `.vrcs` file which can then be imported into VRChat using the steps in the *Using Content* section. 

* `Build and Run Scene from Selection` - creates a `.vrcs` file and launches the VRChat client directly into that room. This is ideal for testing your room while developing.

## Importing Content
To use your custom content in VRChat, your .vrc (content) files must be hosted somewhere and then imported into VRChat.

### Hosting 
You can host your .vrc files either locally (on your local computer) or remotely (ie. web server, google drive, any web-accessable place). 

* Local content files can only be accessed by you. This is good for testing. 
* Remote content files can be accessed by anybody (assuming you've opened your world to the public).

**Note: In order for everybody else to use your content, it must be uploaded to a web-accessible place.**

### Avatars
* Launch the VRChat client
* Click the `Name/Avatar` button
* Click the `avatar` dropdown and select `custom`
* Enter the local (or remote) url of your avatar
	* local - file:///C:/Users/MyName/myAvatar.vrca
	* remote - http://mywebsite.com/myAvatar.vrca
* Click `Save`

Also see our importing avatars [quickstart](http://vrchat.net/docs/sdk/quickstart/avatar#import-avatar).


### Worlds
* Launch the VRChat client
* Click the `Create a Room` button
* Click on the `Level Name` dropdown and select `Custom`
* Enter the local (or remote) url of your world
	* local - file:///C:/Users/MyName/myWorld.vrcs
	* remote - http://mywebsite.com/myWorld.vrcs
* Click `Hide Room` if you don't want your room to appear on the room list
* Click `Persistent` if you don't want your room to dissapear from the room list after everybody has left your room
* Click `Create Room`


