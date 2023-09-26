# Anomaly_detection_waymo_open
Capstone Project - Unviersity of Michigan Master's of Applied Data Science (MADS) program. 



## Summary Poster

![Anomaly Detection - Poster](https://github.com/nixu0617/Way-Anomaly-Detection_DL/assets/145882602/fe2c95ed-0be7-4cdc-819a-f379c781ad9a)


## Accessing the Data
Waymo's open datasets are available to those who register through their site and is generally open for use by the public, especially for those accessing for competitions or for academic use. they have their custom license for their data but it allows usage for academic projects and allows for reasonably small amounts of it's  data  to be published to support these projects.

Their website can be found here: [WAYMO](https://waymo.com/open/)

once you arrive at their website kindly sign up to access the data. there is no cost or restrictions to sign up. once you do, kindly go to download, scroll to perception dataset, click on 'here' link for v2.0.0, March 2023

For this project, the Waymo's Google Cloud Storage of Buckets is utilized by using Google Cloud command line actions to transfer data to personal buckets.

Cloud command line sample code of transferring complete training folder from waymo to our sample bucket:
```
gsutil -m cp -r gs://waymo_open_dataset_v_2_0_0/training gs://waymo_sample_bucket
```

## Introduction
We aim to develop a model specifically tailored for autonomous driving scenarios for helping an anomaly-object detection system of autonomous driving using the Waymo Open Source Dataset. Our project aims to leverage machine learning techniques to identify and label anomalous objects in perception 2D camera data in order to further enhance the safety and reliability of autonomous vehicles (AV). One such application of our resulting model could be the implementation of a more robust motion-prediction-behavior model based on the types of classifications we acquire. For example, whether the object classified is mobile or immobile and how to react to such an occurrence. More and more people are interested in using autonomous driving functionalities to help their driving; whether for personal use or for business, therefore, it is essential and important to improve the safety, reliability, and performance of AV.

## Pipeline
Utilize U-Net model and YOLO object detection model based on the CNN deep learning algorithms, in combination with an Autoencoder, to identify anomalies in complex open source Waymo dataset. The Autoencoder can thus help us pinpoint regions of interest that may be recognized as anomalous and are then run through a segmentation model. The segmentation model allows a clean and clear visualization of a pixel-level acurate border-representation of the anomalous object. This innovative approach allows us to achieve accurate anomaly detection and localization within real-world scenarios in a 2D space.

- Initial Image
  
![origin](https://github.com/nixu0617/Way-Anomaly-Detection_DL/assets/145882602/ca25ef80-7749-47de-a602-072f2ec1a655)



- Image Through Object Detection YOLO Model

![yolo](https://github.com/nixu0617/Way-Anomaly-Detection_DL/assets/145882602/9b152e98-9947-46e6-a12e-c3d2105f6325)


- Image Through Anomaly Detection AutoEncoder Model

<img width="477" alt="Screen Shot 2023-09-26 at 16 53 22" src="https://github.com/nixu0617/Way-Anomaly-Detection_DL/assets/145882602/f23cd8c7-727a-46c9-a5a5-ed3dac51f4d1">



- Image Through Semantic Segmentation U-Net Model
  
![unet](https://github.com/nixu0617/Way-Anomaly-Detection_DL/assets/145882602/c01a1857-c7b3-4668-b701-1b5a536f4be6)



---------------------------
## How to use code
1. Clone the repository.
2. Ensure requirements match those that are mentioned. Extra downloads may include Ultralytics and Altair, as these packages are not native towards Google Colab environments. Ultralytics is for training the YOLO model, and Altair is for statistical visualizations.
3. Model training can be done in any order with different designations of parquet quantities. We offer 1 parquet of each type required. Waymo access is required for the rest. Model training is done is **jupyter notebooks** with assisted scripts and packages. 
4. In depth usage per model is involved in their corresponding readme files.

## Example of the pipeline
With models already trained, located in the deployed_models folder, a demo notebook noted as ```Pipeline_Demo.ipynb``` with an existing demo image can be used to visualize how preprocessing images, how the models interact, and how to the end result is displayed.

## Dashboard
At this time, the dashboard isn't fully implemented with the appropiate model pipeline. Instead, a version is set that a user can upload and display an image. That image would then be prepared to run through a pipeline script. 

-------------------------------------------------------------------------------------------------------------------

### Important Links

| Title | Description | Link |
|-------|-------------|--------|
| Waymo | Location of Data | https://waymo.com/ | 
| YOLOv8 | Documentaiton of YOLO model | [yolov8 by ultralytics](https://docs.ultralytics.com/models/yolov8/) |
| U-Net | Paper citation, introduction, and information of U-Net archetecture | https://arxiv.org/abs/1505.04597 |
| Autoencoder for Anomalies | Inspiration for Autoencoder approach | https://www.analyticsvidhya.com/blog/2021/05/anomaly-detection-using-autoencoders-a-walk-through-in-python/ |

### Important Attribution

@software{yolov8_ultralytics,

author = {Glenn Jocher and Ayush Chaurasia and Jing Qiu},

title = {Ultralytics YOLOv8},

version = {8.0.0},

year = {2023},

url = {https://github.com/ultralytics/ultralytics},

orcid = {0000-0001-5950-6979, 0000-0002-7603-6750, 0000-0003-3783-7069},
icense = {AGPL-3.0}
}

