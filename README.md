# Commonly Interesting Images

<p align="center">
<img src="https://github.com/user-attachments/assets/934bdbff-1ef7-4a4b-bf0c-c54901517671" width="75%">
</p>

## Overview

The **FlickrUser** dataset was introduced in the research work [*Commonly Interesting Images*](https://arxiv.org/abs/2409.16736), authored by Fitim Abdullahu and Helmut Grabner.

The work investigates the concept of visual interestingness, particularly the distinction between images that are commonly perceived as interesting and those whose interestingness depends on individual preferences or interactions between different factors.

The dataset was presented at the European Conference on Computer Vision (ECCV).

## Dataset at a Glance

The FlickrUser dataset contains approximately **500,000 images from nearly 2,500 users** of the photo-sharing platform Flickr.

It combines Flickr metadata with computationally extracted visual and emotional features, as well as annotations and interestingness scores developed in the accompanying research.

The dataset can be used to investigate topics including:

- Visual interestingness and aesthetic perception.
- Differences between commonly and subjectively interesting images.
- Relationships between photographic styles and perceived interestingness.
- Emotional characteristics of images.
- Relationships between image popularity and visual characteristics.

## Dataset Contents

The dataset is distributed through two CSV files:

| File | Description |
|---|---|
| `FlickrUser_definition.csv` | Contains Flickr metadata, perceptual and connotative features, and interestingness annotations. |
| `FlickrUser_additional.csv` | Contains Flickr metadata and the computationally estimated \(CI_R\) score. |

### Download

- [FlickrUser_definition.csv](https://drive.google.com/uc?id=168w1NCAtNB6Ipxz78Q4m03GVpJW4VVsC&export=download)
- [FlickrUser_additional.csv](https://drive.google.com/uc?id=1DAhFJjJBz6Olg1WOcWL9uHoe8LhK5-QH&export=download)

Download the CSV files and place them in your working directory before following the examples below.

## Getting Started

### Requirements

The provided Playground notebook uses Python 3.10.

Create and activate the environment using:

```bash
conda create -n envInt python=3.10
conda activate envInt
pip install -r requirements.txt
```

### Loading the Dataset

The CSV files can be loaded using Pandas:

```python
import pandas as pd

# Load dataset files
df_definition = pd.read_csv("FlickrUser_definition.csv")
df_additional = pd.read_csv("FlickrUser_additional.csv")

# Display basic information
print("Definition dataset:", df_definition.shape)
print("Additional dataset:", df_additional.shape)

# Display the first entries
display(df_definition.head())
```

### Exploring the Dataset

To inspect the available features and their data types:

```python
# Display column names
print(df_definition.columns.tolist())

# Display data types and missing values
df_definition.info()

# Inspect basic statistics
display(df_definition.describe())
```

The provided `Playground.ipynb` notebook offers additional functionality for loading, saving and exploring the dataset.

## Feature Description

The `FlickrUser_definition.csv` file contains the following groups of features.

### 1. Flickr Metadata

| Column | Description |
|---|---|
| `user_id` | Unique identifier of the Flickr user. |
| `user_gender` | Gender information associated with the user. |
| `user_country` | Country associated with the user. |
| `user_timezone_label` | Timezone label of the user. |
| `user_timezone_id` | Timezone identifier of the user. |
| `favimg_url` | URL of the corresponding Flickr image. |
| `favimg_num_views` | Number of views of the image. |
| `favimg_num_favorites` | Number of favorites received by the image. |
| `favimg_num_comments` | Number of comments received by the image. |
| `favimg_upload_date` | Image upload date. |
| `favimg_owner_ispro` | Indicates whether the image owner has a Flickr PRO account. |
| `favimg_owner_occupation` | Occupation information associated with the image owner. |

### 2. Perceptual Features (VILA)

The `VILA_*` columns contain perceptual features extracted using the [VILA model](https://arxiv.org/abs/2303.14302).

These features describe different photographic styles and visual characteristics, including complementary colors, duo tones, HDR and other photographic properties.

They can be used to investigate relationships between photographic characteristics and visual interestingness.

### 3. Connotative Features (CLIP)

The `CLIP_emotion_*` columns contain emotion-related features computed using the [CLIP model](https://arxiv.org/abs/2103.00020).

They represent eight emotions (four positive and four negative) and provide a computational description of the emotional content associated with each image.

These features can be used to explore relationships between emotional characteristics and perceived visual interestingness.

### 4. Annotations and Interestingness Results

| Column | Description |
|---|---|
| `cluster_label` | Cluster assignment of the image used for dataset partitioning. |
| `partition` | Partition assignment of the image. |
| `trend_group` | Interestingness category assigned to the image: 0 (commonly interesting), 1 (interplay), or 2 (subjectively interesting). |
| `ci_score` | Interestingness score associated with the image, indicating its level of commonly interesting characteristics. |

The `trend_group` variable distinguishes three categories investigated in the research:

- **0 – Commonly interesting:** Images exhibiting characteristics associated with commonly perceived interestingness.
- **1 – Interplay:** Images representing an interplay between different factors influencing interestingness.
- **2 – Subjectively interesting:** Images whose interestingness is more dependent on individual preferences.

The `FlickrUser_additional.csv` file contains the Flickr metadata and the \(CI_R\) score computed using the computational model.

For the precise definitions, computation procedures and interpretation of the interestingness scores, please refer to the accompanying research paper.

## Example: Exploring Interestingness Groups

The following example illustrates how to inspect the distribution of the three interestingness groups:

```python
import matplotlib.pyplot as plt

group_counts = df_definition["trend_group"].value_counts().sort_index()

group_counts.plot(kind="bar")

plt.xlabel("Trend Group")
plt.ylabel("Number of Images")
plt.title("Distribution of Interestingness Groups")
plt.xticks(rotation=0)
plt.tight_layout()
plt.show()
```

## Important Considerations

- **Image availability:** Images are hosted on Flickr. Their availability depends on the original owners and Flickr's platform policies. Consequently, some image URLs may no longer be accessible.
- **Metadata:** User and image metadata reflect the information available at the time of data collection and should be interpreted accordingly.
- **Computational features:** VILA and CLIP features are model-generated representations and should not be interpreted as objective ground-truth annotations.
- **Interpretation of scores:** The interestingness scores and group assignments are research-specific computational results. Their interpretation should follow the definitions provided in the accompanying paper.
- **User information:** Demographic metadata should be interpreted with care and should not be assumed to represent the general population.

## Citation

If you use the FlickrUser dataset in your research, please cite the accompanying publication:

```bibtex
@inproceedings{abdullahu2025commonly,
  title={Commonly Interesting Images},
  author={Abdullahu, Fitim and Grabner, Helmut},
  booktitle={European Conference on Computer Vision},
  pages={180--198},
  year={2025},
  organization={Springer}
}
```

## Acknowledgements

This research was funded by the Swiss National Science Foundation (SNSF) under grant number 206319, "Visual Interestingness – All images are equal but some images are more equal than others."
