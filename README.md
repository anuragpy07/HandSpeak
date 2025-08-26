HandSpeak: Real-Time Sign Language Recognition

📄 Overview
This project is a real-time sign language recognition system that translates hand and body gestures into text. It leverages a deep learning model to process video input from a webcam, identifying gestures for words like "hello," "thanks," and "iloveyou." The application is designed to demonstrate an end-to-end machine learning pipeline, from data collection and model training to real-time deployment.

🎥 Demo
A short video or GIF showing the application in action would be ideal here. You can also include a link to a live demo if you deploy it on a platform like Streamlit Community Cloud.

⚙️ How It Works
Keypoint Extraction: The system uses the MediaPipe Holistic model to detect and track 33 pose, 468 face, and 21 hand landmarks in real-time. This process converts visual data (video frames) into a rich set of numerical coordinates.

Data Collection: A custom script is used to capture these landmark coordinates for 30 consecutive frames, creating a time-series sequence for each sign. This dataset is the foundation upon which the model learns to recognize gestures.

Model Training: An LSTM (Long Short-Term Memory) neural network is trained on the collected time-series sequences. The LSTM architecture is specifically chosen for its ability to learn from sequential data, making it ideal for recognizing gestures that evolve over time.

Real-Time Prediction: The trained model is integrated into a live video feed, where it continuously processes new sequences of frames and predicts the corresponding sign language word, displaying the result on the screen.

🚀 Getting Started
To run this project, follow these steps:

Prerequisites
Python 3.8+

A webcam

Installation
Clone the repository:

git clone https://github.com/your-username/HandSpeak.git
cd HandSpeak

Create and activate a virtual environment:

# On Windows
python -m venv venv
.\venv\Scripts\activate

# On macOS and Linux
python3 -m venv venv
source venv/bin/activate

Install the dependencies:

pip install -r requirements.txt

Usage
A. Data Collection
To collect new data for your model, run the main script. The script will guide you through collecting data for each of the predefined actions.

python handspeak.py

After running this, the collected data will be saved in the MP_Data folder.

B. Real-Time Recognition
After the data is collected and the model is trained, you can run the real-time recognition application to see your model in action.

# Command to run your real-time recognition script
# (You may need to update your script to have separate training and recognition parts)

📂 File Structure
HandSpeak/
├── MP_Data/                 # Directory for collected NumPy keypoint data
│   ├── hello/
│   ├── thanks/
│   └── iloveyou/
├── action.h5                # Trained Keras model weights
├── handspeak.py             # The main project script
├── requirements.txt         # Project dependencies
└── README.md                # This file

🤝 Contributing
Feel free to open an issue or submit a pull request if you want to contribute to this project.

Made with ❤️ by Anurag Kumar
