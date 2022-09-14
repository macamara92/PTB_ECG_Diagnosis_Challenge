# PTB Diagnostic ECG Database Challenge

### Author: Miguel Angel Camara Vazquez

### Date: September 14st, 2022

This Challenge is based on the [PTB Diagnostic ECG Database](https://physionet.org/content/ptbdb/1.0.0/). This database contains 549 ECG recordings from 290 subjects. Each record includes 15 simultaneously measured signals: the conventional 12 leads (i, ii, iii, avr, avl, avf, v1, v2, v3, v4, v5, v6) together with the 3 Frank lead ECGs (vx, vy, vz). Signals were recorded with a sampling rate of 1 KHz, and a resolution of 16 bits.

What we wanted with this work is to be able to design and evaluate the performance of some Machine Learning and Deep Learning algorithms in an ECG classification task. One of the main aim of AI in the clinical practice is to help clinicians to decide a diagnostic, and the screening process is the first part of the process in which an algorithm should have a great performance. However, in this Challenge, we were completely unable to do that.

Does it means that AI has nothing to do in this process? Of course it has! We have to take into account several limitations that this Challenge has:
* The first one is the high database imbalance. This database has a huge amount of myocardial infarction examples, and the different algorithms performs well when predicting this category. However, the other categories are not well represented, and it decreased the ability of the models to generalize.
* The second one is the methodology to obtain the features (ML methods). We have computed some of the most simple ECG descriptors available, and there are many others that should be tested. For example, HRV-based features can be used to increase the performance of the classifiers. Moreover, the R-peaks-detection algorithm is far from perfect. The algorithm used works well in sinus rhythm, but it is not reliable in arrhythmic cases.
* The third one is the architecture of the LSTM network (DL methods). In this work we decided to test a very simple architecture, since computation times are quite large. More complex architectures should be tested, including a higher number of layers, hybrid CNN-LSTM architectures, callbacks, etc. 
* The forth one is the lack of a validation set. We decided to not to use this set, since the dataset is not so big, and the more data we have for training, the better results could have in the test set. However, this dataset is needed to better adjust the hyperparameters of both ML and LSTM algorithms.
* The last one, and related with the previous point, is the lack of cross-validation scheme. The number of subjects to which the ECG was recorded has been proved to be not enough in this task, so the selection of the examples that goes to the training or the test set can be crucial to obtain a good classification performance. We should implement a CrossValidation scheme in order to give statistical significance to the obtained results.

In conclusion, we have to be aware that working with real data is a challenge by itself. Of course, a bigger dataset could help to get better results, but developing a good AI tool to help in clinical diagnosis relies in other factors, like the computation resources, the data quality and pre-processing (garbage input... garbage output), and of course, and in-depth study of the ECG of the different pathologies.
