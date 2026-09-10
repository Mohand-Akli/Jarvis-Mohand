# Jarvis-Mohand OS 🧠

This Python-based project is a customizable, local AI assistant inspired by the Jarvis OS concept. It integrates offline speech-to-text, local Large Language Models (LLMs), a local markdown knowledge base, and a cloud-based dashboard for seamless daily organization.

<br>

<a href="https://www.linkedin.com/in/mohand-akli-zidani" target="_blank">
<img src="https://img.shields.io/badge/LinkedIn-0077B5?&style=for-the-badge&logo=linkedin&logoColor=white" alt="linkedin" style="margin-bottom: 5px;" />
</a>

## Table of Contents
- [Prerequisites](#prerequisites)
- [Key Features](#key-features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Notes](#notes)
- [License](#license)

## Prerequisites
- macOS (for `pyaudio` and `keyboard` specific configurations)
- Python 3.8+
- [Ollama](https://ollama.com/) installed locally
- [Obsidian](https://obsidian.md/) installed locally
- A Notion account and API Integration Token

## Key Features
- **The Ears (Voice Recognition):** Push-to-talk speech-to-text using OpenAI's Whisper running locally.
- **The Engine (Local LLM):** Powered by Ollama (Llama 3 / Mistral) to process requests, analyze intentions, and format data into JSON.
- **The Memory (Obsidian):** Automatic generation of markdown (`.md`) files saved directly into a local Obsidian vault.
- **The Face (Notion Dashboard):** API integration to push tasks, events, and reminders directly to a centralized Notion workspace.

## Project Structure
```text
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
├── ears.py             # Push-to-talk and Whisper transcription
├── brain.py            # Ollama routing and LLM logic (WIP)
├── memory.py           # Obsidian local file management (WIP)
├── dashboard.py        # Notion API interactions (WIP)
└── JarvisVault/        # The local Obsidian Vault
    └── Inbox/
```

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Mohand-Akli/jarvis-mohand.git
   cd jarvis-mohand
   ```
2. Set up the virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. Install system and Python dependencies:
   ```bash
   brew install portaudio
   pip install openai-whisper pyaudio keyboard requests litellm
   ```
4. Download the local LLM via Ollama:
   ```bash
   ollama run llama3
   ```

## Usage

To start the voice recognition module (requires administrator privileges on macOS for keyboard monitoring):

```bash
sudo python ears.py
```

Hold the `SPACE` bar to talk. The script will record your audio and transcribe it using Whisper once the key is released.

## Notes
- **Privacy:** All voice processing and logic routing (Ollama) happen 100% locally. Only the final formatted data is sent to the Notion API.
- **macOS Permissions:** You may need to grant your Terminal app "Accessibility" and "Microphone" permissions in the macOS System Settings for the scripts to run properly.

## License
MIT
