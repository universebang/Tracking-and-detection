# py-MDNet-Keras

by [Jacques Thibodeau](https://www.linkedin.com/in/jacques-thibodeau-483030a1/)

## Introduction
Python (Keras) implementation of MDNet tracker. 
#### [[Project]](http://cvlab.postech.ac.kr/research/mdnet/) [[Paper]](https://arxiv.org/abs/1510.07945) [[Matlab code]](https://github.com/HyeonseobNam/MDNet)

It is based off the PyTorch implementation by the authors [Hyeonseob Nam](https://www.linkedin.com/in/hyeonseob-nam/?ppe=1) and [Bohyung Han](http://cvlab.postech.ac.kr/~bhhan/) at POSTECH. You can view that implementation [here](https://github.com/HyeonseobNam/py-MDNet).

If you're using this code for your research, please cite:

	@InProceedings{nam2016mdnet,
	author = {Nam, Hyeonseob and Han, Bohyung},
	title = {Learning Multi-Domain Convolutional Neural Networks for Visual Tracking},
	booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
	month = {June},
	year = {2016}
	}
 
## Prerequisites
- python 3.5
- [Keras](https://github.com/fchollet/keras) and its dependencies
- [Tensorflow](https://www.tensorflow.org/)
- [Numpy](http://www.numpy.org/)
- [h5py](http://www.h5py.org/) (For Keras model serialization.)
- [Pillow](https://pillow.readthedocs.io/) (For rendering test results.)

## Usage

### Tracking
```bash
 cd tracking
 python run_tracker.py -s DragonBaby [-d (display fig)] [-f (save fig)]
```
 - You can provide a sequence configuration in two ways (see tracking/gen_config.py):
   - ```python run_tracker.py -s [seq name]```
   - ```python run_tracker.py -j [json path]```
 
### Pretraining
 - Download [VGG-M](http://www.vlfeat.org/matconvnet/models/imagenet-vgg-m.mat) (matconvnet model) and save as "models/imagenet-vgg-m.mat"
 - Download [VOT](http://www.votchallenge.net/) datasets into "dataset/vot201x"
``` bash
 cd pretrain
 python prepro_data.py
 python train_mdnet.py
```
