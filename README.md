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
all of our data (images and corresponding .pts file of keypoints), should be places in ./data0/Train_set/data/.  <br>
Already, I have put some data for fasting start. <br>
use following command to generate the training pickle: <br>
> python ./RCN/preprocessing/create_raw_300W.py --src_dir=./data0/ --dest_dir=./data0

now, move the generated pickle file to the path which is necessary for RCN by: <br>
> mv -f ./data0/300W_train_160by160.pickle ./RCN/datasets/300W/

## train:

For training the RCN on 68 landmark dataset use following line: <br>
> python ./RCN/models/create_procs.py --L2_coef=1e-12 --L2_coef_ful=1e-08 --file_suffix=RCN_300W_test --num_epochs=1 --paral_conv=5.0 --use_lcn --block_img

do not forget to set the num_epochs.  <br>
After training the trained model and training information would be places at .\RCN\models\exp_shared_conv\  <br>

## prediction

For prediction, it is assumed the test images and gtound truth keypoints are in a pickle.
e.g. Data_Test.pickle in data0 folder with following data structure. X contains images (10 images, gray scale, with size 80x80) and  truth_kpts are the corresponding landmarks. <br>
![Alt text](screen-21.58.58[16.05.2019].png?raw=true "Title") <br>

Note that, for RCN we should prepared our test data such as above config. image size=80x80 and gray scale. 

use following line to predict by trained network. A picke contains both ground truth and predicted keypoints would be generated in outputs folder.
> python ./RCN/plotting/export_draw_points_guide.py  --img_path=./data0/Data_Test.pickle  --path=./RCN/models/exp_shared_conv/shared_conv_params_RCN_300W_test_300W.pickle  

![Alt text](screen-22.05.34[16.05.2019].png?raw=true "Title") <br>


