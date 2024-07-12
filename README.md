# Commonly Interesting Images
<p align="center">
<img src="https://github.com/user-attachments/assets/934bdbff-1ef7-4a4b-bf0c-c54901517671" width="75%">
</p>

The _FlickrUser_ dataset is introduced as part of the _Commonly Interesting Images_ research work, which is authored by Fitim Abdullahu and Helmut Grabner. This dataset was presented at the European Conference on Computer Vision 2024 (ECCV 2024).

## Dataset
The _FlickrUser_ dataset contains 500k images from close to 2.5k users of the popular photo-sharing platform Flickr. The download links provide the files _FlickrUser_defintion.csv_ and _FlickrUser_additional.csv_, which includes detailed information about the users and the images. Use the Jupyter notebook Playground.ipynb to save and load the data with Python. 

### Download Link
[FlickrUser_definition.csv](https://drive.google.com/uc?id=1wX8Ti3opqCS_AnXU88sixHElbcS_Lj03&export=download)  
[FlickrUser_additional.csv](https://drive.google.com/uc?id=1j8J6i14MqyRtlwPGPfNC5lxqIzX_e1N_&export=download)

### CSV Columns Description
The _FlickrUser_definition.csv_ file includes the following columns:

| Column Name                         | Description                                                                                 |
|-------------------------------------|---------------------------------------------------------------------------------------------|
| **Flickr Meta-Data** |
| user_id                         | Unique user ID                                                                              |
| user_gender                     | Gender of the user                                                                          |
| user_country                     | Country of the user                                                                          |
| user_timezone_label             | Timezone label of the user                                                                  |
| user_timezone_id                | Timezone ID of the user                                                                     |
| favimg_url                         | Image URL for download                                                                      |
| favimg_num_views                           | Total number of views on the image                                                          |
| favimg_num_favorites                       | Total number of favorites on the image                                                      |
| favimg_num_comments                        | Total number of comments on the image                                                       |
| favimg_upload_date                     | Upload date of the image                                                                    |
| favimg_owner_ispro                 | Indicates if the image owner is a Flickr PRO user                                           |
| favimg_owner_occupation            | Occupation of the image owner                                                     |
| **Perceptual Features ([VILA](https://arxiv.org/abs/2303.14302))** ||
| VILA_*  | Photographic styles & aesthetic score computed using the VILA model; includes various photographic style such as complementary colors, duo tones, HDR, etc. |
| **Connotative Features (bsaed on [CLIP](https://arxiv.org/abs/2103.00020))** ||
| CLIP_emotion_*                        | Emotions computed using CLIP one-shot-learning; includes eight emotions (four positive and four negative) used in emotional studies     |
| **Annotations/ Results** ||
| cluster_label                   | Cluster label of the image used for partitioning                                            |
| partition                       | Partition of the image                                                                      |
| trend_group                      | Indicates the group in which the image is categorized (0: commonly interesting, 1: interplay, 2: subjective interesting) |
| ci_score                        | CI score of the image, indicating its level of interest                                     |

The _FlickrUser_additional.csv_ file includes only the Flickr Meta-Data columns and the $CI_{R}$ score computed using the computational model.
