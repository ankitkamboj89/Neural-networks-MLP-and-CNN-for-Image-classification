# Neural-networks-MLP-and-CNN-for-Image-classification
Used MLP and CNN models to create image classification

1) Created validation and testing set
2) Visualising the Training set
3) Initial **MLP model**:

_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 flatten_21 (Flatten)        (None, 3072)              0         
                                                                 
 dense_69 (Dense)            (None, 128)               393344    
                                                                 
 dense_70 (Dense)            (None, 64)                8256      
                                                                 
 dense_71 (Dense)            (None, 32)                2080      
                                                                 
 dense_72 (Dense)            (None, 10)                330       
                                                                 
=================================================================
Total params: 404,010
Trainable params: 404,010
Non-trainable params: 0
_________________________________________________________________

we adopt following parameters for MLP model:
*   Sequential model with input dimensions `[32,32,3]`.
*   Activation function: `Relu`
*   Output layer activation function: `softmax`
*   Loss function: `categorical_crossentropy`
*   Three hidden dense layers with '128', '64' and '32' neurons.

Further refinement of model was done using hyper parameter using initialiser, dropout ratio, learning rate schedule, Early stopping.
Achieved accuracy of 52% on testing set

CNN model:

_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 conv2d_10 (Conv2D)          (None, 30, 30, 64)        1792      
                                                                 
 max_pooling2d_5 (MaxPooling  (None, 15, 15, 64)       0         
 2D)                                                             
                                                                 
 dropout_115 (Dropout)       (None, 15, 15, 64)        0         
                                                                 
 conv2d_11 (Conv2D)          (None, 13, 13, 64)        36928     
                                                                 
 dropout_116 (Dropout)       (None, 13, 13, 64)        0         
                                                                 
 flatten_35 (Flatten)        (None, 10816)             0         
                                                                 
 dense_121 (Dense)           (None, 10)                108170    
                                                                 
=================================================================
Total params: 146,890
Trainable params: 146,890

Achieved accuracy of 68% on testing set
