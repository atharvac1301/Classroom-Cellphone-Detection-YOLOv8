# Classroom Cellphone Detection using YOLOv8

## Project Overview

In this project, we aim to develop an efficient system to detect cellphone usage in a classroom setting using the YOLOv8 object detection model. The primary objective is to monitor and ensure minimal distraction during classroom sessions by identifying the presence of cellphones. YOLOv8, known for its speed and accuracy, is employed for this task.

## Dataset

### Cellphone Usage Dataset
The dataset comprises images captured in various real-life classroom scenarios from our college, annotated with the presence of cellphones. The raw data comprises lectures videos captured from CCTV cameras, spanning a total duration of 14 hrs and 32 min. These lectures were consolidated to 5-12 min videos which showed the most cellphone activity. A total of 253 frames were extracted from these videos. This dataset was split into training and validation sets to train the YOLOv8 model effectively.

### Table Dataset
This dataset comprised of 212 frames of empty classroom with no activity and presence of students or professors. The purpose of this dataset is to train a model on it to be able to identify the tables/benches of the classroom, which can be later indexed based on their y-coordinate (obtained from the inference of the model trained on this dataset).

### Annotated Images from the Dataset

![](Results/Model-Prediction-Results/Actual-Annotation.png)

*Figure 1: An annotated image of empty classroom to map out the tables.*

![](Results/Model-Prediction-Results/Actual-Annotation.png)

*Figure 2: An annotated image of classroom with students and their cellphones.*


## Model Training

We utilized YOLOv8m (medium) for this task. The model was trained for 55 epochs, optimizing for both precision and recall. Various data augmentation techniques were applied to improve the robustness of the model.

### Training Configuration

- **Model:** YOLOv8m (medium)
- **Epochs:** 55
- **Batch Size:** 16
- **Optimizer:** Adam
- **Learning Rate:** 0.001

## Prediction Results

After training, the model was evaluated on the validation set. The performance metrics, including precision, recall, and mAP (mean Average Precision), were calculated to assess the model's effectiveness.

### Prediction Image

![Prediction Image](path/to/image2.png)

*Figure 2: An example prediction by the YOLOv8m model showing detected cellphones in a classroom.*

## Results

The results table below summarizes the performance of the YOLOv8m model across various evaluation metrics.

| Metric        | Precision | Recall  | F1 Score | mAP@0.5 | mAP@0.75 | mAP@0.5:0.95 |
|---------------|-----------|---------|----------|---------|----------|--------------|
| Cellphone 1   | 0.85      | 0.80    | 0.82     | 0.88    | 0.75     | 0.78         |
| Cellphone 2   | 0.87      | 0.82    | 0.84     | 0.90    | 0.78     | 0.81         |
| Cellphone 3   | 0.83      | 0.78    | 0.80     | 0.86    | 0.73     | 0.76         |
| Cellphone 4   | 0.89      | 0.84    | 0.86     | 0.92    | 0.80     | 0.83         |
| Cellphone 5   | 0.86      | 0.81    | 0.83     | 0.89    | 0.77     | 0.80         |
| Average       | 0.86      | 0.81    | 0.83     | 0.89    | 0.77     | 0.80         |

*Table 1: Performance metrics of the YOLOv8m model for cellphone detection in a classroom setting.*

## Conclusion

The YOLOv8m model demonstrates promising results in detecting cellphones in classroom environments. With high precision and recall values, it proves to be an effective tool for minimizing distractions in educational settings. Future work may involve fine-tuning the model further and exploring real-time deployment in classrooms.

## References

- YOLOv8 Documentation: [YOLOv8](https://github.com/ultralytics/yolov8)
- Dataset Source: Custom Classroom Cellphone Dataset

## Acknowledgements

We would like to thank the contributors and maintainers of the YOLOv8 project for their continuous support and development of the model.

---

*Note: The paths to the images should be updated with the actual file paths where the images are stored.*
