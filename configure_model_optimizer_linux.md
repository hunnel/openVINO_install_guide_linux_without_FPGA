

# Intel® OpenVINO™ Toolkit <br>Configure the Model Optimizer on Linux*

The Model Optimizer process assumes you have a network model that was trained with a supported framework.

## Configure the Model Optimizer

You must configure the Model Optimizer for the framework that was used to train the model. This section tells you how to configure the Model Optimizer through scripts provided with installation.

> For instructions on how to configure Model Optimizer manually, see the [Model Optimizer Developer Guide](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer)

#### To configure all three frameworks at the same time: 

<ol>
    <li> Navigate to the Model Optimizer prerequisites directory

        cd <INSTALL_DIR>/deployment_tools/model_optimizer/install_prerequisites directory

<li> Run the following script to configure Model Optimizer for Caffe, TensorFlow and MXNet

    install_prerequisites.sh

</ol>

#### To configure each framework separately: 

<ol>
    <li> </li>

<ul>

<li> For Caffe on Linux:</li>

    install_prerequisites_caffe.sh

<li> For TensorFlow on Linux:</li>

    install_prerequisites_tf.sh

<li> For MXNet on Linux:</li>

    install_prerequisites_mxnet.sh

</ul>

</ol>

> **CAFFE* NOTE:** By default, you do not need to install Caffe to create an Intermediate Representation for a Caffe model unless you use Caffe for custom layer shape inference and do not write Model Optimizer extensions. To learn more about implementing Model Optimizer custom operations and the limitations of using Caffe for shape inference, see [Caffe Models with Custom Layers](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer#caffe-models-with-custom-layers).

> **TENSORFLOW* NOTE:** To offload part of the inference to the TensorFlow framework, additional configuration steps are required. See the [Model Optimizer Developer Guide](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer#Offloading%20Computations%20to%20TensorFlow) for detailed information.

<br>

## Next Steps

[How to Run the Sample Applications on Linux*]()

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
