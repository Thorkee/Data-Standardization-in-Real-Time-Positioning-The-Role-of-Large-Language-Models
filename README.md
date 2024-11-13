# Data Standardization in Positioning: The Role of Large Language Models

This repository accompanies the paper *"Data Standardization in Positioning: The Role of Large Language Models,"* which has been submitted to the IEEE Internet of Things (IoT) Journal. The paper explores the use of Large Language Models (LLMs) to automate the standardization of heterogeneous sensor data, thereby improving data compatibility and positioning accuracy in IoT environments.

## Authors

- **Max Jwo Lem Lee** ([@maxystory](https://github.com/maxystory))  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [maxjl.lee@connect.polyu.hk](mailto:maxjl.lee@connect.polyu.hk)

- **Ju Lin** ([@thorkee](https://github.com/thorkee))  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [ju.lin@connect.polyu.hk](mailto:ju.lin@connect.polyu.hk)

- **Xiwei Bai** ([@baaixw](https://github.com/baaixw))  
  Member of IEEE  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [x.w.bai@polyu.edu.hk](mailto:x.w.bai@polyu.edu.hk)

- **Li-Ta Hsu** ([@qmohsu](https://github.com/qmohsu))  
  Senior Member of IEEE  
  Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University  
  Email: [lt.hsu@polyu.edu.hk](mailto:lt.hsu@polyu.edu.hk)

## Abstract

The integration of diverse sensor data from Internet of Things (IoT) devices, such as smartphones and specialized systems like Ultra-Wideband (UWB), is crucial for accurate real-time positioning in various applications. This paper utilizes Large Language Models (LLMs) to automate the standardization of heterogeneous sensor data, thereby enhancing data compatibility and positioning accuracy in IoT environments. We introduce a framework that employs a fine-tuned LLM to transform varied sensor data into a uniform format and automatically generate transformation rules for continuous data standardization. In addition, this approach leverages the Extended Kalman Filter (EKF) for sensor data fusion, improving the accuracy of the positioning system. Key findings include high success rates of 89.47% for handling non-uniform units and 82.35% for managing missing entries. Furthermore, the framework notably reduces positioning errors to 0.33 meters by combining GNSS, Visual Positioning System (VPS), UWB, and IMU. Our real-time evaluation in dynamic environments demonstrates improvements in operational efficiency and scalability, validating the effectiveness of LLMs in managing the complexities of sensor data integration. The proposed method not only streamlines the processing of diverse data types but also sets a foundation for more robust and adaptable IoT navigation solutions. The framework achieves marked improvements in positioning accuracy and operational efficiency.

## Reference Slide

You can refer to the accompanying slide for more details on the project:  
[Reference Slide (PDF)](./Reference%20Slide_Data%20Standardization%20in%20Positioning%20The%20Role%20of%20Large%20Language%20Models.pdf)
