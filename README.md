# Cloud 9 Perecption

### UPDATE AND INSTALL PACKAGES ###
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install gedit git build-essential cmake cmake-curses-gui meld codeblocks unzip

### REMOVE PACKAGES ###
sudo apt-get remove libreoffice*

### DOWNLOAD AND INSTALL CUDA 9.1 ###
wget https://developer.nvidia.com/compute/cuda/9.1/Prod/local_installers/cuda-repo-ubuntu1604-9-1-local_9.1.85-1_amd64

sudo dpkg -i cuda-repo-ubuntu1604-9-1-local_9.1.85-1_amd64.deb
sudo apt-key add /var/cuda-repo-9-1-local/7fa2af80.pub
sudo apt-get update
sudo apt-get install cuda

### ADD CUDA ENTRIES TO BASHRC ###
echo '# add cuda entries' >> ~/.bashrc
echo 'export PATH=/usr/local/cuda/bin:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc

### Dependencies for PCL ###
sudo apt-get install libboost-all-dev libeigen3-dev libflann-dev libglew-dev libxmu-dev libsuitesparse-dev libqhull-dev libpcap-dev libxmu-dev libxi-dev libgtest-dev libvtk6-dev libqt5opengl5-dev

### JDK Java Development Kit ###
cd Downloads
Download - http://www.oracle.com/technetwork/java/javase/downloads/jdk9-downloads-3848520.html
tar zxvf jdk-9.0.1_linux-x64_bin.tar.gz 

sudo mkdir -p /usr/lib/jvm/
sudo cp -r jdk-9.0.1/ /usr/lib/jvm/

Making it Default:
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk-9.0.1/bin/java" 1
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk-9.0.1/bin/javac" 1

Manual Selecting/Checking:
sudo update-alternatives --config java
sudo update-alternatives --config javac

java -version
javac -version


### OpenNI2 ###

https://drive.google.com/a/cloud9perception.com/file/d/1VbvWS7ekSEa8D-hQNK4WmGFLaed7mhfQ/view?usp=sharing
tar zxvf OpenNI-Linux-x64-2.2.0.33.tar.bz2
cd OpenNI-Linux-x64-2.2
sudo chmod a+x install.sh
sudo ./install.sh


### PCL from Source ###
cd ~
sudo apt-get install git
git clone https://github.com/PointCloudLibrary/pcl pcl-trunk
cd pcl-trunk

cd pcl-trunk && mkdir build && cd build
ccmake ..
make -j4
sudo make -j4 install

sudo apt-get install libproj-dev   ## incase it gives libproj.so error





