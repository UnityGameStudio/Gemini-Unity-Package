# Gemini-Unity-Package
> Currently, this plugin is only suported on versions of Unity 2021.x and above

# Installation

This plugin is provided as a custom Unity package that you can import into any existing project with the Unity version 2021.x and above.

Once you've downloaded the Unity package, you can them import it into your project through the `Gemini_Manager` prefab. 

---

# Setup

This plugin provides public functions to send a prompt, and receive a text reply from the Gemini API.

The focus here is to provide an alternative to ChatGPT.


### Step 1: Login to your Google account and copy your secret key
To get started you will first need to fetch your Google API key, which can be found in your Google AI Studio account under `Get API Key` (or through [this direct link](https://aistudio.google.com/app/apikey)). Here, you can create a new secret key and copy the value (you will need to your secret key for the next step).

![](/Images/ScreenShot4.JPG)

### Step 2: Go to Google Scripts
The script will run through Google Script - (or through [this direct link](https://www.google.com/script/start/)). Therefore, you need to create a new project. Inside the script, paste the content from `GoogleScriptGeminiAPI.txt`, and replace the `Key` with your secret key in the `API Key` field. Once this is done, you can safely create a new `Deploy` as a web app with access for anyone. Now, you will get a Google Script URL for calling the script. 

![](/Images/ScreenShot1.JPG)
![](/Images/ScreenShot2.JPG)
![](/Images/ScreenShot3.JPG)


### Step 3: Open the Unity, configure it and start using
Inside the package, you will find a `Gemini_Manager` prefab. Drag the prefab into your scene, and add your Google Script URL inside the `JSONTemplate.json`. We recommend doing that, so you can git ignore your JSON file when working with github. 

![](/Images/ScreenShot6.JPG)

In the component bar you will see a `JsonURL` option where you will attach the `JSONTemplate.json` text Asset. When starting, it will call the URL, and if you check the `Use Prompt`, you will receive an answer from the LLM at the beginning of the game.

![](/Images/ScreenShot5.JPG)


# Usage
When you enter a prompt and send it, Unity will send the prompt to the Google Script, then it will receive the response, and make a `Debug.Log` of the reply.

> Note that each time you send a prompt, a new chat request is sent to Gemini API. 

