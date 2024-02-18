#  I. Introduction 

>  This built-in function is a variant of the RANSAC algorithm, and its biggest advantage is that it uses the maximum likelihood method (MLE) to evaluate the error of external points, rather than relying solely on the number of internal points. For details, please refer to the paper at the end of the article. 

#  II. Relevant parameters 

maxDistance: The maximum distance from the interior point to the plane, specified as a scalar value. The unit of the specified distance should match the unit of the point cloud. referenceVector: The reference direction constraint, specified as a 1 × 3 vector. maxAngularDistance: The maximum absolute angular distance between the normal vector of the fitted plane and the reference direction, specified as a scalar value in degrees. 

>  For more parameter settings, please refer to MATLAB's help documentation. 

#  III. Implementation code 

>  FitCycliner.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026008
 ```  
>  DrawCylinderV1.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574026008
 ```  
#  IV. Achieving results 

![avatar]( 5ceba3e1ea5c4987932daf95d9296693.png) 

 ![avatar]( 46230f0ca22f4b56ad72e6f0cf5ea0a1.png) 

#  reference 

>  [1]Matlba帮助文档 [2]MLESAC:A New Robust Estimator with Application to Estimating Image Geometry 

