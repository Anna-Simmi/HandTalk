# Hand Gesture Recognition

A Python project for **hand gesture recognition** using **OpenCV**, **MediaPipe**, and **scikit-learn**.  
This project allows you to:  
1. Collect hand gesture images via webcam.  
2. Process images into normalized landmarks.  
3. Train a Random Forest classifier.  
4. Run inference on new hand gestures in real-time.

---

## 📁 Project Structure

```

├── collect\_imgs.py        # Capture hand gesture images from webcam
├── create\_dataset.py      # Extract hand landmarks and save dataset
├── train\_classifier.py    # Train Random Forest classifier
├── inference\_classifier.py # Run real-time gesture recognition
├── data/                  # Folder for storing gesture images
├── data.pickle            # Pickled dataset of hand landmarks
├── model.p                # Trained Random Forest model
└── requirements.txt       # Python dependencies

````

---

## ⚡ Requirements

- Python 3.10+
- Packages listed in `requirements.txt`:

```text
opencv-python==4.7.0.68
mediapipe==0.10.21
scikit-learn==1.2.0
numpy>=1.24
````

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

## 🖐️ Usage

### 1. Collect Images

Run the script to capture hand gesture images:

```bash
python collect_imgs.py
```

* Images are saved in `./data/<class_number>/` folders.
* Press **Q** to start capturing after positioning your hand.
* Each class collects **100 images** by default.

---

### 2. Create Dataset

Extract hand landmarks and save to a pickle file:

```bash
python create_dataset.py
```

* This creates `data.pickle` containing `data` (landmarks) and `labels`.

---

### 3. Train Classifier

Train a **Random Forest** classifier:

```bash
python train_classifier.py
```

* Trains on the dataset from `data.pickle`.
* Saves trained model to `model.p`.
* Prints accuracy on the test set.

---

### 4. Inference (Real-Time Recognition)

Run real-time gesture recognition:

```bash
python inference_classifier.py
```

* Detects hand gestures via webcam.
* Uses the trained `model.p` to predict the gesture class.

---

## 🔧 Customization

* **Number of classes**: Change `number_of_classes` in `collect_imgs.py`.
* **Images per class**: Adjust `dataset_size` in `collect_imgs.py`.
* **Model parameters**: Edit `n_estimators` or `max_depth` in `train_classifier.py`.

---

## ⚡ Notes

* Ensure good lighting and a plain background for better hand detection.
* The classifier works best with **one hand per image**.
* All scripts assume the folder `data/` exists (it will be created automatically).

---

## 📄 License

This project is **open-source**. Feel free to use, modify, or share.

---

## 📌 Author

 Anna-Simmi

```


