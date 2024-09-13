# Gemini-Unity-Package
> Currently, this plugin is only suported on versions of Unity 2021.x and above

# Installation

This plugin is provided as a custom Unity package that you can import into any existing project with the Unity version 2021.x and above.

Once you've downloaded the Unity package, you can import the package into your scene through the `Gemini_Manager_V2` prefab. 

---

# Setup

This plugin provides public functions to send a prompt, and receive a text reply from the Gemini API.

The focus here is to provide an alternative to ChatGPT.


### Step 1: Login to your Google account and copy your secret key
To get started you will first need to fetch your Google API key, which can be found in your Google AI Studio account under `Get API Key` (or through [this direct link](https://aistudio.google.com/app/apikey)). Here, you can create a new secret key and copy the value (you will need to your secret key for the next step).

![](/Images/ScreenShot4.JPG)

### Step 2: Open the Unity Editor, configure the package, and start using Gemini
Inside the package, you will find a `Gemini_Manager_2` prefab. Drag the prefab into your scene, and add your API Gemini Secret Key inside the `JSONTemplate.json`. We recommend doing that, so you can git ignore your JSON file when working with github. 

![](/Images/ScreenShot7.JPG)

In the component bar you will see a `JsonURL` option where you will attach the `JSONTemplate.json` text Asset. When starting, it will call the URL, and if you check the `Use Prompt`, you will receive an answer from the LLM at the beginning of the game.

![](/Images/ScreenShot8.JPG)


# Usage
When you enter a prompt and send it, Unity will send the prompt to the Gemini API, then it will receive the response, and make a `Debug.Log` of the reply.

> Note that each time you send a prompt, a new chat request is sent to Gemini API. 

