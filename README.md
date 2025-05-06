# hwswLab2
.
├── sorting_hat_ESP32/
│   ├── sorting_hat_esp_button.ino     # Arduino sketch (main code)
│   └── sorting_hat_model.h            # Exported ML model in C++
├── src/
│   ├── sorting_hat_laptop.py          # Python script for training the model
│   └── Sorting_Dataset.csv            # User response dataset (min 30 entries)
├── assets/
│   └── sorting_hat_button.png         # Wiring diagram image
├── requirements.txt                   # Python package dependencies
├── README.md                          # Documentation (or Lab3_Report.md)
└── video_link.txt (optional)          # Link to your demo video (or include in README)

## 1. Are all 10 questions important?
Not all 10 questions are equally important. After analyzing the data and running the model with various subsets, we found that removing low-impact questions such as Q6 (mystery book behavior) and Q7 (preferred pet) had little effect on accuracy. To streamline user experience, we could reduce the number of questions to 6–7 while maintaining similar performance by keeping only the most informative ones.

## 2. How could you improve the model’s accuracy or efficiency?
We could:

Collect more diverse and balanced data across all houses

Use a more expressive model (e.g., RandomForestClassifier or XGBoost) before converting to embedded C++

Apply feature selection techniques to reduce redundancy

Optimize the decision tree depth and prune it to reduce overfitting

## 3. What additional sensors or hardware could enhance the user experience?
Some ideas to enhance the UX:

A microphone with simple voice recognition to answer questions verbally

A gesture sensor (like APDS-9960) to allow contactless input

RGB LEDs to display the house colors

A speaker module to play house themes when sorted

Touch screen instead of physical buttons for future versions

## 4. Does decision tree remain suitable for your choice of new sensors?
Decision trees are suitable for symbolic and categorical data, like button presses. However, with new sensors like microphones or gesture inputs that generate continuous or time-series data, decision trees may not be sufficient. For such inputs:

A small neural network (e.g., 1D CNN or TFLite Micro model) would be more appropriate

Alternatively, KNN or Naive Bayes could handle simple gestures if data is well-structured

Thus, decision trees are great for current use but limited if we expand to more dynamic sensor inputs.

