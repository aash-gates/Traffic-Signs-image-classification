# Traffic Sign Classification Using CNN

This project uses a Convolutional Neural Network (CNN) to classify traffic signs into various categories. Follow the instructions below to set up the environment, prepare the dataset, and train the model.

---

## Environment Setup

1. Install Anaconda from [https://www.anaconda.com/](https://www.anaconda.com/).
2. Create a virtual environment:
mpy matplotlib
conda create -n traffic_signs python=3.9 -y conda activate traffic_signs

3. Install the required libraries:

pip install tensorflow scikit-learn pillow matplotlib

4. Start Jupyter Notebook:

jupyter notebook


---

## Dataset Preparation

1. The dataset should follow this folder structure:

traffic_signs_dataset/ ├── train/ │ ├── class_1/ │ │ ├── image1.jpg │ │ ├── image2.jpg │ │ └── ... │ ├── class_2/ │ │ ├── image1.jpg │ │ ├── image2.jpg │ │ └── ... │ └── ... └── val/ ├── class_1/ │ ├── image1.jpg │ ├── image2.jpg │ └── ... ├── class_2/ │ ├── image1.jpg │ ├── image2.jpg │ └── ... └── ...

2. Ensure the `traffic_signs_dataset` folder is in the same directory as the Python script or Jupyter Notebook.

---

## Running the Program

1. Launch Jupyter Notebook in the directory containing the script.
2. Verify the dataset path at the beginning of the program:

dataset_path = "./traffic_signs_dataset"

3. Execute the cells step by step:
- Import libraries and verify dataset path.
- Preprocess data using `ImageDataGenerator`.
- Define and compile the CNN model.
- Train the model and evaluate its accuracy.
4. Save the trained model:

model.save('traffic_sign_classifier.h5')


---

## Notes

- If the dataset path is incorrect, the program will display an error message.
- Adjust hyperparameters such as learning rate, batch size, and augmentation settings to improve accuracy.
- Use the saved model (`traffic_sign_classifier.h5`) for predictions on new images.

---

## Environment Activation (Optional)

To activate the environment again later, use:

conda activate traffic_signs

To deactivate:

conda deactivate


---
