## :musical_note:Development of a Python program to record audio, translate text from Farsi to English and convert text to speech in Farsi and English languages.
This code is a Python script designed to create a voice-based translation application that uses speech recognition, translation, and text-to-speech functionalities. Here’s a detailed breakdown of its components and functionality:

## :star::star::star::star::star:Breakdown of the Code

1. **Library Installation**:
   - The script installs necessary libraries such as `SpeechRecognition`, `googletrans`, `gTTS` (Google Text-to-Speech), and `PyAudio` using pip commands.

2. **Importing Modules**:
   - Imports various libraries for audio processing, speech recognition, translation, and text-to-speech conversion.

3. **Model Loading**:
   - Loads a pre-trained translation model (`facebook/mbart-large-50-many-to-many-mmt`) and its tokenizer from the Hugging Face Transformers library. This model is capable of translating between multiple languages.

4. **Speech Recognition**:
   - **`speech_to_text()`**: This function listens for audio input from the microphone, recognizes the speech using Google's speech recognition service, and returns the recognized text. It handles errors if the speech is not understood or if there’s a request error.

5. **Translation Functionality**:
   - **`translate_text(text, src_lang, dest_lang)`**: This function translates the input text from the source language to the destination language using the loaded translation model. 
     - If the source language is Persian (`fa`), it sets the source language to Persian and translates to English (`en`).
     - If the source language is English, it translates to Persian.
     - The translated text is printed and returned.

6. **Text-to-Speech**:
   - **`text_to_speech(text)`**: Converts the given text into speech using gTTS and plays it back. It saves the audio to a temporary file (`output.mp3`), plays it, and then deletes the file.
   - The function checks the language and processes the text accordingly for either English or Persian.

7. **Main Functionality**:
   - **`main()`**: This function orchestrates the overall flow:
     - It calls `speech_to_text()` to get user input.
     - If recognized, it translates the input text from Persian to English.
     - It then uses `text_to_speech()` to read the translated text aloud in English.
     - Additionally, it splits the original user input into words and reads each word aloud in Persian.

8. **Execution**:
   - The script runs the `main()` function when executed directly.

### Summary
In summary, this code creates a voice-activated translation application that listens to user speech in Persian, translates it to English, and then speaks the translated text. It also reads each word of the original input in Persian. The application leverages speech recognition, machine translation, and text-to-speech technologies to provide an interactive translation experience.
