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

