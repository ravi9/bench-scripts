## Benchmarking on Azure Intel Optimized DSVM

This repo contains benchmarking scripts for training and inference on common CNN topologies/networks in TensorFlow: 

* Inception V3
* ResNet 50
* ResNet 152
* VGG 16

Each script run takes the following actions:

1. Parses the arguments `-n` for setting the networks and `-i` for setting either training or inference. 
2. Detects which version of TensorFlow is present and clones the compatible branch of the [official TensorFlow benchmarks repo](https://github.com/tensorflow/benchmarks).
3. Installs default tensorflow.
4. Runs `tf_cnn_benchmarks.py` in the default environment.
5. Activates the Intel optimized tensorflow virtualenv and runs `tf_cnn_benchmarks.py` in the Intel Optimized environment.
6. Prints the throughput with relative speedups realized with Intel Optimized TensorFlow.

**NOTE:** Running the entire benchmarking suite may take some time depending on the hardware you're running on, so please be patient while it is executing.


#### Steps to run training benchmark:

First download the script
```
wget https://raw.githubusercontent.com/ravi9/bench-scripts/master/Azure/azure_dsvm_tf_bench.sh

```
#### Usage Examples:
Run Inference benchmark with resnet50 with BZ=32
```
bash azure_dsvm_tf_bench.sh
```

Run Training benchmark with vgg16 with BZ=32
```
bash azure_dsvm_tf_bench.sh -n "vgg16" -i "False"
```

Run Inference benchmark with vgg16 with BZ=32
```
bash azure_dsvm_tf_bench.sh -n "vgg16"
```

Run Training benchmark with inception3, resnet50, resnet152, vgg16 with BZ=32, 64, 128
```
bash azure_dsvm_tf_bench.sh -n "all" -i "False"
```

Run Inference benchmark with inception3, resnet50, resnet152, vgg16 with BZ=32, 64, 128
```
bash azure_dsvm_tf_bench.sh -n "all"
```


