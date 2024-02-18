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



--------------------------------------------------------------------------------

#  Overview of the principle 

>  In the point cloud model, a certain number of data points are randomly selected and randomly shifted along the normal vector direction by a certain distance to obtain the noise points of the point cloud entity. The amplitude of the offset is related to the scale of the point cloud, and the offset distance obeys the Gaussian distribution. 

#  Implementation code 

>  RandomAddPoints.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574064551
 ```  
#  III. Achieving results 

![avatar]( ab45f1ded6a242a6bac1b234c122601f.png) 



--------------------------------------------------------------------------------

#  First, algorithm implementation 

##  1.1 Implementation steps 

>  1. Determine the model. Three points determine a plane, and the equation is 

          a 

          x 

          + 

          b 

          y 

          + 

          c 

          z 

          + 

          1 

          = 

          0 

         ax+by+cz+1=0 

     Ax + by + cz + 1 = 0. 2. Derive the formula and find  

          a 

          , 

          b 

          , 

          c 

         a,b,c 

     A, b, c, it is much simpler here than other shapes. 3. Calculate the error. Calculate how many points in the point set satisfy the distance threshold (or other conditions) set by our implementation. Here we are the number of points. 4. Select the model. Repeat the process of 1-3 to select the model with the most supported points as the optimal solution to the problem. 

>  The derivation process is as follows:  

           a 

           x 

           + 

           b 

           y 

           + 

           c 

           z 

           + 

           1 

           = 

           0 

          ax+by+cz+1=0 

      ax+by+cz+1=0 

>  Take three points, as follows:  

           { 

                a 

                 x 

                 1 

                + 

                b 

                 y 

                 1 

                + 

                c 

                 z 

                 1 

                + 

                1 

                = 

                0 

                a 

                 x 

                 2 

                + 

                b 

                 y 

                 2 

                + 

                c 

                 z 

                 2 

                + 

                1 

                = 

                0 

                a 

                 x 

                 3 

                + 

                b 

                 y 

                 3 

                + 

                c 

                 z 

                 3 

                + 

                1 

                = 

                0 

          \begin{cases} ax_1+by_1+cz_1+1=0\\ ax_2+by_2+cz_2+1=0\\ ax_3+by_3+cz_3+1=0\\ \end{cases} 

      ⎩⎪⎨⎪⎧​ax1​+by1​+cz1​+1=0ax2​+by2​+cz2​+1=0ax3​+by3​+cz3​+1=0​ 

>  Set: 

>  The original formula can be changed to: 

##  1.2 Code implementation 

>  main.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574098576
 ```  
>  DrawPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574098576
 ```  
#  Realize the effect 

![avatar]( 8773378dd6d04538806abcb64c456614.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

I had always wanted to visualize the triangulation network before, but after thinking about it for a few days, it was finally completed, so I specially recorded it. The data is sliced from the point cloud of the tree canopy, and the final effect is as follows. 

![avatar]( 7ed8efa95d0f4167a722bf37ea9ec400.png) 

#  First, the triangulation algorithm part 

The specific process can refer to this article: https://blog.csdn.net/dayuhaitang1/article/details/109248648, I will not repeat it here. Partial modifications have been made to the algorithm: 

>  Delaunay.hpp 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079684
 ```  
#  Second, the visualization part 

This part mainly uses the OpenGL control in Qt to visualize the process by promoting the control to a custom class. 

##  2.1 New Qt project 

>  This part is all normal operation, and it is particularly important to check the OpenGL library. 

![avatar]( af0bd496016e404e8d1c5e47a5e65b20.png) 

##  2.2 Customizing OpenGL classes 

>  QMyOpenGLWidget.h 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079684
 ```  
Of particular note is the following line of code, in which the QOpenGLFunctions_4_5_Core class contains functions from the specified OpenGL version, and if you want to use other versions, you need to modify the parent class. 

![avatar]( 16764007e46049b3a0c636fe2e00729e.png) 

>  QMyOpenGLWidget.cpp 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079684
 ```  
##  2.3 Promoting custom classes 

![avatar]( e8c7831f4e11481798157ad5cb6525c3.png) 

![avatar]( ec4041eb3f954d3ebe98f98e69321095.png) 

 ![avatar]( f8ce67ef5d374d938d9282c21b3f4eb4.png) 

>  After promoting the OpenGL control, the running effect is as follows: 

![avatar]( e7d6e964482c46c58421f131b0101c53.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  Overview of the principle 

![avatar]( 6179866e81d94773bcb811f35324ef01.png) 

#  Implementation code 

>  SKF.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574062722
 ```  
#  III. Achieving results 

![avatar]( a42baced7fc34a77a5575383d6173ab8.png) 

#  References 

>  [1] Building Contour Extraction from Airborne Lidar Point Cloud under Tree Shading 



--------------------------------------------------------------------------------

>  I have been thinking about using the RANSAC method to improve the slicing method (https://blog.csdn.net/dayuhaitang1/article/details/123049811), and I just studied it before, and realized the idea at that time. The effect is not bad. Record it here. 

#  First, the code implementation 

>  CanopyUnder.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574052612
 ```  
>  RANSAC.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574052612
 ```  
#  Realize the effect 

![avatar]( a478f9654d414e23897e695bddb13cfd.png) 

>  As shown in the figure, using the RANSAC method to extract the canopy is more robust, even if there is some noise, the canopy can still be extracted normally. 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  Overview of the principle 

>  As a surveyor, I have always felt that my understanding of these things is not very solid, so here is a summary. 

>  The basic idea of spatial rear rendezvous is to use the ground control points and their image points on the image to determine the outer azimuth elements of a single image. If we know the six outer azimuth elements of each image, then it is easy to determine the relationship between the subject and the aerial image. Therefore, the methods that can be taken to obtain the outer azimuth elements of the image are: using radar, Global Position System GPS, Inertial Navigation System INS and star camera to obtain the outer azimuth elements of the image; or using the spatial coordinates and image coordinates of a certain number of control points within the image coverage area, the outer azimuth elements of the image can be inverted according to the collinear conditional equation. This method is called spatial rear rendezvous of a single image. 

>  The specific derivation process is as follows 

          S 

         S 

     S is the photography center. 

          ( 

           X 

           S 

          , 

           Y 

           S 

          , 

           Z 

           S 

          ) 

         (X_S,Y_S,Z_S) 

     (XS​,YS​,ZS​)， 

          A 

         A 

     A is an object space point with coordinates 

          ( 

           X 

           A 

          , 

           Y 

           A 

          , 

           Z 

           A 

          ) 

         (X_A,Y_A,Z_A) 

     (XA ,YA ,ZA), 

          a 

         a 

     A for 

          A 

         A 

     The corresponding image point of A on the image, the coordinates are 

          ( 

          X 

          , 

          Y 

          , 

          Z 

          ) 

         (X,Y,Z) 

     (X, Y, Z), then according to the characteristics of collinearity:  

            X 

              X 

              A 

             − 

              X 

              S 

           = 

            Y 

              Y 

              A 

             − 

              Y 

              S 

           = 

            Z 

              Z 

              A 

             − 

              Z 

              S 

           = 

            1 

            i 

          \frac{X}{X_A-X_S}=\frac{Y}{Y_A-Y_S}=\frac{Z}{Z_A-Z_S}=\frac{1}lambda} 

      XA − XS X = YA − YS Y = ZA − ZS Z = λ1 

>  On the basis of the collinear equation, we assume that the external orientation elements of the image are:  

            X 

            S 

           , 

            Y 

            S 

           , 

            Z 

            S 

           , 

           e 

           , 

           w 

           , 

           k 

          X_S,Y_S,Z_S,\varphi,w,k 

      XS, YS, ZS, φ, w, k Due to the nonlinear function of the collinear equation, it must be linearized in order to use the least squares method. Linearization of the collinear conditional equation, the collinear equation at a certain point is: 

![avatar]( 9883ac921b9d4f28adaccaeeefa9ca5a.png) 

>  In the formula, 

          x 

          ， 

          y 

         x，y 

     X, y are the image plane coordinates of this point, 

           x 

           0 

          ， 

           y 

           0 

         x_0，y_0 

     X0, y0 are the inner orientation elements of the image. 

>  We continue to assume nine elements of the image rotation matrix: 

![avatar]( 95f6b1b2beaf46c0ba39ae76e5feb98e.png) 

>  Since the unknown is an outer azimuth element, the collinear equation is regarded as a function of the outer azimuth element. Let the approximate value of the outer azimuth element be: 

           X 

           S 

           0 

          , 

           Y 

           S 

           0 

          , 

           Z 

           S 

           0 

          , 

           e 

           0 

          , 

           w 

           0 

          , 

           k 

           0 

         X_{S}^{0},Y_{S}^{0},Z_{S}^{0},\varphi^0,w^0,k^0 

     XS0, YS0, ZS0, φ 0, w0, k0. Here, the first-order Taylor expansion of the collinear equation at the approximation of the outer azimuth elements is obtained: 

![avatar]( 37f0930f9eb443a9b33d30320cb3ba43.png) 

>  In the formula, 

           x 

           0 

          ， 

           y 

           0 

         x_0，y_0 

     X0, y0 are obtained by substituting the approximate values of the outer azimuth elements into the collinear equation 

          x 

          ， 

          y 

         x，y 

     x，y值。 

>  The image plane coordinates of the image points corresponding to the control points are regarded as observations, and the outer azimuth elements are regarded as parameters. The error equation can be listed from the linear form of the collinear equation: 

![avatar]( c13c415041a944c8986f5e7d010097ca.png) 

 ![avatar]( a770f44440954a57900872307764cc82.png) 

>  in the formula 

          x 

          ， 

          y 

         x，y 

     X, y are the image plane coordinates of the image point corresponding to the control point. 

           V 

           x 

          ， 

           V 

           y 

         V_x，V_y 

     Vx, Vy is the correction number of the image plane coordinates, 

          W 

           X 

           S 

          , 

          W 

           Y 

           S 

          , 

          W 

           Z 

           S 

          , 

          W 

          e 

          , 

          W 

          w 

          , 

          W 

          k 

         \Delta{X_S},\Delta{Y_S},\Delta{Z_S},\Delta{\varphi},\Delta{w},\Delta{k} 

     The correction numbers of the parameters are delta XS, delta YS, delta ZS, delta phi, delta w, and delta k. 

>  After performing the above work, the solution process of the spatial rear intersection is roughly as follows: (1) Obtain known data. Such as image scale 1/m, inner orientation elements x0, y0, f, spatial coordinates X, Y, Z of the control point and the image plane coordinates x, y of the corresponding image point. (2) Determine the initial value of the parameter 

           X 

           S 

           0 

          , 

           Y 

           S 

           0 

          , 

           Z 

           S 

           0 

          , 

           e 

           0 

          , 

           w 

           0 

          , 

           k 

           0 

         X_{S}^{0},Y_{S}^{0},Z_{S}^{0},\varphi^0,w^0,k^0 

     XS0​,YS0​,ZS0​,φ0,w0,k0。 

![avatar]( 507e664b05e745efbca949bd3a48915d.png) 

>  (3) Calculate the rotation matrix. 

![avatar]( 70b5e19ec24342c39ef8ecfb01da090e.png) 

 ![avatar]( 7979cf875ca640f196747267d03c53f1.png) 

>  (4) Calculate the approximation of the image point coordinates. Using the approximation of the parameters, calculate the approximation of the image plane coordinates of the corresponding image points of each control point according to the collinear equation. (5) Calculate the coefficient matrix and constant terms of the error equation. 

![avatar]( 55bcb661fd7348b08529df8c39dbf9ef.png) 

 ![avatar]( d8f672e35d47417da334e13ceb5df085.png) 

 ![avatar]( 3cd3f99a6717418f8c3260c282bafb8b.png) 

 ![avatar]( 0f955feb3135497abf3c6ad02b682e6f.png) 

 The elements in the coefficient matrix A are all partial derivatives, remember: 

![avatar]( 7dc220dabf0242038ac8528b2e0412db.png) 

>  The final error equation is: 

![avatar]( aa19a090d5e643098ff6d4d31fca4b60.png) 

>  (6) Calculation method equation coefficient matrix and constant terms. According to the principle of least squares, take the weighted matrix as the unit matrix, then 

          X 

          = 

          ( 

           A 

           T 

          A 

           ) 

            − 

            1 

           A 

           T 

          L 

         X = (A^TA)^{-1}A^TL 

     X = (ATA) − 1ATL. (7) Check whether it converges. Determine whether it converges by setting limits on the outer azimuth elements. If it converges, the algorithm ends. Otherwise, repeat the above steps until it converges. 

#  Implementation code 

>  main.c 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574096986
 ```  
#  III. Achieving results 

![avatar]( daa4de3f41474abe8c13297676cddfb4.png) 

#  reference 

>  [1] "Photogrammetry" 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  Overview of the principle 

>  In order to obtain two intersecting lines in three-dimensional space, here we use the point direction to represent the line, and create the intersection of the line through the two points and their normal vector. The specific operations are as follows: (1) Determine the axial direction. Here we use the normal vector 

           n 

           1 

          , 

           n 

           2 

         n_1,n_2 

     N1, n2 are cross-multiplied to determine the axial vector 

          A 

         A 

     A. (2) Combine the two parameter lines 

           P 

           1 

          + 

          t 

           n 

           1 

         P_1 +tn_1 

     P1 + tn1 Pal 

           P 

           2 

          + 

          t 

           n 

           2 

         P_2 +tn_2 

     P2 + tn2 project along the axis to 

          A 

          ⋅ 

          x 

          = 

          0 

         A·x = 0 

     A 🥰 x = 0 plane, so that you can create a situation where two straight lines intersect. (3) Derive the formula to find the intersection point of the projected two straight lines. The specific process is as follows: 

>  Since the normal vector is 

           n 

           1 

          , 

           n 

           2 

         n_1,n_2 

     N1, n2 are cross-multiplied, so after the two parameter lines are projected, the direction vector does not change, it is still the same 

           n 

           1 

          ( 

           a 

           1 

          , 

           b 

           1 

          , 

           c 

           1 

          ) 

          , 

           n 

           2 

          ( 

           a 

           2 

          , 

           b 

           2 

          , 

           c 

           2 

          ) 

         n_1(a_1,b_1,c_1),n_2(a_2,b_2,c_2) 

     n1​(a1​,b1​,c1​),n2​(a2​,b2​,c2​)， 

           P 

           1 

          , 

           P 

           2 

         P_1,P_2 

     After P1, P2 projection becomes 

           p 

           1 

          , 

           p 

           2 

         p_1,p_2 

     p1​,p2​。 

>  So we first determine these two projection lines, where we need to first find the projection points of the two points 

           v 

           1 

          , 

           v 

           2 

         v_1,v_2 

     v1​,v2​：  

            { 

                  x 

                  v 

                 = 

                  x 

                  i 

                 − 

                 a 

                 t 

                  y 

                  v 

                 = 

                  y 

                  i 

                 − 

                 b 

                 t 

                  z 

                  v 

                 = 

                  z 

                  i 

                 − 

                 c 

                 t 

           t 

           = 

             a 

              x 

              i 

             + 

             b 

              y 

              i 

             + 

             c 

              z 

              i 

             + 

             1 

              a 

              2 

             + 

              b 

              2 

             + 

              c 

              2 

          \begin{cases} x_v=x_i−at\\ y_v=y_i−bt\\ z_v=z_i−ct\\ \end{cases} \\ t=\frac{ax_i+by_i+cz_i+1}{a^2+b^2+c^2} 

      Xv = xi − atyv = yi − btzv = zi − ct t = a2 + b2 + c2axi + byi + czi + 1 At this point, the coordinates of the two projection points can be found 

           n 

           1 

          ( 

           x 

           1 

          , 

           y 

           1 

          , 

           z 

           1 

          ) 

          , 

           n 

           2 

          ( 

           x 

           2 

          , 

           y 

           2 

          , 

           z 

           2 

          ) 

         n_1(x_1,y_1,z_1),n_2(x_2,y_2,z_2) 

     n1​(x1​,y1​,z1​),n2​(x2​,y2​,z2​)。 

>  Then the equation of the two lines can be expressed as:  

           { 

                  x 

                  − 

                   x 

                   1 

                  a 

                  1 

                = 

                  y 

                  − 

                   y 

                   1 

                  b 

                  1 

                = 

                  z 

                  − 

                   z 

                   1 

                  c 

                  1 

                  x 

                  − 

                   x 

                   2 

                  a 

                  2 

                = 

                  y 

                  − 

                   y 

                   2 

                  b 

                  2 

                = 

                  z 

                  − 

                   z 

                   2 

                  c 

                  2 

          \begin{cases} \frac{x-x_1}{a_1}=\frac{y-y_1}{b_1}=\frac{z-z_1}{c_1}\\ \frac{x-x_2}{a_2}=\frac{y-y_2}{b_2}=\frac{z-z_2}{c_2}\\ \end{cases} 

      {A1 x − x1 = b1 y − y1 = c1 z − z1 a2 x − x2 = b2 y − y2 = c2 z − z2 These two formulas are typically written in the point direction, that is, the line is determined by the point + direction vector. Where only 

          x 

          , 

          y 

          , 

          z 

         x,y,z 

     X, y, z are unknown, everything else is known. 

>  From the above formula, we can obtain:  

            { 

                  b 

                  1 

                 x 

                 − 

                  a 

                  1 

                 y 

                 = 

                  b 

                  1 

                  x 

                  1 

                 − 

                  a 

                  1 

                  y 

                  1 

                  b 

                  2 

                 x 

                 − 

                  a 

                  2 

                 y 

                 = 

                  b 

                  2 

                  x 

                  2 

                 − 

                  a 

                  2 

                  y 

                  2 

           z 

           = 

            z 

            1 

           + 

             x 

             − 

              x 

              1 

             a 

             1 

            c 

            1 

          \begin{cases} b_1x-a_1y=b_1x_1-a_1y_1\\ b_2x-a_2y=b_2x_2-a_2y_2\\ \end{cases} \\ z =z_1+\frac{x-x_1}{a_1}c_1 

      {b1​x−a1​y=b1​x1​−a1​y1​b2​x−a2​y=b2​x2​−a2​y2​​z=z1​+a1​x−x1​​c1​ 

#  Implementation code 

>  TwoPointsDrawCyliner.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079318
 ```  
>  DrawPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079318
 ```  
#  III. Achieving results 

![avatar]( 09515c85bc8a4cef843ea976d754542c.png) 



--------------------------------------------------------------------------------

#  First, the derivation process 

![avatar]( e77926d05ba9435393dfc830fbcaeefd.png) 

>  Suppose the given plane is 

          a 

          x 

          + 

          b 

          y 

          + 

          c 

          z 

          + 

          1 

          = 

          0 

         ax+by+cz+1=0 

     ax+by+cz+1=0，点 

           p 

           i 

          ( 

           x 

           i 

          , 

           y 

           i 

          , 

           z 

           i 

          ) 

         p_i(x_i,y_i,z_i) 

     Pi (xi, yi, zi) is the point outside the plane, 

          v 

          ( 

           x 

           v 

          , 

           y 

           v 

          , 

           z 

           v 

          ) 

         v(x_v,y_v,z_v) 

     V (xv, yv, zv) is the projection point, then the vector 

          v 

           p 

           i 

         vp _ i 

     VPI parallel to normal vector 

          n 

          ( 

          a 

          , 

          b 

          , 

          c 

          ) 

         n(a,b,c) 

     N (a, b, c), therefore:  

              x 

              i 

             − 

              x 

              v 

            a 

           = 

              y 

              i 

             − 

              y 

              v 

            b 

           = 

              z 

              i 

             − 

              z 

              v 

            c 

           = 

           t 

          \frac{x_i-x_v}{a}=\frac{y_i-y_v}{b}=\frac{z_i-z_v}{c}=t 

      axi​−xv​​=byi​−yv​​=czi​−zv​​=t 那么可得：  

           { 

                 x 

                 v 

                = 

                 x 

                 i 

                − 

                a 

                t 

                 y 

                 v 

                = 

                 y 

                 i 

                − 

                b 

                t 

                 z 

                 v 

                = 

                 z 

                 i 

                − 

                c 

                t 

          \begin{cases} x_v=x_i−at\\ y_v=y_i−bt\\ z_v=z_i−ct\\ \end{cases} 

      ⎩⎪⎨⎪⎧​xv​=xi​−atyv​=yi​−btzv​=zi​−ct​ 

>  due to 

           p 

           i 

         p_i 

     The directed distance from pi to the plane is:  

            d 

             p 

             i 

           = 

             a 

              x 

              i 

             + 

             b 

              y 

              i 

             + 

             c 

              z 

              i 

             + 

             1 

               a 

               2 

              + 

               b 

               2 

              + 

               c 

               2 

          d _ {pi} =\ frac {ax _ i + by _ i + cz _ i + 1} {\ sqrt {a ^ 2 + b ^ 2 + c ^ 2}} 

      dpi​=a2+b2+c2

Axi + byi + czi + 1 makes it easy to get:  

           t 

           = 

             a 

              x 

              i 

             + 

             b 

              y 

              i 

             + 

             c 

              z 

              i 

             + 

             1 

              a 

              2 

             + 

              b 

              2 

             + 

              c 

              2 

          t =\ frac {ax _ i + by _ i + cz _ i + 1} {a ^ 2 + b ^ 2 + c ^ 2} 

      t=a2+b2+c2axi+byi+czi+1 

#  Code implementation 

>  main.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574093876
 ```  
>  PointProjPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574093876
 ```  
#  III. Calculation effect 

![avatar]( 47d3172a9dc549d8ab4e0ff366e4fdfe.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

I read an article before that used the PCA method to rotate the point cloud to improve the computational speed of the convex hull of an object. I found it interesting, so I tested it. 

#  I. Introduction 

>  PCA, as a dimensionality reduction method, can be used to analyze the main direction of the data to construct a new coordinate space. For the main ideas, please refer to the article https://blog.csdn.net/dayuhaitang1/article/details/108778144 

#  Code implementation 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574012571
 ```  
![avatar]( 88a30d4c206647389b1150b56b08331a.png) 

 Run effect:  

![avatar]( cbd02c66729d4e4b950f3533498413f2.png) 



--------------------------------------------------------------------------------

#  First, the implementation code 

>  main.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574015571
 ```  
>  DrawCube.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574015571
 ```  
>  Of course, there is also code that only shows a few of these layers (mainV1.m). 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574015571
 ```  
#  Realize the effect 

![avatar]( 1824c3d7f19647cf922296c8b9d10a2e.png) 

![avatar]( 5ed8c6344ffb4252a1165dbc4b562827.png) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Cilantro is a lean, fast C ++ library for working with point cloud data. It includes efficient implementations of a variety of common operations, provides a clean and tidy set of API interfaces, and attempts to minimize the amount of boilerplate code. The library is extensively templated, allowing operations on data of arbitrary numeric types and dimensions (where applicable), and has a modular/extensible design for more complex programs. At the same time, it provides convenient aliases/wrappers for the most common cases. (From the official website of cilantro) 

#  II. Preparations 

>  We need to download these source codes and software. 

1. Source code of Cilantro library: https://github.com/kzampog/cilantro 2. Source code of Eigen library: https://github.com/artsy/eigen. If you have installed or compiled PCL, you can directly use the Eigen library in PCL. 3. Open3D: You can refer to VS2015 (and above versions) to configure the Open3Dv0.15.2 version library. I did not use the Pangolin recommended by the official website (mainly to be lazy). Because this module is just for visualization, I replaced it with the existing Open3D on my computer. Of course, if you have PCL on your computer, you can also use PCL instead, just for visualization (you can refer to the QT configuration PCL process record (1)). 

#  Compile and configure 

1. Use cmake to generate the VS project, specify the directory and installation path of Eigen. 

![avatar]( f4f43ce01dad4bd59d258d7f74152b60.png) 

 ![avatar]( 5a52cc20c3f847e8b783d1ac4f7f78d5.png) 

 2. Use VS2019 to open the generated project and compile and install the source code. 

![avatar]( 8a00b48770464b5f91b509443cd90eb0.png) 

 ![avatar]( 4e8432fb48af4c949db7c625be0f7d2e.png) 

 ![avatar]( b0591fcf14c648379d2a793a0433ee55.png) 

#  III. Give an example 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574039122
 ```  
![avatar]( c5351a6ef9d544ee9059970a5dade087.png) 

#  reference 

>  [1] VS2015 (and above) configuration Open3Dv0.15.2 library 



--------------------------------------------------------------------------------

