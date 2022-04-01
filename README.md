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

## Extra Credit



## Collaboration

Songye Han has finished the majority of the part 1. And Tianyi Huang has implemented the majority of the part 2. The two parts are kind of separated. Therefore, we parallel our work by different github branches and merge the code together after both of us have finished our own work. 
Both of us spent a happy spring break outside. Therefore, it is important to plan the schedule ahead and split the work in advance. 
