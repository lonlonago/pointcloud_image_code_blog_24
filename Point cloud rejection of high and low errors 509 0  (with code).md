#  I. Quote 

>  Due to factors such as the scanner or external conditions during the acquisition process, there will always be many discrete points, and the availability of these discrete points themselves is almost non-existent or even abnormal points, such as common high and low errors, which can cause unnecessary stress or even errors in subsequent program operation and algorithm processing. Therefore, these error points should be eliminated. 

#  Second, algorithm implementation 

##  2.1 Implementation ideas 

>  (1) Search for adjacent points with the specified number of neighboring points for each point, and calculate the average distance d from the point to the adjacent points. (2) Calculate the median value D (overall) and standard deviation S of these average distances. If d is greater than the maximum distance MaxD (MaxD = D + K * S), it is considered noise and will be removed. (Similar to the normal distribution) 

##  2.2 Implementation code 

>  Denoising.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079291
 ```  
#  III. Achieving results 

>  Original data source 

![avatar]( 7ba9020f2b8a4ba790df5e5d5a795c70.png) 

>  After processing: 

![avatar]( 769ecb98330a41dd8cfdc49e4efc0f86.png) 

![avatar]( 0a9b469c200c417e8d0673d38a97795f.png) 

![avatar]( 1c2a43d7641c4224b65e590dbdf0dd76.png) 

>  It can be seen from the results that the algorithm has a good processing effect on the scattered high and low bit errors, but if the high and low bit error points are relatively dense, the processing effect is not ideal. 

![avatar]( 52faa17e0bbd49bfaf7f55425c948c2b.png) 

