# cs284a_hw3-2_webpage

## Project Overview

In this project, we choose part 1 and part 2. Both of the parts implemnt material modeling to get the precise light of different objects by its material. In part 1, I have implemented reflect and refract function to calculate wi. And we implement f-value function of both mirror (merely reflect) and glass (both reflect and refract) models according to its brightness attribute. 


## Part1: Mirror and Glass Materials

### Sequences of Images
Below are the rendered images of scene CBspheres.dae (set maximum depth from 0~5, 100).

m=0 | m=1 | m=2
:---: | :---: | :---:
![](/pic/CBspheres_0.png) | ![](/pic/CBspheres_1.png) | ![](/pic/CBspheres_2.png) 

m=3 | m=4 | m=5 | m=100
:---: | :---: | :---: | :---:
![](/pic/CBspheres_3.png) | ![](/pic/CBspheres_4.png) | ![](/pic/CBspheres_5.png) | ![](/pic/CBspheres_100.png)

### multibounce effects and Explainations
We can see from the picture that the image is totally black except the ceiling when m=0. This is because only zero-bounce radiance will be included when m = 0, making the ceiling the only area lighted. 

When m = 1, the two balls are black. This is because the two shperes are mirror material. Therefore, it will not include one-bounce radiance. And it will also not include zero-bounce radiance when depth is smaller or equal to 1. 

When m = 2, the front ball is nearly black while the ball in the back is white. The front ball needs to be reflected 3 times to get light in the camera. Therefore, it is nearly black when we set m <= 2. Howevevr, the ball in the back can trasmit more ratio of light by refracting the light. Therefore, it is brighter than the front ball.

When m = 3, both ball are brighter, as well as the shadow on the ground of the ball in front. However, when m is increased the brightness are nearly same. 

When m = 4, only the front area of the front ball are visibly brighter. This is because the majority of the light comes from less-than-5 bounce illlumination, which well explains why m=100 and m=5 nearly has the same brightness. 


## Part2: Microfacet Material
### Show a sequence of 4 images of scene CBdragon_microfacet_au.dae rendered with α set to 0.005, 0.05, 0.25 and 0.5. The other settings should be at least 128 samples per pixel and 1 samples per light. The number of bounces should be at least 5. Describe the differences between different images. Note that, to change the α, just open the .dae file and search for microfacet.

α=0.005 | α=0.05 | α=0.25 | α=0.5
:---: | :---: | :---: | :---:
![](/pic/2-1-0005.png) | ![](/pic/2-1-005.png) | ![](/pic/2-1-025.png) | ![](/pic/2-1-05.png)

From the above figures, we can see that with the increasing of α, the specular gloss of the Dragon surface decreases and the roughness increases. When α is 0.005, the Dragon surface is completely specular, and when α is 0.5, the Dragon surface becomes frosted.

### Show two images of scene CBbunny_microfacet_cu.dae rendered using cosine hemisphere sampling (default) and your importance sampling. The sampling rate should be fixed at 64 samples per pixel and 1 samples per light. The number of bounces should be at least 5. Briefly discuss their difference.

Cosine Hemisphere Sampling | Importance Sampling
:---: |:---:
![](/pic/2-2-c.png) | ![](/pic/2-2-i.png)

From the above figures, we can see that Cosine Hemisphere Sampling will cause a lot of noise on Bunny's surface. The reason is similar to that in hw3-1. Cosine Hemisphere Sampling can't accurately sample every light, and some incident light doesn't fully meet the previously used reflection equation. But Importance Sampling solves this problem well, it ensures that each tracked light is guided to the light source, effectively reducing the loss of light, so the noise on the bunny surface is also less.

### Show at least one image with some other conductor material, replacing eta and k. Note that you should look up values for real data rather than modifying them arbitrarily. Tell us what kind of material your parameters correspond to
After looking up the refractive index and the extinction coefficient of conductor material, we chose silver for rendering, the eta of sliver is 0.45138, 46708, 0.45608, and the k of sliver is 5.8554, 5.2037, 4.2763. The result is as follow.
![](/pic/2-3-1.png)

## Extra Credit



## Collaboration

Songye Han has finished the majority of the part 1. And Tianyi Huang has implemented the majority of the part 2. The two parts are kind of separated. Therefore, we parallel our work by different github branches and merge the code together after both of us have finished our own work. 
Both of us spent a happy spring break outside. Therefore, it is important to plan the schedule ahead and split the work in advance. 
