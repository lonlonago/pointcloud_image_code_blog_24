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

