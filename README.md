# Ocular Disease Recognition

Fnu Vishal, Jose M Teodosio-Meza, Solomon Lemma, Irina Chernyavsky and Katie Lamberto

## Problem Statement

This project aims to build a machines learning models that analyzes fundus images of eyes to accurately categorize them as having glaucoma, cataracts, diabetic retinopathy, or no abnormal condition.  

## Table of contents
1. [Executive Summary](#exec)
2. [Background](#back)
3. [Software Requirements](#software)
4. [Data Dictionary](#data)
5. [Flask App Description](#flask)
6. [Conclusions and Recommendations](#concl)


### 1. <a name="exec"></a>Executive Summary

Our team set out to build a convolutional neural network that would classify healthy and non-healthy eyes based on their fundus images.

We combined datasets from several sources and preprocessed the images.

We initially set out to create a multi-class model, but soon realized we needed to switch to separate binary classification models for each disease because some of the images were of eyes that had multiple diseases. This problem became apparent when early modeling showed a large degree of confusion for how to classify many of the images. After switching to binary classification models, our accuracy increased to expected levels in the 85-95% range.

Convolutional Neural Network (CNN) models are documented and analyzed in the CNN_models folder. The [Image Augmentation CNN model used on eyes with Glaucoma](./CNN_models/CNN_image_aug_glauc.ipynb) contains detailed explanations of the techniques we used for these models, including discussions of image augmentation and CNN architecture, as well as discussions of feature maps and filters. The CNN model notebooks for [Diabetic Retinopathy](./CNN_models/CNN_image_aug_dr.ipynb), [Cataracts](./CNN_models/CNN_image_aug_cataracts.ipynb), and [a model that did not use image augmentation](./CNN_models/CNN_glaucoma_no_image_aug.ipynb) contain additional results.

### 2. <a name="back"></a>Background

#### Eye Diseases

The study done by CDC indicates that approximately 12million people over the age of 40 years in the United States have visionimpairment. The number includes 1 million who are blind, 3 million who havevision impairment after correction, and 8 million who have vision impairmentdue to uncorrected refractive error. The prevalence will more than double by20250 due to the increase of diabetic and other chronic diseases. Currently, theeconomy is impacted by more than $145 billion annually because of major visionproblems among the adult population over the age of 40 years. The project builtmodels to look at the prevalence of eye diseases across the states. Sources (AmericanAcademy of Opthamology (http://www.aao.org/),  National Eye Institute (http://www.nei.nih.gov/) and (https://www.cdc.gov).

#### CNN Modeling of Eye Imagery
Our team researched optimal ways to preprocess fundus images of eyes and optimal CNN architecture to get the most accurate results possible while maintaining efficiency.

In anatomy, the [fundus is the back part of any organ]('https://medical-dictionary.thefreedictionary.com/fundus'). For eyes, the fundus specifically refers to [the retina and other parts of the eye's back surface]('https://www.aao.org/eye-health/anatomy/fundus'). Eye doctors are able [to photograph this part of the eye](https://www.opsweb.org/page/fundusphotography) by using a specialized camera and making use of the eye's pupil, which is designed as a passage for light. Eye doctors can examine the images for signs of eye disease, but doing so requires a lot of skill. CNN models offer a way to use machine learning to detect eye disease from fundus images, potentially making it easier, cheaper, and more efficient to test patients for eye disease. CNN models may also be able to detect early signs of eye disease better than eye doctors can by picking up on subtle disease patterns imperceptible to people. Detecting eye disease, and detecting it as soon as possible, significantly improves patient outcomes.



### 3. <a name="software"></a>Software Requirements

This project uses the following Python libraries:

|||
|:--|:--|
| pandas|tensorflow|
| numpy|keras|
| os|sklearn|
| matplotlib.pyplot|PIL|
| seaborn|scipy|
| plotly|skimage|
| shutil|flask|
| argparse|flask_mysqldb|
| math|wtforms|
| glob|passlib.hash|
| cv2|functools|
| pywt||



### 4. <a name="data"></a>Data Dictionary

This study utilized the following datasets:


#### Datasets and Features

The datasets used to create choropleth and multi-classification of the vision prevalence found from (https://data.world/datacrunch/) with the title “prevalence of vision problem in the US”. The datasets have non-modified eye diseases features such as race, sex and age and modifiable with more than 52,000 observations.
The description of the vision problems used in the classifications models:
- Age-Related Macular Degeneration (AMD):   disease happens as age gets older and is a leading cause of vision loss especially among people age 50 and older. 
- Glaucoma: eye conditions that damage the optic nerve by an abnormally high pressure around the eye.
- Myopia: Nearsightedness (meaning you have a difficult time seeing things far away).
- Cataract: “A cataract is a clouding of the eye’s natural lens, which lies behind the iris and the pupil.”
- Diabetic Retinopathy: vision problems caused with chronically high blood sugar from diabetes that leads to damage the tiny blood vessels in the retina and distorting vision.”
- Hyperopia: Farsightedness (meaning you have a difficult time seeing things up close)
- Vision Impairment: “A decreased ability to see to a degree that causes problems not fixable by usual means, such as glasses.”
- Blindness: complete do not see light.

Image data exploration and cleaning is documented in the image_EDA_and_preprocessing folder. Image re-sizing is done in the [image preprocessing notebook](./image_EDA_and_preprocessing/image_preprocessing.ipynb).

#### Datasets
|Dataset|Description|
|:---|:---|
|Kaggle Ocular Disease Recognition|6392 images mixed|
|Cataract Dataset|602 images mixed|
|RETINAL FUNDUS MULTI-DISEASE IMAGE DATASET|3200 images mixed|

1. https://www.kaggle.com/andrewmvd/ocular-disease-recognition-odir5k
2. https://www.kaggle.com/jr2ngb/cataractdataset
3. https://ieee-dataport.org/open-access/retinal-fundus-multi-disease-image-dataset-rfmid#files



### 5. <a name="flask"></a>Flask App
Built with:
- Python
- Java
- Bootstrap
- CSS
- HTML
- SQL
- React
To run an app:
1. Clone the Git repository
2. Install dependencies specified in the requirements.tx
3. Run an app
The application was based on the work of https://reshamas.github.io/deploying-deep-learning-models-on-web-and-mobile/.
![](https://drive.google.com/file/d/1VFrcDHeik4Kd5ti3cWIulYrQQJ_Cy5co/view?usp=sharing)


### 6. <a name="concl"></a>Conclusions and Recommendations

The CNN models used in the image augmentation achieved accuracy scores on test data of 84% for Glaucoma, and 93% for both Diabetic Retinopathy, and Cataracts. These scores are not high enough for applying in a medical diagnostic setting, but show promise because the model in the trained and tested with very limited data. We expect that adding more images to our training set and experimenting with image augmentation parameters would lead to higher accuracy scores that would potentially be useful for deployment to patients. In addition, the work revealed that multi-category classification applied to public datasets with the highest accuracy (98%) using XGB classifier. The random forest model used in the classification also shows moderate performance for multi-classification of the data with 65% accuracy. The models used in the project performs as compared with 13% of the baseline of vision problems.  
The project successfully addressed to classify the most common eye diseases accurately. To advance the performance of the models and making them deployable would be of great benefit to eye doctors and patients because it would allow for quick and accurate eye disease diagnosis without requiring initial analysis by an eye doctor. This would help patients get diagnosed more quickly and allow eye doctors to focus on other aspects of their practice, such as performing medical procedures and treating diseased eyes. 
