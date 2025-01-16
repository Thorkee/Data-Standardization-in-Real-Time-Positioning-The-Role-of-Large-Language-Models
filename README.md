# Enhancing Positioning Accessibility through Large Language Model-Driven Data Standardization

[![Explore our Lab](https://img.shields.io/badge/Visit-PolyU_IPN_Lab-red)](https://www.polyu.edu.hk/aae/ipn-lab/us/index.html)
[![Reference Slide](https://img.shields.io/badge/Explore-Reference_Slide-blue)](https://github.com/maxystory/Data-Standardization-in-Real-Time-Positioning-The-Role-of-Large-Language-Models/blob/main/Reference.pdf)

This repository accompanies the paper *"Enhancing Positioning Accessibility through Large Language Model-Driven Data Standardization,"* which has been submitted to the IEEE Internet of Things (IoT) Journal. The journal manuscript is an extended version of the conference paper presented at the **International Conference on Indoor Positioning and Indoor Navigation (IPIN 2024)**. The conference paper has been indexed by IEEE Xplore: [Exploring the Feasibility of Automated Data Standardization using Large Language Models for Seamless Positioning](https://ieeexplore.ieee.org/abstract/document/10786123).

The paper explores the use of Large Language Models (LLMs) to automate the standardization of heterogeneous sensor data, thereby improving data compatibility and positioning accuracy in IoT environments.

## Authors

### Max Jwo Lem Lee
[![GitHub](https://img.shields.io/badge/GitHub-@maxystory-green)](https://github.com/maxystory)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://www.linkedin.com/in/maxae/)
- PhD Candidate, Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [maxjl.lee@connect.polyu.hk](mailto:maxjl.lee@connect.polyu.hk)

---

### Ju Lin
[![GitHub](https://img.shields.io/badge/GitHub-@thorkee-green?logo=github)](https://github.com/thorkee)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-Profile-blue?logo=google-scholar)](https://scholar.google.com/citations?view_op=list_works&hl=en)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://julin.org/)
- Undergraduate, Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [ju.lin@connect.polyu.hk](mailto:ju.lin@connect.polyu.hk)

---

### Xiwei Bai
[![GitHub](https://img.shields.io/badge/GitHub-@baaixw-green?logo=github)](https://github.com/baaixw)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-Profile-blue?logo=google-scholar)](https://scholar.google.com.hk/citations?user=bnTJHXYAAAAJ&hl=en)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://xiweibai.my.canva.site/)
- Member, IEEE
- Postdoctoral Fellow, Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [x.w.bai@polyu.edu.hk](mailto:x.w.bai@polyu.edu.hk)

---

### Li-Ta Hsu *(Corresponding Author)*
[![GitHub](https://img.shields.io/badge/GitHub-@qmohsu-green?logo=github)](https://github.com/qmohsu)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-Profile-blue?logo=google-scholar)](https://scholar.google.com.hk/citations?user=GxfOCUMAAAAJ&hl=en)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://www.polyu.edu.hk/aae/people/academic-staff/dr-hsu-li-ta/)
- Senior Member, IEEE
- Associate Head and Associate Professor, Limin Endowed Young Scholar in Aerospace Navigation, Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [lt.hsu@polyu.edu.hk](mailto:lt.hsu@polyu.edu.hk)

## Abstract

The integration of diverse sensor data from Internet of Things (IoT) devices, such as smartphones and specialized systems like Ultra-Wideband (UWB), is essential for accurate positioning in various applications. This paper presents a dual-stage data standardization framework that employs Large Language Models (LLMs) to automate the transformation of heterogeneous sensor data into a uniform format. The first stage utilizes a fine-tuned LLM to directly predict standardized data, while the second stage generates transformation rules based on the predictions, enabling continuous and efficient standardization for new incoming data. Additionally, this approach incorporates an Extended Kalman Filter (EKF) for sophisticated sensor data fusion, significantly improving the positioning system’s accuracy. Our dual-stage method achieves high success rates of 97.5% for handling non-uniform units and 98.5% for managing missing entries, while also notably reducing positioning errors to 0.33 meters by integrating GNSS, Visual Positioning System (VPS), UWB, and IMU sensors. Evaluations in dynamic environments have demonstrated the method’s improvements in operational efficiency and scalability, validating the effectiveness of the dual-stage LLM framework in navigating the complexities of sensor data integration. This proposed method not only streamlines the processing of diverse data types but also lays the groundwork for more robust and adaptable IoT navigation solutions, leading to marked enhancements in positioning accuracy and operational efficiency.

# Table of Contents
1. [Contributions](#-contributions)
2. [Framework Overview](#-framework-overview)
   - [Dual-Stage Approach](#dual-stage-approach)
   - [Single-Stage Approach](#single-stage-approach)
   - [Unit Tests for Data Integrity](#unit-tests-for-data-integrity)
   - [Sensor Fusion with EKF](#sensor-fusion-with-ekf)
3. [Automated Data Standardization](#-automated-data-standardization)
   - [Input Data Representation](#input-data-representation)
   - [Output Data Representation](#output-data-representation)
   - [Standardization Process](#standardization-process)
   - [Standardized Data Schema](#standardized-data-schema)
4. [Training and Validation Performance](#-training-and-validation-performance)
   - [Common Data Input Issues](#common-data-input-issues)
   - [Model Performance](#model-performance)
   - [Loss Function](#loss-function)
   - [Mean Token Accuracy](#mean-token-accuracy)
   - [Limitations and Future Work](#limitations-and-future-work)
5. [Standardized Dataset Unit Tests](#-standardized-dataset-unit-tests)
   - [Validation Function](#validation-function)
   - [Feedback Loop](#feedback-loop)
6. [Transformation Rules Automation](#-transformation-rules-automation)
   - [Second Stage in Dual-Stage Approach](#second-stage-in-dual-stage-approach)
   - [Single-Stage Approach](#single-stage-approach)
   - [Transformation Rules Schema Structure](#transformation-rules-schema-structure)
7. [Transformation Rules Unit Tests](#-transformation-rules-unit-tests)
8. [Sensor Fusion](#-sensor-fusion)
   - [State Vector and Transition Matrix](#state-vector-and-transition-matrix)
   - [Measurement Model](#measurement-model)
   - [Statistical Analysis of Sensor Measurement Variances](#statistical-analysis-of-sensor-measurement-variances)
   - [Control Input](#control-input)
9. [Experiment](#-experiment)
   - [Comparison of Data Standardization Methods](#comparison-of-data-standardization-methods)
   - [Experiment Setup](#experiment-setup)
   - [Experiment Results](#experiment-results)
10. [Evaluation of Common Data Input Issues](#-evaluation-of-common-data-input-issues)
    - [Non-uniform Units](#non-uniform-units)
    - [Missing Entries](#missing-entries)
    - [Unstructured Data](#unstructured-data)
    - [Data Type Mismatches](#data-type-mismatches)
11. [Conclusion](#conclusion)
12. [Citations](#citations)



## 🎯 Contributions

This study significantly advances the field of seamless positioning and IoT applications, building upon and extending our previous work presented in our [![IPIN Paper](https://img.shields.io/badge/IPIN_Paper-10.1109/IPIN62893.2024.10786123-white)](https://ieeexplore.ieee.org/abstract/document/10786123):

- **Dual-Stage Approach**: Our research contributes a dual-stage LLM-based framework for data standardization, enhancing scalability and adaptability. The single-stage approach offers a solid baseline by directly generating transformation rules, whereas the dual-stage approach builds upon this by creating an initial standardized output followed by rule generation, thus enabling continuous learning and adaptation to sensor formats.

- **Rigorous Evaluation**: We further contribute through rigorous evaluation, implementing comprehensive unit tests and comparative analyses. This approach secures high success rates for correcting data input issues, showcasing the robustness of our framework in real-world IoT scenarios.

- **Foundational Work for IoT Evolution**: By addressing critical challenges in sensor data integration, this paper contributes foundational work that catalyzes advancements in IoT technology. Our framework sets the stage for the development of more adaptable and scalable navigation solutions that can be seamlessly integrated into diverse IoT ecosystems.

## 🛠️ Framework Overview 

The proposed framework outlines a **dual-stage iterative process** for standardizing and validating data to enhance seamless positioning systems.

<img width="1000" alt="flowchart (1)" src="https://github.com/user-attachments/assets/e6185236-d636-4ae9-b1c3-7ea3583ff57b" />

### Dual-Stage Approach
1. **Stage 1: Data Standardization**  
   Heterogeneous, unstandardized sensor data is processed using a fine-tuned LLM. The LLM predicts standardized data by categorizing it according to sensor type and converting complex data elements into a uniform format. The standardized data is then structured according to a predefined schema.

2. **Stage 2: Transformation Rules Generation**  
   Transformation rules are automatically generated by analyzing discrepancies between the original unstandardized data and the LLM’s standardized output. These rules are designed to standardize new incoming data, reducing the need for continuous LLM processing and improving the framework’s scalability and efficiency.

### Single-Stage Approach
In contrast, the **single-stage approach** relies on the LLM to directly generate transformation rules from the unstandardized input data, bypassing the intermediate prediction step. The LLM examines the raw data and outputs a set of transformation rules that conform to the predefined schema, enabling immediate standardization of subsequent data.

### Unit Tests for Data Integrity
- **Dual-Stage Unit Tests**:  
  - The first unit test checks the standardized data’s compliance with the predefined schema.  
  - The second unit test compares the generated transformation rules’ output against the LLM’s standardized data from the first stage.  

- **Single-Stage Unit Tests**:  
  - The unit test compares the transformation rule output directly with the predefined schema.  

### Sensor Fusion with EKF
In the final step, an EKF integrates the standardized data from various sensors, enhancing the accuracy of the positioning system. The integration uses covariance matrices representing uncertainties, which are manually set based on empirical data and prior knowledge. However, dynamic uncertainties in real-world applications may require adaptive or data-driven techniques for improved robustness and precision.

This framework ensures high data quality and consistency, enabling seamless integration of diverse sensor data for accurate positioning in IoT environments.

## 🤖 Automated Data Standardization

The first stage of the dual-stage LLM framework is designed to take **unstandardized heterogeneous sensor data** (denoted as `D`) as input and produce **standardized sensor data** (denoted as `S`) as output. The input consists of a JSON object representing a single data point, which may contain various sensor readings, metadata, and noise. The structure of this input is flexible and can vary significantly, simulating real-world scenarios. The output is a list of JSON objects, each representing a standardized sensor reading adhering to a predefined schema. This schema specifies the required fields, data types, and units for each sensor type.

### Input Data Representation
The raw data from various sensors is formulated as:

![Equation 1](https://latex.codecogs.com/svg.image?\mathcal{D}&space;=&space;\bigcup_{i=1}^n&space;d_i)

where `d_i` represents the multidimensional data vector from the `i`-th sensor, encapsulating various measurement parameters. In the context of our fine-tuned LLM (GPT-4-0613), these `d_i` serve as the inputs. They are raw, potentially inconsistent or unstructured sensor data strings that may exhibit issues such as:
- Non-uniform units
- Missing entries
- Unstructured formats
- Data type mismatches

### Output Data Representation
The desired output is a standardized, structured representation of the sensor data, denoted as `S`. This standardized output conforms to a predefined schema (outlined in the table below), ensuring consistency and compatibility across different sensor types.

### Standardization Process
The standardization process, facilitated by the LLM, is encapsulated by the transformation function:

![Equation 2](https://latex.codecogs.com/svg.image?\mathcal{S}&space;=&space;\mathcal{F}_{\text{ADS}}(\mathcal{D})&space;=&space;\bigoplus_{i=1}^n&space;\phi(d_i))

In this formulation:
- `F_ADS` denotes the fine-tuned GPT-4-0613 LLM model, specifically trained with a dataset crafted to address the complex challenges of sensor data standardization.
- `ϕ` represents a sequence of preprocessing operations applied to each data vector `d_i`, which includes normalization, error correction, and data type conversion, transforming it into the standardized format.

For example, in this study, it is assumed that UWB data directly provides measurements in meters instead of raw signal strength values. This assumption facilitates straightforward integration into the system, though it may overlook some subtleties of raw data processing, an aspect targeted for enhancement in future research.

### Standardized Data Schema
The structure of the standardized data schema is outlined in the table below:

| Sensor Type     | Required Fields          | Values Object Properties                          | Description                                                                 |
|-----------------|--------------------------|--------------------------------------------------|-----------------------------------------------------------------------------|
| Magnetometer    | name, time, values       | x (µT), y (µT), z (µT)                          | Measures magnetic field strength along x, y, and z axes in microteslas (µT).|
| Gyroscope       | name, time, values       | x (rad/s), y (rad/s), z (rad/s)                 | Measures angular velocity along x, y, and z axes in radians per second (rad/s).|
| Accelerometer   | name, time, values       | x (m/s²), y (m/s²), z (m/s²)                    | Measures acceleration along x, y, and z axes in meters per second squared (m/s²).|
| Gravity         | name, time, values       | x (m/s²), y (m/s²), z (m/s²)                    | Measures gravity effects along x, y, and z axes in meters per second squared (m/s²).|
| UWB             | name, time, values       | x (m), y (m), z (m)                             | Determines spatial position in meters (m).                                   |
| Bluetooth       | name, time, values       | x (m), y (m), z (m)                             | Determines spatial position in meters (m).                                   |
| Pedometer       | name, time, steps        | steps (count)                                   | Tracks the total number of steps taken (count).                              |
| Orientation     | name, time, values       | qx, qy, qz, qw                                  | Provides orientation details in quaternion format.                           |
| Barometer       | name, time, values       | relative altitude (m), pressure (mBar)          | Measures relative altitude in meters (m) and atmospheric pressure in millibars (mBar).|
| Location        | name, time, values       | latitude (°), longitude (°), altitude (m), speed (m/s), speed accuracy (m/s), horizontal accuracy (m), vertical accuracy (m) | Provides comprehensive location data including coordinates (degrees), speed (meters per second), altitude (meters), and accuracies (meters).|
| Image           | name, time, image        | image (data)                                    | Provides image data in binary format.                                        |

## 📊 Training and Validation Performance

Our dataset comprises **1000 diverse samples**, encompassing common data standardization challenges such as:
- Non-uniform units
- Missing entries
- Unstructured data
- Data type mismatches

These challenges reflect real-world IoT complexities and ensure the model is tested under realistic conditions.

### Common Data Input Issues

| **Edge Case**         | **Example Adjustments**                                                                                     |
|------------------------|-------------------------------------------------------------------------------------------------------------|
| **Non-uniform Units**  | **Input**: `"magnetometer": {"x": "45000 nT", "z": -30.0}` <br> **Output**: `"values": {"x": 45.0, "z": -30.0}` (converted from nT to µT) |
| **Rationale and Expected Outcome** | Sensor data often comes in various units that need to be standardized for consistent analysis. The expected outcome is to accurately convert various input units to predefined standard units (e.g., meters for distance, radians/second for angular velocity, Unix nanoseconds for time). |
| **Missing Entries**    | **Input**: `"accelerometer": {"y": -1.0, "z": "9.0 m/s^2"}` (missing x) <br> **Output**: `"values": {"x": "null", "y": -1.0, "z": 9.0}` |
| **Rationale and Expected Outcome** | Real-world data frequently has missing values due to sensor errors, transmission issues, or incomplete records. The expected outcome is to appropriately handle missing data by either inferring it from context (if possible) or marking it with a placeholder like `null` to indicate its absence. |
| **Unstructured Data**  | **Input**: `"gyro_data": {"y": "0.2 rad/s", "z": -0.1}` <br> **Output**: `{"name": "gyroscope", "values": {"y": 0.2, "z": -0.1}}` |
| **Rationale and Expected Outcome** | Data can arrive in various formats that don't match the expected schema. The expected outcome is to correct non-conforming data structures to fit the expected, standardized format (e.g., a flat JSON object with specific keys for each sensor). |
| **Data Type Mismatches** | **Input**: `"total_steps": "1550"` <br> **Output**: `"values": {"steps": 1550}` (string to integer) |
| **Rationale and Expected Outcome** | Values might be represented as incorrect data types (e.g., numbers as strings). The expected outcome is to convert various inputs into their corresponding numerical data types, ensuring consistency and enabling numerical operations. |

### Model Performance
The model's performance is illustrated in the figure below:

![image](https://github.com/user-attachments/assets/21a6ee7b-1847-42db-8b70-2b67fd46add0)
*Training and Validation Metrics. Top: Training and validation loss. Bottom: Training and validation mean token accuracy. The curves are based on 1000 samples and demonstrate improved stability and generalization.*

- **Training Loss Curve**: The training loss curve shows a consistent decrease, indicating effective learning.
- **Validation Loss Curve**: The validation loss curve stabilizes after an initial decrease around 200 steps, demonstrating good generalization without overfitting.
- **Mean Token Accuracy**: Training accuracy rises rapidly and stabilizes at a high level, while validation accuracy remains consistently above **98%**, confirming effective generalization. As expected, lower validation loss corresponds to higher validation accuracy.

These results demonstrate the model's ability to learn complex standardization patterns and generalize effectively to new data, highlighting its potential for real-world IoT applications.

### Loss Function
While the precise details are not in the GPT-4-0613 technical report, the loss function is likely a form of **cross-entropy loss** for next token prediction. We infer the model predicts the probability of each token being the correct next token. The inferred loss for a single training example is:

![Loss Function](https://latex.codecogs.com/svg.image?L_i&space;=&space;-\sum_{t=1}^{T}&space;\sum_{c=1}^{V}&space;y_{itc}&space;\log(p_{itc}))

where:
- `i` is the training example index,
- `T` is the output sequence length,
- `V` is the vocabulary size,
- `y_itc` is 1 if token `c` is correct at position `t` for sample `i`, 0 otherwise,
- `p_itc` is the predicted probability of token `c` being correct at position `t` for sample `i`.

The total loss is likely the average of individual losses:

![Total Loss](https://latex.codecogs.com/svg.image?L&space;=&space;\frac{1}{N}&space;\sum_{i=1}^{N}&space;L_i)

where `N` is the batch size.

### Mean Token Accuracy
The mean token accuracy is likely the average percentage of correctly predicted tokens. The inferred calculation is:

![Mean Token Accuracy](https://latex.codecogs.com/svg.image?\text{Mean&space;Token&space;Accuracy}&space;=&space;\frac{1}{N}&space;\sum_{i=1}^{N}&space;\left(&space;\frac{1}{T_i}&space;\sum_{t=1}^{T_i}&space;\mathbb{1}(y_{it}^*&space;=&space;\arg\max_c(p_{itc}))&space;\right))

where:
- `N` is the batch size,
- `T_i` is the output sequence length for sample `i`,
- `y_it*` is the true token index at position `t` for sample `i`,
- `argmax_c(p_itc)` is the predicted token index at position `t` for sample `i`,
- `1 if y_it* == argmax_c(p_itc), else 0` is an indicator function that returns 1 if the predicted token matches the true token, otherwise 0.

### Limitations and Future Work
Despite the strong performance, edge cases with underperformance are analyzed in the **Evaluation** section to identify limitations and areas for future improvement.

## 🧪 Standardized Dataset Unit Tests

The unit tests validate the standardized dataset `S` against predefined JSON schemas, addressing common data input issues as detailed in the [Common Data Input Issues](#common-data-input-issues) table. This validation ensures that `S` adheres to the required data formats and structures, thereby enhancing data integrity and reliability.

### Validation Function
The validation function is formally expressed as:

![Formula](https://latex.codecogs.com/svg.image?%28%5Cnu%2C%20e%29%20%3D%20%5Cmathcal%7BV%7D_%7B%5Cmathrm%7BADS%7D%7D%28%5Cmathcal%7BS%7D%2C%20%5Csigma%29%20%3D%20%5Cbegin%7Bcases%7D%201%2C%20%26%20%5Ctext%7Bif%20%7D%20%5Cmathrm%7Bschema%7D%28%5Cmathcal%7BS%7D%29%20%5Cequiv%20%5Csigma%20%5C%5C%200%2C%20%26%20%5Ctext%7Botherwise%7D%20%5Cend%7Bcases%7D)

where:
- `ν` indicates whether `S` conforms to schema `σ`,
- `e` contains details of validation errors as a set of tuples `(field, error_type)`.

If errors are detected (`e ≠ ∅`), these errors are fed back into the transformation function:

![Transformation Function](https://latex.codecogs.com/svg.image?\mathcal{S}&space;=&space;\mathcal{F}_{\text{ADS}}(\mathcal{D},&space;e)&space;=&space;\bigcup_{i=1}^N&space;\text{adjust}(\mathcal{D}_i,&space;e_i))

### Feedback Loop
This feedback loop continues, iterating the validation and adjustment process until `S` conforms to the schema or a predefined maximum number of iterations is reached. 

- **98.0% of the datasets** (196 out of 200) required only **one iteration** for successful validation.
- **Four datasets** required **two iterations**.

This rapid initial convergence supports **three iterations** as an optimal limit. These results underscore the robustness and effectiveness of the LLM in standardizing diverse sensor data in most cases, ensuring high data quality and consistency.

## 🛠️ Transformation Rules Automation

The transformation rules automation serves a critical role in the data standardization process. Depending on the approach taken, it can function as either the second stage of a dual-stage process or as a standalone single-stage process.

### Second Stage in Dual-Stage Approach
In the dual-stage approach, the transformation rules automation creates a set of rules (`T`) based on the standardized data (`S`) and the original input data (`D`). These rules are designed to maintain the standardization across future inputs without further LLM processing.

The transformation rules generation is encapsulated by the following equation:

![Dual-Stage Transformation Rules](https://latex.codecogs.com/svg.image?\mathcal{T}&space;=&space;\mathcal{F}_{\text{TRA}}(\mathcal{S},&space;\mathcal{D})&space;=&space;\bigcup_{i=1}^M&space;\text{transform}(\mathcal{S}_i,&space;\mathcal{D}_i))

### Single-Stage Approach
Alternatively, the transformation rules automation can operate independently as a single-stage process, where the rules are directly generated from the input data. In this single-stage context, the process simplifies to:

![Single-Stage Transformation Rules](https://latex.codecogs.com/svg.image?\mathcal{T}&space;=&space;\mathcal{F}_{\text{TRA}}(\mathcal{D}))

Regardless of the approach, the generated transformation rules (`T`) ensure that the sensor data is converted into a uniform format according to the standardized data schema (`σ`), as outlined in the table below.

### Transformation Rules Schema Structure

| **Field Name**    | **Data Type** | **Description**                                                                 |
|--------------------|---------------|---------------------------------------------------------------------------------|
| `inputPath`        | String        | JSONPath expression pointing to the source field in the input JSON structure.   |
| `outputPath`       | String        | JSONPath expression pointing to the target field in the output JSON structure.  |
| `transformation`   | Function      | A function or expression used to transform the input data before mapping it to the output path. |

#### Example
| **Field Name**    | **Data Type** | **Example**                                                                     |
|--------------------|---------------|---------------------------------------------------------------------------------|
| `inputPath`        | String        | `$.sensor_data.Accelerometer.x`                                                |
| `outputPath`       | String        | `$[?(@.name == 'Accelerometer')].x`                                            |
| `transformation`   | Function      | `{float(re.search(r'[-+]?\d*\.?\d+', value).group(0))}`                         |

In the transformation process, **JSONPath expressions** are vital for mapping data elements from the original JSON structure to the target format in the output JSON. For example, a JSONPath expression might be used to select the `x` value from accelerometer data in the input and assign it to a corresponding `x` field in the output. This adjustment ensures that the data conforms to a standardized schema. Additionally, these expressions can be integrated with transformation functions to strip unit symbols, further standardizing and cleansing the data for consistent processing and analysis.

---

## 🧪 Transformation Rules Unit Tests

The unit tests validate the accuracy and functionality of the transformation rules generated by the LLM. These rules are essential for converting the input JSON data (`D`) into the desired standardized format (`S`). The validation function, which assesses whether the transformation rules perform as expected, is formally expressed as:

![Transformation](https://latex.codecogs.com/svg.image?%28%5Cnu%2C%20e%29%20%3D%20%5Cmathcal%7BV%7D_%7B%5Ctext%7BTRA%7D%7D%28%5Cmathcal%7BT%7D%28D%29%2C%20S%29%20%3D%20%5Cbegin%7Bcases%7D%201%2C%20%26%20%5Ctext%7Bif%20%7D%20%5Cmathcal%7BT%7D%28D%29%20%3D%20S%20%5C%5C%200%2C%20%26%20%5Ctext%7Botherwise%7D%20%5Cend%7Bcases%7D)

Here:
- `T(D)` represents the output generated by applying the transformation rules `T` to the input JSON structure `D`.
- `ν` indicates the success of the transformation in matching the standardized data `S` in stage 1.
- `e` details any errors encountered during the process.

If discrepancies or errors (`e ≠ ∅`) are identified, these errors are fed back into the transformation function:

![Transformation Rules Feedback](https://latex.codecogs.com/svg.image?\mathcal{T}&space;=&space;\mathcal{F}_{\text{TRA}}(\mathcal{S},&space;\mathcal{D},&space;e)&space;=&space;\bigcup_{j=1}^P&space;\text{modify}(\mathcal{S}_j,&space;\mathcal{D}_j,&space;e_j))

The newly generated transformation rules `T` are then tested again, iterating the process until no errors are detected (`ν = 1` and `e = ∅`). This iterative approach ensures the transformation rules adapt to meet the requirements of the standardized data schema.

## 🛠️ Sensor Fusion

Sensor fusion is implemented using an **Extended Kalman Filter (EKF)**, which integrates data from various sensors to provide accurate estimates of three-dimensional positions and velocities.

### State Vector and Transition Matrix
The state vector, denoted as `x`, comprises the three-dimensional positions and velocities:

![State Vector](https://latex.codecogs.com/svg.image?\mathbf{x}^T&space;=&space;\begin{bmatrix}&space;x&space;&&space;y&space;&&space;z&space;&&space;v_x&space;&&space;v_y&space;&&space;v_z&space;\end{bmatrix})

The evolution of the state vector is governed by the state transition matrix `F_k`:

![State Transition Matrix](https://latex.codecogs.com/svg.image?\mathbf{F}_k&space;=&space;\begin{bmatrix}&space;\mathbf{I}_{3&space;\times&space;3}&space;&&space;\Delta&space;t&space;\mathbf{I}_{3&space;\times&space;3}&space;\\&space;\mathbf{0}_{3&space;\times&space;3}&space;&&space;\mathbf{I}_{3&space;\times&space;3}&space;\end{bmatrix})

where `Δt` represents the time interval between the updates.

### Measurement Model
The EKF utilizes measurements from multiple sensors, summarized in the table below, which outlines the measurement vectors and their respective covariance matrices.

#### Measurement Vectors and Covariance Matrices for Sensors

| **Sensor Type** | **Measurement Vector**                                                                 | **Measurement Covariance Matrix**                                                                 |
|-----------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| GNSS Receiver   | ![GNSS Measurement Vector](https://latex.codecogs.com/svg.image?\mathbf{z}_{\text{GNSS}}&space;=&space;\begin{bmatrix}&space;\phi_{\text{GNSS}}&space;\\&space;\lambda_{\text{GNSS}}&space;\\&space;h_{\text{GNSS}}&space;\end{bmatrix}) | ![GNSS Covariance Matrix](https://latex.codecogs.com/svg.image?\mathbf{R}_{\text{GNSS}}&space;=&space;\begin{bmatrix}&space;655.00&space;&&space;0&space;&&space;0&space;\\&space;0&space;&&space;655.00&space;&&space;0&space;\\&space;0&space;&&space;0&space;&&space;655.00&space;\end{bmatrix}) |
| UWB Sensor      | ![UWB Measurement Vector](https://latex.codecogs.com/svg.image?\mathbf{z}_{\text{UWB}}&space;=&space;\begin{bmatrix}&space;x_{\text{UWB}}&space;\\&space;y_{\text{UWB}}&space;\\&space;z_{\text{UWB}}&space;\end{bmatrix}) | ![UWB Covariance Matrix](https://latex.codecogs.com/svg.image?\mathbf{R}_{\text{UWB}}&space;=&space;\begin{bmatrix}&space;1.00&space;&&space;0&space;&&space;0&space;\\&space;0&space;&&space;1.00&space;&&space;0&space;\\&space;0&space;&&space;0&space;&&space;1.00&space;\end{bmatrix}) |
| Camera          | ![Camera Measurement Vector](https://latex.codecogs.com/svg.image?\mathbf{z}_{\text{cam}}&space;=&space;img_{\text{cam}}) | ![Camera Covariance Matrix](https://latex.codecogs.com/svg.image?\mathbf{R}_{\text{cam}}&space;=&space;\begin{bmatrix}&space;0.15&space;&&space;0&space;&&space;0&space;\\&space;0&space;&&space;0.15&space;&&space;0&space;\\&space;0&space;&&space;0&space;&&space;0.15&space;\end{bmatrix}) |

### Statistical Analysis of Sensor Measurement Variances
Accurately quantifying sensor errors is crucial for ensuring the robustness of navigation systems. This section presents the methodology for calculating the measurement variances for key sensors based on observed data.

#### GNSS Receiver Variance
Errors in GNSS measurements can significantly affect performance. The variances in the North and East directional components are calculated as follows:

![GNSS North Variance](https://latex.codecogs.com/svg.image?\text{Var}_{\text{North}}&space;(\text{GNSS})&space;=&space;25.02^2)

![GNSS East Variance](https://latex.codecogs.com/svg.image?\text{Var}_{\text{East}}&space;(\text{GNSS})&space;=&space;5.47^2)

The total variance is then given by:

![GNSS Total Variance](https://latex.codecogs.com/svg.image?\sigma_{\text{GNSS}}^2&space;=&space;625.20&space;&plus;&space;29.92&space;=&space;655.12&space;\,&space;\text{m}^2)

#### UWB Sensor Variance
For the UWB sensor, known for its precision in localization, the variances are:

![UWB North Variance](https://latex.codecogs.com/svg.image?\text{Var}_{\text{North}}&space;(\text{UWB})&space;=&space;0.79^2)

![UWB East Variance](https://latex.codecogs.com/svg.image?\text{Var}_{\text{East}}&space;(\text{UWB})&space;=&space;0.62^2)

Summing these results in:

![UWB Total Variance](https://latex.codecogs.com/svg.image?\sigma_{\text{UWB}}^2&space;=&space;0.6241&space;&plus;&space;0.3844&space;=&space;1.0085&space;\,&space;\text{m}^2)

#### Camera Variance
Camera systems, integral for visual navigation, have variances calculated as:

![Camera North Variance](https://latex.codecogs.com/svg.image?\text{Var}_{\text{North}}&space;(\text{cam})&space;=&space;0.32^2)

![Camera East Variance](https://latex.codecogs.com/svg.image?\text{Var}_{\text{East}}&space;(\text{cam})&space;=&space;0.23^2)

The total variance is:

![Camera Total Variance](https://latex.codecogs.com/svg.image?\sigma_{\text{cam}}^2&space;=&space;0.1024&space;&plus;&space;0.0529&space;=&space;0.1553&space;\,&space;\text{m}^2)

These variance calculations are vital for refining the sensor fusion algorithms used in navigation systems, enhancing both reliability and accuracy. The statistical approach ensures that the navigation system accommodates sensor uncertainties effectively.

### Control Input
Control inputs from the Inertial Measurement Unit (IMU) include accelerations, angular velocities, and magnetometer readings as shown in the table below. The orientation matrix `C` transforms these accelerations from the IMU frame to the North-East-Down (NED) frame. The control input matrix `B_IMU` integrates these transformed accelerations into the state vector, adjusted for the time interval `Δt`.

#### Control Input Vectors and Process Noise Covariance for IMU

| **Sensor Type** | **Control Input Vector**                                                                 | **Control Input Matrix**                                                                 | **Process Noise Covariance**                                                                 |
|-----------------|-----------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| IMU             | ![IMU Control Input Vector](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;a_x&space;\\&space;a_y&space;\\&space;a_z&space;\\&space;\omega_x&space;\\&space;\omega_y&space;\\&space;\omega_z&space;\\&space;m_x&space;\\&space;m_y&space;\\&space;m_z&space;\end{bmatrix}) | ![IMU Control Input Matrix](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;\frac{\Delta&space;t^2}{2}&space;\mathbf{I}_{3&space;\times&space;3}&space;\\&space;\Delta&space;t&space;\mathbf{I}_{3&space;\times&space;3}&space;\end{bmatrix}) | ![IMU Process Noise Covariance](https://latex.codecogs.com/svg.image?\begin{bmatrix}&space;\frac{\sigma_a^2&space;\Delta&space;t^4}{4}&space;\mathbf{I}_{3&space;\times&space;3}&space;&&space;\frac{\sigma_a^2&space;\Delta&space;t^3}{2}&space;\mathbf{I}_{3&space;\times&space;3}&space;\\&space;\frac{\sigma_a^2&space;\Delta&space;t^3}{2}&space;\mathbf{I}_{3&space;\times&space;3}&space;&&space;\sigma_a^2&space;\Delta&space;t^2&space;\mathbf{I}_{3&space;\times&space;3}&space;\end{bmatrix}) |

## 🧪 Experiment

### Comparison of Data Standardization Methods
In this section, we compare the performance of various data standardization methods across key metrics such as success rate in handling non-uniform units, missing entries, unstructured data, data type mismatches, and overall accuracy. We evaluate each method's adaptability to new data formats, execution time, and development time. The comparison is based on an experimental setup involving a dataset of 200 samples, which presents a wide range of standardization challenges. The results of this comparison are summarized in the table below.

#### Comparison of Data Standardization Methods

| **Metric**                  | **Single-Stage** | **Dual-Stage (Stage 1)** | **Dual-Stage (Stage 2)** | **Fine-tuned BERT** | **Manual Rule-based System** |
|-----------------------------|------------------|--------------------------|--------------------------|---------------------|------------------------------|
| **Overall Accuracy**        | 88.6%            | 100.0%                   | 99.0%                    | 80.1%               | 100.0%                       |
| **Non-uniform Units**       | 81.0%            | 100.0%                   | 97.5%                    | 20.5%               | 100.0%                       |
| **Missing Entries**         | 78.5%            | 100.0%                   | 98.5%                    | 100.0%              | 100.0%                       |
| **Unstructured Data**       | 98.5%            | 100.0%                   | 100.0%                   | 100.0%              | 100.0%                       |
| **Data Type Mismatches**    | 96.5%            | 100.0%                   | 100.0%                   | 100%                | 100.0%                       |
| **Adaptability to New Formats** | High          | High                     | High                     | Medium              | Low                          |
| **Execution Time**          | Low              | High                     | Low                      | High                | Low                          |
| **Development Time**        | Low              | Low                      | Low                      | Low                 | High                         |

#### Key Findings:
- **Single-Stage Approach**: Demonstrates strong performance with an overall accuracy of 88.6% and high adaptability to new formats. The low execution time is attributed to the method's ability to generate transformation rules directly from the LLM, which streamlines the standardization process. The development time is minimal, making it an efficient solution.
- **Dual-Stage Approach (Stage 1)**: Achieves perfect success rates across all specific data handling tasks, leading to an overall accuracy of 100.0%. Its high execution time is due to the LLM generating the standardized output directly, which involves more computational steps compared to rule generation. The approach remains highly adaptable and requires low development time.
- **Dual-Stage Approach (Stage 2)**: Offers a balance between accuracy and efficiency, achieving a high overall accuracy of 99.0%. The low execution time is achieved by leveraging the transformation rules generated in Stage 2, thereby avoiding the need for direct LLM processing during execution. The development time is low due to the efficiency of the dual-stage process.
- **Fine-tuned BERT Model**: Has moderate adaptability and high execution time due to generating the standardized output directly. While development time is low, the model's overall accuracy is only 80.1%, with particular weakness in handling non-uniform units, where it scores 20.5%. BERT's primary function is to categorize sensor data, not to transform units, which explains its limitations in transforming data formats.
- **Manual Rule-based System**: Shows excellent performance in handling specific data issues with a 100.0% success rate. Its low execution time results from using pre-defined rules without the need for on-the-fly processing. However, its low adaptability and high development time, due to the need for manual rule crafting, may limit its practicality in dynamic environments.

### Experiment Setup
We further conducted an experiment with the dual-stage approach in a dynamic environment transitioning from outdoors to indoors, as depicted in the figure below. This location, characterized by tall buildings, represents urbanized areas where enhanced positioning accuracy through sensor fusion is essential. The total length of the ground truth path was approximately 60 meters. Data collection was performed using four different sensors, each on dedicated devices to simulate sensor fusion from various sources. The table below lists the sensors and their fused counterparts.

![image](https://github.com/user-attachments/assets/78281207-6bb2-4bf7-8f62-118c8c83c3e5)

*Experiment Path and Ultra-Wideband (UWB) Setup for Data Collection.*

#### Descriptions of Measurement Sensors and Fusion Methods

| **Method**                  | **Description**                                                                 |
|-----------------------------|---------------------------------------------------------------------------------|
| **Ground Truth (GT)**       | Data collected at landmark locations identified on Hong Kong Lands Department 3D Spatial Data 3D-BIT00, with an accuracy within 1-2 meters, combined with the indoor floor plan from The Hong Kong Polytechnic University. |
| **GNSS**                    | The u-blox F9P receiver connected to a computer via serial port, streaming GNSS location data at one position per second. A custom script parsed NMEA sentences and transmitted the data to an API endpoint. |
| **UWB**                     | Four Nooploop LinkTrack P-A Series UWB anchors were placed at the corners of the indoor environment, positioned 1.5 meters above the ground. The system was calibrated to align with the global coordinates of the floor plan, enabling global positioning. Data from the UWB system was transmitted at 20 Hz using the Robot Operating System (ROS), which broadcast the data to an API endpoint. |
| **VPS**                     | A 3D sparse point cloud was constructed for positioning using the hierarchical localization toolbox (hloc), consisting of key points covering the area and registered to the global map. A Samsung Galaxy Note 20 Ultra smartphone captured images at 1 frame per second and sent them to an API endpoint, where the server determined the device's position relative to the geo-registered point cloud. |
| **IMU**                     | The iPhone 14 Pro used the “Sensor Logger” app to stream IMU data at 100 Hz to the API endpoint, including accelerometer, gyroscope, and magnetometer readings to estimate the device's orientation and motion. |
| **GNSS + IMU**              | A GNSS solution using the u-blox F9P receiver fused with iPhone IMU data. |
| **VPS + IMU**               | VPS positioning method fused with iPhone IMU data. |
| **UWB + IMU**               | A UWB-based positioning method fused with iPhone IMU data. |
| **GNSS + VPS + UWB + IMU**  | A comprehensive solution combining GNSS (u-blox F9P), VPS, UWB, and iPhone IMU data. |

### Experiment Results
The proposed framework was rigorously evaluated using sensor data collected from a variety of sources, including smartphones, IoT devices, and UWB tags. The dataset comprised over 10,000 entries, each containing diverse elements such as timestamps, sensor readings, and device identifiers.

#### Positioning System Accuracy
The accuracy of the positioning system was assessed by comparing the computed results from various methods against established ground truth data. Positioning error was quantified by calculating the Euclidean distance between the computed positions and the ground truth trajectory. The quantitative results are tabulated below and further visualized in the figure.

#### Performance Metrics of Different Positioning Methods

| **Method**                  | **Mean Error (m)** | **Std. Dev. (m)** | **RMSE (m)** | **Median Error (m)** | **Max Error (m)** |
|-----------------------------|--------------------|-------------------|--------------|----------------------|-------------------|
| GNSS                        | 25.02              | 5.47              | 25.61        | 25.21                | 33.75             |
| GNSS + IMU                  | 23.24              | 4.22              | 23.62        | 23.38                | 29.40             |
| UWB                         | 0.79               | 0.62              | 1.00         | 0.71                 | 4.75              |
| UWB + IMU                   | 0.69               | 0.89              | 1.13         | 0.31                 | 3.92              |
| VPS                         | 0.32               | 0.23              | 0.39         | 0.30                 | 0.76              |
| VPS + IMU                   | 0.33               | 0.23              | 0.41         | 0.31                 | 0.91              |
| GNSS + VPS + UWB + IMU      | 0.33               | 0.24              | 0.41         | 0.27                 | 0.95              |

![image](https://github.com/user-attachments/assets/1aacae78-b3cc-490a-843e-95f7e9722836)

*Comparison of Positioning Results from Various Methods with Ground Truth.*

#### Key Findings:
- The standalone GNSS system exhibited substantial deviations, primarily due to urban multipath effects, with a mean error of 25.02 meters.
- Integration of GNSS with an IMU marginally reduced the mean error to 23.24 meters.
- The UWB system, especially when combined with an IMU, showed significant improvements in indoor environments, reducing the mean error to as low as 0.69 meters.
- The VPS system demonstrated superior accuracy in outdoor settings, achieving a mean error of 0.32 meters.
- Combining GNSS, VPS, UWB, and IMU technologies harnessed the strengths of each, resulting in a highly reliable and precise positioning system with a mean error of just 0.33 meters.

#### Positioning Error Over Time
The figure below illustrates the dynamic performance of each positioning method over time. The UWB system initially exhibited fluctuations but stabilized at a lower error range. Both VPS and its integration with IMU consistently maintained low errors, underscoring their robustness. The UWB and IMU combination notably reduced errors compared to standalone UWB. The comprehensive integration of GNSS, UWB, VPS, and IMU maintained a consistently low error rate throughout the evaluation period, affirming the robustness and effectiveness of this combined technology approach.

![image](https://github.com/user-attachments/assets/604a1dae-b8ac-4920-8c63-e3141124662a)

*Positioning Error Over Time for Various Sensor Fusion Methods.*

---

## 📊 Evaluation of Common Data Input Issues

### Non-uniform Units
The framework achieved a 97.5% success rate in converting specified units to standard units, as shown in the table below. Successful conversions occur primarily when units are explicitly labeled. Challenges arise with unlabeled data, where the system often mistakenly assumes standard units, leading to errors. This problem is highlighted in the table, where missing 'cm' labels result in no conversion, demonstrating the system's current limitations in unit recognition. To address this, future enhancements should focus on developing models that can infer units from the context of historical data, improving the accuracy of unit conversions without explicit labels.

#### Successful Correction for Non-uniform Units

| **Attribute** | **Input**         | **Output** | **Correct Conversion?** |
|---------------|-------------------|------------|-------------------------|
| Name          | "UWB"             | "UWB"      | Yes                     |
| Time          | 1683302400000     | 1683302400000000000 | Yes           |
| X             | 180cm             | 1.8        | Yes                     |
| Y             | 230cm             | 2.3        | Yes                     |
| Z             | 420cm             | 4.2        | Yes                     |

#### Unsuccessful Correction for Non-uniform Units

| **Attributes** | **Input** | **Output** | **Correct Conversion?** |
|----------------|-----------|------------|-------------------------|
| Name           | "UWB"     | "UWB"      | Yes                     |
| Time           | 1683302400000 | 1683302400000000000 | Yes           |
| X              | 180       | 180        | **No**                  |
| Y              | 230       | 230        | **No**                  |
| Z              | 420       | 420        | **No**                  |

### Missing Entries
The framework demonstrated a 98.5% accuracy in identifying and labeling missing entries as `Null`, as indicated in the table below. This method, which accurately represents data absences, improves the reliability of subsequent data sensor fusion. Nonetheless, the framework exhibits shortcomings with datasets that contain large or inconsistent missing entries. In such cases, the model often fails to recognize the absence of data correctly, mistakenly inserting default numeric values like `0` instead of `Null`. This issue highlights the need for enhanced model training that better handles data gaps.

#### Unsuccessful Correction for Missing Entries

| **Attributes**         | **Input**         | **Output** | **Correct Conversion?** |
|------------------------|-------------------|------------|-------------------------|
| Name                   | "Location"        | "Location" | Yes                     |
| Time                   | 1683302400000     | 1683302400000000000 | Yes           |
| Latitude               | 0                 | 0          | Yes                     |
| Longitude              | -122.4194         | -122.4194  | Yes                     |
| Altitude               | 10.0              | 10         | Yes                     |
| Speed                  | (missing)         | 0          | **No**                  |
| Speed Accuracy         | 0.5               | 0.5        | Yes                     |
| Bearing Accuracy       | (missing)         | 0          | **No**                  |
| Horizontal Accuracy    | 1.5               | 1.5        | Yes                     |
| Vertical Accuracy      | (missing)         | 0          | **No**                  |
| Bearing                | (missing)         | 0          | **No**                  |

### Unstructured Data
The framework effectively resolved non-conforming data structure issues, maintaining data integrity and aiding integration. It corrected problems like misplaced keys and disorganized hierarchies, ensuring schema compliance.

### Data Type Mismatches
The framework skillfully handled mismatches, converting strings to numerical values reliably. This is key for accurate string parsing and numerical formatting for sensor fusion. Future enhancements should expand its ability to recognize and convert various numerical representations, including different languages and formats. This will make the framework more versatile and robust for diverse dataset conversions.

## Conclusion

This study has made substantial progress in enhancing positioning accessibility through a framework that integrates Large Language Models for data standardization with Extended Kalman Filter for sensor data fusion. Our dual-stage LLM-driven approach has demonstrated exceptional capabilities in standardizing heterogeneous sensor data, achieving significant accuracy improvements in IoT positioning systems.

The dual-stage methodology, in particular, has proven to be a cornerstone of the framework, enabling perfect or near-perfect success rates across various data standardization tasks. With an overall accuracy of 99% in the second stage, the dual-stage approach shows considerable promise in handling the complexities of sensor data integration. It has notably achieved low positioning errors, down to 0.33 meters, which is a testament to its efficacy in diverse application settings.

Despite these achievements, future research should aim to refine the dual-stage approach further. This includes optimizing the LLMs for even greater efficiency and adaptability, reducing computational overhead, and improving the robustness of the system against dynamic environmental changes. Additionally, enhancing the model's ability to handle edge cases and ensuring robust privacy measures are integral to advancing the framework's application in smart city infrastructures and beyond.

In conclusion, the LLM-driven data standardization framework represents a significant advancement in IoT technologies, setting the stage for more adaptable, scalable, and precise navigation solutions. The dual-stage approach, in particular, provides a clear path forward for addressing the challenges of seamless positioning in IoT and opens up new possibilities for smart navigation in an increasingly interconnected world.

## Citations
If you find this work useful, please consider citing our [![IPIN Paper](https://img.shields.io/badge/IPIN_Paper-10.1109/IPIN62893.2024.10786123-white)](https://ieeexplore.ieee.org/abstract/document/10786123) and the manuscript submitted to IEEE Internet of Things Journal introduced in this repository, which is currently under review:

```bibtex
@INPROCEEDINGS{10786123,
  author={Lee, Max J. L. and Lin, Ju and Hsu, Li-Ta},
  booktitle={2024 14th International Conference on Indoor Positioning and Indoor Navigation (IPIN)}, 
  title={Exploring the Feasibility of Automated Data Standardization using Large Language Models for Seamless Positioning}, 
  year={2024},
  volume={},
  number={},
  pages={1-6},
  keywords={Meters;Accuracy;Large language models;Computational modeling;Data integration;Standardization;Real-time systems;Data models;Internet of Things;Kalman filters;Data compatibility;data standardization;Extended Kalman Filter (EKF);heterogeneous sensor integration;indoor navigation;Internet of Things (IoT);Large Language Models (LLMs);positioning systems;sensor data fusion;UWB},
  doi={10.1109/IPIN62893.2024.10786123}}

@article{IoT-46019-2025,
  author = {Lee, Max Jwo Lem and Lin, Ju and Bai, Xiwei and Hsu, Li-Ta},
  title = {Enhancing Positioning Accessibility through Large Language Model-Driven Data Standardization},
  journal = {IEEE Internet of Things Journal},
  year = {2024},
  note = {Submitted},
  abstract = {The integration of diverse sensor data from Internet of Things (IoT) devices, such as smartphones and specialized systems like Ultra-Wideband (UWB), is essential for accurate positioning in various applications. This paper presents a dual-stage data standardization framework that employs Large Language Models (LLMs) to automate the transformation of heterogeneous sensor data into a uniform format. The first stage utilizes a fine-tuned LLM to directly predict standardized data, while the second stage generates transformation rules based on the predictions, enabling continuous and efficient standardization for new incoming data. Additionally, this approach incorporates an Extended Kalman Filter (EKF) for sophisticated sensor data fusion, significantly improving the positioning system’s accuracy. Our dual-stage method achieves high success rates of 97.5% for handling non-uniform units and 98.5% for managing missing entries, while also notably reducing positioning errors to 0.33 meters by integrating GNSS, Visual Positioning System (VPS), UWB, and IMU sensors. Evaluations in dynamic environments have demonstrated the method’s improvements in operational efficiency and scalability, validating the effectiveness of the dual-stage LLM framework in navigating the complexities of sensor data integration. This proposed method not only streamlines the processing of diverse data types but also lays the groundwork for more robust and adaptable IoT navigation solutions, leading to marked enhancements in positioning accuracy and operational efficiency.},
  keywords = {Data standardization, Extended Kalman Filter (EKF), Internet of Things (IoT), Large Language Models (LLMs), positioning systems, sensor data fusion, positioning, seamless positioning}
}
