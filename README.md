# Commonly Interesting Images
The "FlickrUser" dataset is introduced as part of the research work titled "Commonly Interesting Images" authored by Fitim Abdullahu and Helmut Grabner. This dataset has been presented at the European Conference on Computer Vision 2024 (ECCV 2024).

## Dataset Description
The FlickrUser dataset contains 500k images from close to 2.5k users of the popular photo-sharing platform Flickr. The download link provides the file FlickrUser.csv, which contains detailed information about the users and the images.

### CSV Columns Description
The FlickrUser.csv file includes the following columns:
| Column Name                         | Description                                                                                 |
|-------------------------------------|---------------------------------------------------------------------------------------------|
| **user**                            | Unique user ID                                                                              |
| **img_id**                          | Unique Image ID                                                                             |
| **img_url**                         | Image URL for download                                                                      |
| **views**                           | Total number of views on the image                                                          |
| **favorites**                       | Total number of favorites on the image                                                      |
| **comments**                        | Total number of comments on the image                                                       |
| **upload_date**                     | Upload date of the image                                                                    |
| **user_gender**                     | Gender of the user                                                                          |
| **user_timezone_label**             | Timezone label of the user                                                                  |
| **user_timezone_id**                | Timezone ID of the user                                                                     |
| **img_owner_ispro**                 | Indicates if the image owner is a Flickr PRO user                                           |
| **img_owner_pro_badge**             | Shows which PRO badge the image owner has                                                   |
| **img_owner_occupation**            | Shows the occupation of the image owner                                                     |
| **set**                             | Indicates which images have been used to define the CI score                                |
| **ci_score**                        | CI score of the image, indicating its level of interest                                     |
| **cluster_label**                   | Cluster label of the image, used for categorization                                         |
| **partition**                       | Partition of the image, for dataset splitting purposes                                      |
| **group**                           | Indicates the group in which the image is categorized (0: commonly interesting, 1: interplay, 2: subjective interesting) |
| **photographic styles & aesthetic score** | Computed using the [VILA model](http://example.com) (opens in new tab), includes various photographic style metrics such as complementary colors, duo tones, HDR, etc. |
| **emotions**                        | Computed using CLIP, includes emotion score, specific emotions, and emotion categories      |
