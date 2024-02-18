Because it is a direction of my previous research, I reproduced this method in the paper and recorded it here.  

#  I. Introduction 

>  In short, it is actually a sentence, that is, to simulate the irregular canopy shape with a fixed size of voxel. According to the idea in the paper, the main idea is to segment the canopy equidistant along the tree height direction with k as the step size, project the points of each section of the canopy onto a plane perpendicular to the tree height direction, and then divide the plane into pixels of size k × k. According to the number of points projected into each pixel, determine the validity of the pixel, and count the number of effective pixels T, then the canopy volume is the sum of T k × k × k voxels. As shown in the figure below: 

![avatar]( 8c9ca07a8d1749b080fdd49876342213.png) 

#  Second, code implementation (MATLAB) 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574085109
 ```  
![avatar]( 293341929faf4d069d9871ffc87bbaf7.png) 

 Achieve the effect:  

![avatar]( eeeab7f130404316aafb5b68bf709c28.png) 

#  III. Summary 

>  As a method for calculating the canopy volume, the voxel accumulation method has the characteristics of simple thinking and fast calculation (algorithm complexity is O (n)), but it can also be found that a major drawback of this method is that the appropriate voxel size is difficult to determine. Although many scholars have studied this method, there is still no good way to choose the voxel size. Interested students can find relevant papers for research, and there is no more to say here. 

>  Reference: "Tree Crown Volume Calculation Method Based on 3D Laser Scanning Point Cloud" "Differential 3D Laser Point Cloud Data 3D Green Quantity Determination of Single Wood" 

