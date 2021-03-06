# Debug Draw API for Unity

DbgDraw is an API that provides the ability to render various 2D and 3D shapes for visual debugging purposes. It's similar to Unity's [Gizmos](https://docs.unity3d.com/ScriptReference/Gizmos.html) and [Handles](https://docs.unity3d.com/ScriptReference/Handles.html) API's. Unity also provides a rather limited set of debug draw functions in the Debug class, such as [Debug.DrawLine](https://docs.unity3d.com/ScriptReference/Debug.DrawLine.html) for example.

Unlike Unity's Gizmo, which requires Gizmos rendering code to be located in a [OnDrawGizmos](https://docs.unity3d.com/ScriptReference/MonoBehaviour.OnDrawGizmos.html) method, you can issue DbgDraw calls from anywhere in your code. Rather than issuing these render calls immediately, DbgDraw collects those calls and defers the actual rendering to a later time. This allows to call DbgDraw from any method, be it Start(), Update() etc.

DbgDraw provides functionality to render the following shapes:
* Arc
* Cube
* Disc
* Line, Lines and PolyLine
* Matrix
* Plane
* Pyramid
* Quad
* Ray
* Sphere
* Tube

All of these shapes can be rendered solid and in wireframe.


# Example

```csharp
using Oddworm.Framework;

// Draw a wireframe cube for a single frame
DbgDraw.WireCube(position, rotation, scale, color); 

// Draw a solid cube for ten seconds
DbgDraw.Cube(position, rotation, scale, color, 10);
```
Please import the "DbgDraw Examples" file, which part of this package, for more examples.


# Limitations

* DbgDraw works with Unity 2018.3 and later versions.
* DbgDraw works in the Unity editor and [development mode](https://docs.unity3d.com/Manual/BuildSettings.html) builds. 
* DbgDraw works in play mode only.
* DbgDraw has been created for visual debugging purposes, not a fast general purpose shape rendering API.


# Installation

As of Unity 2019.3, Unity supports to add packages from git through the Package Manager window. In Unity's Package Manager, choose "Add package from git URL" and insert one of the Package URL's you can find below.

In earlier Unity versions, you should be able to download the repository and copy it to your projects 'Assets' directory.

## Package URL's

| Version  |     Link      |
|----------|:-------------:|
| 1.0.0 | https://github.com/pschraut/UnityDbgDraw.git#1.0.0 |



# FAQ

## It's not working in the editor

DbgDraw works in the editor only, if you tick the 'Development Build' checkbox in the Build Settings window (File > Build Settings).

## It's not working in a build

DbgDraw works in a build only, if you tick the 'Development Build' checkbox in the Build Settings window (File > Build Settings).

## Remove DbgDraw calls from release builds

If you untick the 'Development Build' checkbox in the Build Settings window (File > Build Settings), calls to DbgDraw are being removed by the compiler.

