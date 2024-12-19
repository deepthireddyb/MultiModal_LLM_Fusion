# MultiModal_LLM_Fusion
This project is an AI-powered conversational assistant that can understand and respond to user queries through text, audio, and images. It leverages advanced technologies like Large Language Models (LLMs), speech recognition, and optical character recognition (OCR) to provide a versatile and interactive user experience.



## Core Functionalities

1.  **Speech-to-Text:**
    *   **Description:** The application can transcribe spoken words from audio input into text.
    *   **Technology:** It uses speech recognition models, including `whisper-1` and `openai/whisper-base.en`, to convert audio into text.
    *   **How it Works:**
        *   The user provides audio input, either through a microphone.
        *   The selected speech recognition model (chosen by the user) processes the audio.
        *   The system transcribes the audio into text.
    *   **User Interaction:** The user can choose between different speech recognition models and record or upload audio. The transcribed text appears in a designated text box.

2.  **Image-to-Text:**
    *   **Description:** The application can read text from images and convert it into editable text.
    *   **Technology:** It utilizes Optical Character Recognition (OCR) through the `easyocr` library.
    *   **How it Works:**
        *   The user uploads an image.
        *   The OCR engine scans the image for text.
        *   The system extracts and displays the detected text.
    *   **User Interaction:** The user uploads an image, and the extracted text is shown in a separate text box.

3.  **AI Conversation (Q\&A):**
    *   **Description:** The application can engage in conversational interactions with users, answering questions and providing context-aware responses.
    *   **Technology:** It integrates various Large Language Models (LLMs) such as `gpt-4o-mini`, `gpt-3.5-turbo`, and `Llama-3.1-Nemotron-70B-Instruct-HF`.
    *   **How it Works:**
        *   The user provides a text prompt (question or statement).
        *   The selected LLM (chosen by the user) processes the input along with the conversation history.
        *   The LLM generates a relevant and context-aware response.
    *   **User Interaction:**
        *   The user selects an LLM from the available options.
        *   The user types a question or prompt.
        *   The AI's response is displayed in a designated text box.

4. **Memory Management:**
    * **Description** It stores the conversation for a more coherent interaction.
    * **How it Works:**
        * The memory stores the conversation history.
        * User can also clear the chat memory.
        * User can view the conversation history.

5.  **Combined Input Processing:**
    *   **Description:** The AI assistant can combine information from audio transcriptions, image extractions, and user prompts to generate responses.
    *   **How it Works:**
        *   The system takes text from either transcription or extraction, and combine with user prompt.
        *   The combined text is then processed by the chosen LLM.
    *   **User Interaction:** Users can use the system to ask question related to image and audio transcriptions.

## Technical Components

1.  **Large Language Models (LLMs):**
    *   `gpt-4o-mini`: A powerful LLM known for its conversational abilities.
    *   `gpt-3.5-turbo`: A well-rounded LLM, capable of handling a variety of tasks.
    *   `Llama-3.1-Nemotron-70B-Instruct-HF`: A specific variant of the Llama model, known for its strong performance.

2.  **Speech Recognition Models:**
    *   `whisper-1`: A cutting-edge speech recognition model.
    *   `openai/whisper-base.en`: Another speech recognition model.

3.  **Optical Character Recognition (OCR):**
    *   `easyocr`: A library used to extract text from images.

4.  **User Interface (UI):**
    *   `gradio`: A library that makes it easy to create user-friendly interfaces for machine learning models.

5. **Libraries**
    *   `os`: For operating system related operations.
    *   `pickle`: For serializing and deserializing Python objects.
    *   `numpy`: For numerical operations.
    *   `pandas`: For data manipulation and analysis.
    *   `getpass`: For secure password input.
    *   `openai`: For interfacing with OpenAI's APIs.
    *   `langchain`: For building applications with LLMs.
    *   `transformers`: For pre-trained machine learning models.
    *  `google.colab.userdata`: For managing user credentials.

## Setup and Usage

1.  **Installation:**
    *   The code installs the necessary libraries using `pip`.
    *   `!pip -q install ...`: Installs the listed packages without showing verbose output.
    *   The code will be installed while running in Google Colab.
2. **Credentials:**
    *  The code will fetch the credentials for OpenAI from the user data section in Google Colab
3.  **Running the Application:**
    *   The code uses `gradio` to create a web-based user interface.
    *   `demo.launch()`: This line starts the web application, making it accessible through a URL that will be generated when you run the code.
4. **User Interraction**
    * User can use different components, like audio input, image input, prompt box, and response boxes to communicate with the project.
    * User can also select different models, and submit the input.
    * User can also view history and clear memory.

## Key Interactions

*   **Transcription:** Click "Generate Transcription" to convert audio input to text.
*   **Image Extraction:** Upload an image, click "Preview" to see the image, and click "Extract Text from Image" to extract text.
*   **AI Interaction:**
    *   Select an LLM from the "Choose Q\&A LLM" radio buttons.
    *   Type your prompt in the "Enter your prompt" text box.
    *   Click "Generate Response" to get the AI's answer.
*   **Memory:**
    * Click "Clear Memory" to clear all the conversation history.
    * Click "Show Conversation" to view all the stored conversation.

## Testing

*   The code includes a small testing section at the end.
*   `InvokeLLM("gpt-3.5-turbo", "what is the capital of Singapore?")`: Tests the LLM's ability to answer a simple question.
*   `InvokeLLM("gpt-3.5-turbo", "where is India?")`: Tests the LLM's ability to answer another question.
*   `get_conversation_history()`: Shows the conversation log.

## Additional Notes

*   **Error Handling:** The `transcribe` function includes basic error handling to catch and report transcription errors.
*   **Model Selection:** Users can choose between different models for speech recognition and conversational AI, allowing for flexibility and experimentation.
*   **Clear Memory:** The "Clear Memory" button clears the conversation history.
*   **Show history:** The "Show Conversation" button show the history of chat.
*   **Combined Response** The code combines the response of the transcription or extracted text along with the user query to generate a more coherent response.
