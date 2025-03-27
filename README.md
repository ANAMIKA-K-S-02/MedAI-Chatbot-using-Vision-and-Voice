# MedAI Chatbot using Vision and Voice

## Overview
MedAI is an AI-powered chatbot that acts as a virtual medical assistant. It integrates **speech-to-text (STT)**, **image analysis**, and **text-to-speech (TTS)** technologies to provide insights based on spoken input and uploaded images. This project is built using **Groq AI models, ElevenLabs, gTTS, and Gradio**.

## Features
- **Speech-to-Text (STT)**: Converts spoken patient queries into text using **Whisper Large v3**.
- **Medical Image Analysis**: Uses **Llama-3.2-11B-Vision** to analyze uploaded images and provide insights.
- **Text-to-Speech (TTS)**: Converts responses into natural-sounding speech using **ElevenLabs API** and **gTTS**.
- **Interactive UI**: Powered by **Gradio** for easy interaction.

## Tech Stack
- **Python**
- **Gradio** (for UI)
- **Groq AI** (for image & text analysis)
- **ElevenLabs** (for advanced TTS)
- **gTTS** (for alternative TTS)
- **SpeechRecognition** (for voice input processing)
- **pydub** (for audio handling)

---

## Installation

### 1. Clone the Repository
```sh
git clone https://github.com/your-username/MedAI-Chatbot.git
cd MedAI-Chatbot
```

### 2. Create and Activate a Virtual Environment
```sh
python -m venv venv
# Activate (Windows)
venv\Scripts\activate
# Activate (Mac/Linux)
source venv/bin/activate
```

### 3. Install Dependencies
```sh
pip install -r requirements.txt
```

### 4. Set Up API Keys
Create a **.env** file in the project directory and add your API keys:
```sh
GROQ_API_KEY=your_groq_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key
```

### 5. Install FFmpeg (for audio processing)
#### Windows:
Download and install FFmpeg from [FFmpeg official website](https://ffmpeg.org/download.html), then add it to **System PATH**.

#### Mac/Linux:
```sh
sudo apt install ffmpeg  # Ubuntu/Debian
brew install ffmpeg      # macOS
```

---

## Usage

### Running the Chatbot
```sh
python main.py
```

### Access the UI
Once the script runs, open the **Gradio UI** in your browser (usually at `http://127.0.0.1:7860`).

### Interacting with the Chatbot
1. **Speak into the microphone** to describe symptoms.
2. **Upload an image** of the affected area (optional).
3. The AI **transcribes** the speech, **analyzes** the image (if provided), and **responds**.
4. The response is read aloud using **TTS**.

---

## Project Structure
```
MedAI-Chatbot/
│── doctor.py  # Handles image encoding and AI query analysis
│── voice_patient.py  # Manages STT (Speech-to-Text) & audio recording
│── voice_doctor.py  # Handles TTS (Text-to-Speech) functionality
│── main.py  # Runs the chatbot
│── requirements.txt  # Dependencies
│── .env  # API Keys (ignored in Git)
└── README.md  # Documentation
```

---

## Known Issues & Troubleshooting
### 1. **`ModuleNotFoundError: No module named 'speech_recognition'`**
Run:
```sh
pip install SpeechRecognition
```

### 2. **ElevenLabs API Not Working?**
- Ensure the **ELEVENLABS_API_KEY** is correctly set in `.env`.
- Check if ElevenLabs supports the requested **voice model**.

### 3. **FFmpeg Not Found (Audio Issues)?**
- Verify FFmpeg is installed and added to **system PATH** (`ffmpeg -version` in terminal).

---

## Future Enhancements
- Add **multilingual support**.
- Implement **customizable doctor responses**.
- Improve **image analysis accuracy** using fine-tuned medical models.

---

## Contributing
Contributions are welcome! Fork the repo, create a branch, and submit a PR.

---

## Contact
For queries, reach out at **your-email@example.com**.

