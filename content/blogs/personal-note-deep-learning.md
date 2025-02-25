Title: Personal note on deep learning
Date: 2023-11-19 00:00

# CNN
- Default stride is 1
- According to [Wikipedia](https://en.wikipedia.org/wiki/Convolutional_neural_network#Convolutional_layer), the output height/width of a convolutional layer (per channel) is given by
    $$\left\lfloor\frac{W-K+2P}{S}+1\right\rfloor$$
    where $W$ is the input size, $K$ is the filter size, $P$ is the padding size and $S$ is the stride.

# Batch normalisation
- In FC layer, normalise per mini-batch
- In Conv layer, normalise per channel. Per sample normalisation can also be done, which is called layer normalisation.
- Batch normalisation (BN) layer is inserted after FC/Conv layer and before activation layer.
- Batch size becomes an important tunable parameter

# Freezing layers
In addition to controlling `param.requires_grad`, I need to enable `eval()` mode corresponding to `batchnorm layers`, if any. Details: [https://discuss.pytorch.org/t/should-i-use-model-eval-when-i-freeze-batchnorm-layers-to-finetune/39495](https://discuss.pytorch.org/t/should-i-use-model-eval-when-i-freeze-batchnorm-layers-to-finetune/39495)

# PyTorch
- `len(dataloader)`: number of batches
- `len(dataloader.dataset)`: number of samples

# Norm
- Nicely explained in [this SO answer](https://stackoverflow.com/a/68490074).
