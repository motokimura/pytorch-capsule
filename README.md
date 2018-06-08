# CapsNet-PyTorch

A PyTorch implementation of CapsNet based on Geoffrey Hinton's paper [Dynamic Routing Between Capsules](https://arxiv.org/abs/1710.09829).

![capsVSneuron](images/capsule_vs_neuron.png)

This figure is from [CapsNet-Tensorflow](https://github.com/naturomics/CapsNet-Tensorflow).

## Current Status
- The current `test accuracy =  99.67 % (test error = 0.33)`, see `Results` section for details
- Trying to find the reason why the test accuracy is lower than the one reported in the paper

## Requirements

- [PyTorch](http://pytorch.org/) (with CUDA)
- [TensorBoard](https://github.com/tensorflow/tensorboard)
- [tensorboard-pytorch](https://github.com/lanpa/tensorboard-pytorch)

## Usage

**Step 1.** Clone this repository

```bash
$ git clone https://github.com/motokimura/CapsNet-PyTorch.git
$ cd CapsNet-PyTorch
```

**Step 2.** Start the training

```bash
$ python main.py
```

**Step 3.** Check training status and validation accuracy from TensorBoard

```bash
# In another terminal window, 
$ cd CapsNet-PyTorch
$ tensorboard --logdir ./runs

# Then, open "http://localhost:6006" from your browser and 
# you will see something like the screenshots in the `Results` section.
```

Some training hyper parameters can be specified from the command line options of `main.py`. 

At default, batch size is 128 both for training and validation, and epoch is set to 100. 
Learning rate of Adam optimizer is set to 0.001 and is exponentially decayed every epoch with the factor of 0.9. 

For more details, type `python main.py --help`.

## Results

Some results at default training settings are shown here.

### Train loss

![](images/train_loss.png)

### Test loss

![](images/test_loss.png)

### Test accuracy

![](images/test_accuracy.png)

Method     |   Routing   |   Reconstruction  |  Test error  |  *Paper*    
:---------|:------:|:---:|:----:|:----:
CapsNet-v1 |  1 | no | not tested yet  | *0.34 (0.032)* 
CapsNet-v2  |  1 | yes | not tested yet | *0.29 (0.011)*
CapsNet-v3 |  3 | no | not tested yet | *0.35 (0.036)*
CapsNet-v4  |  3 | yes| 0.33 | *0.25*

### Reconstruction results

![](images/reconstruction_results.png)

## License

[MIT License](LICENSE.txt)

## References

- [naturomics/CapsNet-Tensorflow](https://github.com/naturomics/CapsNet-Tensorflow)
- [XifengGuo/CapsNet-Keras](https://github.com/XifengGuo/CapsNet-Keras)
- [timomernick/pytorch-capsule](https://github.com/timomernick/pytorch-capsule)
