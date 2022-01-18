# AI poject
The aim of this project is to determine the style of the painting using CNN.

The main things that differ in paintings are lines, colours, composition, also some styles take into account the lighting, and some do not. So I had to keep the color of the paintings. 

# Dataset
I took a dataset from kaggle "Painter by Numbers". As you can see from the graph, it is not very balanced. I took only 6 classes in which there are enough pictures or which are visually different.
##
![image](https://user-images.githubusercontent.com/54356826/149970364-c7d937e7-46c2-4acf-9b13-56557f7e5d14.png)
![image](https://user-images.githubusercontent.com/54356826/149970993-0e47542d-6ab4-4a0b-a197-ae9c5fad62d6.png)
##
Before training them on the neural network, I normalized the images and passed them through VGG and resize to 256x256. To save time I stored preprocessed images in folders for classes. I also balanced this folders.
##
![image](https://user-images.githubusercontent.com/54356826/149971624-933771ee-5966-46c4-9e31-e1aa171f502d.png)
## CNN model
As convolutional neural network have the highest accuracy for image classification I used it. Unlike ANN CNN can extract features from the image. 
#####
![image](https://user-images.githubusercontent.com/54356826/150005262-3e1bc152-f42b-4f62-a877-20d9efbe3b8f.png)
#####
I have 4 convolutional layers in which 3x3 convolutional filters were used to create a feature map. After each of convolutional layer go PReLu and MaxPooling.
The model is regularized using batch normalizations and dropout. Also, for weight regularization l2 (calculate the sum of the squared values of the weights) were used in convolutional layers and dense layers.
![image](https://user-images.githubusercontent.com/54356826/150019326-2f5bd641-040a-4562-8cbe-6f79c07d0299.png)
######
![image](https://user-images.githubusercontent.com/54356826/149972521-e2bf5aa7-237a-4012-9d9a-bc0aadf64fe4.png)
At the end I used Adam optimizer, although SGD gave almost the same result. 

# Results
6 classes, only normalization. As you can see it doesn't work good

![image](https://user-images.githubusercontent.com/54356826/150005462-dee147c1-e5ec-4c13-97dd-163d2b5fb821.png)

6 classes, double convolution layes (meaning, we take 2 times 32 filters, than 2 times 64...). At the beggining it works better, but as you can see it doesn't make any progress.

![image](https://user-images.githubusercontent.com/54356826/150005769-dd5374e5-405a-4936-a755-98c80e11648d.png)

6 classes, vgg

![image](https://user-images.githubusercontent.com/54356826/150005971-71d44f87-6359-424a-addb-56b528431e23.png)
