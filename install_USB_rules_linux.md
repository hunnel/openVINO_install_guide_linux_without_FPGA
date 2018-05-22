

# Intel® OpenVINO™ Toolkit | Post-Installation Steps for Intel® Movidius™ Neural Compute Stick (VPU)

## Prerequisites

- [ ] [Download and Install Intel® OpenVINO™ Toolkit for Linux*](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/readme.md)<br>

<br>

## Install USB Rules

> **Note:**  These steps are only required if you want to to perform inference on Intel® Movidius™ Neural Compute Stick using Intel® OpenVINO™ Toolkit.

The installation automatically creates the install_dependencies directory under /opt/intel/computer_vision_sdk. This directory contains several scripts to enable OpenVINO™ Toolkit to utilize processor graphics on your system.

    cat <<EOF > 97-usbboot.rules
    SUBSYSTEM=="usb", ATTRS{idProduct}=="2150", ATTRS{idVendor}=="03e7", GROUP="users", MODE="0666",     ENV{ID_MM_DEVICE_IGNORE}="1"
    SUBSYSTEM=="usb", ATTRS{idProduct}=="f63b", ATTRS{idVendor}=="03e7", GROUP="users", MODE="0666",    ENV{ID_MM_DEVICE_IGNORE}="1"
    EOF

<br>

    sudo cp 97-usbboot.rules /etc/udev/rules.d/
 
<br>
 
    sudo udevadm control --reload-rules
  
<br>
 
    sudo udevadm trigger
  
<br>
  
    sudo ldconfig
   
<br>
   
    rm 97-usbboot.rules

<br>

## Next Steps

[Hello World Tutorial for Linux (w/o FPGA)](https://github.com/hunnel/openVINO_install_guide_linux_without_FPGA/blob/master/hello_world_tutorial_linux.md)

<br>


***

###### OpenCL is a trademark of Apple Inc. used by permission by Khronos   
###### Intel is a registered trademark of Intel Corporation
###### &ast;Other brands and names may be the property of others
