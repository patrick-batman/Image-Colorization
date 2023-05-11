# Image Colourisation via Raspberry Pi
## Abstract

<p>
  Manual colourization of black and white images is an uphill task and inefficient. It has been attempted using Photoshop editing, but it is difficult as it requires extensive research, and a picture can take up to one month to colorise. A pragmatic approach to the task is to implement sophisticated image colourization techniques. Colourisation of grayscale images has become a more researched area in recent years, the most recent development is using GANs and U-net.</p>
  <p>
  We attempt to apply this concept to the colourisation of Victorian images, which have a tinted colour scheme and are not precisely very brightly coloured. Previous similar research focused mainly on the colourization of natural images, while we have trained on Victorian images. We propose to train the model, get inferences, and deploy it on a Raspberry Pi. We are using CNN and pre-trained Resnet to train our model due to the limited computer resources available to us.
  </p>



 ## Introduction - with the description of the Problem statement

<p>
  When photography was just starting in old times, most images were in black and white (B&W). Hence, efforts to colourize old B&W images started to give the image a different perspective and a beautiful insight into the captured moments. Colourisation efforts began to appear in the early 1900s, using paints and brushes. This painstaking process took days, sometimes weeks, to generate a rough recreation of reality.</p>
  
 <p>
  The trend has shifted to the use of computer software such as Adobe Photoshop, GIMP etc, but the procedure remains the same. The present-day techniques for manual colourization of these B&W images are: cleaning the image, adjusting the image tones and contrast, converting the image to CMYK and finally, adding solid colour to specific entities in the picture. But even digital colourisation using software like Photoshop, which helped in colourisation, pixel by pixel, along with improved handling of colour bleeding and colour continuity, and reduced manual work to some extent, now seems tedious. Thanks to colour cameras, a massive gallery of photographs is available. </p>
  <p>
  It offers great information to determine the colour schemes of familiar objects, scenes, lighting conditions, and colour intensities. With advancements in technology and extensive research in deep learning, models can be trained to learn knowledge and then apply it to colourise old photographs.
  </p>

<img width="549" alt="Screenshot 2023-05-12 at 12 55 17 AM" src="https://github.com/patrick-batman/Exploratory-Project/assets/98745676/500911bd-768f-409a-bd2b-ddd975a9bb6e">


 Using such techniques to colorize the photographs can modernise and automate how things are done and relieve the pressure on the colourizing artists to some extent. We implemented different CNN and GAN models used for image colourizing and provided their quantitative and qualitative comparisons. We also show that incorporating pre-trained models can significantly improve performance, making the training and hyperparameter tuning processes less cumbersome. We created a custom dataset of high-resolution images; categorised them according to scenery, background, and artistic theme since the colours involved in such photos are generic and not complex. 

# Methodology
The methodology of building an ML model for colourizing black-and-white images and deploying it on a Raspberry Pi involves several steps. Here's an overview of the process:
## 1. Dataset Preparation:
We have used this dataset that consists of different Victorian arts and paintings. We have chosen this dataset because we often find models that colour typical images, but one of the essential applications of colourising black and white images is restoring old photographs thus, training the model on a dataset consisting of old pictures having the tinted shade will actually address that problem particularly.
## 2. Model Development and Training:
There were several options, such as a Convolutional Neural Network (CNN) or a Generative Adversarial Network (GAN), for choosing the ML model to perform the desired operations. We chose to work with a CNN, followed by inceptions from ResNet. We then split the dataset into training and validation sets, followed by choosing the particular parameters for the model decided. Then training the model for epochs and optimise the model's parameters to minimise the difference between the predicted colours and the ground truth colours.

<img width="624" alt="Screenshot 2023-05-12 at 12 58 33 AM" src="https://github.com/patrick-batman/Exploratory-Project/assets/98745676/750cde08-0b53-4301-82a8-5736ae8c6c80">

## 3. Model Evaluation:
We compared the results produced from the model to the ground truth and observed that the results produced are okay for the computational limitations provided to us.

<br>
<img width="624" alt="Screenshot 2023-05-12 at 12 59 51 AM" src="https://github.com/patrick-batman/Exploratory-Project/assets/98745676/6bc155db-7671-4666-9a5e-8a105efaba23">

## 4. Model Optimization for Raspberry Pi:
 Once the model is trained and evaluated, it must be optimised for deployment on a resource-constrained device like Raspberry Pi. Since the Raspi we have chosen to work with has the memory constraint of 1 GB, we cannot deploy our trained model into the Raspi. Thus we were required to convert the model into Tensorflowlite model is smaller and easier to deploy on the Raspberry Pi.

## 5. Deployment on the Raspberry Pi: 
Transfer the optimised model to the Raspberry Pi. Then we install the necessary libraries and dependencies on the device, such as Tensorflow, Tflite, Numpy, and PIL. 
Then we load the Tflite converted model on the Raspberry Pi that can accept black and white images as input and generate colourized 
versions using the trained model. 
<br>
<img width="642" alt="Screenshot 2023-05-12 at 1 00 31 AM" src="https://github.com/patrick-batman/Exploratory-Project/assets/98745676/0ea09dd5-0ade-4991-8e05-b28d5af1f70c">
## 7. Testing and Iteration:
We now validate the deployed model by testing it with various black-and-white images. This could be further optimised.
Thus we developed the ML model for colourizing black and white images and deployed it on a Raspberry Pi, which performs colourization tasks locally on the device.

# Preliminary Results and Insights
<img width="642" alt="Screenshot 2023-05-12 at 1 03 03 AM" src="https://github.com/patrick-batman/Exploratory-Project/assets/98745676/3fd03fd9-dd88-4181-89b1-5db4b59e16ff">

<br>
The model was successfully able to convert black and white images into its coloured version. When tried on general images this model will often lead to some errors due to its restriction of being trained on only Victorian images.
This could be improved by improving the computation power,however, this comes at the cost of the size of the device.

