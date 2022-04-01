# cs284a_hw3-2_webpage

## Project Overview


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




## Part2: Microfacet Material

## Extra Credit

## Collaboration
