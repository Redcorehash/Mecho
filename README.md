# Mecho
🌐[Websim Chat Bot](https://websim.ai/p/geycdn7jd9533ul49pmu/)
😊[Character AI Chat Bot](https://character.ai/chat/uFznJOl_Ocez0GZcSYAZaPrxcr5wWFcwKj5cD65baSs)
🤗[demo by space].(https://huggingface.co/spaces/Doubleupai/Mecho)
# Mecho - A Free Chatbot Experience

Welcome to Mecho, a site similar to ChatGPT but completely free! You can write whatever you want to the bot, and it will respond to you without any cost.

## How to Use Mecho

1. **Visit the Website**: Go to [Mecho](https://websim.ai/p/geycdn7jd9533ul49pmu/ or https://character.ai/chat/uFznJOl_Ocez0GZcSYAZaPrxcr5wWFcwKj5cD65baSs).
2. **Start Chatting**: Type your message in the chat box.
3. **Receive Responses**: The bot will reply to your queries instantly.

## Features

- **Free Access**: No subscription or payment required.
- **User-Friendly Interface**: Easy to navigate and use.
- **Instant Responses**: Get answers to your questions in real-time.

## Contact Us

For any inquiries, feel free to reach out to us at [support@mecho.com](mailto:support@mecho.com).

## codes
HTML 
# Mecho Chat in Hugging Face

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mecho Chat</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="chat-container">
        <h1>Mecho Chat</h1>
        <div id="messages"></div>
        <input type="text" id="user-input" placeholder="Type your message here...">
        <button id="send-button">Send</button>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/@huggingface/huggingface.js"></script>
    <script>
        const messagesDiv = document.getElementById('messages');
        const userInput = document.getElementById('user-input');
        const sendButton = document.getElementById('send-button');

        sendButton.addEventListener('click', async () => {
            const userMessage = userInput.value;
            messagesDiv.innerHTML += `<div class="user-message">${userMessage}</div>`;
            userInput.value = '';

            const response = await HuggingFace.chatbot(userMessage);
            messagesDiv.innerHTML += `<div class="bot-message">${response}</div>`;
        });
    </script>
</body>
</html>

gradio

# Mecho Chat with Gradio and Hugging Face

import gradio as gr
from transformers import pipeline

# Load the Hugging Face model
chatbot = pipeline("conversational", model="microsoft/DialoGPT-medium")

def respond_to_message(message):
    response = chatbot(message)
    return response.generated_responses[0]

# Create the Gradio interface
iface = gr.Interface(fn=respond_to_message, 
                     inputs="text", 
                     outputs="text", 
                     title="Mecho Chatbot", 
                     description="Chat with Mecho powered by Hugging Face")

# Launch the interface
iface.launch()
