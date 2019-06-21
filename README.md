# tensorflow_image_classifier

## Installation Guide

**1. Download Android Studio** *( https://developer.android.com/studio/)*   **and Git**  *(https://git-scm.com/downloads)* <br/>

**2. Download and unzip the file OR To clone the file, go to command prompt or terminal and type the following**
```
git clone <link>
```

## Creating an Image Classfication Tensorflow Model



## Retraining an existing model

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
