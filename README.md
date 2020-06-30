# Benchmark Scripts for Intel-Tensorflow

This repo has benchmark scripts for performance comparision of Intel Tensorflow vs Default Tensorflow.

Sanity check to see if MKL is enabled in Tensorflow.
```
python -c "import tensorflow; print(tensorflow.pywrap_tensorflow.IsMklEnabled())"
```
