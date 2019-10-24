**Note**
This is a simple script that was part of a pipeline tool. The only purpose was to extract metadata/data from dds textures for assembly into an engine specific format.

# dds_loader
Python 3.5+ DDS loader module

Minimal DDS loader Python module aimed at offline tools.

Textures need to be :
- Squared power of two
- DX10 extended header has to be present ( -dx10 switch in texconv/texassembler )

Supports:
- Texture2D
- Texture2DArray
- TextureCube
- TextureCubeArray

What it does:
- Texture information
- List of surfaces with width/height/pitch/size ready to use
- Array of already layed out ( not modified ) texture data ready to load or embed in other custom formats
- Performs some validation checks on the file to assure some consinstency

How to use:
```python
from dds_loader import DDSTexture

dds_texture = DDSTexture()
dds_texture.load(filename)

for surface in dds_texture.surfaces:
  print(surface)
```
