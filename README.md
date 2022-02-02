# VIDEO MEMORABILITY PREDICTION BASED ON C3D FEATURES

MediaEval 2018 is a competition which took place at France, Sophia Antipolis and EURECOM in October 2018. This competition had various tasks and predicting media memorability is one among those. Memorability can be defined as how good or bad a person can remember any video after a specified period of time. This is a part of MediaEval 2018 Benchmarking Initiative for Multimedia Evaluation.This study proposes a prediction of short-term memorability and long term mermarbalitiy based on the video feature called C3D Feature.

# INTRODUCTION

The fast-growing digital video media makes our life more colorful. We may enjoy dozens or even hundreds of video clips everyday while watching TV, browsing the internet,
reading multimedia magazines, watching films, etc. However, the memorability of various videos is generally not equal. We can remember some videos for a long time while forgetting others quite soon. Two interesting questions naturally arising from this phenomenon are “What makes a video memorable?” and “Can we build computational models to predict the video memorability (VM)?” The study of these questions will significantly benefit a wealth of people including not only common users, but also professional ones such as artists, photographers, advertisers, and makers of video sharing websites, games, movies, and multimedia magazines.[8].In this work I investigate the video features to predict video memorability. We conducted an extensive analysis on these features and built different regression models to determine the most robust method amongst them for predicting memorability. Among the features provided for the model, I used HMP (Hierarchical Matching Pursuit) and C3D features in a deep learning model.

# RELATED WORK

An earlier approach to model video memorability by Han et al. [8] deploys a survey-based recall experiment. Here, the participants (about 20) were initially made to watch several
videos played together in a sequence, followed by a recall task after two days or a week, where they were asked if they remember the videos being shown. The score for a video was taken to be the fraction of correct responses by the participants. Due to the long time span of the experiment, it is difficult to scale it to a larger participant size. Further, there is no control over the user behavior between viewing and recall stage[9]. The works of (Cohendet, no date), (Isola et al., 2013) and (Shekhar and Singal, no date) tells about the use multiple low level and high level visual features and some deep learning based action recognition representation (C3DPreds), and image and video captions for memorability prediction. The important conclusions from these papers are that models using captions give the best individual results and the features when passed through deep learning models significantly improve those results. Adding to that, it was found out by the researchers that high level semantic features learned by CNNs trained for image classification give state of the art performance on a variety of computed vision tasks. (Han, Liu and Fan, 2018) emphasized the use of Inception V3 features on a pre-trained model using transfer learning to have given astonishing results in areas of image classification for smaller datasets.

# METHODOLOGY


