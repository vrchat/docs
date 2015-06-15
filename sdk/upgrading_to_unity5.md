# Unity 4 to Unity 5
As of client 0.8.0, VRChat is now built with Unity 5 instead of Unity 4. This means **VRChat content built with Unity 4 may not be compatable with client version 0.8.x (or higher) and needs to be rebuilt with Unity 5**. We've allowed Unity 4 content in 0.8.x that doesn't crash the client, but those pieces of content still should be rebuilt in Unity 5 to make them look and work better. This applies to environments and avatars.

Upgrading your `Unity 4 VRChat project` to a `Unity 5 VRChat project` has two steps

* Upgrade the Unity project
* Add the new VRChat SDK

## Upgrade Project

Upgrading your Unity is almost completely automated by Unity. All you need to do is open your original project using Unity 5 and it should prompt you to let it upgrade your project. After the auto-upgrade is completed, your project should be updated without any errors. If your project does have errors, you'll have to manually go and make the appropriate changes for Unity 5.

**Note** You should create a backup of your project before upgrading. It's possible that the Unity 5 upgrade may break your project. 

**Note** If you are using custom DLLs, be sure to link to the Unity 5 version of the UnityEngine.dll in your Visual Studio project.

## Upgrade VRChat SDK

Download the latest SDK from [here](http://vrchat.net/download). Next, with your Unity 5 project open, double click the downloaded .unitypackage to import it (and override the old SDK) into your Unity 5 project.

## Build for Unity 5 VRChat
Once your project has been upgraded to Unity 5 and the newest VRChat SDK has been imported, you should be ready to build your VRChat assets. Export your upgraded asset and confirm it works in the latest VRChat [client](http://vrchat.net/download). 

Visit our [quickstart guide](http://vrchat.net/docs/sdk/quickstart/world#build-and-run) to see how to quickly build and run your VRChat assets. 