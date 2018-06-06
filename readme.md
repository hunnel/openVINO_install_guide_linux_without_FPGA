# Intel® OpenVINO™ Toolkit | Installation Guide for Linux*

> It you are using OpenVINO™ Toolkit on Windows, please see [Installation Guide for Windows*](https://github.com/hunnel/openVINO_hello_world_windows)

> The OpenVINO™ toolkit was formerly known as the Intel® Computer Vision SDK. These steps apply to Ubuntu*, CentOS*, and Yocto*.

<br>

## Prerequisites

- [ ] [Download Intel® OpenVINO™ Toolkit for Linux*](https://software.intel.com/en-us/openvino-toolkit/choose-download)<br>

<br>

## Introduction

The OpenVINO™ toolkit quickly deploys applications and solutions that emulate human vision. Based on Convolutional Neural Networks (CNN), the toolkit extends computer vision (CV) workloads across Intel® hardware, maximizing performance. The OpenVINO™ toolkit includes the Intel® Deep Learning Deployment Toolkit.

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

Some topology-specific layers, like DetectionOutput used in the SSD*, are delivered in source code that assumes the extensions library required for pre-trained model inference is compiled and loaded, and installed with the OpenVINO™ toolkit. However, since the best performance is achieved when this library is compiled directly on your machine, the installation delivers the library source instead of pre-compiled libraries. The library is compiled after installation, when you execute the demo scripts used in the Hello World walkthrough. If you choose not to use Hello World, you must build the library manually before you use your pre-trained models.

<br>

## Included with Installation

| Component  			| Description |
| ------------- 		| ------------- |
| Deep Learning Model Optimizer | Model import tool. Imports trained models and converts them to the Intermediate Representation format for use by Deep Learning Inference Engine. The Model Optimizer is part of the Intel® Deep Learning Deployment Toolkit.  |
| Deep Learning Inference Engine| Unified API to integrate the inference with application logic. The Inference Engine is part of the Intel® Deep Learning Deployment Toolkit.|
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

This guide covers the Linux* version of the OpenVINO™ toolkit that does not include FPGA support. For the toolkit that includes FPGA support, see the [OpenVINO™ Toolkit Installation Guide for Linux with FPGA Support](https://software.intel.com/en-us/articles/OpenVINO-Install-Linux-FPGA).

<br>

### Development and Target Platform

The development and target platforms have the same requirements.

#### Processors

<ul>
	<li> 6th-8th Generation Intel® Core™</li>
	<li> Intel® Xeon® v5 family, Xeon® v6 family</li>
	<li> Intel® Pentium® processor N4200/5, N3350/5, N3450/5 with Intel® HD Graphics</li>
	<li> Intel® Movidius™ Neural Compute Stick</li>
</ul>

#### Processor Notes:

<ul>
	<li> Processor graphics are not included in all processors. See https://ark.intel.com/ for processor information.</li>
	<li> A chipset that supports processor graphics is required for Intel® Xeon® processors.</li>
</ul>

#### Operating Systems

<ul>
	<li> Ubuntu* 16.04.3 long-term support (LTS), 64-bit</li>
	<li> CentOS* 7.4, 64-bit</li>
	<li> Yocto Project* Poky Jethro* v2.0.3, 64-bit (for target platform only)</li>
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
</ol>

### Choose between the GUI or command-line installer.

> You have the option to use either a GUI installation wizard or command-line instructions. The only difference between them is that the command-line installer is text-based. Instead of clicking options from a GUI, command-line prompts ask for input on a text screen.

#### option 1. Use the GUI-based installation wizard.

<ol>
<li> Run the following script to use the GUI-based installation wizard.</li><br>
	
	./install_GUI.sh

</ol>

#### option 2. Use the command-line installation wizard.

<ol>
<li> Run the following script to use the command line installation:</li><br>

	./install.sh

<li> Follow the command-line instructions to complete installation.</li><br>
</ol>

The Getting Started guide should open automatically in a web browser once you complete the installation. Follow the steps in the Getting Started Guide, but remember to come back to this document to set your environment variables and to use the information in Next Steps.

If you used the default installation configuration, you can navigate to the OpenVINO™ Toolkit directory using the following command:

	cd /opt/intel/computer_vision_sdk_2018.1.<version>/

<br>

## Set Environment Variables

Updates to several environment variables are required to compile and run OpenVINO™ toolkit applications. You can permanently set environment variables in a way matching your system's conventions. 

A method to set these variables temporarily (lasting only as long as the shell) is provided. For a standard OpenVINO™ toolkit installation:<br>

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
