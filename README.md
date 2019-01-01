# Install_tensorflow-gpu_and_keras_in_windows_10

keras + tensorflow offers an ease-of-use solution for ANN. However, it is not recommended to use CPU for modeling due to the speed limit. Using GPU is always more preferrable should your graphic card supports Nvidia CUDA ([what is CUDA](https://blogs.nvidia.com/blog/2012/09/10/what-is-cuda-2/)), and you can use this [website](https://developer.nvidia.com/cuda-gpus) to check whether your graphic card satisfies the requirement.

The conventional way of installing Keras with tensorflow-gpu is well documented by many people (https://github.com/antoniosehk/keras-tensorflow-windows-installation). It is in general very tedius and not straightforward, and can easily get beginners confused like me. You can imagine that it has a high chance of failure should any of the many steps is not properly followed or any of the packages is not compatible. 

After hours of trial-and-error, I believe the following way is the best for a beginner like me, which involves fewer steps and no path or environment settings. Here we go.
