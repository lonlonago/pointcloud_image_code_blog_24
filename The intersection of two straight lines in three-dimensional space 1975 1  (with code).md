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

