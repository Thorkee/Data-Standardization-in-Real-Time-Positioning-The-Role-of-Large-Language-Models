# Enhancing Positioning Accessibility through Large Language Model-Driven Data Standardization

This repository accompanies the paper *"Enhancing Positioning Accessibility through Large Language Model-Driven Data Standardization,"* which has been submitted to the IEEE Internet of Things (IoT) Journal. The journal manuscript is an extended version of the conference paper presented at the **International Conference on Indoor Positioning and Indoor Navigation (IPIN 2024)**. The conference paper has been indexed by IEEE Xplore: [Exploring the Feasibility of Automated Data Standardization using Large Language Models for Seamless Positioning](https://ieeexplore.ieee.org/abstract/document/10786123).

The paper explores the use of Large Language Models (LLMs) to automate the standardization of heterogeneous sensor data, thereby improving data compatibility and positioning accuracy in IoT environments.

## Authors

- **Max Jwo Lem Lee** ([@maxystory](https://github.com/maxystory))  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [maxjl.lee@connect.polyu.hk](mailto:maxjl.lee@connect.polyu.hk)

- **Ju Lin** ([@thorkee](https://github.com/thorkee))  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [ju.lin@connect.polyu.hk](mailto:ju.lin@connect.polyu.hk)

- **Xiwei Bai** ([@baaixw](https://github.com/baaixw))  
  Member, IEEE  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [x.w.bai@polyu.edu.hk](mailto:x.w.bai@polyu.edu.hk)

- **Li-Ta Hsu** ([@qmohsu](https://github.com/qmohsu))  
  Senior Member, IEEE  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [lt.hsu@polyu.edu.hk](mailto:lt.hsu@polyu.edu.hk)

## Abstract

The integration of diverse sensor data from Internet of Things (IoT) devices, such as smartphones and specialized systems like Ultra-Wideband (UWB), is essential for accurate positioning in various applications. This paper presents a dual-stage data standardization framework that employs Large Language Models (LLMs) to automate the transformation of heterogeneous sensor data into a uniform format. The first stage utilizes a fine-tuned LLM to directly predict standardized data, while the second stage generates transformation rules based on the predictions, enabling continuous and efficient standardization for new incoming data. Additionally, this approach incorporates an Extended Kalman Filter (EKF) for sophisticated sensor data fusion, significantly improving the positioning system’s accuracy. Our dual-stage method achieves high success rates of 97.5% for handling non-uniform units and 98.5% for managing missing entries, while also notably reducing positioning errors to 0.33 meters by integrating GNSS, Visual Positioning System (VPS), UWB, and IMU sensors. Evaluations in dynamic environments have demonstrated the method’s improvements in operational efficiency and scalability, validating the effectiveness of the dual-stage LLM framework in navigating the complexities of sensor data integration. This proposed method not only streamlines the processing of diverse data types but also lays the groundwork for more robust and adaptable IoT navigation solutions, leading to marked enhancements in positioning accuracy and operational efficiency.

## Reference Slide

![image](https://github.com/user-attachments/assets/24311f4e-27de-4f1c-98ab-e0566e45a47a)
![image](https://github.com/user-attachments/assets/5b5049e9-1192-4a8c-bdfa-619cafea7aea)


You can view the full slide deck here:  
[Data Standardization in Positioning: The Role of Large Language Models - Full Slide (PDF)](./Reference%20Slide_Data%20Standardization%20in%20Positioning%20The%20Role%20of%20Large%20Language%20Models.pdf)
