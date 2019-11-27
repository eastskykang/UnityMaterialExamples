# UnityMaterialExamples

Unity material examples created with texture images from
- https://cc0textures.com/
- https://freepbr.com/ 

## Installation

### Downloading

You can download materials and textures from [Release tab](https://github.com/eastskykang/UnityMaterialExamples/releases).
Download Resources.tar.xz file and extract it to your Unity project Asset directory.

### Cloning project

1. Clone this repository with git and [git-lfs](https://git-lfs.github.com/): we use git-lfs for large files such as materials, meshes, texture images etc.
    ```sh
    $ git clone https://github.com/eastskykang/RaiSimUnity.git
    ```
2. Once you cloned source code, get lfs files by 
    ```sh
    $ git lfs pull origin
    ```
    You should see texture JPEG files properly from ```Assets/Resources/texture/cc0/```. 

## How to create Unity material from texture images?

### Prerequisite 

- Unity Editor
- Texture images 
- [Gimp](https://www.gimp.org/) or Photoshop (optional)

### Steps

1. Download texture files from web sources.
2. Create a material from Unity Editor 
    - If the material is transparent, set rendering mode to ```Transparent``` instead of ```Opaque```.
3. Add textures to the ```material/Main Maps``` in Unity Editor
    - Ambient occlusion map file (e.g. AO.jpg) to ```Occlusion```.
    - Albedo map file (e.g. col.jpg) to ```Albedo```.
    - Normal map file (e.g. normal.jpg) to ```Normal Map```.
    - Height map file (e.g. disp.jpg) to ```Height Map```.
4. Setting Roughness and Metallic of material is a bit tricky. 
    - Unity uses alpha channel of either Metallic map file or Albedo map file as a ```Smoothness```. Here, we use Metallic map alpha channel as smoothness.
    - Note that ```Smoothness``` is an inverse of Roughness. You need to inverse roughness map file (e.g. rgh.jpg) by image editing tools (e.g. gimp or Photoshop etc.)
    - In the image editing tool, add inversed roughness map to metallic map file (met.jpg) as a alpha channel: see [this](https://graphicdesign.stackexchange.com/questions/8397/gimp-using-an-image-as-the-transparency-layer-of-another-image) for gimp.
    - Save new image as a png file.
    - Add image to ```Metallic```.
