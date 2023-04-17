This ReadMe describes the how to use the scripts in the MorphologyML.tar 

MorphologyML.tar has 3 scripts:

feature_generating.py
image_splitting_loop.py
CNN_model_loop.py 




feature_generating.py

File input: Reads in a two-channel tif, the staining that is to be compared should be on channel 1, input type for 
image can be changed by modifying the following function: multichannel_image[0, :, :]

This script is used to generate features from images using the package pyclesperanto_prototype
This script loops through a directory of images, opens up images, uses cellpose to segment images, then gets the values for the features
associated with pyclesperanto_prototype. The final product of the feature_set_generation function is a table where the column headers are
feature names and each row corresponds to a different cell. 
This script then utilizes sklearn to implments RandomForests, LogisticRegression and MLP machine learning models




image_splitting_loop.py

File inputs: Reads in two-channel tifs
This script is nescarry for getting individual images for the CNN model (which requires individual images as input) 

This script splits images (40x zoom) into squares of 200x200 pixels surronding a nucleus.
Directories are cycled through so that all images within a directory are split





CNN_model_loop.py 

File inputs: Reads in 200x200pixel 1 channel black and white images. If input is changed; array stacking, model input shape and result array also need to be changed