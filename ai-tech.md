---
description: Text, image generation and big GPUs
---

# 🤖 AI Tech

I find AI is genuinely one of the most interesting fields in computing and technology in general right now. It feels like back in the early days of smartphones when every years there was a big jump with new capabilities added. So this page will hopefully keep being revised often. (May 2023)

## General

* [In defense of AI Art (YouTube)](https://www.youtube.com/watch?v=dXWAllbYzes)
* [Intelligence Explosion (YouTube)](https://www.youtube.com/watch?v=c9c5a4IsjOA)

## Image Generation & Manipulation

### Generation

* [Dall-E](https://openai.com/dall-e-2/): Cloud Service with API by OpenAI
* [Stable-Diffusion](https://stability.ai/blog/stable-diffusion-public-release): Open & free AI models for image generations made by Stability AI, can be used in the cloud e.g. via DreamStudio oder locally on a machine with a big GPU
  * [Simple Installer with Web UI for windows](https://github.com/EmpireMediaScience/A1111-Web-UI-Installer)
    * [Enable sharing/external access](https://www.reddit.com/r/StableDiffusion/comments/xtkovu/is\_there\_a\_way\_i\_can\_share\_my\_local\_automatic1111/)
  * [InvokeAI](https://github.com/invoke-ai/InvokeAI): Stable diffusion UI with lots of utility functions, alternative to automatic1111
  * [DiffusionBee](https://diffusionbee.com/): Very easy to use standalone app/UI for mac m1 stable diffusion.
  * [Civitai](https://civitai.com/): Share custom stable diffusion models
    * [Protogen x3.4](https://www.reddit.com/r/StableDiffusion/comments/100fmx6/comment/j2hglyx/?utm\_source=share\&utm\_medium=web2x\&context=3): Model for photorealistic images&#x20;
  * [Lexica.art](https://lexica.art/): Images and corresponding prompts for stable diffusion
  * [/r/StableDiffusion](https://www.reddit.com/r/StableDiffusion/): Subreddit about stable diffusion and other interesting AI topics
* [Midjourney](https://www.midjourney.com/home/?callbackUrl=%2Fapp%2F): AI Image generator using Discord as frontend. It's paid and a bit annoying to access via discord but it does output some really solid, high quality images. Imho better then Dall-E but not as versatile as Stable Diffusion. Although I haven't used Midjourney as much so I may be biased.

### Upscaling

* [Upscale.media](https://www.upscale.media/): Upscale and other image improvement algorithms. Can be used to upscale AI generation low resolution images.

### Image to Video Transformations

* [D-ID](https://www.d-id.com/speaking-portrait/): Animated faces of people with voice lines or slight head movements. Can be used to create short clips where a person is speaking some text. Mouth movements are synchronised to the spoken audio clip.

## Text Generation

### Conversational Interaction LLMS

* [Chat GPT](https://chat.openai.com/): The leader in conversational AIs. A free version is available but the more advanced model and additional features are a paid service. A lot of other AI products are based on this, respectively the same API that powers ChatGPT so it can be made to do a lot of things if you know how to prompt it right.
* [Google Bard](https://bard.google.com/): Free conversational LLM from Google. So far (as of May 2023) not available in Europe due to Google fearing EU laws. This can be circumvented by using a VPN to a US server but so far I don't find it better then ChatGPT therefor it's not worth the hassle of using a VPN.
* [Bing AI](https://www.bing.com/): Free conversational LLM based on GPT4. Works well and is based on the same advanced model that ChatGPT premium uses. However you can only access it in Edge currently (May 2023).
* [HeyPi](https://heypi.com/talk): Free conversational LLM by Inflection AI. Supposedly the model is trained in house by them and it is not using any of the other vendors LLM models. It feels very like chatGPT but if it is indeed based on their own original design this is very impressive.

### Experimental / local clients

* [KoboldAI-Client](https://github.com/KoboldAI/KoboldAI-Client): WebUI for text generation model, has a simple installer for windows and can self-download models such as GPT-J and others. Can be used for text-based adventures similar to aiDungeon, novel text generation or universal text generation as well as chat-based answers. Models are quite big, so a good GPU is needed.
  * [Google Colab installation of KoboldAI](https://colab.research.google.com/github/KoboldAI/KoboldAI-Client/blob/main/colab/TPU.ipynb)
* [FreedomGPT](https://freedomgpt.com/): Somewhat rightwing inspired LLM that can be run locally. I've tested it and it's impressive in the sense that it does indeed work locally and can talk/answer similar to ChatGPT. Afaik it's based on facebooks LAMA. Supposedly it has no filter (as compared to strongly filtered online LLMs) and therefor can give answers to even controversial topics.

### Roleplaying & Gaming

* [AI Dungeon](https://play.aidungeon.io/): Text based adventure generator. Similar to old school D\&D or early computer games.. with the slight difference that you're playing with an all-knowing AI that can respond to everything you throw at it. Contrary to serious LLMs like ChatGPT this does allow for nsfw/violence/nonethical things that would otherwise be filtered.
* [Novel AI](https://novelai.net/): Cooperative human & AI story writing generator

## Voice Generation & Cloning

* [ElevenLabs](https://beta.elevenlabs.io/voice-lab): Allows to easily create new voices or clone existing ones by submitting a few minutes of audio of a person speaking. Allows to easily clone voices of movie characters such as Severus Snape. I have tested this and even with poor quality audio and relatively low effort it works really well. Need some voice lines for a YouTube video, TikTok etc. but don't want to speak yourself? This is the tool to use.

