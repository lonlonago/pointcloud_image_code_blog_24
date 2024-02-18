#  I. Introduction 

>  Point cloud normal vectors are often messy because of their ambiguity, as shown below. But sometimes we need to use the normal vector to determine whether a point is inside the point cloud, and the orientation of the normal vector comes in handy. 

![avatar]( 8b921bc0ed0449ac93678b4f0f5270a8.png) 

#  Second, algorithm implementation 

##  2.1 Algorithm steps 

>  The theoretical basis of point cloud redirection is that the normal vector between two adjacent points should be consistent, that is, the "proximity principle". The specific process is as follows: 1. Find the point with the smallest z value in the point cloud as the seed point. Since this point is the lowest point of the point cloud, the product of the normal vector towards the (0,0,1) vector should be a positive number. If it is negative, the normal vector should be flipped. 2. Find the adjacent point set of the point, multiply the normal vector of the adjacent point set point P with the normal vector of the point, if it is negative, flip the normal vector of the point P, otherwise do not flip until all the adjacent points are involved in the operation. 3. Use the adjacent point set as a new seed point and repeat the process in 2 until all the points in the point cloud are traversed and the algorithm stops. 

##  2.2 Code implementation 

>  normal.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574063379
 ```  
#  III. Achieving results 

>  Primitive point cloud normal vector 

![avatar]( e02f49f96d824568993d30b9fd6a21c5.png) 

>  Point cloud normal vector after redirection 

![avatar]( 67cafc21acfa4c4c8a132fa8bf55cc58.png) 

![avatar]( 071cf505f45b49c398658f1d755f6fdd.png) 

From the perspective of the implementation effect, the normal vector after the redirection is much better than the one before the redirection. Most of the normal vectors point to the inside of the point cloud, and the experiment is very successful. "~". 

>  参考文献： [1]Semantic 3D Object Maps for Everyday Manipulation in Human Living Environments 

