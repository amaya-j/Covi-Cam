# CoviCAM

## Overview
CoviCAM is an object detection system specifically designed for detecting people in images, particularly for applications related to social distancing and crowd monitoring. The project utilizes YOLOv3, a popular deep learning algorithm, trained on the COCO dataset for accurate object detection.

## Theory
- **YOLOv3**: This deep learning model is employed for object detection. YOLO (You Only Look Once) is renowned for its speed and efficiency in real-time object detection tasks. It treats object detection as a regression problem, predicting bounding box coordinates and class label probabilities simultaneously for objects within an image.
- **Single-stage detection vs. Two-stage detection**: YOLO falls under the category of single-stage detectors, which sacrifice some accuracy for speed when compared to two-stage detectors like R-CNN. However, for applications where real-time processing is crucial, the speed advantage of YOLO is highly beneficial.
- **Non-maxima Suppression (NMS)**: To refine the detection results, NMS is applied to eliminate overlapping bounding boxes. This process ensures that only the most confident detection results are retained, reducing redundancy and facilitating accurate object counting.
- **Centroid Calculation**: After obtaining bounding box coordinates for detected persons, the centroid (center) of each bounding box is computed. This centroid information is crucial for analyzing the spatial distribution of individuals within the scene.
- **Social Distancing Monitoring**: By computing pairwise distances between centroids, CoviCAM assesses the proximity of individuals. If the distance between any two centroids falls below a certain threshold, indicating individuals are too close, it flags this as a potential violation of social distancing protocols.

## Usage
1. **Setup**: Ensure you have all necessary dependencies installed as specified in the requirements file.
2. **Model**: Download or train YOLOv3 on the COCO dataset for object detection. Pre-trained models are available for download from various sources.
3. **Configuration**: Adjust parameters such as the confidence threshold for detection and the distance threshold for social distancing monitoring to suit your application.
4. **Run**: Execute the main script, providing input images or video streams as required.
5. **Visualization**: Visualize the detection results overlaid on the input images or video frames. Additionally, monitor any violations of social distancing protocols as flagged by the system.

## Dependencies
- Python 3.x
- YOLOv3
- OpenCV
- NumPy

## Acknowledgments
- YOLOv3 implementation by [Joseph Redmon](https://pjreddie.com/darknet/yolo/)
- COCO dataset for training and evaluation

## License
This project is licensed under the [MIT License](LICENSE).

---

Feel free to customize this README according to your specific project details and requirements.
