## cross entropy in Pytorch
**F.cross_entropy** will apply softmax and log to the output while **F.nll_loss** will not so you have to apply **F.log_softmax** to the output when the model returns.
As for dim, since the output is a matrix containing all the nodes and the size is NxF(N is the number of nodes and F is the length of the node features), the dim should be set to 1.

## early stopping in Pytorch
3rd lib *early-stopping-pytorch* is easy to use. Remember to detach the val_loss before using. If the model is trained by GPU, to.("cpu") should be called after detach()