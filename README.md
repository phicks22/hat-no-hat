# hat-no-hat
PA2-deliverables for CSCI 5931

## Training data
I generated a training dataset of 43 images  

## Network

I chose to use the cascading residual network architecture developed by Ahn _et al_ (2018) \[1\]. 

GitHub repo: https://github.com/nmhkahn/CARN-pytorch/tree/master

This method was developed for resolution enhancement of images, not classification. Although it wasn't used for classification, I chose it because I've used it before for resolution enhancement and wanted to see how the learned feature maps perform in classification tasks.


\[1\] Ahn, N., Kang, B., & Sohn, K. A. (2018). Fast, accurate, and lightweight super-resolution with cascading residual network. In Proceedings of the European conference on computer vision (ECCV) (pp. 252-268).

## Compute environment

I used two t4 GPUs. 
