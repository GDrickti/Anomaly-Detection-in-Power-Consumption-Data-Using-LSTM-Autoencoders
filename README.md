# Anomaly-Detection-in-Power-Consumption-Data-Using-LSTM-Autoencoders
## Project Overview

This project implements an anomaly detection system for power consumption data using Long Short-Term Memory (LSTM) autoencoders. As energy demands grow, identifying unusual patterns in power usage becomes crucial for maintaining reliability, reducing costs, and preventing waste. This system leverages the UCI Household Power Consumption dataset to learn typical consumption patterns and detect anomalies that may indicate issues such as equipment malfunctions or energy theft.

## Objectives
#### Anomaly Detection: 
Develop a reliable method to automatically identify unusual patterns in power consumption data using an LSTM autoencoder.

#### Insights for Utility Companies: 
Provide actionable insights into power consumption patterns to support energy management systems.

#### Operational Efficiency: 
Enhance the reliability of power systems and reduce operational costs by flagging abnormal consumption events.
Foundation for Future Systems: Establish a scalable tool that can be adapted for various contexts, including industrial facilities and smart homes.

## Methodology

### Dataset - 
https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption

#### 1.Data Loading and Preprocessing:

Load the Household Power Consumption dataset and perform initial data analysis.
Handle missing values by filling them with the mean of respective columns.
Scale the data using MinMaxScaler for normalization.

#### 2.Dataset Creation:

Create a custom dataset class to prepare sequences of data for the LSTM model.

#### 3.Model Definition:

Define an LSTM autoencoder model consisting of an encoder and a decoder to reconstruct normal power consumption patterns.

#### 4.Training:

Train the model using Mean Squared Error (MSE) as the loss function and Adam optimizer for 10 epochs.

#### 5.Anomaly Detection:

Calculate reconstruction errors during evaluation and set a threshold to identify anomalies based on a specified percentile of errors.

#### 6.Visualization:

Visualize detected anomalies on the power consumption data and plot reconstruction errors with the threshold for easy interpretation.

## Result

![image](https://github.com/user-attachments/assets/3de592ce-9496-4ccf-87a7-d11b4fb72706)

The graph shows global active power consumption over
 time (blue line), with anomalies highlighted in red. The model
 detected unusual spikes and drops in power usage, indicating
 potential issues or irregular events. The scattered red dots
 represent the anomalies identified by the model. This visual
 helps assess the model’s ability to flag deviations from normal
 power consumption patterns accurately.

 ![image](https://github.com/user-attachments/assets/51fd731a-a7c3-403b-a39e-aad13007c811)

 The graph titled **"Reconstruction Error with Anomaly Threshold"** provides a detailed view of the performance of the LSTM autoencoder model used for anomaly detection. On the x-axis, we see an index or time series ranging from 0 to 80,000, while the y-axis displays the reconstruction error, which ranges from 0 to 0.040. The blue line on the graph represents the reconstruction error for each data point over time, exhibiting significant fluctuations. These fluctuations indicate the varying accuracy of the model in reconstructing the input data. Most reconstruction errors are relatively low, suggesting that the model performs well on the majority of the data points.

A red dashed line is prominently featured on the graph, set at approximately 0.015 on the y-axis. This line serves as the anomaly threshold, distinguishing between normal and anomalous data. When the reconstruction error, represented by the blue line, exceeds this threshold, the data point is considered an anomaly. This constant value of the threshold is crucial in identifying unusual patterns or outliers in the dataset.

The graph's overall interpretation indicates that the model accurately captures normal patterns, as evidenced by the low reconstruction errors for most of the data points below the threshold. The anomalies, marked by instances where the blue line crosses above the red dashed line, are relatively rare. These high reconstruction errors signify unusual events, confirming the model's effectiveness in distinguishing between normal and abnormal power consumption patterns. This visual representation is instrumental in validating the model's performance and its ability to detect anomalies in the dataset.

![image](https://github.com/user-attachments/assets/7094276d-b13c-4819-ac56-2ee1a173cee9)

 The histogram titled **”Reconstruction Errors Distribution”**
 suggests that the model is quite accurate. Here’s why:
 
 • **Majority of Errors are Small:** The majority of recon
struction errors are very small (close to 0), indicating that
 the model’s predictions are close to the actual values most
 of the time.
 
 • **Right-Skewed Distribution:** The distribution is heavily
 skewed to the right, with the frequency of errors decreas
ing as the error increases. This means that larger errors
 are relatively infrequent.
 
 This pattern suggests that the model accurately captures
 normal patterns in the data, with only occasional larger errors
 that might represent anomalies. Overall, the low frequency of
 large errors indicates a good level of accuracy in the model’s
 predictions.


