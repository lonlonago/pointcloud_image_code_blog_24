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

