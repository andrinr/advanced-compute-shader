# Advanced-Compute-Shader-TD
Pseuddo 3D music visualisation in TouchDesigner. 
Basic Principles: https://andrinrehmann.com/pseudo3d/
Watch previous version in action: https://www.youtube.com/watch?v=C2fMCBgaxlo

Issues:
As you can see in the video, the surfaces are only able to grow along the opposite direction of the coordinate axis but not with the axis. I found if they grow along the direction, they can only do so within the local group size of the compute shader. I have tried to adress this issue, but with no succes.
