# TensorRT Custom Plugin Example

Adapted Gelu Plugin from https://github.com/NVIDIA/TensorRT/tree/master/plugin/geluPlugin

## Train model with GeLu 
The [model](https://github.com/codesteller/trt-custom-plugin/blob/45532a116791cd6ffb5a607db3adccadbeabe035/tf_utils/model.py#L14) can be trained using the script do_train.py.

## Save the Models
The do_train.py saves the model after training.

## Converting the Model
Before the model is converted to tensorRT engine file we need to compile the custome plugin.
### Compiling the custom layer
Custom TensorRT layer for Gelu is inside the "geluPluginv2" directory. To compile the gelu custom layer,
```
cd geluPluginv2
mkdir build && cd build
cmake ..
```

### Convert model to TRT Engine
You can use the converter.py in the trt_utils directory to do this. Please change this [line](https://github.com/codesteller/trt-custom-plugin/blob/45532a116791cd6ffb5a607db3adccadbeabe035/trt_utils/trt_inference.py#L12) to the correct path in your system

## Inference code
You can run the inference.py code in trt_utils directore. Like the last section please change the path to the libGeluPlugin.so.

# More Details
For more details please refer the [documentation](https://github.com/codesteller/trt-custom-plugin/blob/ce657aac93ed70bee9da18913a46127ffda9efbe/Extending_TensorRT_with_custom_layers.pdf)

