![image](https://github.com/user-attachments/assets/4c086306-3334-4c0a-866b-239b697d2cd7)
# What is Normalising Flow?
Normalizing flows (NFs) are an exciting new family of neural networks for density estimation, sampling, and likelihood inference [1]. A NF is built by combining invertible components with tractable Jacobian computations, and they are shown to generalize many known models, such as invertible ResNets or autoregressive architectures.
Normalizing Flow (NF) model for better and more powerful distribution approximation. A normalizing flow transforms a simple distribution into a complex one by applying a sequence of invertible transformation functions. Flowing through a chain of transformations, we repeatedly substitute the variable for the new one according to the change of variables theorem and eventually obtain a probability distribution of the final target variable.
![image](https://github.com/user-attachments/assets/780db3c0-c2b0-4457-b448-4417a25d7e54)

![image](https://github.com/user-attachments/assets/352862e7-cbea-4e52-bce8-0e99606e2ca1)

# Loss Function
Loss function used is the combination of negative log likelihood loss and the MSE (reconstruction loss). Since the values of the loss functions were pretty far we had to use a scale factor (alpha)
so that the values of both losses would be comparable. Further we had also added the eucidian norm of mean of original and predicted distributions 
across the rgb channels trying to enhance the results. We shall see how the model is performing the image generation and also compare the results with different tweakings

## Without any scaling of the loss functions and without adding the norm term in the loss function and without the reconstruction loss term in the loss function
<img width="1150" alt="image" src="https://github.com/user-attachments/assets/6a2e63c8-490c-4451-b0f1-ed02022ac31d">

## With scaling of the loss function and without adding the norm term in the loss function and with the reconstruction loss term in the loss function
<img width="829" alt="image" src="https://github.com/user-attachments/assets/4cbad959-249d-4149-b6bf-3a4cdca6660f">

## With scaling of the loss function and with adding the reconstruction loss term and also adding the norm term in the loss function. We DIDNOT scale noise to 64*64 before the generation

<img width="815" alt="image" src="https://github.com/user-attachments/assets/22c1b3b3-65e3-4ce5-8658-1ffad34582f0">

## With scaling of the loss function and with adding the reconstruction loss term and also adding the norm term in the loss function. We also scaled the noise to 64*64 (according to the paper) before the generation
<img width="817" alt="image" src="https://github.com/user-attachments/assets/1fd822b5-b962-46bd-ae18-8613b67b359c">

