# Longnao-Bridge-3D-Style-Migration

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

```
conda create --name nerfstudio -y python=3.8
conda activate nerfstudio
python -m pip install --upgrade pip
```

```
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 -f https://download.pytorch.org/whl/torch_stable.html
```

```
git clone https://github.com/colmap/colmap.git
cd colmap
git checkout dev
```

```
git fetch
git branch -a
git checkout dev
```

```
mkdir build
cd build
make
sudo make install
```

```
nvcc –version
which nvcc
sudo cmake .. -D CMAKE_CUDA_COMPILER="/usr/local/cuda/bin/nvcc" ../CMakeLists.txt -D CMAKE_CUDA_ARCHITECTURES='native'
```

```
colmap -h
```

```
sudo apt install ffmpeg
```

```
wget https://cmake.org/files/v3.18/cmake-3.18.0-Linux-x86_64.tar.gz
tar zxvf cmake-3.18.0-Linux-x86_64.tar.gz
sudo mv cmake-3.18.0-Linux-x86_64 /opt/cmake-3.18.0
sudo ln -sf /opt/cmake-3.18.0/bin/*  /usr/bin/
cmake --version
```

```
git clone --recursive https://github.com/nvlabs/tiny-cuda-nn
cd tiny-cuda-nn
pip install fmt
pip install cutlass
cmake . -B build
```

Check for working CUDA compiler: /usr/bin/nvcc 
```
exec /usr/local/cuda/bin/nvcc "$@"
```

```
cmake . -B build -DCMAKE_CUDA_COMPILER=/usr/local/cuda-11.4/bin/nvcc
```

```
cmake --build build --config RelWithDebInfo -j
cd bindings/torch
python setup.py install
```

```
python
import tinycudann
quit（）
```

```
git clone https://github.com/nerfstudio-project/nerfstudio.git
cd nerfstudio
pip install --upgrade pip setuptools
pip install -e .
```

```
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 -f https://download.pytorch.org/whl/torch_stable.html
```

```
git clone https://github.com/ayaanzhaque/instruct-nerf2nerf.git
cd instruct-nerf2nerf
pip install --upgrade pip setuptools
pip install -e .
```

```
pip uninstall functorch
pip install functorch==0.2.1
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 -f https://download.pytorch.org/whl/torch_stable.html
```

```
ns-train -h
```

```
ns-train nerfacto --data {PROCESSED_DATA_DIR}
```

```
ns-train in2n --data {PROCESSED_DATA_DIR} --load-dir {outputs/.../nerfstudio_models} --pipeline.prompt {"prompt"} --pipeline.guidance-scale 7.5 --pipeline.image-guidance-scale 1.5
```










