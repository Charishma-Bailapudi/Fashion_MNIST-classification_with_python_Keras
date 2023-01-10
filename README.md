# Fashion_MNIST-classification_with_python_Keras

### *About DataSet*
The very popular Fashion MNIST dataset to classify clothing,footwear and other related items.So,lets dive in.<br>
###### What actually is Fashion MNIST ? <br>
Fashion-MNIST is a dataset of Zalando’s article images consisting of a training set of 60,000 examples and a test set of 10,000 examples.It’s great for writing “hello world” tutorials for deep learning.This dataset contains 28 * 28px of clothing-greyscale images. The library contains 10 types of clothing items:

<ul>
<li>T-shirt/top</li>
<li>Trouser</li>
<li>Pullover</li>
<li>Dress</li>
<li>Coat</li>
<li>Sandal</li>
<li>Shirt</li>
<li>Sneaker</li>
<li>Bag</li>
<li>Ankle Boot</li>
</ul>

![Alt text](https://miro.medium.com/max/1100/1*ymrqRtMnRIy4IM4IexLr9g.webp "")

So, given an input image, these would be our possible outputs. In total, the Fashion MNIST dataset contains 70,000 images which are undoubtedly plenty for us to work with. Out of the 70,000 images, we will use 60,000 of them to train the neural network with the other 10,000 being used to test the neural network. Also, remember that each image is a 28px x 28px image meaning that there are 784 pixels. And so, the job would simply be to take the 784 pixels as input and then output one of the 10 different items of clothing the image represents.<br>

Let’s take a quick look at how our neural network would look like:<br>
<br>
What happens here is that the neural network can’t work with a 2-D image (the 28 x 28 image) and can only work with a 1-D image (array). So, what we’d do here is compress the image into a 1-D array by multiplying the length by the height. That’s where the 784 comes from (28 x 28). This is known as a method called *flattening*. So, our input layer would be 784 neurons in this case. Our hidden layer, in this case, would be of 128 neurons and then from there, show 10 outputs which were the possible types of clothing.

![Alt text](https://miro.medium.com/max/1400/1*S6t_smvyXvXnDAO7UkL4MA.webp "")
### *Data visualization*
Now we will see some of the sample images from the fashion MNIST dataset. For this, we will use the library matplotlib to show our np array data in the form of plots of images.

```

for i in range(1, 10):
    # Create a 3x3 grid and place the
    # image in ith position of grid
    plt.subplot(3, 3, i)
    # Insert ith image with the color map 'grap'
    plt.imshow(trainX[i], cmap=plt.get_cmap('gray'))
 
# Display the entire plot
plt.show()

```
![Alt text](https://media.geeksforgeeks.org/wp-content/uploads/20220408134114/sampleimage.png "")

### *Model Training*
```
#build
model = tf.keras.Sequential([
  tf.keras.layers.Flatten(input_shape=(28, 28)),                           
  tf.keras.layers.Dense(128, activation='relu'), 
  tf.keras.layers.Dense(64, activation='relu'),                              
  tf.keras.layers.Dense(10),                             
  ])
  
  ```
 As you can see, we’re using the TensorFlow library to build our neural network. Let’s go a bit more in-depth into what we’re doing:
  
<ul>
<li>
<b>input</b> tf.keras.layers.Flatten - This layer transforms a 2-d array (matrix) into a 1-D array of 784 (28 x 28). Think of this layer as lining up the images from a square to one, long line. This layer doesn't learn anything; it simply reshapes the data.
</li>
<li>
    <b>hidden</b> <mark>tf.keras.layers.Dense</mark> - A densely connected layer of 126 neurons. Each neuron (otherwise known as a node) takes input from all 784 nodes in the previous layer, weighting that input according to hidden parameters which will be learned during training, and outputs a single value to the next layer.
</li>
</ul>
  






