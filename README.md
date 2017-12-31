# Advanced-Compute-Shader-TD
Pseuddo 3D music visualisation in TouchDesigner. 
Basic Principles: https://andrinrehmann.com/pseudo3d/
Watch previous version in action: https://www.youtube.com/watch?v=C2fMCBgaxlo

Issues:
There seems to be a problem with the structure of the shader. The shader can only draw lines and surfaces with the texture coordinate axises but not against them. I assume, if pixels are written against the direction of the axis, it will be drawn with other information in the same frame.
