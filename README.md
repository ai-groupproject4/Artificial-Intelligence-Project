# Malware Detection using ML and DL Algorithms.
CS-5233-001-Spring-2022-Artificial Intelligence.

This repository is the implementation code of 5 different ML and DL algorithms used to classify and detect malware using the KDD-CUP-99 Dataset.

Malware and cyber-attack detection are field that as we move into a much more virtually connected world will continue to increase in importance. With this increase in connection there is a need to understand and evaluate methods for processing and detecting traffic. Using the KDD-CUP-99 dataset which continues a combination of legitimate and malicious traffic, we were able to evaluate multiple deep learning and machine learning models to illustrate their effectiveness in classifying that traffic. The algorithms used to classify those attacks were Random Forest (RF), K-nearest neighbor (KNN), Long Short Term Memory (LSTM-RNN), Linear Regression (LR), and Deep Belief Network (DBN). 


#  1-Random Forest

Random Forest is a supervised machine learning algorithm that is used to classify and categorize data. This method is implemented by passing data through various decision trees. Each tree will output a prediction when a datapoint passes through it. The RF classifier will select the most popular outcome between the trees.

![image](https://user-images.githubusercontent.com/100402089/166165845-b8801835-be60-42a2-b77a-ee30fce989bc.png)

To implement this algorithm rows of the dataset are randomly selected and with these rows a new dataset is built. A dataset containing the same dimensions as the original dataset. This is know as "bootstrapping".

A decision tree is then trained in each of the boothstrapped datasets and a random number of subset features is used for each of the trainings. The default parameter for the SKLEARN Random Forest Classifier is the square root of the total number of features in the dataset.
After inputing the training data, for our forest to make a prediction a data point needs to be passed through each of the decision trees and each outcome is stored. The most popular outcome between the trees of the forest will be selected and outputed as the prediction as shown in the image above. 
This means that the hight the number of trees the more accurate that our model becomes. However, one should be cautios as to not overpopulate with trees. Overpopulation may result in wasting memory space when fewer trees couldve hit the same accuracy metrics.

The model was trained using the KDD-CUP-99 dataset. The outcomes of the RF algorithm in detecting malicous connections did extremely well. After the dataset was loaded into our script and reshaped to fit the model. An accuracy of 99.87% was achieved using 50 decision trees in our forest. A confusion matrix was rendered to help visualize how our algorithm performed. 

![image](https://user-images.githubusercontent.com/100402089/166167155-1be866a4-f9a6-46c6-b35e-f1e81a1a2cd9.png)

Testing the model while adjusting different parameters showed that running the model with fewer leaf nodes resulted in better accuracy results. The model was then ran with 50 decision trees and varying the minimum leaf nodes from 1 to 10.
![image](https://user-images.githubusercontent.com/100402089/166167227-cf18465d-59aa-4016-95a7-3fc29c70b703.png)

Finally, we also ran the classifier through a set of different number of trees. This was done to see how the model performed when increasing the trees in the forest from 1 to 100. In our plot we could clearly determine how one decision tree produced the highest amount of error while exponentially reducing that error as the # of trees increased. Th graph shows how after a certain amount of trees. Around the 40 mark, the margin for error stabilizes throught out the rest. Meaning that using more that 40 trees in our model would lead to consume more memory without having any significantly improvement. 
![image](https://user-images.githubusercontent.com/100402089/166167365-1ae941e0-2aac-4f96-9cf4-3facf6b184b6.png)

RF is a fast and accurate algotihm that holds up extremely well in this scenario against deep learning methods.


























# References
-    AL-Ma'amari, M. (2018, November 17). Introduction to random forest algorithm with python. Medium. Retrieved May 1, 2022, from https://blog.goodaudience.com/introduction-to-random-forest-algorithm-with-python-9efd1d8f0157 
-    Breiman, L. Random Forests. Machine Learning 45, 5–32 (2001). https://doi.org/10.1023/A:1010933404324
-    Garg, M. (2019, February 2). Understanding random forest better through visualizations. Medium. Retrieved May 1, 2022, from https://garg-mohit851.medium.com/random-forest-visualization-3f76cdf6456f#:~:text=Tree%20plot,by%20classification%20using%20single%20feature.
-    Random Forest algorithm clearly explained! - youtube. (n.d.). Retrieved May 1, 2022, from https://www.youtube.com/watch?v=v6VJ2RO66Ag 
-    Random Forest in machine learning | machine learning training - youtube.com. (n.d.). Retrieved May 1, 2022, from https://www.youtube.com/watch?v=MpgusfbXjnM  
-    Sklearn.ensemble.randomforestclassifier. scikit. (n.d.). Retrieved May 1, 2022, from https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html 
-    Yiu, T. (2021, September 29). Understanding random forest. Medium. Retrieved May 1, 2022, from https://towardsdatascience.com/understanding-random-forest-58381e0602d2 
-    Yiu T 2019,Visualization of a Random Forest Model Making a Prediction, digital image, Towards Data Science, accessed 28 April; 2022, <https://towardsdatascience.com/understanding-random-forest-58381e0602d2/>.
-    
