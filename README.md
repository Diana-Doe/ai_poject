# AI poject
The aim of this project is to determine the style of the painting using CNN.

The main things that differ in paintings are lines, colours, composition, also some styles take into account the lighting, and some do not. So I had to keep the color of the paintings. 

# Dataset
I took a dataset from kaggle "Painter by Numbers". As you can see from the graph, it is not very balanced. I took only 6 classes in which there are enough pictures or which are visually different.
##
![image](https://user-images.githubusercontent.com/54356826/149970364-c7d937e7-46c2-4acf-9b13-56557f7e5d14.png)
![image](https://user-images.githubusercontent.com/54356826/149970993-0e47542d-6ab4-4a0b-a197-ae9c5fad62d6.png)
##
Before training them on the neural network, I normalized the images and passed them through VGG and resize to 256x256
##
![image](https://user-images.githubusercontent.com/54356826/149971624-933771ee-5966-46c4-9e31-e1aa171f502d.png)
## CNN model
As convolutional neural network have the highest accuracy for image classification I used it. Unlike ANN CNN can extract features from the image. 

I have 4 convolutional layers after each of which goes PReLu and MaxPooling. 3x3 convolutional filters were used to create a feature mapю. The model is regularized using batch normalizations and dropout.
![image](https://user-images.githubusercontent.com/54356826/149969757-643657e6-0a66-4dc6-9611-9d142ad192da.png)
######
![image](https://user-images.githubusercontent.com/54356826/149972521-e2bf5aa7-237a-4012-9d9a-bc0aadf64fe4.png)
At the end I used Adam optimizer, although SGD gave almost the same result. 
