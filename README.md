# YOLOv9 Training Pipeline

This repository demonstrates the process of training a custom object detection model using YOLOv9. Follow the steps below to set up your environment, prepare data, and train the model.

---

## Table of Contents

1. [Mount Google Drive](#mount-google-drive)
2. [Prepare Data](#prepare-data)
3. [Clone Repository](#clone-repository)
4. [Install Requirements](#install-requirements)
5. [Train Model](#train-model)
6. [Save Results](#save-results)

---

## Mount Google Drive

Mount your Google Drive to save and access data easily.

```python
from google.colab import drive
drive.mount('/content/drive')
```

---

## Prepare Data
Upload and unzip your data files. Update the paths accordingly.

```!scp /path/to/your/data.zip /content/
!unzip /content/data.zip -d /content/
```

---

## Clone Repository
Clone the YOLOv9 repository for model training.

```!git clone https://github.com/computervisioneng/yolov9
%cd yolov9
```

---

## Install Requirements
Install all dependencies needed to run YOLOv9.

```!pip install -r requirements.txt
```

---

## Train Model
Use the Yolov9 class to initiate model training. Replace <path_to_data.yaml> with the actual path to your data.yaml file.

```from yolov9 import Yolov9

model = Yolov9('object-detection')
model.train(data='/content/path_to_data.yaml', epochs=20)

```

## Save Results
Copy the results of the training (runs directory) to your Google Drive for future reference.

```from shutil import copytree

source_directory = '/content/yolov9/runs'
destination_directory = '/content/drive/MyDrive/YoloV9_Results'

copytree(source_directory, destination_directory)

```

## Notes
- Data Preparation: Ensure the data.yaml file is properly configured with paths to your training, validation datasets, and class labels.
- Custom Parameters: You can adjust hyperparameters (e.g., learning rate, batch size, etc.) within the train() method.
- Environment: This guide is optimized for use in Google Colab but can be adapted for other environments.


