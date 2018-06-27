# Unsupervised Vehicle Re-Identification using Triplet Networks

This repository contains the code of track3 in the NVIDIA AI City Challenge at CVPRW 2018, in which the sixth place was obtained.

## Introduction

This repository contains our implementation to vehicle re-identification. We use a SSD detector to detect the different vehicles and then, a triplet architecture based on VGG to generate an embedded feature space. After that, a quadruple strategy is used to match the vehicles.

## Code structure

1.	In ```data_parser``` is the code to generate the dataset of one video. After in ```utils/preProcesedDataSets.py``` is the code to remove wrong detections.
2.	In ```utils```, you have utilities to shuffle the dataset (```shuffleDataSet.py```), concatenate different datasets generated by the ```data_parser``` (```concatDataSets.py```) and in the case that you have cropped the video, a script to store the true bounding box of the detection (```correctBoundingboxDataSet.py```).
3.	```trainTriplet.py``` generates a model that is used in ```reduced_dataSet_generator.py``` to transform the detections to a new feature vector generating a new reduced dataset with only one frame per vehicle ID.
4.	The re-id strategy is comprised in ```sorted_quadrupla_list_generation.py``` script.
5.	To output the results in the format of the challenge, you can use ```k_top_output-template.py```.

## Resources

1. Pretrained SSD model. <a href="http://mozart.dis.ulpgc.es/~pedro/resources/NVIDIACHACHENGE18-models/VGG_coco_SSD_300x300_iter_400000.h5">detector_model</a>
2. Trained triplet network model, dimension of 100 to feature embedding. <a href="http://mozart.dis.ulpgc.es/~pedro/public_html/resources/NVIDIACHACHENGE18-models/modelBatch64embe100.hdf5">triplet_model</a>

## Reference

Pedro A. Marín-Reyes, Andrea Palazzi, Luca Bergamini, Simone Calderara, Javier Lorenzo-Navarro, Rita Cucchiara. <a href="http://mozart.dis.ulpgc.es/~pedro/resources/pdf/cvpr18.pdf"> Unsupervised Vehicle Re-Identification using Triplet Networks</a>, in Proc. IEEE/CVF International Conference on Computer Vision and Pattern Recognition Workshops (CVPRW). Salt Lake City, EEUU, June 2018.
