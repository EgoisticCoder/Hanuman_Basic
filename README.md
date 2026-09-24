# Hanuman

A voice-enabled AI assistant inspired by the spirit of Hanuman. This project turns a browser microphone into a smart voice interface that listens for spoken commands, transcribes audio using Groq Whisper, processes requests through a large language model, and responds with natural-sounding speech using ElevenLabs or Edge TTS.

## Overview

Hanuman is a lightweight Flask app designed for real-time voice interaction in the browser. It is ideal for building a personal assistant experience with:

- microphone input from the frontend
- automatic speech recognition (ASR)
- command detection for wake words and intents
- LLM-powered chat responses
- text-to-speech playback for audio replies
- easy deployment on Vercel or a local Python server

## Features

- Voice input via browser microphone
- Audio transcription with Groq Whisper models
- Intent detection for commands such as:
  - wake / greeting
  - chat / general conversation
  - joke / humor
  - search / information requests
  - exit / stop
- AI responses from Groq's LLM API
- TTS output using ElevenLabs with Edge TTS fallback
- Vercel-ready deployment configuration
- Local caching of generated audio files

## Tech Stack

- Python
- Flask
- Groq API
- OpenAI-compatible transcription endpoints
- gTTS / Edge TTS / ElevenLabs
- JavaScript in the browser for microphone capture and audio playback

## Project Structure

```text
.
├── app.py              # Flask app and voice assistant logic
├── requirements.txt    # Python dependencies
├── vercel.json         # Vercel deployment configuration
├── README.md           # Project documentation
├── audio/              # Temporary uploaded audio files
├── cache/              # Generated audio cache
└── .env                # Local environment variables (not committed)
```

## Prerequisites

- Python 3.10+
- A Groq API key
- Optional: ElevenLabs API key for higher-quality TTS
- FFmpeg (required for audio conversion in some environments)

## Installation

1. Clone the repository:

```bash
git clone https://github.com/EgoisticCoder/Hanuman-.git
cd Hanuman-
```

2. Create a virtual environment and install dependencies:

```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

3. Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key_here
ELEVENLABS_API_KEY=your_elevenlabs_api_key_here
```

Note: `ELEVENLABS_API_KEY` is optional. If it is missing, the app falls back to Edge TTS.

## Running the App

Start the app locally:

```bash
python app.py
```

Then open:

```text
http://localhost:5000
```

Click the microphone button, speak naturally, and the app will process the audio and respond with a spoken answer.

## Supported Interaction Modes

The assistant recognizes a few categories of prompts:

- Wake / greeting: "Hanuman", "hello", "jai shri ram"
- Chat: general questions or conversation
- Joke / fun responses
- Search / research oriented commands
- Exit / stop commands

## Deployment

This project includes a `vercel.json` file for deployment on Vercel.

To deploy:

1. Push the repo to GitHub.
2. Import the project in Vercel.
3. Add environment variables in the Vercel dashboard:
   - `GROQ_API_KEY`
   - `ELEVENLABS_API_KEY` (optional)
4. Deploy the app.

## Notes

- The app is designed for a voice-first assistant experience and is best used with a browser that allows microphone access.
- The repository is small and modular, making it easy to extend with more commands, custom prompts, or persistent memory.
- Audio files are stored in the local runtime filesystem and can be cleaned up or replaced depending on deployment environment.

## License

This project does not currently include a license file. If you plan to publish or distribute it publicly, consider adding an open-source license such as MIT.

## Contributing

Contributions, improvements, and feature ideas are welcome. You can fork the repository, create a feature branch, and open a pull request with your changes.

## Author

EgoisticCoder
