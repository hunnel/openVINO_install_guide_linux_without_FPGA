# Intel® OpenVINO™ Toolkit | Installation Guide for Linux*

> It you are using OpenVINO™ Toolkit on Windows, please see [Installation Guide for Windows*](https://github.com/hunnel/openVINO_hello_world_windows)

> The OpenVINO™ toolkit was formerly known as the Intel® Computer Vision SDK. These steps apply to Ubuntu*, CentOS*, and Yocto*.

## Prerequisites

[ ] [Download Intel® OpenVINO™ Toolkit for Linux*](https://software.intel.com/en-us/openvino-toolkit/choose-download)<br>

<br>

The OpenVINO™ toolkit quickly deploys applications and solutions that emulate human vision. Based on Convolutional Neural Networks (CNN), the Toolkit extends computer vision (CV) workloads across Intel® hardware, maximizing performance. The OpenVINO™ Toolkit includes the Intel® Deep Learning Deployment Toolkit.

The OpenVINO™ toolkit for Linux:
<ul>
	<li> Enables CNN-based deep learning inference on the edge</li>
	<li> Supports heterogeneous execution across a CPU, Intel® Integrated Graphics, and Intel® Movidius™ Neural Compute Stick</li>
	<li> Speeds time-to-market via an easy-to-use library of computer vision functions and pre-optimized kernels</li>
	<li> Includes optimized calls for computer vision standards including OpenCV*, OpenCL™, and OpenVX*</li>
	</ul>

The installation package is free and comes as an archive that contains the software and installation scripts.
These instructions describe:
<ul>
	<li> What is included in the free download</li>
	<li> System requirements</li>
<li> Software dependencies</li>
<li> Installing the OpenVINO™ toolkit for Linux</li>
<li> Next steps</li>
</ul>

In addition, some topology-specific layers, like DetectionOutput used in the SSD*, are delivered in source code that assumes the extensions library is compiled and loaded. The extensions are required for pre-trained models inference. While you can build the library manually, the best way to compile the extensions library is to execute the demo scripts used in the Hello World walkthrough.

<br>

## Included with Installation

| Component  			| Description |
| ------------- 		| ------------- |
| Deep Learning Model Optimizer | Model import tool. Imports trained models and converts to the Intermediate Representation format for use by Deep Learning Inference Engine. This is part of the Intel® Deep Learning Deployment Toolkit.  |
| Deep Learning Inference Engine| Unified API to integrate the inference with application logic. This is part of the Intel® Deep Learning Deployment Toolkit.|
| Drivers and runtimes for OpenCL™ version 2.1| Enables OpenCL 1.2 on the GPU/CPU for Intel® processors|
| Intel® Media SDK | Offers access to hardware accelerated video codecs and frame processing |
| OpenCV* version 3.4.1 | OpenCV* community version compiled for Intel® hardware. Includes PVL libraries for computer vision |
| OpenVX* version 1.1 | Intel's implementation of OpenVX* 1.1 optimized for running on Intel® hardware (CPU, GPU, IPU). |
| Documents and tutorials | https://software.intel.com/en-us/openvino-toolkit/documentation/featured |

<br>

## Where to Download This Release

https://software.intel.com/en-us/openvino-toolkit/choose-download/free-download-linux

<br>

## System Requirements

This guide covers the Linux* version of the OpenVINO™ toolkit that does not includes FPGA support. For the toolkit that includes FPGA support, see the [OpenVINO™ Toolkit Installation Guide for Linux with FPGA Support](https://software.intel.com/en-us/articles/OpenVINO-Install-Linux-FPGA).

<br>

### Development and Target Platform

The development and target platforms have the same requirements, but you can select different components during the installation.

#### Processors

<ul>
	<li> 6th-8th Generation Intel® Core™</li>
	<li> Intel® Xeon® v5 family, Xeon® v6 family</li>
	<li> Intel® Pentium® processor N4200/5, N3350/5, N3450/5 with Intel® HD Graphics</li>
	<li> Intel® Movidius™ Neural Compute Stick</li>
</ul>

#### Processor Notes:

<ul>
	<li> Processor graphics are not included in all processors. See https://ark.intel.com/ for information about your processor.</li>
	<li> A chipset that supports processor graphics is required for Intel® Xeon® processors.</li>
</ul>

#### Operating Systems:

<ul>
	<li> Ubuntu* 16.04.3 long-term support (LTS), 64-bit</li>
	<li> CentOS* 7.4, 64-bit</li>
	<li> Yocto Project* Poky Jethro* v2.0.3, 64-bit (for target only)</li>
</ul>

<br>

## Pre-Installation

Use these steps to prepare your development machine for the OpenVINO™ toolkit.

<ol>
<li> Download the OpenVINO™ toolkit. By default, the file is saved as:</li><br>

	l_openvino_toolkit_p_2018.1.<version>.tar
	
<li> Unpack the .tar file:</li><br>

	tar -xf l_openvino_toolkit_p_2018.1.<version>.tar

The files are unpacked to a directory named l_openvino_toolkit_p_2018.1.<version>

<li> Go to the l_openvino_toolkit_p_2018.1.<version> directory:</li><br>

	cd l_openvino_toolkit_p_2018.1.<version>
	
<li> <strong>Install external software dependencies</strong></li>

The dependencies are packages required for Intel-optimized OpenCV 3.4, the Deep Learning Inference Engine, and the Deep Learning Model Optimizer tools. Before installing the OpenVINO™ toolkit, use an installation script that is in l_openvino_toolkit_p_2018.1.<version>:<br>

	./install_cv_sdk_dependencies.sh

</ol>

<br>

## Installation

<ol>
<li> Go to the l_openvino_toolkit_p_2018.1.<version> directory:</li><br>

	cd l_openvino_toolkit_p_2018.1.<version>

<li> Start the GUI-based installation wizard:</li><br>
	
	./install_GUI.sh

(optional) <strong>or</strong> the CLI installer:<br>

	./install.sh

<li> Choose between a GUI installation wizard or command-line instructions. The only difference between them is that the command-line installer is text-based. Instead of clicking options from a GUI, command-line prompts ask for input on a text screen.</li>

<li> The Prerequisites screen tells you if you are missing any required or recommended components, and the effect the missing component has on installing or using the product.</li>

<li> Click Next to begin the installation, or make final changes to your component selections and choose your installation directory.</li>

<li> The Installation summary screen shows you the options that will be installed if you make no changes.</li>

<li> Choose Install if you are ready to start the installation, or if you want to change the selected components and/or specify the installation directory, choose Customize. To proceed with the standard installation, choose Install.</li>

<li> A Complete screen indicates the software is installed. Click Finish to close the wizard.</li>

<li> Open the Getting Started page in the browser in the same mode in which you completed the installation. For example, if you performed your installation in sudo mode, use this command to go to the default installation directory:</li><br>

	cd /opt/intel/computer_vision_sdk_2018.1.<version>/
</ol>

## Set Environment Variables

Updates to several environment variables are required to compile and run OpenVINO™ toolkit applications. You can permanently set environment variables in a way matching your system's conventions. A method to set these variables temporarily (lasting only as long as the shell) is provided. For a standard OpenVINO™ toolkit installation:<br>

	source /opt/intel/computer_vision_sdk_2018.1.<version>/bin/setupvars.sh


<br>

## Next Steps

(Optional) [Post-Installation Steps for Processor Graphics (GPU)](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/install_GPU_linux.md)

(Optional) [Post-Installation Steps for Intel® Movidius™ Neural Compute Stick (VPU)](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/install_USB_rules_linux.md)

[Hello World Tutorial for Linux (w/o FPGA)](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/hello_world_tutorial_linux.md)

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
