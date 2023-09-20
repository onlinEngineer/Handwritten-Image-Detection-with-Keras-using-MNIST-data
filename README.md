# Handwritten-Image-Detection-with-Keras-using-MNIST-data
Handwritten Image Detection with Keras using MNIST data

## PART 1.
In this part, we used keras.dataset mnist dataset. We splitted data into two parts which are traning and testing part. We used Sequential library.
### Model_1
We have 50.890 parameters in total. 50240 belongs to first hidden layer (relu activation) , and 650 is belongs to softmax layer.

![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/78e018d1-7610-4f4d-968d-028902fb21e9)


### Epochs
After 30 epocs, our training loss reduced from 0.3234 to 0.1277, accuracy increased from 0.9056 to 0.9732. Also, our test loss (val_loss) increased from 0.1713 to 0.1883, test accuracy increased from 0.9503 to 0.9722. That’s not a good model since test loss increased from 0.1713 to 0.1883. Thus, we have overfitting problem.

![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/70026f1f-cae3-4d38-b4e6-4712e71c61f7)

### Outputs of Model_1

![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/017fe8eb-5584-4654-95b2-bd0507ce1ccc)

## Our Model (Model_2)
We have 27194 parameters in total. There is almost a half of parameters when we compare with the model_1 parameter. Normally Once the layer and neuron size increased, parameters increased. For model 1, at the first layer we have 64 layers, so that we have more parameters than model_2. However, because of dropouts, for second layer, we have less parameters even if we have more neurons.

![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/f8b7a980-2290-4f76-9a58-e00eb7ba709c)

### Epochs
After 40 epocs, our training loss reduced from 0.5509 to 0.2176, accuracy increased from 0.8241 to 0.9347. Also, our test loss (val_loss) reduced from 0.2313 to 0.1462, test accuracy increased from 0.9322 to 0.9597.
![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/4e42f763-3b66-4d0a-bc20-d8989f2529cd)

### Outputs of Model_2

![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/c4254d35-5161-49dc-98ef-1642bffd8296)

## PART 2.

1) How do model_1 and model_2 compare? Which do you prefer? If you were going to
put one into production, which would you choose and why?
- We can compare model_1 and model_2 by looking at test accuracy and loss functions. While the test accuracy of model_1 is 0.97, model_2 is 0.95, and loss function is 0.18 for model_1, 0.14 for model_2. When we consider of two model, the second model is more suitable for putting into a production since the loss is less.
2) Compare the trajectories of the loss function on the training set and test set for each
model? How do they compare? What does that suggest about each model? Do the same
for accuracy? Which do you think is more meaningful, the loss or the accuracy?
- To compare the loss and accuracy, we can use some trajectory graphics. When we considered trajectory of model_1, train loss decreasing and validation loss starting to increase after a certain period. That means, our model is overfitting. So, for the training part, our model gives good performance for training data, but when we test our data for the test data, the model will fail. So, we can already see the situation in the accuracy graphics. After a certain period, the validation accuracy starting to decrease. To avoid the overfitting, we can add more data to our model or apply regularization. On the other hand, model_2 is a good model. So that, we can use this model. Also, we can carefully add more neurons or epoch to increase the accuracy, but we should make sure to avoid complex model. Loss function is more meaningful to make a comparison because we can see our model clearly there is an overfitting or underfitting situations.
3) Suggest an improvement to model_2 (changing network structure, learning rate, batch
size, number of epochs, etc.) that you think will result in a better model. Repeat Part-1
with this improved model (model_3). How much improvement can you achieve?
- Removing the second dropout and reduce the epoch size from 40 to 20, we can have better results. So, the accuracy has increased the .96, and the losses are reduced for both training and validation data.




## Model_3
In model_2, we do not need to use second dropout as our model is not having overfitting problem. So that, I dropped the second dropout section, and reduced the epochs size to 20. Thus, our parameters have decreased to 27.194. When we compare with the model_2, we have a better model as we can see from the test accuracy and test loss.

![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/1951b369-6f3b-448e-9b36-4cd7f94dc36d)


### Epochs
After 20 epochs, our training loss reduced from 0.4462 to 0.1837, accuracy increased from 0.8604 to 0.1854. Also, our test loss (val_loss) reduced from 0.1854 to 0.1227, test accuracy increased from 0.9434 to 0.9638.

![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/61fc8dd5-31b4-4559-b234-b9398181756f)

### Outputs of Model_3
![image](https://github.com/onlinEngineer/Handwritten-Image-Detection-with-Keras-using-MNIST-data/assets/70773825/89026109-1d43-4f04-a45a-f82195a4d260)
