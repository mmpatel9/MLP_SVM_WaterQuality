# A Comparative Study of Multilayer Perceptron and Support Vector Machine on Water Quality

[View Full Water Quality Report](https://github.com/mmpatel9/MLP_SVM_WaterQuality/blob/main/A%20Comparative%20Study%20of%20Multilayer%20Perceptron%20and%20Support%20Vector%20Machine%20on%20Water%20Quality.pdf)


## Dataset 

The dataset we have chosen, downloaded from Kaggle, looks at water quality from 3726 different samples, to decide whether the water is safe to drink or not. The decision whether the water source is safe to drink or not is based on 9 features (pH Value, Hardness, Solids, Amount of Chlorine, Sulphate, Conductivity, organic carbon, Trihalomethanes and turbidity) and has 2 possible output classes (1- Safe to drink the water, 0-Not safe to drink the water).


 

## Methodology:

The dataset, after scaling, was split into training and testing into proportion of 80% and 20% respectively with a random state of 10. The testing data will be unseen until the best hyperparameters have been chosen for the respective model. To ensure fair comparison grid search approach will be applied to both models to adjust and optimize the hyperparameters. As well as that, a K-fold cross validation will be applied to evaluate the performance of the models, as this will, be better for generalisation of the model performance against the unseen data. As I am predicting a close accuracy for both models, I will be using this search ahead of random search hence will be looking at all the possible outcomes based on the chosen hyperparameters. As this will be computationally expensive a K-fold of 3 will be used and the average of the K-folds will be used model accuracy. To be able to compare performance of the chosen models using the test set, metrics such as accuracy, precision recall & F1 will be used. In additional to this confusion matrix will also be produced to further asses the performance of the misclassified data. The time taken to train the models will also be investigated.


## Architecture and Parameters used for the MLP 

Our model will consist of two hidden layers, fully connected, with a sigmoid activation function. The input layer and output layer will remain constant, while the hyperparameters such as learning rate, hidden layers, momentum, weight decay and dropout will be varied. It was decided to use a maximum of two layers only as having more than 3 layers is mainly for the complex representations [9] For the loss criterion, a cross entropy loss function was chosen as it is more effective for binary classification classifiers. The weights will be updated using backpropagation using the ‘stochastic gradient descent’ (SGD) as the optimizer with momentum. An early stopping criterion was used to prevent overfitting so that training stops if the validation set does not improve for a certain number of epochs, this will help prevent overfitting. A grid search will be implemented. To give us an understanding of how the hyperparameters are affecting the model and then a grid search will be applied again with a change of hyperparameters based of the results of the first grid search. 

## Architecture and Parameters used for the SVM 

The choice of hyperparameters for SVMs is significantly less when compared to MLP therefore, the following hyperparameters will be tuned. The type of kernel (linear, rbf & polynomial), box constraint C and gamma. A trial-and-error approach will be initially implemented to find the optimum kernel, and from the different values of gamma and kernel scale will be used. Once an optimum value is found a grid search will be used for a range of hyperparameters based on the previous results to find the optimum generalisation model



## Conclusion, Lessons learnt & Future Work 

In conclusion we learnt that the SVM was better at predicting whether the quality of water was safe to drink or not, however the SVM was not perfect with it showing some biasness towards the false negative values. Comparing my results to the papers I have read, my results were less accurate, however, this may be due to the dataset not being entirely the same. What I have learnt that having more hypermeters in a model does not mean that it would perform any better, having only tuned 3 hypermeters in my SVM model, with 6 being used for the MLP model. As well as that checking the quality of the results from the training stage will ensure that the best performing model is put forward, so just because a model is showing high accuracy, does not mean it will generalise well, even though K Fold is used. Going forward I would like to use a computer with more GPUs as this will allow me to use a wider range of hyperparameters and a K 10/15 K-fold Cross validation. Also get more data so that training size is able to increase. In addition to this, able to combine both models to create a hybrid [12].
<img width="451" height="688" alt="image" src="https://github.com/user-attachments/assets/0f013321-54c3-40d3-bd53-03fbe5750b5c" />
