# Train-Predict-Landmarks-by-RCN
this repository is dedicated to train and use the RCN method (Recombinator Networks) for landmark localization/detection. <br>
The source and original repository is https://github.com/SinaHonari/RCN and please consider that first. <br>
The original repository was very dependent to the face datasets and this repository is an example for how to deal with that and use RCN for our dataset. For this reason some of the RCN scripts are modified. <br>
My interest was just 68 landmarks version of the paper.

## set up:
- Ubuntu 16.4 <br>
- python 2.7 <br>
- create your python environment if you prefer <br>
- install opencv <br>
    pip install opencv-python <br>
    pip install opencv-contrib-python <br>
- install pil <br>
    pip install Pillow <br>

- install theano <br>
    
- create config file for theano <br>
echo -e "\n[global]\nfloatX=float32\n" >> ~/.theanorc <br>

## adding RCN to python path: 
> export PYTHONPATH=/path/to/parent/dir/of/our-repository:$PYTHONPATH <br>
e.g. <br>
> export PYTHONPATH=~/Desktop/Train-Predict-Landmarks-by-master:$PYTHONPATH <br>

## prepare train data:

## train:


## prediction





