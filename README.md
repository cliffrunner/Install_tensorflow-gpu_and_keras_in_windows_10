# Install_tensorflow-gpu_and_keras_in_windows_10

keras + tensorflow offers an ease-of-use solution for ANN. However, it is not recommended to use CPU for modeling due to the speed limit. Using GPU is always more preferrable should your graphic card supports Nvidia CUDA ([what is CUDA](https://blogs.nvidia.com/blog/2012/09/10/what-is-cuda-2/)), and you can use this [website](https://developer.nvidia.com/cuda-gpus) to check whether your graphic card satisfies the requirement.

The conventional way of installing Keras with tensorflow-gpu is well documented by many people (https://github.com/antoniosehk/keras-tensorflow-windows-installation). It is in general very tedius and not straightforward, and can easily get beginners confused like me. You can imagine that it has a high chance of failure should any of the many steps is not properly followed or any of the packages is not compatible. 

After hours of trial-and-error, I believe the following way is the best for a beginner like me, which involves fewer steps and no path or environment settings. Here we go.

## Step 1. download and install Anaconda
You need to go to the anaconda archive site to download anaconda5.2.0. Please be aware that by this time this article is written (1.1.2019), there are 3 higher versions of anacondas available (5.3.0, 5.3.1, 2018.12). After trying all these versions, my conclusion is 5.2.0 is the most stable version of all. If you don't want to deal with package compatibility issues, 5.2.0 is the one you should use.

Here is the link to download: https://repo.continuum.io/archive/

Note that there is anaconda2 and anaconda3. The number just means whether is python2 or python3. Unfortunately python2 and python3 are not compatible. But for a beginner, I would recommend python3.

The installation is very straightforward, click 'next's to finish installation.

## Step 2. install Cudatoolkit, Cudnn, and Opencv
Once anaconda is installed, start Anaconda Prompt, and type:

`conda install cudatoolkit`

Conda will check package dependency and let you know which packages should be install, proceed by typing `yes`. This would install cudatookit 9.0 on your computer.

Once cudatookit is installed, you can type:

`conda install cudnn`

then Conda will check package dependency again, once the process is over, proceed by typing `yes`. This would install Cudnn version 7.1.4 on your computer.

Finally, type:

`conda install opencv`

and install whatever packages conda wants you to install.

That is it. Easy, right? For some reason I have never seen any instruction showing people this way. All other instructions require people to download CUDA and Cudnn from their individual websites and requires path setup for Cudnn, which is not friendly for new-comers. 

## Step 3. install tensorflow-gpu
In Anaconda Prompt, type:

`pip install tensorflow-gpu==1.9.0`

Please note that

+ here we use `pip` instead of `conda`. Using `conda` will install many packages you don't need.

+ by using `==1.9.0` you tell `pip` that you would like to install tensorflow-gpu with version 1.9. The latest version of tensorflow (1.12.0) IS NOT COMPATIBLE with CUDA 9.0 and Cudnn 7.1.4. 

## Step 4. install keras
In Anaconda Prompt, type:

`pip install keras`


Horray, you are all set! Once you are using keras to run ANN, your GPU should automatically be called to run the modeling.

## Conclusion
One biggest mistake I made before was using Anaconda Navigator to install keras and tensorflow-gpu. The problems with this method are:

+ Package versions are the not the latest.

+ Dependency is tricky. Both tensorflow and tensorflow-gpu will be installed even you only want to install tensorflow-gpu. In such case I believe CPU is by default called instead of GPU when you do computation 

Conclusion is: Avoid using Anaconda Navigator, and always use Anaconda Prompt instead.
