# SMP2023
The repository describes the models we used in SMP2023 Challenge.

In general, we have adopted several methods. 

The first one is HyFea, of which the codes could be found in https://github.com/runnerxin/HyFea. The codes were applied to download the images, generate the glove embeddings of the titles and tags, crawl the user additional information such as 'Pathalias', 'totalViews', 'totalTags', 'totalGeotagged', 'totalFaves','totalInGroup','photoCount', 'followerCount' and 'followingCount'. The crawled information were proved to be very useful in pratice. HyFea used the catboost as the backbone and we trained several catboost models, including using different feature combinations, different normed_labels.  

The second one is DAE+1DCNN, which was often used in time series models. We used this model to catch some times-series related information. The codes could be found in https://www.kaggle.com/code/isaienkov/keras-autoencoder-dae-neural-network-starter/notebook and https://www.kaggle.com/code/yhx003/baseline-denoiseautoencoder-1dcnn/notebook.

The third one is AutoGluon, which could be found in https://auto.gluon.ai/stable/tutorials/multimodal/multimodal_prediction/beginner_multimodal.html. We applied several models using different combinations of modalities.

The quickest way to reproduce our model is to run the **./HeyFea-main/test_k_fold_model.py** using the checkpoints in **./HeyFea-main/save_model/**. We used the pesudo-labels technique to get these checkpoints.
If you want to reproduce the our model from scratch, please follow the steps blow.

Firstly, re-pretrain the roberta models using the script: wait to be updated.

Next, extract the features using pretrained models: Wait to be updated

Finally, use all the features to do the prediction.
