#NeuralTalkServer

[NeuralTalk2](https://github.com/karpathy/neuraltalk2)


##Instruction

Download this repository.

```

$ git clone https://github.com/kiyomaro927/NeuraltalkServer.git

```

Download the pretrained checkpoint.

This is [pretrained checkpoint link](http://cs.stanford.edu/people/karpathy/neuraltalk2/checkpoint_v1.zip)
If you only have cpu, download the [cpu model checkpoint](http://cs.stanford.edu/people/karpathy/neuraltalk2/checkpoint_v1_cpu.zip)


## Run the local server

```

$ python neuralTalkServer.py

```

## Check operation

```
$ curl -F "file=@path/to/img" localhost:8000
```

