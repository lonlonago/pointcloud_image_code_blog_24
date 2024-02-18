Since the voxel accumulation method has been reproduced, I will also reproduce the platform-convex hull algorithm by the way haha.  

#  I. Introduction 

>  The idea of this method is also very simple, that is, divide the canopy into multiple irregular tables, and sum the volumes of each table to approximate the canopy volume. The approximate situation is shown in the figure below: 

![avatar]( 49fe13b7691f47a8b12edf2e6ec04a48.png) 

#  II. Implementation steps 

>  1. By slicing the canopy point cloud data based on the elevation and using the discrete Green formula to solve the area of each slice, this paper will use the Graham algorithm to calculate the area of each slice. For details, please refer to the https://blog.csdn.net/dayuhaitang1/article/details/122821546?spm=1001.2014.3001.5502 of this article. 2. Calculate the volume of each table, and then add up the volumes of these tables and cones to calculate the volume of the entire canopy. The calculation formula is as follows: 

![avatar]( ef2fc51090ac488895902a75298864a6.png) 

 ![avatar]( 890fde0341354e5ca4d4bd1e1cef3a80.png) 

#  III. Code implementation 

>  PedestalMethodPlus.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574084076
 ```  
>  CrossProduct.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574084076
 ```  
>  PolarAngle1.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574084076
 ```  
>  Graham.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574084076
 ```  
![avatar]( 9b05a8b8a4a940449553c84906ce4c3e.png) 

 Achieve the effect:  

#  IV. Summary 

>  In general, the platform method is a simple, fast and effective method for measuring canopy volume by converting the three-dimensional canopy volume calculation into multiple two-dimensional slice area calculations, which makes it possible to solve the three-dimensional canopy information on the basis of making full use of the external geometric characteristics of the canopy. Some scholars have applied this method to forestry to evaluate forest biomass and three-dimensional green volume. 

>  References: [1] An automatic extraction algorithm for single tree crown projected area and crown volume based on 3D laser point cloud data [2] Tree 3D green content measurement based on 3D laser scanning [3] Coniferous forest drone image canopy segmentation algorithm based on SfM 

