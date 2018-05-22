

# Intel® OpenVINO™ Toolkit <br>Configure the Model Optimizer on Linux*

The Model Optimizer process assumes you have a network model that was trained with a supported framework.

## Install Prerequisites

<ol>
<li>Configure the Model Optimizer for the framework that was used to train the network. To perform this configuration, use the configuration Linux bash script, or the Windows batch file. The script and batch file are in: <INSTALL_DIR>/deployment_tools/model_optimizer/install_prerequisites

For Linux:

    install_prerequisites.sh

For Windows:

    install_prerequisites.bat

</ol>

<br>

## Configure the Model Optimizer

> This guide uses the configuration scripts included with installation. To configure Model Optimizer manually see the [Model Optimizer Developer Guide](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer)

You can either configure all three frameworks at the same time, or install an individual framework. The scripts install all required dependencies and provide the fastest and easiest way to configure the Model Optimizer.

To configure all three frameworks: Go to the <INSTALL_DIR>/deployment_tools/model_optimizer/install_prerequisites directory and run:

For Linux*:

    install_prerequisites.sh

For Windows*:

    install_prerequisites.bat

To configure a specific framework: Go to the <INSTALL_DIR>/model_optimizer/install_prerequisites directory and run:

CAFFE* NOTE: By default, you do not need to install Caffe to create an Intermediate Representation for a Caffe model unless you use Caffe for custom layer shape inference and do not write Model Optimizer extensions. To learn more about implementing Model Optimizer custom operations and the limitations of using Caffe for shape inference, see Caffe Models with Custom Layers.

TENSORFLOW* NOTE: To offload part of the inference to the TensorFlow framework, additional configuration steps are required:

<br>

## Convert the trained model to an optimized Intermediate Representation.


<br>

## Next Steps

[How to Run the Sample Applications on Linux*]()

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
