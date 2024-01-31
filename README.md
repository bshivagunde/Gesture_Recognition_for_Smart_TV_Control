# Gesture_Recognition_for_Smart_TV_Control

## Project Overview
This project focuses on building a deep learning model to recognize gestures captured through a smart TV's webcam, where each gesture corresponds to specific TV control functions. The goal is to achieve high accuracy while maintaining a low memory footprint, suitable for real-world applications.

## Gesture Classes
1. **Thumbs Up:** Increase the volume
2. **Thumbs Down:** Decrease the volume
3. **Left Swipe:** Jump backward 10 seconds
4. **Right Swipe:** Jump forward 10 seconds
5. **Stop:** Pause the movie

## Dataset
The dataset includes 'train' and 'val' folders containing 663 and 100 video frames, respectively. Two CSV files provide frame details and corresponding class labels. Each video consists of 30 frames with two different sizes - 120x160 and 320x320.

## Solution Approach
Two main model architectures were explored:
- Conv3D CNNs
- 2D CNN + RNN (Custom CNN + RNN and Pre-Trained CNN + RNN using MobileNet and ResNet152V2)

## Experimental Methodology
Models were initially tested with 30% of the input data to evaluate learning capabilities. Only learnable models were selected for further experiments. Once confirmed, the chosen models were retrained from scratch using 100% of the data.

## Constant Conditions/Variables
- Image Size: 160 x 160
- Number of Channels: 3
- Number of Epochs: 55
- Batch Size: 10

## Experimental Observations with 100% Data
1. **Custom CNN with GRU as RNN:**
   - Training Accuracy: 55%
   - Validation Accuracy: 36%
   - Learning issues; not effective.

2. **Custom CNN with LSTM as RNN:**
   - Training Accuracy: 85%
   - Validation Accuracy: 56%
   - Overfitting observed.

3. **Pre-trained MobileNet with GRU as RNN:**
   - Training Accuracy: 95%
   - Validation Accuracy: 72%
   - Overfitting persists, but with an improvement in validation accuracy.

4. **Pre-trained ResNet152V2 with GRU as RNN:**
   - Training Accuracy: 98%
   - Validation Accuracy: 75%
   - Overfitting persists, but enhanced accuracy compared to MobileNet.

5. **3D Convolution Model with Kernel Regularizer ('l2'):**
   - Training Time: ~574ms/step
   - Training Accuracy: 94.53%
   - Validation Accuracy: 82%
   - Improved accuracy and reduced overfitting.

## Conclusion
The 3D Convolution Model with kernel_regularizer='l2' emerged as the most promising solution, offering faster training, improved accuracy, and reduced overfitting. The final model, despite its performance, is of only 32.3 MB in size, making it highly suitable for deployment in real-world applications with limited memory resources.

## Technologies Used
- Python
- TensorFlow
- Numpy
- Pandas
- Matplotlib
- Seaborn
- skimage
- OpenCV
- keras


## Acknowledgements
This project was conducted by [@bshivagunde](https://github.com/bshivagunde) - Feel free to contact me!
