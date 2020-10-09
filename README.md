# UV Viewer for Unity Editor (English translation by DancingPhoenix88)
UVViewer visualizes unwrapped UV map in Unity 5.4+.

![](Screenshot.png)

## Installation
You could use [this .unitypackage](https://github.com/songkyoo/UVViewer/releases) or clone this project and copy UVViewer plugin assets in folder [Assets/Plugins](Assets/Plugins) to your project.
When installed, you could open the UV Viewer Window from the menu bar Window > UV Viewer.

## Usage
### Mesh
Just select a mesh, and it's UV will be displayed in the UV Viewer Window. If the selected object has a MeshFilter component, the mesh will be recognized too.
In the UV Viewer window, there are settings for Mesh too. If you change the Mesh loading mode from `Selected Object` to `Custom`, you could load a specific mesh.

Mesh 항목을 Custom으로 설정하면 메시를 직접 설정할 수 있습니다. 오브젝트를 뷰 영역으로 드래그 앤 드롭해도 동일한 동작을 수행합니다. 드래그 가능한 오브젝트는 메시 혹은 MeshFilter, SkinnedMeshRenderer 컴포넌트를 포함하는 게임 오브젝트입니다.

### Texture
Default texture mode is `None`.
If you change to `Custom`, you could load any texture and draw it below the UV map.

### Dynamic mesh and texture settings
You could set custom mesh and texture from Editor script as well:

```csharp
using Macaron.UVViewer.Editor;

class EditorClass
{
    void SetCustom(Mesh mesh, Texture texture)
    {
        UVViewerWindow.ShowWindow().SetCustomMesh(mesh);
        UVViewerWindow.ShowWindow().SetCustomTexture(texture);
    }
}
```


## Notes
1. The UV, mesh and texture is loaded once. If you change something outside of the UV Viewer Window, you'll need to click the button `Reload` to reflect the changes.

2. For machines which Geometry shader is unsupported, `Line Thickness` and other options are disabled.
