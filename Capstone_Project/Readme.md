
# CT Scan Image Classification

This dataset contains 1252 CT scans that are positive for SARS-CoV-2 infection (COVID-19) and 1230 CT scans for patients non-infected by SARS-CoV-2, 2482 CT scans in total. These data have been collected from real patients in hospitals from Sao Paulo, Brazil. The aim of this dataset is to encourage the research and development of artificial intelligent methods which are able to identify if a person is infected by SARS-CoV-2 through the analysis of his/her CT scans.

# DATA PREPROCESSING:

-From the image we can see that covid-19 ct scan has round glass opacities which is not seen in the non- covid patient ct.

-These feature can be used to classify the images but with help of convolution neural network (CNN) which are specially designed for feature detection can give better classification results.


![download](https://user-images.githubusercontent.com/92459017/208454827-e7ecb9f6-3954-4d2e-b4ef-bc83505c580b.png)

# Data vizualization

- visualise the data and splitted the data


![Screenshot_20221219_203956](https://user-images.githubusercontent.com/92459017/208459791-f4e4c7fd-9537-4ffd-8112-858d9f2a9cbe.png)


![Screenshot_20221219_203919](https://user-images.githubusercontent.com/92459017/208459902-4940d340-904b-4304-b717-2cc535ff1349.png)

 # Model Building
 

 
 The accuracy values obtained after fine-tuning the
ResNet models are compared with the accuracy values
obtained from various existing methods in the literature and
the results are presented in table V. Most of the existing
methods make use of chest X-Ray images. The proposed
method using ResNet152 performs better.This can
be attributed to the fact that it uses Chexnet pre-trained
model which has already learnt features specific to chest XRay images.

The model's summary() method displays all the model's layers, Including each layer's name,Its output shape ,and its number of parameters.
The summary ends with the total number of parameters,including trainable and non-trainable parameters.


![modeldisplay](https://user-images.githubusercontent.com/92459017/208462259-c90b944f-f07d-45bb-b48c-8dedd8352ead.png)

# Training and evaluating the model

Now the model is ready to trained.For this we simply need to call its **fit()** method

Train the model with batch size = 18 with 50 epochs using callback.


![Screenshot_20221219_210726](https://user-images.githubusercontent.com/92459017/208463086-3b7b27ec-5153-4010-ba76-804e83ca5911.png)

We pass it the input feature **(X_train)** and the target classes **(Y_train)**, as well as the number of epochs 50 to train.
Keras will measure the loss and the extra metrics on this set at the end of each epoch, Which is very useful to see how well the model really performs.If the performance on the training set is much better than on the validation set.






![Screenshot_20221219_211608](https://user-images.githubusercontent.com/92459017/208464903-5036b12e-75fb-4583-b12e-50916a55ba1e.png)



# Predicting the COnfusion matrics

Confusion matrices, a key tool to evaluate machine learning algorithm performance in classification, are a statistical tool.

Contingency tables, a type of confusion matrix, are used in the evaluation of many diagnostic exams for sensitivity, specificity, positive and negative predictive values. A contingency table is an example of a confusion matrix that is made for a binary classifier


My model is 

True Positive: 226
False Negative: 42
True Negative: 223
False Positive: 6
True Positive Rate: 0.8432835820895522
True Negative Rate: 0.9737991266375546


# Training Curves

![download (2)](https://user-images.githubusercontent.com/92459017/208465651-e24df357-5d12-493c-8493-fe79e6cb32ad.png)

 You can see that the training accuracy and the validation accuracy steadily increase during training, while the training loss and the validation loss decrease.
 
 # Predict
 
 
![Screenshot_20221219_201435](https://user-images.githubusercontent.com/92459017/208466246-b7036111-5c98-4697-b834-4a0a1a298d21.png)

Finally Predicted my model with sample picture, I got correct predicted result
