## ⚡ First Order Motion Model for Image Animation ⚡

This repository contains source code for the paper [First Order Motion Model for Image Animation](https://papers.nips.cc/paper/8935-first-order-motion-model-for-image-animation) by Aliaksandr Siarohin, [Stéphane Lathuilière](http://stelat.eu), [Sergey Tulyakov](http://stulyakov.com), [Elisa Ricci](http://elisaricci.eu/) and [Nicu Sebe](http://disi.unitn.it/~sebe/). 
This repository is taken from a Youtube video by [Two Minute Papers](https://www.youtube.com/watch?v=mUfJOQKdtAk&t=17s)

Original Aliaksandr Siarohin Repo: [Github](https://github.com/AliaksandrSiarohin/first-order-model)<br>
Two Minute Papers Youtube Video Link : [Youtube-Video](https://www.youtube.com/watch?v=mUfJOQKdtAk&t=17s)

### 📝 Model Output
![Screenshot](https://github.com/snehitvaddi/Deep-Fake_First_Order_Model/blob/master/sup-mat/vox-teaser.gif)
### 🖼 Example on Custom Data
<img src="https://github.com/snehitvaddi/Deep-Fake_First_Order_Model/blob/master/sup-mat/download.gif" width="700" height="350"></a>
### 🔬 COLAB DEMO
You can run this code from  [GOOGLE COLAB](https://colab.research.google.com/drive/11YHTBYpBDoG28RwmVKj2VYt2jBblMh1M?usp=sharing)
### 📌 Installation
This code supports ```python3```. To install the dependencies run:
```
pip install -r requirements.txt
```
### 🕶 Pre-trained checkpoint
Checkpoints can be found under following link: [google-drive](https://drive.google.com/open?id=1PyQJmkdCsAkOYwUyaj_l-l0as-iLDgeH) or [yandex-disk](https://yadi.sk/d/lEw8uRm140L_eQ).

### ⚡ Animation Demo
To run a demo, download checkpoint and run the following command:
```
python demo.py  --config config/dataset_name.yaml --driving_video path/to/driving --source_image path/to/source --checkpoint path/to/checkpoint --relative --adapt_scale
```
The result will be stored in ```result.mp4```.

The driving videos and source images should be cropped before it can be used in our method. To obtain some semi-automatic crop suggestions you can use ```python crop-video.py --inp some_youtube_video.mp4```. It will generate commands for crops using ffmpeg. In order to use the script, face-alligment library is needed:
```
git clone https://github.com/1adrianb/face-alignment
cd face-alignment
pip install -r requirements.txt
python setup.py install

### ⚖ Training on your own dataset
1) Resize all the videos to the same size e.g 256x256, the videos can be in '.gif', '.mp4' or folder with images.
We recommend the later, for each video make a separate folder with all the frames in '.png' format. This format is loss-less, and it has better i/o performance.

2) Create a folder ```data/dataset_name``` with 2 subfolders ```train``` and ```test```, put training videos in the ```train``` and testing in the ```test```.

3) Create a config ```config/dataset_name.yaml```, in dataset_params specify the root dir the ```root_dir:  data/dataset_name```. Also adjust the number of epoch in train_params.

