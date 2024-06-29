## Introduction
This data analysis project is based on Kaggle Competition:
https://www.kaggle.com/competitions/digit-recognizer 

All the datasets could be found from that project. Unzip the data into the subfolder "data". I will not post data in the repo because the size is not trivial.

## How to run the Notebook file
Copy the data folder and .jpynb to Colab to run the code from the Notebook.
If your commputer is fast enough, run .jpynb locally in VSCode. You need to adjust the data_path accrordingly. The current data_path is designed to run in Colab.

## Explanation of the two .ipynb files
- Since MNIST dataset is simple and image size is small, using start-from-scratch neural network could achieve better effect.
- Using the more complicated model such as GoogleNet, however, we got pretty poor training result. It might be due to the following reasons:

    - The model uses a big kernel (size = 7) so it will ignore many details of the small image with 28 pixels on each dimension. 
    - Even we freeze the majority of the parameters, running the big models still takes much resources. Therefore, the sample .ipynb file only runs five epochs, which is not enough.
    - The original file dimension is 28 * 28, even less than the minimum requirement of GoogleNet model's 32 * 32 pixels. We need to scale the image and convert the 1-channel grayscale image to 3-channel RGB image, which increases the training effort and makes the model not so suitable for this scenario.


    ## Final training result with start-from-scratch model:
    [Training result](./training_result.png)


    ## To DO
    Improve the model to get higher accuracy level. We could change kernel size, add dropout layer, and more convolution layers. Refer to this code file on Kaggle: https://www.kaggle.com/code/metinmekiabullrahman/digit-recognizer 


