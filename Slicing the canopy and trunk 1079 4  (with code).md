I saw this method in the paper before, and I reproduced it privately. I feel that the effect can be recorded. 

#  I. Introduction 

>  The principle of this method is relatively simple. It extracts the canopy by comparing the horizontal and vertical distances of two adjacent slices, and slices are made axially in the elevation direction. When the slices reach the canopy, their horizontal or vertical distances will suddenly increase. At this time, the starting elevation value of the canopy can be determined, and the canopy part of the entire tree can be extracted. 

![avatar]( 8cd5f50d43d24884abc1ca9f724f5110.png) 

#  Second, code implementation (MATLAB) 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079868
 ```  
#  III. Achieving results 

![avatar]( d67224c05f5f4081adf92e111225cd0b.png) 

![avatar]( 2d61ec021f7545f2a7c63285ca31acde.png) 

#  IV. Some ideas 

>  1. This method is sensitive to noise and prone to invalid segmentation, as shown in the figure below, because the judgment conditions are relatively simple and simple. 

![avatar]( 46668e5490254d84809745b6d2aa1554.png) 

>  2. Point cloud density has always been a drawback of slicing methods. Low point cloud density may cause empty slices. Therefore, such methods often need to combine point cloud density to set parameters, such as d (point cloud slice thickness) in the above. For specific solutions, please refer to this article: https://blog.csdn.net/dayuhaitang1/article/details/122971656?spm=1001.2014.3001.5502, first find the average point spacing of out-point clouds, and then set relevant parameters according to this. 

>  3. In the existing papers, the projection area of the slice is used as the judgment condition of the method. According to the characteristics of the trunk, it is more suitable to use RANSAC to fit a circle, and the RANSAC method has strong robustness, which can overcome the above-mentioned noise. Sensitive situation, which requires subsequent verification "_". 

