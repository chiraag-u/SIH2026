# Smart Farming Assistant

**Note: This AI model developed is a prototype; further datasets and fields would be added. As an example, just a few fields and datasets have been uploaded; in further rounds, complete and extended datasets will be used.**

**Team Name**: Cipher Lords

**Problem Statement ID**: SIH26180 - Agriculture, FoodTech & Rural Development

Instructions to run the project can be found in the [**Usage**](#usage) section (at the last).

Model training results can be found in the [**Results**](#results) section (at the last).

If the .ipynb file doesn't open in inbuilt github editor, you can check my code in this link 
https://colab.research.google.com/drive/1AKtagHTiKVXlClUHg-jJcrs0zpi1tpKy?usp=sharing

**Farmer Analytics & Advisory Website**: https://tinyurl.com/Farmer-Advisory-SIH

### Edge AI-powered crop health monitoring and precision farming system

An **AI-powered, field-deployable Smart Farming Assistant** designed to help farmers detect crop diseases, pests, nutrient deficiencies, irrigation requirements, and environmental risks at an early stage.

The system combines **Edge AI, multi-sensor monitoring, computer vision, and weather APIs** to provide real-time, actionable insights directly at the farm level  even in areas with limited internet connectivity.

---

## Our Solution

The Smart Farming Assistant is a **Raspberry Pi-based edge system** that continuously monitors the farm using sensors and a camera.

### Core capabilities

* AI-based crop disease & pest detection
* Nutrient deficiency analysis
* Smart irrigation monitoring
* Environmental condition monitoring
* Weather-based risk forecasting
* Real-time edge processing
* Early alerts and farmer recommendations
* Crop health and environmental analytics

Critical processing is performed locally on the edge device, reducing dependence on continuous cloud connectivity.

---

## AI & Computer Vision

A deep-learning model is trained to analyze crop images and identify diseases and pests.

### Model Pipeline

```text
Crop Image
    ↓
Data Augmentation
    ↓
Data Transformation
    ↓
Transfer Learning
    ↓
SqueezeNet
    ↓
Model Training
    ↓
Model Testing
    ↓
Deployment on Raspberry Pi
```

The project uses a large dataset of crop diseases and pests, with **data augmentation and transformation** to improve model robustness.

The trained model is tested using real-time images before deployment on the Raspberry Pi.

---

## Multi-Sensor Monitoring

The system combines multiple sensors to monitor field conditions.

| Sensor                    | Purpose                                      |
| ------------------------- | -------------------------------------------- |
| DS18B20               | Temperature monitoring                       |
| AHT20                  | Temperature & humidity                       |
| Soil Moisture Sensor   | Soil moisture & irrigation decisions         |
| Rain Sensor           | Rainfall detection                           |
| Photoresistor / BH1750 | Ambient light monitoring                     |
| RS485 NPK Sensor       | Nitrogen, Phosphorus & Potassium measurement |

An **ESP32** is used for sensor connectivity, while the **Raspberry Pi** performs higher-level processing and AI inference.

---

## Smart Irrigation

The system monitors:

* Soil moisture
* Temperature
* Humidity
* Rainfall
* Weather forecasts

These parameters are used to identify potential **water stress and over-irrigation** conditions.

The system can provide recommendations such as:

```text
 Irrigate Now
 Delay Irrigation
 Rain Expected
 Low Soil Moisture
```

A relay can also be integrated to control irrigation equipment electronically.

---

##  Crop Health & Pest Detection

The camera captures plant images that are analyzed by the AI model.

The system aims to identify:

* Crop diseases
* Pest activity
* Nutrient deficiencies
* Plant growth and health

Early detection enables **targeted intervention** instead of blanket treatment across the entire field.

---

## Environmental Risk Monitoring

Sensor data and weather API forecasts are combined to identify potentially harmful environmental conditions.

The system can provide warnings for:

* Heat stress
* Drought conditions
* Excessive rainfall
* Flood risk
* Increasing pest activity
* Potential disease outbreaks

This allows farmers to respond before a localized problem becomes a larger crop failure.

---

## Edge AI Architecture

```text
                 ┌──────────────────┐
                 │   Farm / Crops   │
                 └────────┬─────────┘
                          │
             ┌────────────┴────────────┐
             │                         │
       ┌─────▼─────┐             ┌────▼─────┐
       │  Sensors  │             │  Camera  │
       └─────┬─────┘             └────┬─────┘
             │                        │
             └──────────┬─────────────┘
                        │
                  ┌─────▼─────┐
                  │   ESP32   │
                  │  Sensors  │
                  └─────┬─────┘
                        │
                  ┌─────▼─────┐
                  │ Raspberry │
                  │    Pi     │
                  └─────┬─────┘
                        │
             ┌──────────┴──────────┐
             │                     │
       ┌─────▼─────┐        ┌──────▼──────┐
       │ Edge AI   │        │ Sensor Data │
       │ Inference │        │ Processing  │
       └─────┬─────┘        └──────┬──────┘
             │                     │
             └──────────┬──────────┘
                        │
                  ┌─────▼─────┐
                  │ Decision  │
                  │  Engine   │
                  └─────┬─────┘
                        │
             ┌──────────┴──────────┐
             │                     │
       ┌─────▼─────┐        ┌──────▼──────┐
       │ Farmer    │        │ Weather API │
       │ Alerts    │        │ Forecasts   │
       └───────────┘        └─────────────┘
```

The key advantage is that **AI inference and sensor processing happen on the field-deployed device**, allowing the system to continue providing critical insights even with poor or intermittent connectivity.

---


## Technologies Used

### Hardware

* Raspberry Pi
* Camera Module
* ESP32
* DS18B20
* AHT20
* Soil Moisture Sensors
* Rain Sensor
* Photoresistor / Light Sensor
* RS485 NPK Sensor
* Relay Module

### AI / Software

* Deep Learning
* Computer Vision
* SqueezeNet
* Transfer Learning
* Data Augmentation
* Edge AI
* Weather API
* Web Dashboard
* SMS Alerts

---

##  Results

These are the predictions made by our pretrained AI model.
The Prob, is the probability with which model can assure that it is the disease classified.

<img width="512" height="411" alt="download" src="https://github.com/user-attachments/assets/d83e1ff9-4e0e-41f5-9550-6c6c0904c365" />

<img width="297" height="411" alt="download" src="https://github.com/user-attachments/assets/089eea69-d55a-459f-9d9c-60fec698d9d0" />

<img width="297" height="411" alt="download" src="https://github.com/user-attachments/assets/8038d705-d927-424f-bb5e-9801375c3bcc" />

<img width="290" height="411" alt="download" src="https://github.com/user-attachments/assets/339d3763-c28a-409a-af30-a941d926ff4b" />


---

## Usage
The same can be replicated in any computer, by downloading the SIH_ModelTransferLearning.ipynb, uploading it in Google Collaboratory. To run the file, you can connect it to Nvidia Tesla T4 GPU, and click on run all. Make sure to download the necessary dataset.



---
