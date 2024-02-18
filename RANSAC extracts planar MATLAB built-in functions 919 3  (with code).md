#  I. Introduction 

>  There is a built-in RANSAC extraction plane function in MATLAB. Although the function and the RANSAC method in PCL and CloudCompare are slightly crude, they can already meet our requirements. 

>  This built-in function is a variant of the RANSAC algorithm, and its greatest advantage is that it uses the maximum likelihood method (MLE) to evaluate the error of external points, rather than relying solely on the number of internal points. 

#  II. Relevant parameters 

maxDistance: The maximum distance from the interior point to the plane, specified as a scalar value. The unit of the specified distance should match the unit of the point cloud. referenceVector: The reference direction constraint, specified as a 1 × 3 vector. maxAngularDistance: The maximum absolute angular distance between the normal vector of the fitted plane and the reference direction, specified as a scalar value in degrees. 

>  In addition, there are many more parameter settings available in MATLAB's help documentation. 

#  III. Implementation code 

>  FitPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574016684
 ```  
>  Because the function can detect only one plane at a time, a loop is used to detect all planes. 

#  IV. Achieving results 

![avatar]( 2098a9ac34b3426aa4b5af41b4bad327.png) 

#  reference 

>  [1]Matlba帮助文档 [2]MLESAC:A New Robust Estimator with Application to Estimating Image Geometry 

