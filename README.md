# Pix2Pix-PracticalML
Co-Author: Marcelo Padovani

### Goal of the project:  
To explore and try out practical usages of Pix2Pix Machine Learning approach on dancing that could be used by dancers or choreographers to create and visualize new movements and choreographies.

Here's a demo of the final results:  

https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/b449721c-f906-4ddb-8d1d-04d3208b1efe


## How It's Made


### Process of Implementation and tools used:

To create the training database we used a [videoclip from Mc Dadinho](https://www.youtube.com/watch?v=kpJApAfODSE): we extracted his position using [posenet](https://github.com/tensorflow/tfjs-models/tree/master/posenet) and [Processing](https://processing.org/) where we matched with the frame of the video, 10 frames per second of video, and exported the images of the pose + video frame.

<p align="center">
  <img width=50% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/59070d44-2feb-4476-90ed-3a6dd1a8db8c">
</p>

Then, we trained [Tensor Flow Implementation of Pix2Pix](https://github.com/affinelayer/pix2pix-tensorflow) using Google Colab and generated the images using skeletons extracted using posenet from [another video of a person dancing](https://www.youtube.com/watch?v=UMFUz7-kik8).  

Processing's [Grafica library](https://jagracar.com/grafica.php) was used to create graphs so that we could analyze the training of the model. Below are the graphs indicating the Discrimination, Gan and L1 losses during the last training in which we used 164 images for 463 epochs.  

<p align="center">
  <img width="60%" src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/a2c066cf-4d3b-4ad6-9b47-c8e885cbd00c">
</p>

## Lessons Learned:

Based on the observation of the graph, since the result are somewhat linear, it means that both “Discriminator” and “GAN” are still advancing. According to [other users](https://github.com/affinelayer/pix2pix-tensorflow/issues/99) running models on Pix2Pix, we haven’t reached the point where “Discriminator” starts to fluctuate along with “GAN”. This means that the Generator hasn’t really won over the DIscriminator in a lot of the epochs so far, and more training time can be done to further enhance the output.

<br>

---

## :books: [Slides] Pix2Pix & How it works
Below are some slides explaining how Pix2Pix works in our project.

<details>
  <summary> Click here to view </summary> 
<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/fb5cf3a1-ebc4-4c29-ab7f-ab3af465b7dd">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/002cae54-583e-4cbc-8264-c6e53801df9d">
</p>


#### How it works:

<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/26926428-a71c-459d-b51a-3f263668c847">
</p>


#### Differences between different methods of training:

<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/a7803ca4-b423-4d6e-87e6-31eb31f682e1">
</p>

#### Noise Vector = cGAN - Conditional GAN, uses Observed image along with Noise vector to generate the output image.

<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/b6222e43-b7d0-4887-b85c-61a1f7ef361b">
</p>

#### Generator interaction with Discriminator:

<p align="center">
<!--   ![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/8f952d32-0d6a-49b1-abeb-3f5ae4d4cc27)
![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/b075045d-3361-4332-be42-b62048c9bbe6)
![image](https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/1eb2cc8b-d60e-4724-8d44-3a81bfdadc1c) -->

  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/8f952d32-0d6a-49b1-abeb-3f5ae4d4cc27">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/b075045d-3361-4332-be42-b62048c9bbe6">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/1eb2cc8b-d60e-4724-8d44-3a81bfdadc1c">
</p>

#### Creating the Training Data Sets
<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/7cbb3782-9da4-4760-89fd-a413edc70695">
</p>

#### Results

##### Initial Tests of ML Model Training
Trained with 30 images, 100 Epochs (15 min)
<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/4540dcb3-7160-4b7b-9e07-66865b23c45f">
</p>

##### With 300 images & 6hrs Training Time (Epochs: 166)

<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/15401fb6-b3b6-4ade-b889-197d30360a74">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/752f3ea5-940f-4435-a915-c0e15a580cac">
</p>
  
##### With 164 images & 8hrs Training Time (Epochs: 463)

<p align="center">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/dbb8dd76-0c40-40d9-a44e-6f2dcf20693c">
  <img width=60% src="https://github.com/Code4Dopamine/Pix2Pix-PracticalML/assets/11954656/7d69249c-c6ce-4ef7-9749-d7a4025f74cc">
</p>

</details>
