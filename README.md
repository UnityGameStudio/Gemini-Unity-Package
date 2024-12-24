# Gemini-Unity-Package
> Currently, this plugin is only suported on versions of Unity 2021.x and above

# Installation

This plugin is provided as a custom Unity package that you can import into any existing project with the Unity version 2021.x and above.

Once you've downloaded the Unity package, you can import the package into your scene through the `Gemini_Manager_V3` prefab. 

---

# Setup

Gemini provides an alternative to ChatGPT for Unity developers. Here's a quick guide to setting up the latest release (V3) and previous release (V2):

- **V3 Setup Guide (Latest Release)**: [Watch the YouTube tutorial](https://www.youtube.com/watch?v=J-6bymbjT_M&ab_channel=UnityGameStudio)
- **V2 Setup Guide (Previous Release)**: [Watch the YouTube tutorial](https://www.youtube.com/watch?v=Z6MFqIzOHK0&ab_channel=UnityGameStudio)


### Step 1: Login to your Google account and copy your secret key
To get started you will first need to fetch your Google API key, which can be found in your Google AI Studio account under `Get API Key` (or through [this direct link](https://aistudio.google.com/app/apikey)). Here, you can create a new secret key and copy the value (you will need to your secret key for the next step).

![](/Images/ScreenShot4.JPG)

### Step 2: Open the Unity Editor, configure the package, and start using Gemini
Inside the package, you will find a `GeminiManager` prefab. Drag the prefab into your scene, and add your API Gemini Secret Key inside the `JSONTemplate.json`. We recommend doing that, so you can git ignore your JSON file when working with github. 

![](/Images/Chatbot.JPG)

In the component bar you will see a `JsonApi` option where you will attach the `JSONTemplate.json` text Asset. When starting the script, it will set your API_Key, and send your `prompt`, then you will receive an answer from the LLM at the beginning of the scene.

![](/Images/ScreenShot8.JPG)


# Functions

This plugin provides two public functions. One function to send a prompt, and receive a text reply from the Gemini API. And another function to send a chat history, and receive a reply from the Gemini API based on the chat. 

Prompt Function: 

The script contains an IEnumerator function that sends your prompt to the Gemini API and prints the response to the console by calling Debug.Log().

`private IEnumerator SendPromptRequestToGemini(string promptText)`

Chatbot Function:

The script contains an IEnumerator function that stores the user and Gemini responses, then sends the chat history to the Gemini API and prints the response to the console by calling Debug.Log().
There is a sample scene called `Chatbot` in the `Example` folder.  

`private IEnumerator SendChatRequestToGemini(string newMessage)`

![](/Images/ChatbotScene.JPG)




# Usage
The unity package was made to directly use the prompt function. When you enter a prompt and send it (click on play), Unity will send the prompt to the Gemini API, then it will receive the response, and make a `Debug.Log` of the reply.

> Note that each time you send a prompt, a new chat request is sent to Gemini API. If you want to keep a chat history, I recommend using the `SendChatRequestToGemini(string newMessage)` function instead.

