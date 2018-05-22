

# Intel® OpenVINO™ Toolkit <br>How to Build the Sample Applications on Linux*

The Inference Engine sample applications are simple console applications that demonstrate how to use Intel's Deep Learning Inference Engine in your applications.

### Samples included in the Samples Directory

The following sample applications are available in the samples directory in the Inference Engine installation directory:

| Sample Application  | Description |
| ------------- | ------------- |
| CPU Extensions | Library with topology-specific layers, like `DetectionOutput` used in the SSDl  |
| Image Classification Sample | Inference of image classification networks like AlexNet and GoogLeNet (the sample supports only images as inputs) |

<br>

### Samples That Support Pre-Trained Models Shipped With the Product

You are provided several pre-trained models. The table below shows the correlation between models and samples/devices.  The samples are available in `<INSTALL_DIR>/deployment_tools/inference_engine/samples`


| Model	  | Sample Supported on the Model  | CPU	  | Intel® Integrated Graphics  	| HETERO:FPGA,CPU	  | Intel® Movidius™  Myriad™ 2 VPU   |
| ------------- | ------------- |
| CPU Extensions | Library with topology-specific layers, like `DetectionOutput` used in the SSDl  |
| Image Classification Sample | Inference of image classification networks like AlexNet and GoogLeNet (the sample supports only images as inputs) |

<br>

## Introduction to the **Model Optimizer** and **Inference Engine**

<br>

## Next Steps

[How to configure the Model Optimizer](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/configure_model_optimizer)

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
