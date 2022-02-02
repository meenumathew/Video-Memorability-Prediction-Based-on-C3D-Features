# VIDEO MEMORABILITY PREDICTION BASED ON C3D FEATURES

MediaEval 2018 is a competition which took place at France, Sophia Antipolis and EURECOM in October 2018. This competition had various tasks and predicting media memorability is one among those. Memorability can be defined as how good or bad a person can remember any video after a specified period of time. This is a part of MediaEval 2018 Benchmarking Initiative for Multimedia Evaluation.This study proposes a prediction of short-term memorability and long term mermarbalitiy based on the video feature called C3D Feature.

# I. INTRODUCTION

The fast-growing digital video media makes our life more colorful. We may enjoy dozens or even hundreds of video clips everyday while watching TV, browsing the internet,
reading multimedia magazines, watching films, etc. However, the memorability of various videos is generally not equal. We can remember some videos for a long time while forgetting others quite soon. Two interesting questions naturally arising from this phenomenon are “What makes a video memorable?” and “Can we build computational models to predict the video memorability (VM)?” The study of these questions will significantly benefit a wealth of people including not only common users, but also professional ones such as artists, photographers, advertisers, and makers of video sharing websites, games, movies, and multimedia magazines.[8].In this work I investigate the video features to predict video memorability. We conducted an extensive analysis on these features and built different regression models to determine the most robust method amongst them for predicting memorability. Among the features provided for the model, I used HMP (Hierarchical Matching Pursuit) and C3D features in a deep learning model.

# II. RELATED WORK

An earlier approach to model video memorability by Han et al. [8] deploys a survey-based recall experiment. Here, the participants (about 20) were initially made to watch several
videos played together in a sequence, followed by a recall task after two days or a week, where they were asked if they remember the videos being shown. The score for a video was taken to be the fraction of correct responses by the participants. Due to the long time span of the experiment, it is difficult to scale it to a larger participant size. Further, there is no control over the user behavior between viewing and recall stage[9]. The works of (Cohendet, no date), (Isola et al., 2013) and (Shekhar and Singal, no date) tells about the use multiple low level and high level visual features and some deep learning based action recognition representation (C3DPreds), and image and video captions for memorability prediction. The important conclusions from these papers are that models using captions give the best individual results and the features when passed through deep learning models significantly improve those results. Adding to that, it was found out by the researchers that high level semantic features learned by CNNs trained for image classification give state of the art performance on a variety of computed vision tasks. (Han, Liu and Fan, 2018) emphasized the use of Inception V3 features on a pre-trained model using transfer learning to have given astonishing results in areas of image classification for smaller datasets.

# III. METHODOLOGY
# Data Set: 
The dataset is composed of 10,000 short soundless videos shared under a license that allows their use and redistribution in the context of MediaEval 2018. These 10,000 videos were split into 8,000 videos for the development set and 2,000 videos for the test set.[1].Also have data sets of features includes: Captions, C3D spatiotemporal visual features,a 3-dimensional convolutional network proposed for generic video analysis[2] , HMP, the histogram of motion patterns for each video[3].HoG descriptors (Histograms of Oriented Gradients) [4] are calculated on 32x32 windows on a grayscale version of each frame; LBP (Local Binary Patterns) are calculated for patches of 8x15 pixels[5], InceptionV3 features correspond to the output of the fc7 layer of the InceptionV3 deep network [6]; ORB features[7] ,BRIEF descriptor ,Color histograms are computed in the HSV space and Aesthetic visual features, composed of color, texture and object based descriptors, aggregated through the computation of their mean and median values, are extracted for each 10-frame of one single video[1].
# Approach
Among the above mentioned features I have selected two features such as HMP and C3D for predicting short term memorability and long term memorability.
To find the best model, I have used Dev-Set data which contains information of 6000 videos with ground truth values and then split it into two datasets for training and
testing purposes. First I take HMP Features and then combine it with a ground truth dataset. While analysing this data I could find that there exist so many columns(1189 columns) having zero values;In addition to no of features of data set is much bigger than its row count.And so to improve its accuracy I
have applied Principal Component Analysis (PCA) to this data set.Before implementing PCA,scale the X data to unit variance by using Standard Scaler Method.And then split
the data sets as X_Tarin,Y_Train, X_Test, And Y_Test.After that build a four different model involves Linear Regression,Decision Tree Model,Gradient Boosting
Regression and Random Forest Regression and then Calculate the Spearman’s Rank Correlation Coefficient of both Short Term Memorability Score and Long Term Memorability Score.The Spearman’s Rank Correlation Coefficient of predicted Y values helped me to realise HMP features has less influences on accurate prediction. This leads me to take another feature called C3D. The second model uses the joined data set of ground truth values and C3D features of video.The main steps involves in this phase are:
- ● Make a list of video names and its C3D features and combine it as a single dataframe.
- ● Merge this ground truth data set with C3D features with index as video name and save it as pickle file for easy access of data set .
● Find X and Y variables and apply PCA after scaling the x values.
● Split the 80% of data set as training set and 20% of data set as testing set.
● Build a Linear Regression, Decision Tree Model, Gradient Boosting Regression and Random Forest Regression for both Short TErm Memorability and Long Term Memorability.
● Find the Spearman’s Rank Correlation Coefficient of each model for finding the best one.
After analyzing the value of Spearman’s Rank Correlation Coefficient of this dataset ,decided to take this dataset and also choose the Random Forest Model, which has the highest score, for determining the final data set.For predicting ground truth values take combined dataset of ground truth and C3D Features of Dev-Set as aTraining Set and corresponding Test-Set data(ground truth data set +C3D features dataset of Test-Set Folder).Then applied PCA for X variable and build Random Forest Regression Model.Finally, the predicted ground truth values are saved as csv file.

# IV. RESULTS AND ANALYSIS

As compared GroundTruth DataSet With HMP features,The second data set(GroundTruth DataSet With C3D features)has great influence on predicting more accurate data. While analysing the second data set we could reach the conclusion that the Random Forest Regression model is the best one.The results are tabulated as below (Table 1). and the scores are calculated using Spearman's Correlation.

# V. DISCUSSION AND OUTLOOK
Selecting the most relevant features of each feature data tests and then combining all that revant features into a ground truth set might give more accurate predictions.

# REFERENCES
[1] Romain Cohendet, Claire-Hélène Demarty, Ngoc Q. K.Duong1, Mats Sjöberg, Bogdan Ionescu, and Thanh-Toan Do.(2018). MediaEval 2018: Predicting Media Memorability. arXiv:1807.01052
[2] Du Tran, Lubomir Bourdev, Rob Fergus, Lorenzo Torresani, and Manohar Paluri. 2015. Learning Spatiotemporal Features with 3D Convolutional Networks. In Proc. IEEE Int. Conf. on Computer Vision (ICCV). 4489–4497
[3] Jurandy Almeida, Neucimar J Leite, and Ricardo da S Torres. 2011. Comparison of video sequences with histograms of motion patterns. In Image Processing (ICIP), 2011 18th IEEE International Conference on. IEEE, 3673–3676.
[4] Navneet Dalal and Bill Triggs. 2005. Histograms of oriented gradients for human detection. In Computer Vision and Pattern Recognition, 2005. CVPR 2005. IEEE Computer Society Conference on, Vol. 1. IEEE, 886–893.
[5] Dong-Chen He and Li Wang. 1990. Texture unit, texture spectrum, and texture analysis. IEEE transactions on Geoscience and Remote Sensing 28, 4 (1990), 509–512.
[6] Christian Szegedy, Vincent Vanhoucke, Sergey Ioffe, Jon Shlens, and Zbigniew Wojna. 2016. Rethinking the inception architecture for computer vision. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2818–2826.
[7] Ethan Rublee, Vincent Rabaud, Kurt Konolige, and Gary Bradski. 2011. ORB: An efficient alternative to SIFT or SURF. In Computer Vision (ICCV), 2011 IEEE international conference on. IEEE, 2564–2571.
[8] J. Han, C. Chen, L. Shao, X. Hu, J. Han, and T. Liu. Learning computational models of video memorability from fmri brain imaging. IEEE transactions on Cybernetics, 45(8):1692– 1703, 2015.
[9] S. Shekhar, D. Singal, H. Singh, M. Kedia and A.Shetty, "Show and Recall: Learning What Makes Videos Memorable," 2017 IEEE International Conference on Computer Vision Workshops (ICCVW), 2017, pp. 2730-2739, doi: 10.1109/ICCVW.2017.321.



