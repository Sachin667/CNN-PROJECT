# CNN-PROJECT
Image Classfication using CNN
## Rice_Deases_Classfication
The cultivation of rice, a staple crop in Asia, is threatened by various diseases at different stages of production, posing a significant risk to food safety and agricultural productivity. Severe infestations of rice plant diseases can even lead to a complete loss of harvest. Therefore, there is a critical need for automated disease identification and diagnosis in the agricultural industry. While several methods have been proposed, deep learning has emerged as the most promising approach due to its exceptional performance. In this study, we propose a hybrid deep CNN transfer learning method for the classification and identification of various rice diseases using rice plant images. We leverage transfer learning techniques and utilize the Rice_Leaf_Dataset to train our deep learning model. The proposed approach achieves an impressive accuracy rate of 94%, demonstrating its feasibility and superiority over existing methods in efficiently detecting plant diseases.
## AIM
1, PREPARE A COMPLETE DATA ANALYSIS REPORT ON THE GIVEN DATA 

2, CREATE A MODEL WHICH CAN CLASSIFY THE THREE MAJOR ATTACKING DISEASES OF RICE PLANTS LIKE LEAF BLAST, BACTERIAL BLIGHT AND BROWN SPOT

3, ANALYZE VARIOUS TECHNIQUES LIKE DATA AUGMENTATION, ETC AND CREATE A REPORT ON THAT.

### RICE LEAF DISEASES -

Agriculture is the primary source of income and livelihood in a number of countries,In india almost 70% people depends on agriculture sector..Out of this 70% people,40% of th epeople are engaged in rice production...There are number of diseases that affect the quality and growth of the crop..If not resolved in time,it will considerably affect the production..An automated system is very helpful to find the disease at the right time which will help the farmers to prevent the crop from damage in an earlier stage.Convolutional Neural Network (CNN) models can be very beneficial in such problems.
The major rice leaf diseasea are Leaf smut disease,Brown spot and Bacterial leaf blight

* **Leaf smut disease**-
What causes rice leaf smut is a fungus called Entyloma oryzae. Fortunately for your garden, if you see its signs, this infection is usually minor. It is widespread where rice is grown, but leaf smut doesn’t often cause serious damage. However, leaf smut can make your rice vulnerable to other diseases, and ultimately this can cause a yield reduction.
* **Brown spot**-
Brown spot has been historically largely ignored as one of the most common and most damaging rice diseases.Its most observable damage is the numerous big spots on the leaves which can kill the whole leaf. When infection occurs in the seed, unfilled grains or spotted or discolored seeds are formed.
* **Bacterial leaf blight**-
Bacterial blight of rice is one of the deadliest diseases for rice which occur in both tropical and temperate climates where there are irrigated and rainfed lowlands.. Xanthomonas oryzae pv. Oryzae(type of virus) is the causal agent of the bacterial blight of rice. The disease occurs in areas with high numbers of weeds and can spread easily from one infected plant to another.


## **CNN MODEL PERFORMANCE**
*  CNN is a feedforward multilayered hierarchical network in which each layer conducts several transformations using a bank of convolutional kernels. The convolution procedure aids in the extraction of valuable characteristics from data points that are spatially connected.
* We implemented a custom 10 layer model for the recognition of rice leaf disease..And it include 3 convolution layers followed by 3 max pooling layers,2 dense layers and one output layer.. In this 3 convolutional layers we include several combination of filters to see how well the image assembles to the ﬁlter..pooling also pays a vital role in reducing varianceand computation complexity, resulting in fewer parameters to learn. it summarizes the feature thatappears in a portion of the feature map generated by the convolution layer.The output layer applies the softmax activation function which exponentially normalizes the dense layer..
* At the base model building with 50 epochs,after 35 epchos it overfits and main reason we observed that is insufficient training data for learning 
* We implemented augmentation technique and genrated more than 800 images using image genrator,we traained by finding best paramters using Random search in keras tuner
* After augmentation of data we searched for the best paramters using Random search in keras tuner
* We got a valuation accuracy 100% with a minimal loss of 0.2 and got a test accuracy of 94% with 0.2 loss
* To further evaluate the performance of our model, we also consider the metrics such as accuracy, precision, recall and F1 score of each rice leaf disease class,we got good precision and recall in all the disease class,but recall of class was 83% which we need to consider..
* We got an **accuracy of 94%** and it is the best model for predicting the rice leaf disease correctly
* There is only one misclassifcation in class 2 that is misclassified as class 1..The reason for this misclassification is abasense of quality and insufficient data points...Augmented images are created out of existing 85 actual images,but we need more actual images of each disease and thus we can train the model very well..Despite having better accuracy, we aim to improve the reliability and robustness of our model on diﬀerent datasets from other regions.

## **DATA AUGMENTATION AND HYPERPARAMETER TUNING IMPACT**

* **Data Augmentation**- Fewer amount of training data is a major bottleneck for developing an eﬀective deep learning models including CNN-based models for
rice leaf disease detection. To ensure the robustness of the neural network based model, we need bigger amount of data to expand the functional diversity of the model.
* We implemented data augmentation techniques and created around 800 images from  85 training images
* To augment data with image rotations, we rotate the images by 45 ◦, respectively.We also apply ﬂipping and shifting (horizontal and vertical) . Finally, shear range and fill mode is applied in augmenting rice leaf disease images. To implement the above data augmentation techniques we adopt OpenCV library and created iamges using Imagegenerator..
* Data augmentation helps to reduced overfitting issue of the data and bring a positive impact on model building
* **Hyperparamter Tuning**- We used sparse category cross_entropy as the loss function and optimizer adam(is a stochastic gradient descent method) which is computationally efficient, has little memory requirement, invariant to diagonal rescaling of gradients, and is well suited for problems that are large in terms of data/parameters..
* We run our model for maximum 6 trails and each trails include 40 epochs,The best tuned epoch is 30 in the fifth trail, as there are no further improvements in training and validation accuraciesfound for our model. it is shown that the validation and training loss also reduced to a  minimu as expected
* There are three convolution layers, Convolution 1,2 and 3 and we used 16,32 64 and in the 3rd convolution layers it is 256 which is maxmimum
* We used 3 maxpooling layers followed by each convolution layers between the range of 2 and 5 and the best result we got it from 2*2 pooling size
* We used relu as the activation function and softmax for the output layer
* Diﬀerent dropout rates 0.1 to 0.5 are experimented in the dense layer(s) of our CNN-based model.We ﬁnd that our model showcases higher training accuracies incomparison to validation accuracies for dropout rates less than 0.3 and dropoutrates greater than 0.4% (data overﬁtting)

## CHALLENGES FACED DURING THE PROJECT
* The first and most difficult challenge that we faced was lack of domain knowledge,Without domain knowledge we cannot address the relevent features correctly..For this we reffered plenty of websites to understand the rice leaf diesases
* This is the first project that we are working with CNN,Keras and Tensorflow,it feels difficult at the first time and then reffered a study materails,youtube vedios and websites like medium,geekforgeeks,towards datascience etc,....
* There is lot of syntax and logical errors while working with images and most of them resolved through stackoverflow
* Lot of time taken for model creation and we worked first in jupiter notebook(lot of experimental test are necessary) and then we used google collab to process more fast.(later integrated run with jupiter notebook)
* Less number samples for training is the another challenge,for deep learning for a better model we need sufficient samples to train and this can be solved by data augmentation
* There is also experimented some techniques that didnt went as expected.We used cut mixgenrator,Random insersion,K fold cross optimization etc and result didnt generated as expected
* Data overfitting was the another main problem, we reduced the epochs,batch size and optimised the parameters keras tuner
* Lack of knowledge regarding openCV,Random search and augmentation takes lot of time,this was resolved by reffering medium website and stackoverflow
* After data augmentation size of data get increased and it was very difficult to manage,we created a batch 16 images for training and it results easy processing



