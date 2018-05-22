

# Intel® OpenVINO™ Toolkit | Post-Installation Steps to Support Processor Graphics (GPU)

> **Note:**  This step is only required if you want to enable OpenVINO™ Toolkit components to utilize processor graphics on your system

<br>

## Prerequisites

[ ] [Download Intel® OpenVINO™ Toolkit for Linux*](https://software.intel.com/en-us/openvino-toolkit/choose-download)<br>
[ ] [Install Intel® OpenVINO™ Toolkit for Linux*](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/readme.md)<br>

<br>

## Set External Software Dependencies (Processor Graphics)

The installation automatically creates the install_dependencies directory under /opt/intel/computer_vision_sdk. This directory contains several scripts to enable OpenVINO™ Toolkit to utilize processor graphics on your system.

<ol>
  
  <li> Navigate to the install_dependencies directory in the installation location:</li><br>

    cd /opt/intel/computer_vision_sdk/install_dependencies/

  <li> Enter super user mode</li><br>
  
    sudo –E su
    
  <li> Check your kernal version. The minimum kernel supported is 4.14.</li><br>
  
    uname –r
  
> 4.14 is the validated configuration, but you can choose newer kernels as well. Note that these are mainline kernels, not the kernels officially validated with your operating system.

  <li> If your current configuration does not meet the minimum requirement, update your kernel to 4.14</li><br>

    ./install_4_14_kernel.sh

<li> Install the OpenCL™ NEOdriver components needed to use the clDNN GPU plugin and write custom layers for Intel® Integrated Graphics. For full functionality from this driver you must be running a 4.14 or newer kernel.</li><br>

    ./install_NEO_OCL_driver.sh

<li> Navigate to the Media Stack directory.</li><br>
    
     cd MediaStack

<li> Install the Intel® Media SDK. This SDK offers access to hardware accelerated video codecs and frame processing. This version of Intel Media SDK also requires a 4.14 or newer kernel. For more information, see https://github.com/Intel-Media-SDK/MediaSDK/releases.
</li><br>

    ./install_media.sh

<li> You must reboot the machine after running the Processor Graphics dependency scripts.</li><br>

    reboot

</ol>

<br>

## Next Steps

(Optional) [Post-Installation Steps for Intel® Movidius™ Neural Compute Stick (VPU)](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/install_USB_rules_linux.md)

[Hello World Tutorial for Linux (w/o FPGA)](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/hello_world_tutorial_linux.md)

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
