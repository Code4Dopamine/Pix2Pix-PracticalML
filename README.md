# Pix2Pix-PracticalML
Authors: Marcelo Padovani, Edward Wu

### Goal of the project:  
To explore and try out practical usages of Pix2Pix ML approach on dancing that could be used by dancers or choreographers to create and visualize new movements and choreographies.

Here's a demo of the final result:  

https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/a70433d2-6b2a-4485-8ebe-3459ffa0d1f4


## How It's Made

### Process of Implementation and tools used:

To create the training database we used a [videoclip from Mc Dadinho](https://www.youtube.com/watch?v=kpJApAfODSE): we extracted his position using [posenet](https://github.com/tensorflow/tfjs-models/tree/master/posenet) and [Processing](https://processing.org/) where we matched with the frame of the video, 10 frames per second of video, and exported the images of the pose + video frame.

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/fd4d045e-e42d-4533-9d74-4b392e5b9e8d)

Then, we trained [Tensor Flow Implementation of Pix2Pix](https://github.com/affinelayer/pix2pix-tensorflow) using Google Colab and generated the images using skeletons extracted using posenet from [another video of a person dancing](https://www.youtube.com/watch?v=UMFUz7-kik8).  

Processing's [Grafica library](https://jagracar.com/grafica.php) was used to create graphs so that we could analyze the training of the model. Below are the graphs indicating the Discrimination, Gan and L1 losses during the last training in which we used 164 images for 463 epochs.  

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/bb9b3744-7ef8-4072-8646-16ae7fd78ab6)


## Lessons Learned:

Based on the observation of the graph, since the result are somewhat linear, it means that both “Discriminator” and “GAN” are still advancing. According to [other users](https://github.com/affinelayer/pix2pix-tensorflow/issues/99) running models on Pix2Pix, we haven’t reached the point where “Discriminator” starts to fluctuate along with “GAN”. This means that the Generator hasn’t really won over the DIscriminator in a lot of the epochs so far, and more training time can be done to further enhance the output.

## Pix2Pix & How it works
Below are some slides explaining how Pix2Pix works in our project.

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/9eb69911-5793-4b8e-b5fc-a8333bf6c69d)

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/239bc104-c0ea-469b-9680-853258f13d33)

#### How it works:

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/7a4365d7-e980-43c5-a72a-88c2de1e03c1)

#### Differences between different methods of training:

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/14242a16-638a-4570-806d-3f5102bf5682)

#### Noise Vector = cGAN - Conditional GAN, uses Observed image along with Noise vector to generate the output image.

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/2ac5a8fc-76b8-4575-baeb-8ebaebc21a72)


#### Generator interaction with Discriminator:

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/f4e1d4b2-4ce2-4e92-b179-8c602352d14e)

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/282a3c46-2369-4034-8af2-4e62cb3ba47c)

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/f9004adc-55a6-4137-9625-01ce7deb2e71)

#### Creating the Training Data Sets

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/3e3d1e63-4380-4d52-a3e8-7c104f6fe1ff)

#### Results

##### Initial Tests of 15min Training Time
![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/74246d67-3d63-4e68-9768-d7ebe9adeccf)

##### With 4hrs Training Time

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/8693c1c5-8b5f-4084-bc55-fe5c06f52747)

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/9b4a9e64-6ca3-4b8f-a217-f25aa43af02a)

##### With 8hrs Training Time

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/4000bac2-5fdc-42d2-8a13-75d6dca234d2)

![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/07c40ef4-e08d-4109-a418-f117ca63b296)



