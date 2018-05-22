

# Intel® OpenVINO™ Toolkit <br>Build the Sample Applications on Linux*

The Inference Engine sample applications are simple console applications that demonstrate how to use Intel's Deep Learning Inference Engine in your applications.

### Samples included in the Samples Directory

The following sample applications are available in the samples directory in the Inference Engine installation directory:

| Sample Application  | Description |
| ------------- | ------------- |
| CPU Extensions | Library with topology-specific layers, like `DetectionOutput` used in the SSDl  |
| Image Classification Sample | Inference of image classification networks like AlexNet and GoogLeNet (the sample supports only images as inputs) |

<br>

### Samples that Support Pre-trained Models Included with Installation

You are provided several pre-trained models. The table below shows the correlation between models and samples/devices.  The samples are available in `<INSTALL_DIR>/deployment_tools/inference_engine/samples`

> placeholder for detailed sample/model compatibility table

<br>

## Build the Sample Applications on Linux

Supported Linux build environment:

<ul>
  <li>Ubuntu* 16.04 LTS 64-bit or CentOS* 7.4 64-bit</li>
<li>GCC* 5.4.0 (for Ubuntu* 16.04) or GCC* 4.8.5 (for CentOS* 7.4)</li>
<li>CMake* version 2.8 or higher.</li>
<li>OpenCV* 3.3 or later (required for some samples and demonstrations). Use the OpenVINO toolkit installation download and instructions to complete this installation.</li>
</ul>

Prepare your Linux computer for the samples:

<ol>
<li>Navigate to a directory that you have write access to and create a samples build directory. This example uses a directory named build:</li><br>

    mkdir build

<li> Navigate to the new directory:</li><br>

    cd build

<li> Run CMake to generate the Make files with or without debug information:

Without debug information:<br>

    cmake -DCMAKE_BUILD_TYPE=Release <path_to_inference_engine_samples_directory>

With debug information:<br>

    cmake -DCMAKE_BUILD_TYPE=Debug <path_to_inference_engine_samples_directory>

</li>

<li> Build the application:</li><br>

    make

The sample application binaries are in <path_to_build_directory>/intel64/Release/.

</ol>

<br>

## Set Your Environment Variables

Use the setupvars script to make sure your application can find the Interface Engine libraries.

For Linux, execute the following command to set the environment variable:<br>

    source <INSTALL_DIR>/bin/setupvars.sh

<br>

## Next Steps

[How to Configure the Model Optimizer on Linux*](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/configure_model_optimizer_linux.md)

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
