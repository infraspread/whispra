# Whispra

A cross-platform desktop application for speech-to-text transcription using OpenAI's Whisper.

The Reason for creation of this app is the simple fact that I tried out several open source and commercial apps that serve the same purpose, but:
- (commercial) privacy concerns towards cloud services: stuff you talk is sent and transcribed by machines located in - countries - (no matter which actually, they all suck nowadays). Machines owned by people I do not know. 
- (commercial) pay per usage fees - for me this boils down to - lets say a keyboard company charging for key presses, a mouse manufacturer charging for mouse movement distance. Surely hope noone from that greedy two letter printer company reads this...
- (both) interfaces not living up to expectation
- (open source) complicated setup procedures excluding regular skilled users (Noobs)


## Features

- Record audio directly from your microphone
- Import existing audio files (mp3, wav, m4a, flac)
- Transcribe speech in multiple languages
- Choose from different Whisper model sizes for accuracy and performance
- Copy transcriptions to clipboard or save to files
- Clean, modern user interface
- **Scan for locally downloaded Whisper models** to avoid re-downloading

## Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package installer)

### Windows Installation

1. Clone or download this repository
2. Create a virtual environment:
   ```
   python -m venv .venv
   .venv\Scripts\activate
   ```
3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

### Running the Application

```
python run.py
```

## Usage

1. Select a Whisper model size (base is recommended for most use cases)
2. Choose a language or use Auto-detect
3. Click "Start Recording" to record audio from your microphone
4. Speak clearly into your microphone
5. Click "Stop Recording" when finished
6. The transcription will appear in the text area
7. Use the buttons at the bottom to copy, save, or clear the text

Alternatively, you can use the "Import Audio" button to select an existing audio file for transcription.

## Model Management

Whispra includes a powerful model management system that allows you to:

- View detailed information about all available Whisper models
- Scan directories recursively for already downloaded Whisper models
- Use local model files instead of downloading them again

### Using Local Models

1. Click the "Manage Models" button
2. Click "Select Directory" or choose a common location from the dropdown
3. Click "Scan for Models" to search for Whisper model files
4. The application will identify models based on file size and SHA-256 hash verification
5. Select a model from the table and click "Use Selected Model"

The model scanner works by checking file sizes first (for efficiency), then verifying the SHA-256 hash of files that match the expected size. This allows it to find Whisper model files regardless of their filename.

### Supported Whisper Models

| Model | Size | Language Support | Default Filename |
|-------|------|------------------|------------------|
| tiny | 37.4 MB | Multilingual | tiny.pt |
| tiny.en | 37.4 MB | English only | tiny.en.pt |
| base | 135.4 MB | Multilingual | base.pt |
| base.en | 135.4 MB | English only | base.en.pt |
| small | 445.2 MB | Multilingual | small.pt |
| small.en | 445.2 MB | English only | small.en.pt |
| medium | 1.4 GB | Multilingual | medium.pt |
| medium.en | 1.4 GB | English only | medium.en.pt |
| large | 2.8 GB | Multilingual | large.pt |
| large-v1 | 2.5 GB | Multilingual | large-v1.pt |
| large-v2 | 2.8 GB | Multilingual | large-v2.pt |
| large-v3 | 2.8 GB | Multilingual | large-v3.pt |

## Model Sizes

Whispra supports all Whisper model sizes:

- **tiny**: Fastest, lowest accuracy
- **base**: Good balance of speed and accuracy
- **small**: Better accuracy, slower than base
- **medium**: High accuracy, slower
- **large**: Highest accuracy, slowest

Larger models require more RAM and may perform better with a GPU.

## Dependencies

The application uses the following main libraries:

- OpenAI Whisper for speech recognition
- PyQt5 for the user interface
- PyAudio for audio recording
- Torch for machine learning
- NumPy for numerical operations

## License

This project is licensed under the MIT License - see the LICENSE file for details. 
