
# Intel® OpenVINO Toolkit™ | Hello World (Linux w/o FPGA support)

<br>

### Introduction

The Hello World demonstration serves several purposes:
<ol>
	<li><strong>to ensure complete and accurate installation and setup of the Intel CV SDK</strong> and</li>
	<li><strong>to introduce baseline capabilities needed to optimize end-to-end computer vision and deep-learning on Intel hardware</strong></li>
</ol>

In addition, some topology-specific layers, like DetectionOutput used in the SSD*, are delivered in source code that assumes the extensions library is compiled and loaded. The extensions are required for pre-trained models inference. While you can build the library manually, the best way to compile the extensions library is to execute the demo scripts used in the Hello World walkthrough.

<br>

### Introduction to the **Model Optimizer** and **Inference Engine**

This demo utilizes two key components from the OpenVINO Toolkit: the **Model Optimizer** and **Inference Engine**

The Model Optimizer is a Python*-based command line tool for importing trained models from popular deep learning frameworks such as Caffe*, TensorFlow*, and Apache MXNet*.

Key features of the Model Optimizer include:
<ul>
<li>Run on both Windows* and Linux*</li>
<li>Perform analysis and adjustments for optimal execution on endpoint target devices using static, trained models</li>
<li>Serialize and adjust the model into an intermediate representation (IR) format from Intel</li>
<li>Support over 100 public models for Caffe, TensorFlow, and MXNet</li>
<li>Standard frameworks are not required when generating IR files for models consisting of standard layers. When processing custom layers in original models, the Model Optimizer provides a flexible mechanism of extensions .</li>
</ul>

The Inference Engine uses a common API to deliver inference solutions on the platform of your choice: CPU, GPU, VPU, or FPGA.

Key features of the Inference Engine include:
<ul>
<li>Execute different layers on different targets (for example, a GPU and selected layers on a CPU)</li>
<li>Implement custom layers on a CPU while executing the remaining topology on a GPU—without having to rewrite the custom layers</li>
<li>Optimize execution (computational graph analysis, scheduling, and model compression) for target hardware with an embedded-friendly scoring solution</li>
<li>Take advantage of new asynchronous execution to improve frame-rate performance while limiting wasted cycles</li>
<li>Use a convenient C++ API to work on IR files and optimize inference</li>
</ul>

<br>

### Part 1: Image Classification

This first demo uses the Model Optimizer to convert a SqueezeNet model to two Intermediate Representation (IR) files (one .bin and one .xml). The Inference Engine requires this model conversion so it can use the IR as input and achieve optimum performance on Intel hardware.

#### 1. Navigate to the demo files included with the OpenVINO Toolkit™ installation.

	cd <INSTALL_DIR>/deployment_tools/demo
>
**Note:** If you performed your installation in sudo mode, the path to the default installation directory is /opt/intel/computer_vision_sdk/deployment_tools/demo

#### 1. Run the Image Classification demo script.

This demo uses the Model Optimizer to convert a SqueezeNet model to two Intermediate Representation (IR) files (one .bin and one .xml). The Inference Engine requires this model conversion so it can use the IR as input and achieve optimum performance on Intel hardware. The demo also automatically builds one of the sample applications included in the package.


	sudo ./demo_squeezenet_download_convert_run.sh

>
**Note:** All of the Inference Engine sample applications, including the classification sample used in this demo, can be found in the following directory: <INSTALL_DIR>/deployment_tools/inference_engine/samples/). For information about building and running the samples, please see the [Inference Engine Developer Guide - Building the Sample Applications on Linuz](https://software.intel.com/en-us/articles/OpenVINO-InferEngine).


When the demo completes, you should see the label and confidence for the top-10 categories (based on the cars.png image included in the demo directory.


#### Run the Inference Pipeline demo script.

>**Note:** The Inference Pipeline demo requires several libraries compiled in the previous section. Please make sure to run ./demo_squeezenet_download_convert_run.sh prior to moving on to the steps below.


This demo shows an inference pipeline using three of the pre-trained models included with the OpenVINO™ toolkit. The region found by one model becomes the input to the next. Vehicle regions found by object recognition in the first phase become the input to the vehicle attributes model, which locates the license plate. The region identified in this step becomes the input to a license plate character recognition model.


	sudo ./demo_squeezenet_download_convert_run.sh

#### Other Important Information

<ul>

<li>For documentation on the demo apps, see the README.txt file in the <INSTALL_DIR>/deployment_tools/demo directory.</li>

<li> The Inference Engine Samples can be found in the following directory: <INSTALL_DIR>/deployment_tools/inference_engine/samples/

<ul>
<li>For information about building and running the samples, please see the [Inference Engine Developer Guide - Building the Sample Applications on Linux](https://software.intel.com/en-us/articles/OpenVINO-InferEngine).</li>

<li>For detailed information about the samples, please see the <strong>samples overview documentation</strong> included in the installation.</li>
</ul>

<li>You may need to take additional steps before using the Model Optimizer to start working with your trained model. Please see the [Model Optimizer Guide](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer) for information on how to configure your Caffe*, TensorFlow*, or MXNet* framework.</li>

<li>Additional developer guides, API references, tutorials, and other documentation, see the [OpenVINO Toolkit documentation](https://software.intel.com/en-us/openvino-toolkit/documentation/featured).</li>

</ul>

## Next Steps

[Hello World | Part 2: Re-purpose a Pedestrian Detection application to identify cars](https://)  (coming soon)

[Determine the right balance between power, performance and form-factor (CPU vs GPU)](https://)  (coming soon)

[How to use Model Optimizer with custom layers](https://)  (coming soon)

<br>


<br>

***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
