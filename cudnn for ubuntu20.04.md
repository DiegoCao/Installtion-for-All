
>: warning: If you have not decided to use tensorflow or pytorch, strongly suggest to use pytorch, since the GPU version for tensorflow is so annoying. It requires basically three things: *Cuda, CUDNN,TensorRT*

After days struggling with Tensorflow GPU:

## CUDA


As there is no official installation for 20.04 version, record the installtion process here for reference.

First, go to this website:
https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/

As deb version


https://developer.nvidia.com/cuda-10.2-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=deblocal

https://arabelatso.github.io/2020/01/08/Install%20CUDA%20Toolkit%2010.2%20on%20Ubuntu%2018.04.3/

If warning comes that 'SSR cannot connect, change `https` to `http` instead.





## CUDNN

If you use pytorch, here, we are already done. But we need tensorflow, so install CUDNN:

The warning indicates that some libraries are not installed entirely, you need to install cuDNN, a library designed for accelerating in ML computation. The installation  for this can be found through:

https://developer.nvidia.com/rdp/cudnn-download

Need to register for an account at first.

Then download the corresponding CUDNN according to the Ubuntu version and cuda version on the computer. 

## Tensor-RT,

After installing CUDNN, error still exists,

```libnvinfer.so.6 
2021-01-21 15:19:15.844026: W tensorflow/stream_executor/platform/default/dso_loader.cc:55] Could not load dynamic library 'libnvinfer.so.6'; dlerror: libnvinfer.so.6: cannot open shared object file: No such file or directory
2021-01-21 15:19:15.844066: W tensorflow/stream_executor/platform/default/dso_loader.cc:55] Could not load dynamic library 'libnvinfer_plugin.so.6'; dlerror: libnvinfer_plugin.so.6: cannot open shared object file: No such file or directory
2021-01-21 15:19:15.844071: W tensorflow/compiler/tf2tensorrt/utils/py_utils.cc:30] Cannot dlopen some TensorRT libraries. If you would like to use Nvidia GPU with TensorRT, please make sure the missing libraries mentioned above are installed properly.
2021-01-21 15:19:16.343918: I tensorflow/stream_executor/platform/default/dso_loader.cc:44] Successfully opened dynamic library libcudart.so.10.1
```

that is because we do not install TensorRT. It still needs to be installed.

HOWEVER, IT IS VERY SAD THAT FOR UBUNTU20.04, THERE IS NO AVAILABLE TENSORRT VERSION SUPPORTS(*the supports only for ubuntu18.04, and it seems that I have made a huge mistake to install the system UBUNTU20.04 for the computer in the lab*). 

It needs to be noticed that 'libvnifer.so.6', here '6' means, I need to install tensorrt version 6, but the only good news here is: even without tensorRT 6, you can still run part of the GPU version, so just try to live with it and wait for NVidia company to give new support.


A very useful note:
https://medium.com/analytics-vidhya/installing-tensorflow-with-cuda-cudnn-gpu-support-on-ubuntu-20-04-f6f67745750a


Useful note for installing TensorRT:
https://www.jianshu.com/p/09ef0ad2ef4a
