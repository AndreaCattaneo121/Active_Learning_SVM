# Active_Learning_SVM
An Active Learning approach for scaling the SVM algorithm on huge datasets
My thesis work consisted of developing an algorithm for scaling a binary SVM classifier on huge datasets. The idea was to use an active learning approach to speed up the training of an SVM. The active learning approach consists in using a model to select the most informative points and to use them to build a subset of points on which the final model will be trained. 
In this case the active learning procedure was carried out as follows:
Step 1: Extract a random subset from the original data set and train a model on this subset.
Step 2: Create a new subset consisting of the support vectors of the previous model and a maximum of 4 points from the entire training set. The 4 points were selected according to the following criteria: 
   - one point for each class corresponding to the closest point to the hyperplane, chosen between the correctly classified points that are inside the margin
   - one point for each class corresponding to the point furthest from the hyperplane and selected between the misclassified points.
Step 3: Train a new model with this new subset and check if there are any points inside the margin or misclassified.
The procedure is iterative and stops when there are no points inside the margin or misclassified, or when the selected points are already in the training set.
