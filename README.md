# Sign-Language-Recognition
Here is a short write-up summarizing my approach, results, and challenges:  

# **Sign Language Recognition using PyTorch**  

## **Approach**  
The goal of this project was to develop a real-time sign language recognition system using deep learning. The system classifies six different sign language gestures (`Hello`, `I love you`, `No`, `Please`, `Thanks`, and `Yes`) and converts predictions into text and speech output.  

1. **Dataset Handling**:  
   - The dataset consists of images stored in `train/images` and `test/images`, with YOLO-style labels.  
   - Labels were preprocessed by extracting only the first value (class ID) from the YOLO label files.  
   - The images were resized to **224x224 pixels** and normalized for better model performance.  

2. **Model Selection**:  
   - Used **ResNet-50**, a pre-trained deep learning model, for feature extraction.  
   - Modified the final layer to output six classes corresponding to the sign language gestures.  

3. **Training & Optimization**:  
   - Used **CrossEntropyLoss** as the loss function and **Adam** optimizer.  
   - Trained for **50 epochs** with a batch size of **32**.  
   - Applied **data augmentation** (random horizontal flipping, rotation, and brightness adjustments) to make the model more robust.  

4. **Inference & Real-Time Prediction**:  
   - The trained model was saved as `"sign_language_model.pth"` for later use.  
   - Implemented a webcam-based real-time recognition system using OpenCV.  
   - Integrated **text-to-speech (TTS)** using `pyttsx3` to convert predictions into speech output.  

## **Results**  
- The model achieved **~70% accuracy** on the test dataset.  
- The real-time recognition worked well for clear hand gestures but struggled with lighting variations and certain hand positions.  

## **Challenges Faced**  
1. **Finding a Suitable Training Dataset**:  
   - It was difficult to find a well-labeled dataset for sign language gestures.  
   - The dataset had to be manually reviewed and cleaned before training.  
2. **Label Processing**:  
   - The dataset used YOLO format annotations, so extracting correct class IDs required custom preprocessing.  
3. **Model Performance**:  
   - The model sometimes misclassified gestures due to variations in hand positioning and lighting.  
   - Using a larger dataset and a more complex model (e.g., ResNet-50) could improve accuracy.  

## **For Improvements**  
- Collect and annotate a **larger, more diverse dataset**.  
- Use a **more advanced model** like EfficientNet for better accuracy.  
- Implement **gesture tracking with sequence models (LSTMs or Transformers)** for continuous sign recognition.  
 
