

# Intel® OpenVINO™ Toolkit <br>Configure the Model Optimizer on Linux*

The Model Optimizer produces an Intermediate Representation (IR) of the network as output. The Inference Engine reads, loads, and infers the Intermediate Representation. The Inference Engine API offers a unified API across supported Intel® platforms. The Intermediate Representation is a pair of files that describe the whole model:

<strong>.xml</strong>: Describes the network topology<br>
<strong>.bin</strong>: Contains the weights and biases binary data
   
<br>

## Configure the Model Optimizer

You must configure the Model Optimizer for the framework that was used to train the model. This section tells you how to configure the Model Optimizer through scripts provided with installation.

> Model Optimizer currently supports Caffe*, TensorFlow* and MXNet*

> For instructions on how to configure Model Optimizer manually, see the [Model Optimizer Developer Guide](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer)

#### To configure all three frameworks at the same time: 

<ol>
    <li> Navigate to the Model Optimizer prerequisites directory</li><br>

    cd <INSTALL_DIR>/deployment_tools/model_optimizer/install_prerequisites directory

<li> Run the following script to configure Model Optimizer for Caffe, TensorFlow and MXNet</li><br>

    ./install_prerequisites.sh

</ol>

#### To configure each framework separately: 

<ol>
    <li> Navigate to the Model Optimizer prerequisites directory</li><br>
    

    cd <INSTALL_DIR>/deployment_tools/model_optimizer/install_prerequisites directory

<li> Run the script necessary for your model framework</li><br>

<ul>

<li> For Caffe* on Linux*</li><br>

    ./install_prerequisites_caffe.sh

<li> For TensorFlow* on Linux*</li><br>

    ./install_prerequisites_tf.sh

<li> For MXNet* on Linux*</li><br>

    install_prerequisites_mxnet.sh

</ul>

</ol>

> <strong>CAFFE* NOTE:</strong> By default, you do not need to install Caffe to create an Intermediate Representation for a Caffe model unless you use Caffe for custom layer shape inference and do not write Model Optimizer extensions. To learn more about implementing Model Optimizer custom operations and the limitations of using Caffe for shape inference, see [Caffe Models with Custom Layers](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer#caffe-models-with-custom-layers).

> <strong>TENSORFLOW* NOTE:</strong> Additional configuration steps are required to offload part of the inference to the TensorFlow framework. See the [Model Optimizer Developer Guide](https://software.intel.com/en-us/articles/OpenVINO-ModelOptimizer#Offloading%20Computations%20to%20TensorFlow) for detailed information.

<br>

## Next Steps

[How to Run the Sample Applications on Linux*]()

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
