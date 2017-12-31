# Advanced-Compute-Shader-TD
Pseuddo 3D music visualisation in TouchDesigner. 
Basic Principles: https://andrinrehmann.com/pseudo3d/
Watch previous version in action: https://www.youtube.com/watch?v=C2fMCBgaxlo

Issues:
As you can see in the video, the surfaces are only able to grow along the opposite direction of the coordinate axis but not with the axis. I found if they grow along the direction, they can only do so within the local group size of the compute shader. I have tried to adress this issue, but with no succes.

With my limited understanding of compute shaders and how exactly they are exectued in TouchDesigner, my best guess is:
Local Work groups are executed at the same time, meaning race conditions determine which pixels takes the longest to render. The three main structures of the program, the three if() statemts, will slow the execution of the pixel down by a great amount, meaning the calulcation takes the longest. The pixels they are writing to will not be overwritten within the local work group, as all other pixels are already written. The Lines and Structures can be drawn in the oposite direction of the coordinate system, because the shader will execute local work groups in the order of their coordinates. ( Work group [0,0], then [1,0] then [2,0] and so on.) If a line is written in the opposite direction of the coordinate space, it will later on be overwritten by another work group. 
The shader is always overwriting each pixel value, since there is a fade out effect. (See in the very first lines of the shader). I have tried to adress this issue by checking if the ouput pixel is brighter than the the input pixel at the current location, and only overwriting it, if the output pixel is darker. But with no success.

