#Part 1 Sin Wave
* Using Color_High to set the color of the highest point.  
* Using Color_Low to set the color of the lowest point.  
* Using Frequency to set the vibration speed.  
* Using Height to set the height of the highest point.  
* Using Div to set different vibration mode.  
The center point of the grid will vibrate following a cos function. The surrounding points also vibrate following the cos function, 
however there is time offset and the height decreases as the distance to the center point increases.
![wave](result/wave.bmp)

#Part 2 Globe  

Basic fatures:  
* Rim Light
* Specular on water
* Bump mapping  
  
  
Extra fatures:  
* Clouds shadow
* Height shade
* Water rendering

![Title Image](result/0.bmp)

* Initial mapping
![No special effect](result/1.bmp)
* Bump mappint effect
![Add bump mapping](result/2.bmp)
* Rim light effect
![Add rim light](result/3.bmp)
* Clouds Shadow  
According to the light direction to offset the cloud's map and use the cloud's map to cover the color behind the cloud.
![Add cloud shadow](result/4.bmp)
* Height Shape  
Using bump map to set the vertex shader. I ever tried to set the vertex shader according to the real earth radius ratio. 
However, the radius of earth is 6400 km and the highest mountain on earth is 8.8km. That means if I really set the vertex
shader according to the real ratio, we could almost see nothing difference. Therefore, I used a modified ratio to set the vertex shader.
![Add height shade](result/5.bmp)
* Water Rendering  
I used a noise function to generate a random normal vector every 50 frames. Then, add this vector to the original normal vector of each fragment to assemble to a new normal.
Finally, used this new normal to compute the diffuse color and specular color.
![Add water rendering](result/6.bmp)




#Performance Analysis
Actually, I can't find any FPS difference between the fragment shader with full effects and the fragment shader without any effect.
From the image below we could see that even I just directly assign the fragment color to (1,1,1) 
without any calculation, the FPS is still 60 which is the same with which with full effects.  
I also ever tried to create more vertices when building the sphere, but the FPS is still 60. 
![Without any effect](result/white.bmp)

![FPS](result/FPS comparison.jpg)
#Video
http://youtu.be/NRenJzGajc0

#Try it
http://foxking0416.github.io/Project5-WebGL/
