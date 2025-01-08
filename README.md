# Gesture Recognition for Smart TV Control

## Project Description
This project, developed as part of the **Postgraduate Program in Machine Learning and Artificial Intelligence by IIIT-Bangalore**, explores deep learning-based solutions for recognizing user gestures to control smart TVs. The system identifies five gestures, performed in front of a webcam, that correspond to TV commands such as increasing/decreasing volume, jumping forward/backward, or pausing playback. By leveraging advanced architectures like Conv3D, CNN-RNN stacks, and Transfer Learning, the solution achieves robust spatiotemporal modeling and high accuracy. 

---

## Problem Statement
The aim is to enable gesture-based control for smart TVs without requiring a remote control. Each gesture corresponds to the following commands:
- **Thumbs Up**: Increase the volume
- **Thumbs Down**: Decrease the volume
- **Left Swipe**: Jump backward 10 seconds
- **Right Swipe**: Jump forward 10 seconds
- **Stop**: Pause playback

The system uses a webcam to monitor gestures, processing video sequences of 30 frames each. The dataset consists of training, validation, and test splits, with each video classified into one of the five gesture categories. The challenge lies in effectively extracting spatiotemporal features to achieve high accuracy while generalizing across unseen data.

---

## Key Technologies
- **CNN (Convolutional Neural Networks)**: Used for spatial feature extraction from individual frames.
- **RNN (Recurrent Neural Networks)**: GRU and LSTM networks modeled temporal dependencies between frames.
- **Conv3D**: Enabled simultaneous spatiotemporal feature extraction using 3D convolutions.
- **Transfer Learning**: Pre-trained MobileNet was utilized for efficient and high-quality spatial feature extraction.
- **Regularization Techniques**: Included Dropout layers and learning rate scheduling to reduce overfitting.
- **Data Augmentation**: Enhanced generalization by creating robust variations of the training data.

---

## Architectures Explored
1. **Conv3D**:
   - Spatiotemporal modeling with 3D convolutional layers.
   - Variants with different filter sizes, regularization, and parameter reductions were implemented.
2. **CNN + RNN**:
   - Combined spatial feature extraction (CNN) with temporal modeling (RNN).
   - Both GRU and LSTM were tested to capture temporal relationships effectively.
3. **Transfer Learning + GRU**:
   - Leveraged pre-trained MobileNet for spatial features, followed by GRU for sequence modeling.
   - Emerged as the best-performing architecture.
4. **CNN + LSTM**:
   - Sequential CNN-LSTM architecture modeled spatiotemporal dependencies well but exhibited overfitting.

---

## Performance Comparison

| **Model** | **Architecture**       | **Validation Accuracy** | **Comments**                                                                 |
|-----------|-------------------------|--------------------------|-------------------------------------------------------------------------------|
| **8**     | CNN + LSTM             | 44%                     | Improved temporal modeling but overfitting persisted.                         |
| **9**     | Conv3D + Augmentation  | 71%                     | Strong performance with effective regularization and data augmentation.       |
| **15**    | Conv3D (Optimized)     | 81%                     | Balanced accuracy and parameter efficiency.                                   |
| **18**    | Transfer Learning + GRU| 84%                     | Best performance. Leveraged pre-trained MobileNet and GRU for robust generalization.|

---

## Conclusion
Model 18 (Transfer Learning + GRU) was finalized as the most robust solution, achieving a **validation accuracy of 84%**. This architecture demonstrated excellent generalization and scalability, benefiting from:
- **Transfer Learning**: MobileNet pre-trained weights for spatial feature extraction.
- **GRU**: Efficient temporal modeling with fewer parameters compared to LSTM.
- **Regularization**: Dropout and learning rate scheduling minimized overfitting.

### Key Takeaways:
- Conv3D models delivered strong spatiotemporal modeling but required high computational resources.
- Data augmentation significantly boosted Conv3D performance.
- CNN-RNN architectures effectively combined spatial and temporal modeling, with GRU outperforming LSTM.
- Transfer learning proved critical in achieving state-of-the-art performance.

This project showcases the application of cutting-edge deep learning techniques in real-world problems, highlighting the importance of architecture selection and optimization for gesture-based video classification tasks.

---

**Author**: Ursina Sanderink  
**Institution**: IIIT-Bangalore  
**Acknowledgements**: This project is part of the IIIT-Bangalore postgraduate program in Machine Learning and Artificial Intelligence, where industry-driven problems are tackled with state-of-the-art methodologies.
