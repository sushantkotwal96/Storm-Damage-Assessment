# Storm-Damage-Assessment

## Objective:
The aim of this project is to identify damaged and undamaged residential and commercial buildings in Puerto Rico from satellite images taken in 2017. This project focuses on the city of San Juan, utilizing a GeoTiff file of satellite imagery to detect and classify building damage.

## Problem Statement
Given a large GeoTiff file (1.5 GB, approx 38000x74000 pixels) of San Juan, Puerto Rico, the challenge is to accurately detect damaged and undamaged buildings, both residential and commercial. The project involves:

Handling large satellite images
Generating smaller image grids for processing
Annotating images for training the model
Training and evaluating object detection models

## Approach
1. Image Processing
- Initial Data Handling:
  - The GeoTiff file was split into 10,000 smaller images of size 512x512 pixels.
Annotation:
Selected images based on building types: damaged commercial, damaged residential, undamaged commercial, undamaged residential.
Used the LabelMe tool for annotating images.
2. Model Training
- Initial Model:
  - Trained using Yolov8.
  - Evaluation Metric: Mean Average Precision (MAP).
  - Initial training on 50 images yielded a MAP of 0.40.
  - Further training on 100 images improved MAP to 0.60.
- Challenges:
  - Imbalance in data with more residential buildings.
  - Difficulty in distinguishing between residential and commercial buildings.
  - Limited manually annotated images for comprehensive training.
3. Generative AI Integration
- Synthetic Data Generation:
  - Used Stable Diffusion Model (Turbo version) to generate additional images of damaged commercial buildings.
  - Generated 10-15 synthetic images due to cost constraints.
- Outcome:
  - Synthetic images slightly improved the MAP.
4. Model Improvement
- Yolov9 Implementation:
  - Adopted Yolov9 for better performance.
  - Overcame the lack of Ultralytics integration by cloning and modifying the Yolov9 repository.
  - Adjusted detection scripts to match required submission format.
   Achieved a final MAP of 0.40.
