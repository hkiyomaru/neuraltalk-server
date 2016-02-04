#NeuralTalkServer

This is a server program to return an image caption.

To create a caption, I use [NeuralTalk2](https://github.com/karpathy/neuraltalk2).

##Preparation to run the NeuralTalk2

Neuraltalk2 is writeen in Lua (and requires Torch).

If you use Ubuntu, installation is like this.

```
$ curl -s https://raw.githubusercontent.com/torch/ezinstall/master/install-deps | bash

$ git clone https://github.com/torch/distro.git ~/torch --recursive

$ cd ~/torch

$ ./install.sh      # and enter "yes" at the end to modify your bashrc

$ source ~/.bashrc
```

After Torch is installed, you have to get a few more packages.

```
$ luarocks install nn

$ luarocks install nngraph

$ luarocks install image
```

If __you'd like run this on an NVIDIA GPU using CUDA__, you have to install the [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit).

And get the below packages.

```
$ luarocks install cutorch

$ luarocks install cunn
```

If __you'd like to use the cudnn backend(the pretrained checkpoint dose)__, you also have to install cudnn.

First, register with [NVIDIA Website](https://developer.nvidia.com/cuDNN) and download cudnn library.

Then set your LD_LIBRARY_PATH to point to the lib64 folder that contains the library.

Then git clone the ```cudnn.torch``` repo, ```cd inside```, and do ```luarocks make cudnn-scm-1.rockspec```.

If you'd like to know details of the instllation, click [this link(original page)](https://github.com/karpathy/neuraltalk2).


##Instruction

Download this repository.

```
$ git clone https://github.com/kiyomaro927/NeuraltalkServer.git
```

I tweaked eval.lua, so you have to install luasocket.


```
luarocks install luasocket
```

This package supports Lua5.1 only.

So, if your Lua version is not 5.1, please match the Lua version.

If you use Ubuntu, this install is very simple.

```
sudo apt-get install lua5.1
```

Download the pretrained checkpoint to model directory.

This is [pretrained checkpoint link](http://cs.stanford.edu/people/karpathy/neuraltalk2/checkpoint_v1.zip)

__If you only have cpu__, download the [cpu model checkpoint](http://cs.stanford.edu/people/karpathy/neuraltalk2/checkpoint_v1_cpu.zip)



## Run the local server

```

$ python neuralTalkServer.py

```

If you'd like to run without using GPU,

```

$ python neuralTalkServer.py -cpu

```


## Check operation

```
$ curl -F "file=@path/to/img" localhost:8000
```
