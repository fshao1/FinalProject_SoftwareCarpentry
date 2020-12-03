# SoftwareCarpentry_Final_Project
Final Project for Software Carpentry (EN.540.635)

## Designer
Fangchi Shao <fshao1@jhmi.edu>

## Requirement
1. Google Colab is needed for this project as the codes were designed for using Google Colab. Modificaitons will be needed if not using Google Colab. 
2. PyTorch needs to be installed for implementing the model. You can download it from: https://pytorch.org/

## GTSRB Classification Challenge
This is a multi-classs, single-image classification challenge that was posted in 2011 at the International Joint Conference on Neural NEtworks (LJCNN). The dataset contains 43 classes and 51,839 images. More information or details can be found: http://benchmark.ini.rub.de/?section=gtsrb&subsection=news

## Dataset Preparation
### Option 1: Creating the dataloader step-by-step
1. Download the dataset from https://sid.erda.dk/public/archives/daaeac0d7ce1152aea9b61d9f1e19370/published-archive.html
2. Open the link and download the following files:
* GTSRB_Final_Training_Images.zip
* GTSRB_Final_Test_Images.zip
* GTSRB_Final_Test_GT.zip
3. Unzip the files into a folder called "GTSRB" and the folder content should look like this:

![](/README_images/Data%20folder%20Image.JPG)

4. Then upload the folder to the Colab Notebook folder of your drive, which looks like:

![](/README_images/Data%20folder%20Image_Drive.JPG)

5. Open "GTSRB_Dataloader.ipynb" in Google Colab and modify the directory based on your drive directory following the TODOs.
6. Run "GTSRB_Dataloader.ipynb" and save the dataloader to your desired directory.

### Option 2: Using the pre-saved dataloader directly
If you do not want to go through step-by-step methods to generate the dataloader for training, validation, and testing. You can directly download the saved dataloaders from this drive: https://drive.google.com/drive/folders/1bzzHut9rjGefyBHE5aT8Fmujo75MQwr7?usp=sharing

Save the three dataloader.pth files in the GTSRB folder in your drive.

## Methods
### Neural Network
* I used three layers of convolutional neural networks (CNNs) and two fully connected layers. 
* I used relu as the activation function.
* Max pooling, batch normalization,a and dropout were performed after each CNN.
* The performance of the netwrok is evaluated by Cross Entropy Loss.

### Hyperparameters
* I used Adam as the optimizer
* I used 150 epochs for training
* I used 0.0001 as the optimal learning rate

Note: These hyperparameters can be modified and tuned by yourself.

### Dataset Image Modifications
Since each image in the dataset has different sizes, so I resized them to 32 by 32 pixels.

## Run the program
Once the dataloader have been saved to drive, you can open the "GTSRB_Model.ipynb" and fine rune the hyperparameters as you prefered and then run the notebook. The loss and accuracy for training and validation will be ploted w.r.b. to epochs and the testing accuracy will be calcualted after all the trainings are done.

I uploaded a "Final_GTSRB_Example_Results.ipynb" as an example for my own training. This is optimized by testing out different hyperparameters.

## Results
My appraoch got an test accuracy of around 95.41%.

The training loss curve w.r.t epochs looks like:

![](/README_images/Training_loss.png)

The validation loss curve w.r.t epochs looks like:

![](/README_images/Validation_loss.png)

The training accuracy curve w.r.t epochs looks like:

![](/README_images/Training_acc.png)

The validation accuracy curve w.r.t. epochs looks like:

![](/README_images/Validation_acc.png)

## Future perspectives
There are other things that can be modified or implemented by yourself. Here the batch size I used is 1 due to the GPU limitations, which can be made larger to speed up the training time. Also, some other image transformations can be added to achieve data augmentations such as vertical and horizontal flips. You can find more information from this link: https://pytorch.org/docs/stable/torchvision/transforms.html

