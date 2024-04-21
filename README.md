# Final project - Unconsciousness detection (by João Lopes)

This project was carried out as part of the Data Analytics course at the *Ironhack* programming school, and it was awarded the best data analytics project during the *Hackshow*, the final graduation and award ceremony. This project is about **Unconsciousness detection**, an application of artificial intelligence in image recognition and classification, and can be divided in three main chapters:
1. **Face and eye detection** in video by applying an image recognition algorithm to each of its frames in real time
2. **Eye classification** to predict whether the eyes are open or closed, and then conclude about the person’s unconsciousness
3. Identification of some **applications** in everyday situations, aiming to determine the usefulness of the previous tools

## Face and eye detection
For face and eye detection it was applied *Haar Cascades*, an object detection algorithm used in *OpenCV*, an open computer vision library. That algorithm is capable of detecting objects in images regardless of their location and scale and, although it's not the most accurate algorithm, it's realy fast, making it possible to detect objects in real-time video streams. *Haar Cascades* tend to be prone to false-positive detections and, to solve that problem, some code implementations related to facial symmetries and proportions were made in order to have the desirable outcome, i.e., the corrected face and eye detection.

## Eye classification
For eye classification it was applied the transfer learning technique. This is a technique that uses knowledge from an existing model to boost the performance of a new model used on a related task. Therefore, it was created a new neural network using some pretrained layers from *MobileNet*, an existing deep learning architecture that works with image recognition, and joining them to other completely new layers. From that new deep learning model it was possible to indentify if an eye is open or closed. That new model was trained using almost 80 000 pictures from the MRL Eye dataset, with different dimensions and equal number of open and closed eyes. That dataset was constituted by 37 people, with diversity in gender and race, and some of them were wearing glasses and makeup. Finally, it was performed a train test validation split where it was achieved 98% of accuracy for the new classification model.

## Applications
Among many possibilities, some applications were identified and explored such as:
- Alarm sounds when a security guard falls asleep
- Vehicle stops when the driver passes out 

## Conclusions
- Although Haar Cascades is not the most accurate object detection algorithm, it’s really fast, making it possible to apply it to real-time video streams
- The implementation of relevant changes related to facial symmetry and proportions allowed the improvement of the face and eye detection algorithm
- With the transfer learning technique it was possible to use existing knowledge to boost the performance of a new model used on a related task
- The eye classification model was trained using a very diverse and complete database, which made it more robust and allowed it to achieve an accuracy of 98%
- The biggest challenges faced are related to the quality of the captured image and to the difficulty of producing fast and accurate results at the same time
- The work developed was successfully applied in some real-life examples and, from one of them, an app was created (removed from this repository due to a patenting process)