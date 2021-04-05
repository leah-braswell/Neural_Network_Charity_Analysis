# Neural Network Charity Analysis


## Overview
Alphabet Soup is a charitable group who grants funds to organizations who seek to do good in the world through projects such as lifesaving technology research and reforestation efforts.  They are asking for a binary classifier to predict which organizations will be successful if granted funds by the foundation.  They have provided information on more than 34,000 organizations who have received funding from Alphabet Soup over the years.  


## Results
* Data Preprocessing
    * The target for this model is the 'IS_SUCCESSFUL' column.  This target was chosen because the objective of the model is to predict whether or not an organization will successfully use the funds provided by Alphabet Soup.

    * Originally, all variables except the target, EIN, and NAME were used as features.  During optimization, the 'SPECIAL CONSIDERATIONS' column was also dropped as a feature.  

    * EIN and NAME had no bearing on the success of the organization and were, therefore, not used as either features or targets.

* Compiling, Training, and Evaluating the Model
    * The Input layer had nodes equal to the number of features in the dataset.  This is standard among all Neural Networks.

    * The [original model](pics/original_structure.PNG) had two hidden layers each using a relu activation function.  The first hidden layer took 80 nodes, approximately double the number of nodes in the input layer, and the second layer had 30.  The relu activation function was chosen because there were no negative input values.  The relu function is also considered a good default starting point for deep learning neural networks due to its ability to learn quickly.

    * The output layer had one node with a sigmoid activation function.  The sigmoid function was chosen because the purpose of the model was binary classification.  

    * The [original model](pics/original_result.PNG) did not achieve the target performace of 75%.
    accuracy.

* Optimization
    * The first adjustment I made for optimization was to drop the 'SPECIAL CONSIDERATIONS' column and adjust the binning in step six to include all application types with a [count of less than 1000 based on the density plot.](pics/app_count.PNG).  Thsese changes did not improve the [performance of the model.](pics/optimize1.PNG)

    * The next step I took for optimization was to [add nodes](pics/increase_nodes.PNG) to the hidden layers.  I multiplied the number of features by 3 to arrive at 114 nodes in the first hidden layer.  This did not improve the [performance of the model.](pics/optimize2.PNG)

    * Then I added a [third hidden layer](pics/third_layer.PNG) which did not improve the [performance of the model.](pics/optimize3.PNG)

    * Finally I tried [changing the activation function](pics/change_activation.PNG) on the third layer from relu to sigmoid.  I thought a more binary classifier would help, but it did not improve the [performance of the model.](pics/optimize4.PNG)

## Summary
The deep learning model was only able to achieve 72% accuracy even after I made adjustments for optimization.  Were I to continue with this project, I would most likely try a Support Vector Model. Since this problem is a pretty straight forward binary classification, an SVM should perform better.  The SVM will consider a more "global" approach to the features and effectively separate non-linear groups. 



