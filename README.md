# tensorflow object detection with your own images
Using tensorflow object detection API with your own image set

The create_tf_record.py is a modified version of the original create_pet_tf_record.py that is given in tensorflow object detection API as an example. 

The original create_pet_tf_record.py targets at a specifically formatted images set and annotations and generate corresponding .record files that can be used for model training. The modified create_tf_record.py can take any image sets and associated PASCAL formated annotations as input to generate .record files. 
