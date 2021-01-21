As there is no official installation for 20.04 version, record the installtion process here for reference.

First, go to this website:
https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/

As deb version


https://developer.nvidia.com/cuda-10.2-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=deblocal

https://arabelatso.github.io/2020/01/08/Install%20CUDA%20Toolkit%2010.2%20on%20Ubuntu%2018.04.3/


Then if you want to use GPU for tensorflow, cuda is not enough. You will face following warning:
```
2021-01-21 15:19:15.844026: W tensorflow/stream_executor/platform/default/dso_loader.cc:55] Could not load dynamic library 'libnvinfer.so.6'; dlerror: libnvinfer.so.6: cannot open shared object file: No such file or directory
2021-01-21 15:19:15.844066: W tensorflow/stream_executor/platform/default/dso_loader.cc:55] Could not load dynamic library 'libnvinfer_plugin.so.6'; dlerror: libnvinfer_plugin.so.6: cannot open shared object file: No such file or directory
2021-01-21 15:19:15.844071: W tensorflow/compiler/tf2tensorrt/utils/py_utils.cc:30] Cannot dlopen some TensorRT libraries. If you would like to use Nvidia GPU with TensorRT, please make sure the missing libraries mentioned above are installed properly.
2021-01-21 15:19:16.343918: I tensorflow/stream_executor/platform/default/dso_loader.cc:44] Successfully opened dynamic library libcudart.so.10.1
```

The warning indicates that some libraries are not installed entirely, you need to install cuDNN, a library designed for accelerating in ML computation. The installation  for this can be found through:

https://developer.nvidia.com/rdp/cudnn-download

Need to register for an account at first.

Then download the corresponding CUDNN according to the Ubuntu version and cuda version on the computer. 
