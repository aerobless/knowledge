---
description: Text, image generation and big GPUs
---

# 🤖 AI Tech

I find AI is genuinely one of the most interesting fields in computing and technology in general right now. It feels like back in the early days of smartphones when every years there was a big jump with new capabilities added. So this page will hopefully keep being revised often. (May 2023)

## General

* [In defense of AI Art (YouTube)](https://www.youtube.com/watch?v=dXWAllbYzes)
* [Intelligence Explosion (YouTube)](https://www.youtube.com/watch?v=c9c5a4IsjOA)

## Image Generation & Manipulation

* [Clipdrop.co](https://clipdrop.co/): Various Generation, Manipulation & Editing Tools by Stability AI (creators of Stable Diffusion). Includes uncrop, face swap, upscale, replace background, and more.
* [Dall-E](https://openai.com/dall-e-3): Cloud Service with API by OpenAI
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
* [Upscale.media](https://www.upscale.media/): Upscale and other image improvement algorithms. Can be used to upscale AI generation low resolution images.
* [Leiapix.com](https://www.leiapix.com/): Turn 2D images to 3D animations via AI generated depth maps.

## Video Generation

### Generation

* [Pika.art](https://pika.art/): Generate video clips based on prompts and/or source material. Source material may consist of existing video clips or images.

### Image to Video Transformations

* [D-ID](https://www.d-id.com/speaking-portrait/): Animated faces of people with voice lines or slight head movements. Can be used to create short clips where a person is speaking some text. Mouth movements are synchronised to the spoken audio clip.

## Text Generation

### Conversational Interaction LLMS

* [Chat GPT](https://chat.openai.com/): The leader in conversational AIs. A free version is available but the more advanced model and additional features are a paid service. A lot of other AI products are based on this, respectively the same API that powers ChatGPT so it can be made to do a lot of things if you know how to prompt it right.
* [Google Bard](https://bard.google.com/): Free conversational LLM from Google. So far (as of May 2023) not available in Europe due to Google fearing EU laws. This can be circumvented by using a VPN to a US server but so far I don't find it better then ChatGPT therefor it's not worth the hassle of using a VPN.
* [Bing AI](https://www.bing.com/): Free conversational LLM based on GPT4. Works well and is based on the same advanced model that ChatGPT premium uses. However you can only access it in Edge currently (May 2023).
* [HeyPi](https://heypi.com/talk): Free conversational LLM by Inflection AI. Supposedly the model is trained in house by them and it is not using any of the other vendors LLM models. It feels very like chatGPT but if it is indeed based on their own original design this is very impressive.
* [Mixtral](https://neets.ai/chat/mixtral): Mistral based LLM. Free to use without sign-up. Responses are less moderated than with ChatGPT. Mistral can also be run locally.

### Programming Assistant / AI Pair Programming

* [GitHub Copilot](https://github.com/features/copilot): Can be used as plugin in common IDEs, such as IntelliJ, Visual Studio Code etc. The broadly available version (June 2023) provides mainly helpful suggestions and advanced autocomplete funcationality while coding. Copilot X (currently in BETA) will also be able to do refactoring and have a chat prompt to answer questions.&#x20;
  * Current features & how to use them:
    * Start typing code & autocomplete. Can be only a single line or a whole method block or even class.
    * Ask questions via comments. Type //q: Your question? and you will get a autocomplete with //a: answer on the next line.
    * Create unit tests via comments. Type // Create unit tests for x-y
    * Get multiple solutions for a problem. Hover over suggestions and click on the "3 dots -> Copilot" to open a window with up to 10 solutions.
* [OpenDevin](https://github.com/OpenDevin/OpenDevin): Autonomous agent that can use a variety of models as backend. Give it a task and it attempts to break it down into smaller pieces. It can then try to implement this smaller pieces on it's own directly writing code and using a shell to install dependencies.

### Experimental / local clients

* [KoboldAI-Client](https://github.com/KoboldAI/KoboldAI-Client): WebUI for text generation model, has a simple installer for windows and can self-download models such as GPT-J and others. Can be used for text-based adventures similar to aiDungeon, novel text generation or universal text generation as well as chat-based answers. Models are quite big, so a good GPU is needed.
  * [Google Colab installation of KoboldAI](https://colab.research.google.com/github/KoboldAI/KoboldAI-Client/blob/main/colab/TPU.ipynb)
* [FreedomGPT](https://freedomgpt.com/): Somewhat rightwing inspired LLM that can be run locally. I've tested it and it's impressive in the sense that it does indeed work locally and can talk/answer similar to ChatGPT. Afaik it's based on facebooks LAMA. Supposedly it has no filter (as compared to strongly filtered online LLMs) and therefor can give answers to even controversial topics.

### Roleplaying & Gaming

* [AI Dungeon](https://play.aidungeon.io/): Text based adventure generator. Similar to old school D\&D or early computer games.. with the slight difference that you're playing with an all-knowing AI that can respond to everything you throw at it. Contrary to serious LLMs like ChatGPT this does allow for nsfw/violence/nonethical things that would otherwise be filtered.
* [Novel AI](https://novelai.net/): Cooperative human & AI story writing generator

### User Moderation & Censorship

* Heavenbanning: The practise of banishing a user form a platform by replacing everyone they speak to with LLM responses. The banned users content/comments are only shown to themselves. Responses to the questionable content are generated by an LLM instructed to praise the user and agree with their remarks. This is similar to the concept of shadowbanning with the added benefit of keeping the segregated user engaged. The engagement of the segregated user can be advantageous in order to keep them busy and prevent them from making a new profile. And depending on the monetisation strategy of the platform the user may continue to consume ads and/or paid services.
  * [example usage in Dating app filteroff](https://medium.com/@beweinreich/we-flooded-our-dating-app-with-bots-to-scam-scammers-dc84c3f5c89a)
  * This is a dark pattern when used on platforms where free speech is paramount - such as X or facebook. On platforms such as these, it is more appropriate to outright ban a bad user rather than shadow- or heavenban them.
    * [HN: Is AI for online segregation ethical?](https://news.ycombinator.com/item?id=33307725)

## Voice Generation & Cloning

* [ElevenLabs](https://beta.elevenlabs.io/voice-lab): Allows to easily create new voices or clone existing ones by submitting a few minutes of audio of a person speaking. Allows to easily clone voices of movie characters such as Severus Snape. I have tested this and even with poor quality audio and relatively low effort it works really well. Need some voice lines for a YouTube video, TikTok etc. but don't want to speak yourself? This is the tool to use.

## Music Generation

* [Suno.ai](https://app.suno.ai/create/): LLM based music generation. Can be prompted similar to image generators with lyrics and a music style. Generates high quality output in multiple languages. \[[Impressive example](https://app.suno.ai/song/a4c6bb70-3616-4658-89b8-8bcc1a58b199/)]

## News & Search

* [Preplexity.AI](https://www.perplexity.ai/discover): Perplexity AI is a AI search engine offering usage of a variety of commercial models (Open AI, Opus, etc.) to search for things and the summarise the results. They also have a free but very good news aggregation sections ([https://www.perplexity.ai/discover](https://www.perplexity.ai/discover)).
