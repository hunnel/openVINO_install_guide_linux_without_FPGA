

# Intel® OpenVINO™ Toolkit | Post-Installation Steps to Support Processor Graphics (GPU)

> **Note:**  This step is only required if you want to enable OpenVINO™ Toolkit components to utilize processor graphics on your system

<br>

## Set External Software Dependencies (Processor Graphics)

The installation automatically creates the install_dependencies directory under /opt/intel/computer_vision_sdk. This directory contains several scripts to enable OpenVINO™ Toolkit to utilize processor graphics on your system.

<ol>
  
  <li> Navigate to the install_dependencies directory in the installation location:</li>

    cd /opt/intel/computer_vision_sdk/install_dependencies/

  <li> Enter super user mode</li>
  
    sudo –E su
    
  <li> Update your kernel to 4.14. This is the minimum kernel supported, and the configuration that is validated, but you can choose newer kernels as well. These are mainline kernels, not the kernels officially validated with your operating system.</li>
  
> To see if you need to run this script, check your kernel version use uname –r.

    ./install_4_14_kernel.sh

<li> Install the OpenCL™ NEOdriver components needed to use the clDNN GPU plugin and write custom layers for Intel® Integrated Graphics. For full functionality from this driver you must be running a 4.14 or newer kernel.</li>

    ./install_OCL_driver.sh

<li> Navigate to the Media Stack directory.
    
     cd MediaStack

<li> Install the Intel® Media SDK. This SDK offers access to hardware accelerated video codecs and frame processing. This version of Intel Media SDK also requires a 4.14 or newer kernel. For more information, see https://github.com/Intel-Media-SDK/MediaSDK/releases.
</li>

    ./install_media.sh

<li> You must reboot the machine after running the Processor Graphics dependency scripts. </li>

    reboot

> NOTE: You must reboot the machine after running the scripts.

<br>

## Next Steps

(Optional) [Post-Installation Steps for Intel® Movidius™ Neural Compute Stick (VPU)]()

[Hello World Tutorial for Linux (w/o FPGA)](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/hello_world_tutorial_linux.md)

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
