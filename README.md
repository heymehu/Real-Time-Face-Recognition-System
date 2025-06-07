# Real-Time Face Recognition System

A real-time face recognition system built with Python and OpenCV that can detect and recognize faces in real-time using your webcam.

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![OpenCV](https://img.shields.io/badge/opencv-4.x-green)

![Demo](media/gif.gif)

## Features

- Real-time face detection and recognition
- Multiple face support
- Configurable settings
- Easy to use interface
- High accuracy recognition
- Support for adding new faces

## Installation

1. Clone the repository:
```bash
git clone https://github.com/heymehu/Real-Time-Face-Recognition-System.git
cd Real-Time-Face-Recognition-System
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

Required packages:
- opencv-python
- opencv-contrib-python
- pillow
- pyyaml

## Configuration

All settings are stored in `src/settings/settings.py`:
- Camera settings (resolution, device index)
- Face detection parameters
- Training parameters
- File paths
- Confidence threshold (how confident the model has to be to recognize a face)

You can modify these settings without changing the code.

## Usage

The system works in three steps:

### 1. Capture Face Data
Run `face_taker.py` to capture training images:
```bash
python src/face_taker.py
```
- Enter your name when prompted
- The script captures 120 images of your face. Make sure to have a good lighting and move your head around to capture different angles.
- Keep your face centered in the frame
- Images are saved in the `images` folder
- Your name and ID are stored in `names.json`
- Press 'ESC' to exit early

Format of `names.json`:
```json
{
    "1": "Joe",
    "2": "Jane"
}
```

### 2. Train the Model
Run `face_train.py` to create the recognition model:
```bash
python src/face_trainer.py
```
- Processes all images in the `images` folder
- Creates a trained model file `trainer.yml`
- Shows number of faces trained

Note: Training images are saved as: `Users-{id}-{number}.jpg`

### 3. Run Face Recognition
Run `face_recognizer.py` to start real-time recognition:
```bash
python src/face_recognizer.py
```
- Your webcam will open and start recording
- Recognizes faces in real-time
- Shows name and confidence level
- Press 'ESC' to exit

## Project Structure
```
├── src/
│   ├── settings/
│   │   ├── __init__.py      # init file
│   │   ├── settings.py      # Configuration settings
│   ├── __init__.py      # init file
│   ├── face_taker.py    # Capture training images
│   ├── face_trainer.py  # Train the model
│   └── face_recognizer.py # Real-time recognition
├── images/              # Training images
├── names.json           # Name-ID mappings
└── trainer.yml          # Trained model
```

## Contributing

Contributions are welcome! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## Acknowledgments

- OpenCV for the face detection and recognition algorithms
- Python community for the amazing tools and libraries


