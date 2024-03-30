# hat-no-hat
PA2-deliverables for CSCI 5931

## Training data
I generated a training dataset of 43 images. These images are of my room mate and I wearing different hats from
different angles and I tried to collect images from multiple types of backgrounds and facial expressions. However, the 
dataset is definitely too small and not diverse enough.

The training set is too big to store on GitHub, but can be found in my Google drive at this link:
https://drive.google.com/file/d/1h_703Jdt-u__73my9c_T5ZpJE2Dqi13i/view?usp=sharing
or on Kaggle: https://kaggle.com/datasets/83ae4dd02ce91faad8fcf8d7ec19c5180c82b48097a942a1f67166136a0dce2d

## Network

I chose to use the cascading residual network architecture developed by Ahn _et al_ (2018) \[1\]. 

GitHub repo: https://github.com/nmhkahn/CARN-pytorch/tree/master

This method was developed for resolution enhancement of images, not classification. 
Although it wasn't used for classification, I chose it because I've used it before for resolution enhancement, it 
performed very well for that task, and I wanted to see how the learned feature maps perform in classification tasks.
I used the default hyperparameters set by the authors of this model.

To apply the model to a classification task, I added a 3-layered MLP that takes the flattened vector of feature maps as 
input with a single output node to classify images as being positively labeled as 'hat' or not. No hyperparameter tuning
was performed on this MLP classifier.

The loss function used was binary cross entropy loss.

\[1\] Ahn, N., Kang, B., & Sohn, K. A. (2018). Fast, accurate, and lightweight super-resolution with cascading residual
network. In Proceedings of the European conference on computer vision (ECCV) (pp. 252-268).

## Compute environment

I used two t4 GPUs on Kaggle.

## Results

I trained the model with 25, 50, 100, and 150 epochs. Given that my training dataset only consisted of 43 images the 
model would overfit using a higher number of epochs in training. The highest performance I got was 62% using 25 epochs.
The model tends to output high probabilities for most samples and the best threshold I found for considering a sample
as positive was 0.999. The model definitely needs more training data consisting of more diverse settings (background,
hats, people, etc.). It could also potentially benefit from leveraging feature map generation capabilities from a 
pretrained model like VGG16.
