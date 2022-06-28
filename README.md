# Human-Activity-Recognition
A LSTM + CNN or LRCN model which recognises the action performed in a video. It is trained on the UFC-50 dataset.

Link To the UFC-50 Dataset: https://www.crcv.ucf.edu/data/UCF50.php
<br/>
Google Colaboratory Link: https://colab.research.google.com/drive/1mftAh_YV_GhO0L8iA0M_G83agbbcUsKq?usp=sharing

## **<font style="color:rgb(134,19,348)">Implementing the LRCN Approach</font>**

An approach known as Long-term Recurrent Convolutional Network (LRCN) was implemented, which combines CNN and LSTM layers in a single model. The Convolutional layers are used for spatial feature extraction from the frames, and the extracted spatial features are fed to LSTM layer(s) at each time-steps for temporal sequence modeling. This way the network learns spatiotemporal features directly in an end-to-end training, resulting in a robust model.

<center>
<img src='https://drive.google.com/uc?export=download&id=1I-q5yLsIoNh2chfzT7JYvra17FsXvdme'>
</center>

[**`TimeDistributed`**](https://keras.io/api/layers/recurrent_layers/time_distributed/) wrapper layer is also used, which allows applying the same layer to every frame of the video independently. So it makes a layer (around which it is wrapped) capable of taking input of shape `(no_of_frames, width, height, num_of_channels)` if originally the layer's input shape was `(width, height, num_of_channels)` which is very beneficial as it allows to input the whole video into the model in a single shot. 

<center>
<img src='https://drive.google.com/uc?export=download&id=1CbauSm5XTY7ypHYBHH7rDSnJ5LO9CUWX' width=400>
</center>
