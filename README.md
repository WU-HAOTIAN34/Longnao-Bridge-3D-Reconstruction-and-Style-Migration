# Longnao-Bridge-3D-Style-Migration

This is a quick toolkit for 3D style migration using nerfstudio and nerf2nerf

![img](https://github.com/WuHaotian0930/Longnao-Bridge-3D-Style-Migration/blob/main/res/output6.gif)


# Configure environment

## 1. Create a virtual environment

```
conda create --name nerfstudio -y python=3.8
conda activate nerfstudio
python -m pip install --upgrade pip
```

```
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 -f https://download.pytorch.org/whl/torch_stable.html
```

## 2. Installing tiny-cuda-nn

If you clone the repository, you can simply run the last command to complete the installation

```
git clone --recursive https://github.com/nvlabs/tiny-cuda-nn
cd tiny-cuda-nn
pip install fmt
pip install cutlass
cmake . -B build
```

If cuda cannot be found, use:

```
cmake . -B build -DCMAKE_CUDA_COMPILER=/usr/local/cuda-11.4/bin/nvcc
```

You can run the following command to view cuda and installation paths:

```
nvcc –version
which nvcc
```

```
cmake --build build --config RelWithDebInfo -j
cd bindings/torch
python setup.py install
```

```
python setup.py install
```

Check whether the installation is successful by performing the following operations:

```
python
import tinycudann
quit（）
```

## 3. Installing nerfstudio

```
git clone https://github.com/nerfstudio-project/nerfstudio.git
cd nerfstudio
pip install --upgrade pip setuptools
pip install -e .
```

If you clone the repository, you can simply run this command to complete the installation:

```
pip install -e .
```

Installing nerfstudio automatically installs the latest version of cuda, so you need to reinstall cuda:

```
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 -f https://download.pytorch.org/whl/torch_stable.html
```

## 4. Installing nerf2nerf

```
git clone https://github.com/ayaanzhaque/instruct-nerf2nerf.git
cd instruct-nerf2nerf
pip install --upgrade pip setuptools
```

If you clone the repository, you can simply run this command to complete the installation

```
pip install -e .
```

```
pip uninstall functorch
pip install functorch==0.2.1
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 -f https://download.pytorch.org/whl/torch_stable.html
```

Check whether the installation is successful by performing the following operations:

```
ns-train -h
```

## 5. Installing colmap and ffmpeg

```
sudo apt-get update
```

```
sudo apt-get install \
    git \
    cmake \
    ninja-build \
    build-essential \
    libboost-program-options-dev \
    libboost-filesystem-dev \
    libboost-graph-dev \
    libboost-system-dev \
    libeigen3-dev \
    libflann-dev \
    libfreeimage-dev \
    libmetis-dev \
    libgoogle-glog-dev \
    libgtest-dev \
    libsqlite3-dev \
    libglew-dev \
    qtbase5-dev \
    libqt5opengl5-dev \
    libcgal-dev \
    libceres-dev
```

```
sudo apt-get install -y \
    nvidia-cuda-toolkit \
    nvidia-cuda-toolkit-gcc
```

If there are errors, try:

```
cd /root
sudo su 
sudo vim /etc/apt/sources.list
Insert button
```

Insert the following content:

```
deb http://archive.ubuntu.com/ubuntu/ trusty main universe restricted multiverse
deb http://gb.archive.ubuntu.com/ubuntu/ bionic main universe
```

```
#中科大源
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse

#阿里云源
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse

#清华源
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
```

then:

```
Ese
：wq
Enter
```

```
sudo apt-get update
sudo apt upgrade
```

Installing cmake:

```
wget https://cmake.org/files/v3.18/cmake-3.18.0-Linux-x86_64.tar.gz
tar zxvf cmake-3.18.0-Linux-x86_64.tar.gz
sudo mv cmake-3.18.0-Linux-x86_64 /opt/cmake-3.18.0
sudo ln -sf /opt/cmake-3.18.0/bin/*  /usr/bin/
cmake --version
```

If you clone the repository, you can simply run the last command sudo make install to complete the installation:

```
git clone https://github.com/colmap/colmap.git
cd colmap
git checkout dev
```

if there are errors, try:

```
git fetch
git branch -a
git checkout dev
```

then:

```
mkdir build
cd build
make
sudo make install
```

```
sudo apt install ffmpeg
```

Check whether the installation is successful by performing the following operations:

```
colmap -h
```

## 6. Using custom data

You can get more information about nerfstudio from [here](https://docs.nerf.studio/quickstart/installation.html)

```
ns-process-data {video,images,polycam,record3d} --data {DATA_PATH} --output-dir {PROCESSED_DATA_DIR}
```

## 7. Training

You can get more information from [here](https://github.com/ayaanzhaque/instruct-nerf2nerf)

```
ns-train nerfacto --data {PROCESSED_DATA_DIR}
```

```
ns-train in2n --data {PROCESSED_DATA_DIR} --load-dir {outputs/.../nerfstudio_models} --pipeline.prompt {"prompt"} --pipeline.guidance-scale 7.5 --pipeline.image-guidance-scale 1.5
```

If you cannot connect huggingface.co, please access [here](https://huggingface.co/timbrooks/instruct-pix2pix), and try:

```
sudo apt-get install git-lfs
git lfs clone https://huggingface.co/timbrooks/instruct-pix2pix
```

Move the cloned repository to /root/.cache/huggingface/hub/models--timbrooks--instruct-pix2pix/snapshots/31519b5cb02a7fd89b906d88731cd4d6a7bbf88d (the location where the error shows the missing file)








