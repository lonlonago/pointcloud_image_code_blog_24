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

