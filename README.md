# SMP2023
The repository describes the models we used in SMP2023 Challenge.

In general, we have adopted several methods. 

The first one is HyFea, of which the codes could be found in https://github.com/runnerxin/HyFea. The codes were applied to download the images, generate the glove embeddings of the titles and tags, crawl the user additional information such as 'Pathalias', 'totalViews', 'totalTags', 'totalGeotagged', 'totalFaves','totalInGroup','photoCount', 'followerCount' and 'followingCount'. The crawled information were proved to be very useful in pratice. HyFea used the catboost as the backbone and we trained several catboost models, including using different feature combinations, different normed_labels.  

The second one is DAE+1DCNN, which was often used in time series models. We used this model to catch some times-series related information. The codes could be found in https://www.kaggle.com/code/isaienkov/keras-autoencoder-dae-neural-network-starter/notebook and https://www.kaggle.com/code/yhx003/baseline-denoiseautoencoder-1dcnn/notebook.

The third one is AutoGluon, which could be found in https://auto.gluon.ai/stable/tutorials/multimodal/multimodal_prediction/beginner_multimodal.html. We applied several models using different combinations of modalities. Such as we first ignored the categorical columns, then assigned them as categorical features.

The fourth one is Tabular, which could be found in https://www.kaggle.com/code/optimo/tabnetbaseline.

The sixth one is multimodal toolkit, which could be found in https://github.com/georgian-io/Multimodal-Toolkit.

The seventh one is lightGBM.

The fifth is the roberta model using only the text data. The pretraining codes was in https://www.kaggle.com/code/rhtsingh/commonlit-readability-prize-roberta-torch-itpt/notebook?scriptVersionId=63560998, while the finetuning codes in https://www.kaggle.com/code/rhtsingh/commonlit-readability-prize-roberta-torch-fit/notebook, and the inferencing codes in https://www.kaggle.com/code/rhtsingh/commonlit-readability-prize-roberta-torch-infer/notebook. Besides, we also used the https://www.kaggle.com/code/andretugan/lightweight-roberta-solution-in-pytorch/notebook for regression.

The quickest way to reproduce our model is to run the **./HeyFea-main/test_k_fold_model.py** using the checkpoints in **./HeyFea-main/save_model/**. We used the pesudo-labels technique to get these checkpoints.
If you want to reproduce the our model from scratch, please follow the steps blow.

Firstly, re-pretrain the roberta models using the script: wait to be updated.

Next, extract the features using pretrained models: Wait to be updated

Finally, use all the features to do the prediction.
