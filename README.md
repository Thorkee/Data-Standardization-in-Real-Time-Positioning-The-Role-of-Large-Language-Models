# Enhancing Positioning Accessibility through Large Language Model-Driven Data Standardization

[![Explore our Lab](https://img.shields.io/badge/Explore-PolyU_IPN_Lab-red)](https://www.polyu.edu.hk/aae/ipn-lab/us/index.html)

This repository accompanies the paper *"Enhancing Positioning Accessibility through Large Language Model-Driven Data Standardization,"* which has been submitted to the IEEE Internet of Things (IoT) Journal. The journal manuscript is an extended version of the conference paper presented at the **International Conference on Indoor Positioning and Indoor Navigation (IPIN 2024)**. The conference paper has been indexed by IEEE Xplore: [Exploring the Feasibility of Automated Data Standardization using Large Language Models for Seamless Positioning](https://ieeexplore.ieee.org/abstract/document/10786123).

The paper explores the use of Large Language Models (LLMs) to automate the standardization of heterogeneous sensor data, thereby improving data compatibility and positioning accuracy in IoT environments.

## Authors

### Max Jwo Lem Lee
[![GitHub](https://img.shields.io/badge/GitHub-@maxystory-green)](https://github.com/maxystory)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://www.linkedin.com/in/maxae/)
- Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [maxjl.lee@connect.polyu.hk](mailto:maxjl.lee@connect.polyu.hk)

---

### Ju Lin
[![GitHub](https://img.shields.io/badge/GitHub-@thorkee-green?logo=github)](https://github.com/thorkee)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-Profile-blue?logo=google-scholar)](https://scholar.google.com/citations?view_op=list_works&hl=en)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://julin.org/)
- Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [ju.lin@connect.polyu.hk](mailto:ju.lin@connect.polyu.hk)

---

### Xiwei Bai
[![GitHub](https://img.shields.io/badge/GitHub-@baaixw-green?logo=github)](https://github.com/baaixw)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-Profile-blue?logo=google-scholar)](https://scholar.google.com.hk/citations?user=bnTJHXYAAAAJ&hl=en)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://xiweibai.my.canva.site/)
- Member, IEEE
- Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [x.w.bai@polyu.edu.hk](mailto:x.w.bai@polyu.edu.hk)

---

### Li-Ta Hsu *(Corresponding Author)*
[![GitHub](https://img.shields.io/badge/GitHub-@qmohsu-green?logo=github)](https://github.com/qmohsu)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-Profile-blue?logo=google-scholar)](https://scholar.google.com.hk/citations?user=GxfOCUMAAAAJ&hl=en)
[![Website](https://img.shields.io/badge/Personal-Website-black?logo=safari)](https://www.polyu.edu.hk/aae/people/academic-staff/dr-hsu-li-ta/)
- Senior Member, IEEE
- Department of Aeronautical and Aviation Engineering, The Hong Kong Polytechnic University
- Email: [lt.hsu@polyu.edu.hk](mailto:lt.hsu@polyu.edu.hk)

## Abstract

The integration of diverse sensor data from Internet of Things (IoT) devices, such as smartphones and specialized systems like Ultra-Wideband (UWB), is essential for accurate positioning in various applications. This paper presents a dual-stage data standardization framework that employs Large Language Models (LLMs) to automate the transformation of heterogeneous sensor data into a uniform format. The first stage utilizes a fine-tuned LLM to directly predict standardized data, while the second stage generates transformation rules based on the predictions, enabling continuous and efficient standardization for new incoming data. Additionally, this approach incorporates an Extended Kalman Filter (EKF) for sophisticated sensor data fusion, significantly improving the positioning system’s accuracy. Our dual-stage method achieves high success rates of 97.5% for handling non-uniform units and 98.5% for managing missing entries, while also notably reducing positioning errors to 0.33 meters by integrating GNSS, Visual Positioning System (VPS), UWB, and IMU sensors. Evaluations in dynamic environments have demonstrated the method’s improvements in operational efficiency and scalability, validating the effectiveness of the dual-stage LLM framework in navigating the complexities of sensor data integration. This proposed method not only streamlines the processing of diverse data types but also lays the groundwork for more robust and adaptable IoT navigation solutions, leading to marked enhancements in positioning accuracy and operational efficiency.

## 🎯 Contributions

This study significantly advances the field of seamless positioning and IoT applications, building upon and extending our previous work presented in our [![IPIN Paper](https://img.shields.io/badge/IPIN_Paper-10.1109/IPIN62893.2024.10786123-white)](https://ieeexplore.ieee.org/abstract/document/10786123):

- **Dual-Stage Approach**: Our research contributes a dual-stage LLM-based framework for data standardization, enhancing scalability and adaptability. The single-stage approach offers a solid baseline by directly generating transformation rules, whereas the dual-stage approach builds upon this by creating an initial standardized output followed by rule generation, thus enabling continuous learning and adaptation to sensor formats.

- **Rigorous Evaluation**: We further contribute through rigorous evaluation, implementing comprehensive unit tests and comparative analyses. This approach secures high success rates for correcting data input issues, showcasing the robustness of our framework in real-world IoT scenarios.

- **Foundational Work for IoT Evolution**: By addressing critical challenges in sensor data integration, this paper contributes foundational work that catalyzes advancements in IoT technology. Our framework sets the stage for the development of more adaptable and scalable navigation solutions that can be seamlessly integrated into diverse IoT ecosystems.
