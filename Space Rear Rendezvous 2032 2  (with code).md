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

