# Cloud9Perecption

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
