# tensorflow object detection with your own images
Using tensorflow object detection API with your own image set

The create_my_tf_record.py is a modified version of the original create_pet_tf_record.py that is given in tensorflow object detection API as an example. 

The original create_pet_tf_record.py targets at a specifically formatted images set and annotations and generate corresponding .record files that can be used for model training. The modified create_my_tf_record.py can take any image sets and associated PASCAL formatted annotations as input to generate .record files. 

Usage: 

1. Create a data directory /path/to/data/
2. Under the above directory, make two directories 'images' and 'annotations', and under the 'annotations' make another directory 'xmls'
3. Create a label map .pbtxt file that contains the your class information. Something like the tensorflow example https://github.com/tensorflow/models/blob/master/object_detection/data/pet_label_map.pbtxt but with your own classes
4. Put all your sample images (.jpeg) under /path/to/data/images
5. For annotations xml files, you can use this tool https://github.com/tzutalin/labelImg.git . Put all xml files under /path/to/data/annotations/xmls.
6. Download create_my_tf_record.py and put it under tensorflow/models/object_detection/. Then open terminal, cd to that directory and run: 
```
$ python create_my_tf_record.py --data_dir=/path/to/data/ \
                           --output_dir=/path/to/output \
                           --label_map_path=/path/to/label/map/file
```
7. You will then find the generated train.record and val.record files at /path/to/output

Then with the .record files and your label map, you can proceed to train the model as instructed in the example https://github.com/tensorflow/models/blob/master/object_detection/g3doc/running_pets.md
