# Train-Predict-Landmarks-by-RCN
this repository is dedicated to train and use the RCN method (Recombinator Networks) for landmark localization/detection.
The source and original repository is https://github.com/SinaHonari/RCN and please consider that first.
The original repository was very dependent to the face datasets and this repository is an example for how to deal with that and use RCN for our dataset. For this reason some of the RCN scripts are modified.
My interest was just 68 landmarks version of the paper.

## set up:
-Ubuntu 16.4
-python 2.7
-create your python environment if you prefer
-install opencv
    pip install opencv-python
    pip install opencv-contrib-python
-install pil
    pip install Pillow

-install theano
    
-create config file for theano
echo -e "\n[global]\nfloatX=float32\n" >> ~/.theanorc

## adding RCN to python path:
> export PYTHONPATH=/path/to/parent/dir/of/our-repository:$PYTHONPATH
e.g.
> export PYTHONPATH=~/Desktop/Train-Predict-Landmarks-by-master:$PYTHONPATH

## prepare train data:

## train:


## prediction





