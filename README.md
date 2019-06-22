# tensorflow_image_classifier

## Installation Guide

**1. Download Android Studio** *( https://developer.android.com/studio/)*   **and Git**  *(https://git-scm.com/downloads)* <br/>

**2. Download and unzip the file OR To clone the file, go to command prompt or terminal and type the following**
```
git clone https://github.com/Thumar/tansorflow-lite.git
```

## Retraining an existing model

**Note: Python 3.7 is currently not entirely compatible with TensorFlow**

This is a workaround for the issue. 

**Download and Install Anaconda** *(https://www.anaconda.com/distribution/)*

**1. Once it is installed, open the Anaconda prompt and install the following things**

```
conda create --name tensorflow python=3.6
```
**Windows:**
```
activate tensorflow
```
**Mac:**
```
source activate tensorflow
```

**Install Jupyter notebook**
```
conda install jupyter
```


```
python3 retrain.py --image_dir data_dir \
--saved_model_dir saved_model_dir \
--bottleneck_dir bottleneck_dir \
--how_many_training_steps 2000 \
--output_labels output/output_labels.txt \
--output_graph output/retrain.pb
```

## Converting a Tensorflow model to Tensorflow lite

```
import tensorflow as tf

converter = tf.lite.TFLiteConverter.from_saved_model(saved_model_dir)
tflite_model = converter.convert()
open("converted_model.tflite", "wb").write(tflite_model)
```
