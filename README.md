# Traffic Sign Classification Project

This project builds a Convolutional Neural Network (CNN) for traffic sign classification.

---

## Prerequisites

1. Install Anaconda:
   Download and install Anaconda from https://www.anaconda.com/.

2. Create a Virtual Environment:
   conda create -n traffic_signs python=3.9 -y  
   conda activate traffic_signs  

3. Install Required Libraries:
   pip install tensorflow scikit-learn pillow matplotlib  

4. Dataset Requirements:
   Place the dataset in the following format:  
   Main_Dataset/  
   ├── Images/  
   │   ├── Class_1/  
   │   │   ├── image1.jpg  
   │   │   ├── image2.jpg  
   │   │   └── ...  
   │   ├── Class_2/  
   │   │   ├── image1.jpg  
   │   │   ├── image2.jpg  
   │   │   └── ...  
   │   └── ...  
   └── labels.csv  

5. Launch Jupyter Notebook:
   jupyter notebook  

---

## Steps to Run

1. Verify Dataset Path:  
   dataset_path = "./Images"  
   if not os.path.exists(dataset_path):  
       print(f"The dataset path {dataset_path} doesn't exist!")  
   else:  
       print("Dataset found!")  

2. Build the CNN Model:  
   model = Sequential([  
       Conv2D(32, (3, 3), activation='relu', input_shape=(32, 32, 3)),  
       MaxPooling2D(pool_size=(2, 2)),  
       Conv2D(64, (3, 3), activation='relu'),  
       MaxPooling2D(pool_size=(2, 2)),  
       Flatten(),  
       Dense(128, activation='relu'),  
       Dropout(0.5),  
       Dense(num_classes, activation='softmax')  
   ])  
   model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])  

3. Train the Model:  
   history = model.fit(X_train, y_train, validation_data=(X_val, y_val), epochs=30, batch_size=32)  

4. Evaluate the Model:  
   with tf.device('/GPU:0'):  
       pred = np.argmax(model.predict(X_test), axis=-1)  
   print(accuracy_score(labels, pred))  

5. Save the Model:  
   model.save('traffic_sign_classifier.h5')  

---

## Environment Management

- To activate the environment:  
   conda activate traffic_signs  

- To deactivate the environment:  
   conda deactivate  

---

## Notes

- Adjust hyperparameters and data augmentation for better accuracy.  
- Use the following code to load a saved model:  
   from tensorflow.keras.models import load_model  
   model = load_model('traffic_sign_classifier.h5')  

---
