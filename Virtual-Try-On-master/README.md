# Virtual-Try-On

This project has wrapped a complete pipline of virtual try on based on official implementations of [cp-vton](https://github.com/sergeywong/cp-vton), [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) and [JPPNet](https://github.com/Engineering-Course/LIP_JPPNet).

## Installation
* **Important**: Python-3.6.5, Tensorflow-1.13.1, pytorch-1.3.0, torchvision-0.2.1 
* Download [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) to the```OpenPose``` directory and compile it according to its instruction.
* Download pre-trained model for [JPPNet](https://github.com/Engineering-Course/LIP_JPPNet) and put it under ```LIP_JPPNet/checkpoint/JPPNet-s2/```. There should be 4 files in this directory: checkpoint, model.ckpt-xxx.data-xxx, model.ckpt-xxx.index, model.ckpt-xxx.meta.
* Download pre-trained models for [cp-vton](https://github.com/sergeywong/cp-vton) and put them under ```cp_vton/checkpoints/```. There should be two folders as ```gmm_train_new``` and ```tom_train_new``` in this directory. The authors have not provided the original models but you may download the models from [a re-implemented one](https://github.com/cinastanbean/cp-vton).

## Usage
* Put the image and cloth under ```data/raw_data/image``` and ```data/raw_data/cloth``` respectively.
* Use OpenPose to get the pose information. Please refer to the [instructions](https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/demo_overview.md) from OpenPose. Some key parameters: ```--image_dir YOUR_IMAGE_PATH --model_pose COCO --write_json RESULT_PATH```. Put the .json result in ```data/raw_data/pose/```.
* Run ```python try_on.py``` to get the result.
* The result will be put in ```result/```.
