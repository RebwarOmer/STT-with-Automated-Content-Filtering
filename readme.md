# README.md

# Speech to Text with Automated Content Filtering

A Streamlit application that records audio from your microphone, converts speech to text using Google's Speech Recognition API, and automatically filters profanity and negative language.


## Features

- Real-time microphone recording
- Speech-to-text transcription using Google Speech Recognition
- Automatic profanity filtering using `better-profanity`
- Custom negative word detection
- Light and dark mode support
- Live statistics dashboard
- Recording timer with visual indicator
- Session history for previous recordings
- Clear history functionality

## Technologies Used

- Python 3.12
- Streamlit
- SpeechRecognition
- sounddevice
- SciPy
- NumPy
- better-profanity

## Requirements

- Python 3.12 or newer
- A working microphone
- Internet connection (required for Google Speech Recognition)

## Installation

### Clone the repository

```bash
git clone https://github.com/RebwarOmer/STT-with-Automated-Content-Filtering.git
cd STT-with-Automated-Content-Filtering
```

### Create a virtual environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

## Running the Application

```bash
streamlit run speech_to_text_filter.py
```

Open the local URL displayed in your terminal, typically:

```text
http://localhost:8501
```

## Project Structure

```text
speech-to-text-filter/
├── speech_to_text_filter.py
├── requirements.txt
└── README.md
```

## How It Works

1. Audio is captured from the user's microphone using `sounddevice`.
2. Audio data is converted into WAV format in memory.
3. `SpeechRecognition` sends the audio to Google's Speech Recognition API.
4. The transcribed text is checked against:
   - The `better-profanity` word list
   - A custom list of negative words
5. Offensive words are censored before displaying the filtered result.
6. Statistics and recording history are stored during the session.

## Example

### Original Text

```text
You are stupid and this is awful.
```

### Filtered Text

```text
You are s*** and this is a***.
```

## Limitations

- Requires an active internet connection for transcription.
- Recognition accuracy depends on microphone quality and background noise.
- Filtering is keyword-based and may not detect contextual toxicity.
- Google Speech Recognition usage may be subject to rate limits.

## License

This project is intended for educational purposes.

---

# requirements.txt

```txt
streamlit>=1.45.0
SpeechRecognition>=3.10.0
sounddevice>=0.5.0
scipy>=1.13.0
numpy>=1.26.0
better-profanity>=0.7.0
```
