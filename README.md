# VaahanFlow v1.1.0

![Demo GIF](https://imgur.com/a/d9zcX1k)

## Project Overview

VaahanFlow v1.1.0 is an advanced vehicle classification and estimation project designed to automate the analysis of traffic footage. By leveraging state-of-the-art deep learning models such as YOLOv8 and SSD300\_VGG16, this project processes video footage and real-time camera feeds to classify vehicles efficiently. The project also features an automated web scraping module for collecting live traffic images and analyzing vehicle type distributions.

## Key Components

### 1. Vehicle Classification and Inference

- **`main.ipynb`**: Implements the YOLOv8 model for vehicle classification. This notebook runs inferences on videos and outputs annotated results, demonstrating high accuracy and real-time processing capabilities.
- **`ssd.ipynb`**: Implements the SSD300\_VGG16 model as an alternative to YOLOv8, showcasing a different approach to vehicle classification.

### 2. Image Scraping and Analysis

- **`surveillance_distribution.ipynb`**: Automates the process of scraping images from [LTA's traffic camera page](https://onemotoring.lta.gov.sg/content/onemotoring/home/driving/traffic_information/traffic-cameras/tpe.html). The collected images are processed using the trained YOLOv8 model (`best.pt`), and visualizations are created to show the distribution of vehicle types over a 30-minute period.

### 3. Dataset Structure

- **`train/`**: Contains raw images and label files for training.
- **`dataset/`**: A processed directory mirroring `train/` but organized into `train` and `val` subfolders for model training and validation with an 80-20% split.

### 4. Model Weights

- **`yolov8n.pt`**: Pre-trained YOLOv8 weights used for initial model implementation and testing.
- **`best.pt`**: Fine-tuned weights from the trained YOLOv8 model for running inferences on scraped images.

## Installation and Usage

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/VaahanFlow.git
   cd VaahanFlow
   ```

2. **Install Required Packages**: Ensure you have Python 3.8+ and run the following command to install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Notebooks**:

   - Launch Jupyter Notebook or Jupyter Lab.
   - Open `main.ipynb`, `ssd.ipynb`, or `surveillance_distribution.ipynb` and run the cells step-by-step.

4. **Execute Image Scraping**:

   - Run `surveillance_distribution.ipynb` to collect images from the traffic camera source and perform vehicle type distribution analysis.

## Features

- **YOLOv8 Vehicle Classification**: High-speed, accurate vehicle classification on videos.
- **SSD300\_VGG16 Implementation**: An alternative deep learning model for benchmarking.
- **Image Scraping Module**: Automates collection of live traffic images from web sources.
- **Data Visualization**: Generates insightful visualizations for analyzing traffic flow and vehicle type distributions.

## Output Examples

- **Processed Videos**: Annotated videos with detected vehicles.
- **Distribution Graphs**: Charts showing the frequency of vehicle types over specific time periods.

## Future Enhancements

- Integrating more advanced models and architectures for better accuracy.
- Adding a real-time processing pipeline for live video feeds.
- Expanding the dataset to include different times of day and weather conditions for improved model robustness.

## Acknowledgements

- Special thanks to the [LTA Traffic Cameras](https://onemotoring.lta.gov.sg/content/onemotoring/home/driving/traffic_information/traffic-cameras/tpe.html) for providing public access to traffic images.
- The project utilizes the YOLOv8 architecture developed by the Ultralytics team.

---

**Author**: Sarang Deb Saha\
**Version**: 1.1.0\
**License**: MIT License
