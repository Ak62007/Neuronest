# Voice-Enabled AI Assistant

A conversational AI assistant that supports both voice and text interactions using Google's Generative AI.

## Overview

This application allows users to interact with Google's Generative AI model through either voice or text input. It features real-time speech recognition, text-to-speech output, and maintains conversation context for natural interactions.

## Features

- **Dual Input Methods**: Choose between voice or text input for interactions
- **Voice Activity Detection**: Automatically detects speech and silence to manage recording sessions
- **Text-to-Speech Output**: Converts AI responses to spoken audio
- **Interruptible Speech**: Press 's' during speech playback to interrupt and start a new recording
- **Conversation History**: Maintains context throughout the interaction session
- **Markdown Cleaning**: Removes formatting from AI responses for better speech synthesis

## Requirements

- Python 3.6+
- Internet connection for API access

## Dependencies

```
google-generativeai
SpeechRecognition
sounddevice
numpy
pyttsx3
```

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/voice-enabled-ai-assistant.git
   cd voice-enabled-ai-assistant
   ```

2. Install the required dependencies:
   ```
   pip install google-generativeai SpeechRecognition sounddevice numpy pyttsx3
   ```

3. Set up your Google API key:
   - Get a Google Generative AI API key
   - Replace the API key in the code or set it as an environment variable

## Usage

Run the main script:
```
python main.py
```

### Voice Input Mode
1. Select option 1 for voice input
2. Speak clearly into your microphone
3. The application will automatically detect when you've finished speaking
4. Listen to the AI response or press 's' to interrupt it

### Text Input Mode
1. Select option 2 for text input
2. Type your message and press Enter
3. The AI will respond both in text and speech

### Exiting the Program
- Select option 3 from the menu
- Type "quit", "exit", or "stop" when prompted for input

## How It Works

1. **Audio Recording**: Uses sounddevice to capture audio with voice activity detection
2. **Speech Recognition**: Converts recorded audio to text using Google's Speech Recognition
3. **AI Processing**: Sends the text to Google's Generative AI model
4. **Text-to-Speech**: Converts the AI's response to speech using pyttsx3
5. **Conversation Management**: Maintains conversation history for context

## Configuration Options

Several parameters can be adjusted in the code:

- `SAMPLE_RATE`: Audio sampling rate (default: 44100)
- `SILENCE_THRESHOLD`: Threshold for detecting silence (default: 500)
- `SILENCE_DURATION`: How long silence must persist before stopping recording (default: 1.0 seconds)
- `MAX_RECORDING_DURATION`: Maximum recording time (default: 300 seconds)
- Text-to-speech settings: Speech rate and volume can be adjusted in the `text_to_speech` function

## Customization

You can customize the AI model by modifying the `generation_config` dictionary:

```python
generation_config = {
    "temperature": 1,        # Controls randomness (lower = more deterministic)
    "top_p": 0.95,           # Nucleus sampling parameter
    "top_k": 40,             # Limits token selection to top k options
    "max_output_tokens": 8192,  # Maximum response length
}
```
## Acknowledgments

- Uses Google's Generative AI API
- Speech recognition powered by Google Speech Recognition
- Text-to-speech functionality provided by pyttsx3
