# IUST_PersonReID Dataset  
<div align="center">
 
[![per](https://img.shields.io/badge/Language-Persian-orange.svg)](https://github.com/ComputerVisionIUST/IUST_PersonReId/blob/main/README.per.md)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Q_lA1Hi_SqVnYueyqlhTaxM2SpbRsd_K?usp=sharing)

</div>

![Dataset Overview](https://github.com/IRIUST/Iranians_Reid_dataset/assets/141324225/782122d5-235a-4314-9d81-7eceec56c960)

## News! ✨📢  
We are pleased to announce the release of **IUST_PersonReID Dataset Paper**, now available on [**arXiv**](https://arxiv.org/abs/2412.18874).  
We invite you to explore our work and welcome any feedback or discussions.

## About the Dataset
The **IUST_PersonReID** dataset was developed to address limitations in existing person re-identification datasets by including cultural and environmental contexts unique to **Islamic countries**, especially Iran and Iraq. Unlike common datasets, which don’t reflect the clothing styles common in these regions—such as hijabs and other coverings—the IUST_PersonReID dataset represents this diversity, helping to reduce **demographic bias** and improve model accuracy. Collected from a variety of real-world settings under different lighting, camera angles, indoor & outdoor, and weather conditions, this dataset provides extensive, overlapping views across multiple cameras. By capturing these unique conditions, IUST_PersonReID offers a valuable resource for developing re-ID models that perform more reliably across diverse environments and populations.

### Video Recording Locations
The videos were recorded at the locations listed below, with details summarized in the following table:

| Location                                      | Cameras | Total Hours | Resolution   | Number of Days |
|-----------------------------------------------|---------|-------------|--------------|----------------|
| Iran University of Science and Technology     | 17      | 383         | Variable     | 5              |
| Al-Aima Mosque                               | 5       | 40          | 960×1080     | 2              |
| Local Fruit Shop                              | 7       | 38          | 944×1080     | 1              |
| Local Supermarket                             | 6       | 124         | 1280×1944    | 4              |
| Arbaeen Procession                            | 2       | 3           | 1280×720     | 5              |

### Dataset Comparison
The table below compares our dataset with several well-known labeled datasets worldwide:

| Dataset    | Location                | ID (Multi-Camera) | ID (Single Camera) | Scenes | Images   |
|------------|-------------------------|--------------------|---------------------|--------|----------|
| [SoccerNet-ReID](https://github.com/SoccerNet/sn-reid)   | Football Leagues        | 243,432             | -                   | -      | 340,993   |
| [MSMT17](https://www.pkuvmc.com/dataset.html)     | University Campus       | 4,101               | -                   | 15     | 126,441   |
| [Duke](https://paperswithcode.com/dataset/dukemtmc-reid)       | Duke University Campus   | 1,413               | 439                 | 8      | 466,261   |
| [MARS](http://zheng-lab.cecs.anu.edu.au/Project/project_mars.html)       | Tsinghua University     | 1,261               | -                   | 6      | 1,191,003  |
| [Market1501](https://paperswithcode.com/dataset/market-1501) | Supermarket, Tsinghua   | 1,501               | -                   | 6      | 32,217    |
| **IUST_PersonReID**   | **Various Locations in Iran & Iraq**| **1847**           | **-**            | **19**     | **117,455**        |

### Annotation Statistics
The dataset contains 117,455 images featuring 1,847 unique identities across about 20 different scenes. Many identities are captured from multiple camera views, making this dataset valuable for testing cross-camera re-identification. You can see the distribution of identities across cameras and genders in the images below.

<p align="center">
  <img src="https://github.com/user-attachments/assets/b94e5b53-8a8f-433c-a562-87f6d6af7381" width="45%" alt="Number of IDs per Camera numbers" />
  <img src="https://github.com/user-attachments/assets/5ff8315f-d413-4bf7-9d51-050f8b1863b6" width="45%" alt="Number of IDs per Gender" />
</p>

## Key Dataset Features

1. **Automated Pedestrian Tracking**: We utilize multiple pedestrian tracking models to pre-label our data, selecting algorithms that perform best within specific environments. This approach leverages the unique strengths of each model. Our dataset is pre-labeled using [YOLOv5](https://docs.ultralytics.com/models/yolov5/), [YOLOv8](https://docs.ultralytics.com/models/yolov8/) with ByteTrack, [FairMOT](https://github.com/ifzhang/FairMOT), and [YOLOE](https://github.com/PaddlePaddle/PaddleDetection/blob/release/2.7/deploy/pipeline/docs/tutorials/pphuman_mot_en.md) models trained on the [CrowdHuman](https://www.crowdhuman.org/) dataset.

2. **Human Annotation for Enhanced Accuracy**: Human annotators use the [CVAT]([https://github.com/opencv/cvat](https://github.com/cvat-ai/cvat)) tool to refine tracking model outputs, correcting errors such as missed detections and handling challenging cases like occlusions, veiled individuals, etc. This process significantly improves the accuracy and quality of the dataset.

3. **Cross-Camera Re-identification Model**: To aid in the cross-camera re-identification of individuals, we employ a pre-trained person re-identification model based on the [Swin Transformer](https://github.com/layumi/Person_reID_baseline_pytorch) model, applied to cropped images to pre-label our data.

4. **Human-Guided Re-identification Correction**: Human reviewers further correct errors in the re-identification process across cameras using both temporal and appearance-based features. We developed a custom web application to streamline this annotation process, now publicly available on [CVLab-ReId-Tool](https://github.com/ComputerVisionIUST/CVLab-ReId-Tool), as no comparable tool was previously accessible to the public.

For detailed annotation guidelines, please refer to the [annotation documentation](https://docs.google.com/document/d/1Upnm1nJ9e8Jn3odAjlbICwgNXtRzPghF7wl5_eQRcdo/edit?usp=sharing) provided to annotators.

### Demonstration of AI Limitations
Despite advancements in artificial intelligence, AI models still struggle with video data, often resulting in missed detections and inaccuracies in tracking individuals. The following video illustrates these limitations.

https://github.com/user-attachments/assets/4cef8880-6f00-43e4-a52d-eb3f8657c31b

To overcome these issues, we employ human annotators to improve detection and tracking accuracy, ensuring a higher-quality dataset.

### Clothing Variations Over Time
The dataset also features images of individuals wearing different clothing across time frames. For instance, one identity is often captured wearing a tent-like garment and later appearing on a mantle.

![clothing-variations-over-time](https://github.com/user-attachments/assets/d79bb5bc-59b6-4476-b135-8a23c4f97c96)


## Download the Dataset

You can download the dataset package from [Google Drive](https://zaya.io/iust_personreid).

### Bounding Box Naming Convention

The **IUST_PersonReID** dataset adopts a naming convention identical to that of the Market-1501 dataset. The image naming format is structured as follows:

```
<personID>_<cameraID>_<sequenceID>_<frameID>.<extension>
```

#### Components Breakdown

1. **personID**: A unique identifier for each individual in the dataset, ranging from `0001` to the total number of identified persons.

2. **cameraID**: A single-digit identifier indicating the camera that captured the image. This ranges from `1` to the total number of cameras used in the dataset.

3. **sequenceID**: In the **IUST_PersonReID** dataset, this field is often fixed as `s1`, as it does not vary significantly.

4. **frameID**: A unique number that indicates the frame in which the person appears. This is crucial for distinguishing images captured in rapid succession of the same person and camera.

5. **extension**: The file format of the image, typically `.jpg`.

#### Example Filename

A typical filename in the **IUST_PersonReID** dataset might look like this:

```
0001_c1_s1_000151.jpg
```

#### Interpretation:

- **0001**: `personID` = `0001`
- **c1**: `cameraID` = `1`
- **s1**: `sequenceID` = `1` (often static in this dataset)
- **000151**: `frameID` = `151`

Each image represents a cropped bounding box of a pedestrian captured by one of the cameras in a real-world setting. The `personID` and `cameraID` are particularly important for person re-identification tasks, where the goal is to match images of the same individual across different camera views.


## Re-identification Models Training and Evaluation

We trained various person re-identification models using the **IUST_PersonReID** dataset to showcase their performance on the specific challenges of this dataset, such as varying clothing and different environments.

| Model | Rank-1 | Rank-5 | Rank-10 | mAP |
|-------|--------|--------|---------|-----|
|[SOLIDER-ReID](https://github.com/tinyvision/SOLIDER-REID)| 51.08%      | 65.32%      | 70.76%       | 42.35%   |
|[CLIP-ReID](https://github.com/Syliz517/CLIP-ReID)| 61.40% | 72.50% | 77.50% | 51.60% |

To make it easy to reproduce the results, we created a [**Google Colab notebook**](https://colab.research.google.com/drive/1Q_lA1Hi_SqVnYueyqlhTaxM2SpbRsd_K?usp=sharing) 
 that allows users to train and test the model on this dataset. The notebook provides simple instructions for training and evaluating the model.

## Citation

If you find this dataset useful for your research, please cite our paper.

```bibtex
@article{moghaddam2024iust_personreid,
  title={IUST\_PersonReId: A New Domain in Person Re-Identification Datasets},
  author={Moghaddam, Alireza Sedighi and Anvari, Fatemeh and Haghighi, Mohammadjavad Mirshekari and Fakhari, Mohammadali and Mohammadi, Mohammad Reza},
  journal={arXiv preprint arXiv:2412.18874},
  year={2024}
}
```
---
