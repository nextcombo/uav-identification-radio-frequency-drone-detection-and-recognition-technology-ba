# UAV Identification]Radio Frequency Drone Detection and Recognition Technology Based on Hierarchical Learning, with an Accuracy Rate of 99%! [Attached Python code]

Based on hierarchical learning, the RF drone detection and recognition technology achieves a precision rate of 99%!
Abstract: Drones are increasingly being used in civilian and industrial fields, but the illegal use of drones has also surged. The efficient detection and recognition of drones have become a pressing research problem to be solved. This paper proposes a new drone detection and recognition method based on machine learning, relying on the concept of hierarchy to construct an integrated learning model. It preprocesses and extracts features from RF (Radio Frequency) data, and optimizes the output effect of RF signals through filtering. The model includes four hierarchical working classifiers, successively completing the detection of drone existence, identification of drone models, and determination of flight modes for Bebop and AR drones. Validation results based on public datasets show that this method performs better than existing systems, with a comprehensive recognition accuracy of drone existence, model, and flight mode around 99%.
Introduction: Since this century, drones have achieved global popularity due to the development of precise sensor technology. Their low cost and high spatial resolution advantages have replaced or supplemented traditional satellite and communication systems in multiple fields such as military mapping, agricultural pest control, logistics distribution, emergency search and rescue, etc., becoming an important part of modern technological systems.
However, the widespread use of drones has also led to serious safety and privacy issues: unauthorized drones not only hit military helicopters, entered the White House restricted area, but were also used for smuggling, prison contraband transportation, and even carried explosives posing significant safety threats. Additionally, most drones have not been registered, and their geographical fence functions are easily disabled, making rapid detection of drones entering restricted areas, identification of models, and determination of flight modes a core demand for ensuring public safety.
The current drone detection technology mainly includes RF, radar, acoustics, vision, and LiDAR, but each single technology has its obvious shortcomings: radar is limited by the small cross-sectional characteristics of drones, vision technology relies on line of sight and cannot work at night, and acoustics technology is easily interfered with by environmental noise. RF signal detection has the advantages of low cost, no requirement for line of sight, and long detection distance. By extracting the RF fingerprints of the drone controller and combining machine learning technology to achieve drone feature recognition, it has become a research hotspot in this field.
To this end, this paper designs an intelligent hierarchical detection method based on machine learning, relying on RF signals to achieve hierarchical identification of drone presence, model, and flight mode, aiming to achieve lightweight, efficient, and high accuracy drone detection and recognition results.
Method Introduction
The RF drone detection and recognition method proposed in this paper is centered around a hierarchical ensemble learning model. The overall process includes data preprocessing, feature extraction, and hierarchical classification recognition, which are three key steps. Based on the public drone RF dataset, the model is trained and validated. The specific design is as follows:
1. Experimental basis and dataset selection
The experimental subjects in this paper are three mainstream small drones: Parrot Bebop, Parrot AR, DJI Phantom 3. The USRP-2943 RF receiver is used to collect RF signals (including dual frequency bands) at 2.4GHz ISM band. The publicly available dataset contains 227 signal segments (each segment 20 million samples), divided into three detection levels: no drone, three drones, and four flight modes (on, hover, fly, record) of Bebop/AR.
2. Data preprocessing
The original RF signals are filtered smooth and feature engineered: FIR filters based on the average method are used to eliminate noise and interference, and the Fast Fourier Transform (FFT) is used to convert the time domain signal to the frequency domain signal and remove the zero frequency component, reducing computational complexity. At the same time, the signal is normalized to enhance the stability of the model recognition.
3. The hierarchical ensemble classifier design model includes four integrated classifiers that work in successive stages, all based on the XGBoost and K-Nearest Neighbor (KNN) algorithms to construct an ensemble learning module. Classification results are output through majority voting, with each classifier progressively enhancing its functionality:
★  
Classifier 1 (Binary Classification): Completes the detection of drone presence, determining "with drone/without drone".
★  
Classifier 2 (Triple Classification): Identify the model of detected drones, distinguishing between Bebop, AR, and Phantom 3.
★  
Classifier 3 (four-class): For Bebop drone, further identification of its four flight modes;
★  
Classifier 4 (four-class): For AR drones, further identification of their four flight modes.
The core advantage of hierarchical design lies in progressively eliminating irrelevant categories, reducing the recognition interference of similar radio frequency signals, and accomplishing hyperparameter optimization for XGBoost (learning rate 0.1, estimator count 100) and KNN (K=1) through grid search to avoid overfitting and underfitting.
4. Model validation metrics include accuracy, precision, recall, F1 score, ROC curve (AUC value) as performance evaluation indicators. At the same time, detection processing time is statistically counted to comprehensively verify the model's recognition effect and real-time performance.
Conclusion This paper addresses the issue of drone detection and identification for radio frequency signals, designing a detection model based on hierarchical ensemble learning. It achieves the gradual and precise identification of drone existence, model type, and flight mode through a four-tier classifier. The core conclusions are as follows:
1  
The model, through RF signal preprocessing and hierarchical classification design, effectively reduces interference from environmental noise and similar drone RF signals. In 10 detection scenarios (including no drone, three models, and Bebop/AR flight modes), the overall recognition accuracy reaches 99.2%, with an average F1 score of 99.1%, a recall rate of 99.11%, and the processing time for single sample detection is only 6.54-7.41 milliseconds, demonstrating both high accuracy and real-time performance.
2  
Compared to methods such as CNN (59.2%), XGBoost (70.1%), and DNN (46.8%) under the same dataset, the recognition performance of the hierarchical ensemble learning model has been significantly surpassed, verifying the effectiveness of hierarchical design in radio frequency drone recognition. 
3 
This method is based on low-cost radio frequency sensors, without the need for line-of-sight requirements, and can operate in complex urban environments, providing a lightweight and efficient technical solution for drone safety inspections. 
Future research will further expand the dataset by incorporating more types of drone samples, enhancing the generalization capability of the model, making it suitable for more complex practical application scenarios.

## Images

![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](01.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](02.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](03.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](04.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](05.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](06.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](07.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](08.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](09.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](10.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](11.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](12.png)
![(UAV Identification)Radio Frequency Drone Detection and Identification Technology Based on Hierarchical Learning, with a accuracy rate of 99%! [Attached Python Code]](13.png)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
