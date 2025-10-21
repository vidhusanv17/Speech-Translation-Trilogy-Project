# Real-Time Speech Translator App

A full-stack AI-powered real-time speech translator that works seamlessly during Zoom or Google Meet meetings.
It captures live audio, transcribes it into text, translates it into a selected language, and displays subtitles with punctuation and silence detection in real time.

---

## Features

* Live Audio Capture – captures microphone or system audio during calls
* Streaming Speech-to-Text – real-time transcription using Whisper, Deepgram, or Google STT
* Instant Translation – powered by DeepL or Google Translate APIs
* Silence Detection – adds punctuation and pauses naturally
* Low Latency Pipeline – WebSocket-based streaming between frontend and backend
* Interactive UI – built with React for dynamic subtitle display
* Multi-Language Support – translate speech to and from 100+ languages
* Lightweight Backend – FastAPI-based architecture with asynchronous streaming

---

## Architecture Overview

```
Audio Input (Mic/Zoom/GMeet)
        ↓
Audio Stream (WebRTC / MediaRecorder)
        ↓
Backend (FastAPI + WebSocket)
        ↓
Speech-to-Text (Whisper API / Google STT)
        ↓
Translation Layer (DeepL / Google Translate API)
        ↓
Silence Detection (Punctuation Engine)
        ↓
UI Subtitles (React + WebSocket)
```

---

## Tech Stack

| Layer              | Technology                    | Purpose                            |
| ------------------ | ----------------------------- | ---------------------------------- |
| Frontend           | React + WebSocket             | Real-time UI for subtitles         |
| Backend            | FastAPI                       | Stream handling and API management |
| Speech Recognition | OpenAI Whisper / Deepgram API | Transcription                      |
| Translation        | DeepL / Google Translate API  | Translation                        |
| Audio Capture      | WebRTC / MediaRecorder        | Live audio input                   |
| Deployment         | Docker / Vercel / Render      | Hosting                            |

---

## Folder Structure

```
speech-translator
 ┣ frontend/           # React UI
 ┣ backend/            # FastAPI server
 ┣ start.sh            # Unix startup
 ┣ start.bat           # Windows startup
 ┗ README.md
```

---

## Installation and Usage

### Backend Setup

```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

### Frontend Setup

```bash
cd frontend
npm install
npm start
```

### Open in Browser

```
http://localhost:3000
```

---

## Environment Variables

Create a `.env` file inside `/backend` with the following:

```
OPENAI_API_KEY=your_openai_key_here
DEEPL_API_KEY=your_deepl_key_here
GOOGLE_API_KEY=your_google_key_here
```

---

## API Endpoints

| Method | Endpoint    | Description             |
| ------ | ----------- | ----------------------- |
| GET    | /health     | Check server status     |
| POST   | /transcribe | Upload or stream audio  |
| POST   | /translate  | Translate text          |
| WS     | /ws/audio   | Real-time speech stream |

---

## Future Enhancements

* Multi-user subtitle sync for group calls
* Offline Whisper model support
* Speaker identification and tone detection
* Auto-language detection

---

## Contributors

* **Vidhusan V** – Full Stack Developer and Architect
* **Cursor AI Assistant** – Code Generation Support

---

## License

This project is licensed under the MIT License – free to use, modify, and distribute with attribution.

---

Built using FastAPI, React, and AI Translation APIs.
