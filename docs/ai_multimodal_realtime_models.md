# 🧠 Realtime Models & Multimodal Models

## OpenAI
LLMs can process audio by using sound as input, creating sound as output, or both. OpenAI has several API endpoints that help you build audio applications or voice agents.
Voice agents understand audio to handle tasks and respond back in natural language. There are two main ways to approach voice agents: either with speech-to-speech models and the Realtime API, or by chaining together a speech-to-text model, a text language model to process the request, and a text-to-speech model to respond. Speech-to-speech is lower latency and more natural, but chaining together a voice agent is a reliable way to extend a text-based agent into a voice agent. If you are already using the Agents SDK, you can extend your existing agents with voice capabilities using the chained approach.

Models such as GPT-4o or GPT-4o mini are natively multimodal, meaning they can understand and generate multiple modalities as input and output.
If you already have a text-based LLM application with the Chat Completions endpoint, you may want to add audio capabilities

If you need real-time interactions or transcription, use the Realtime API.
If realtime is not a requirement but you're looking to build a voice agent or an audio-based application that requires features such as function calling, use the Chat Completions API.
For use cases with one specific purpose, use the Transcription, Translation, or Speech APIs.

https://platform.openai.com/docs/guides/audio
https://platform.openai.com/docs/guides/realtime

## Google
### Live API
- [Live API in Google AI Studio.](https://aistudio.google.com/live) The Live API enables low-latency, two-way voice and video interactions with Gemini.Use the Live API to provide end users with natural, human-like voice conversations, including the ability to interrupt the model's responses with voice commands.The Live API is supported for use in both the Google Gen AI SDK and using Vertex AI Studio. Some features (like text input and output) are only available using the Gen AI SDK.
    - gemini-live-2.5-flash	Private GA*
    - gemini-live-2.5-flash-preview-native-audio-09-2025	Public preview
    - gemini-live-2.5-flash-preview-native-audio	Public preview; Discontinuation date: October 18, 2025

    - [How to use WebSockets with the Live API](https://colab.research.google.com/github/GoogleCloudPlatform/generative-ai/blob/main/gemini/multimodal-live-api/intro_multimodal_live_api.ipynb)
    - [How to use the Live API in a streaming audio and video format](https://colab.research.google.com/github/GoogleCloudPlatform/generative-ai/blob/main/gemini/multimodal-live-api/intro_multimodal_live_api_genai_sdk.ipynb)
    - https://google.github.io/adk-docs/streaming/custom-streaming/
 
### Multimodal 
- [Gemini 2.5 Multimodal Livel API](https://ai.google.dev/gemini-api/docs/models)
  - Gemini 2.5 Pro : Capable of reasoning over complex problems in code, math, and STEM
  - Gemini 2.5 Flash: Best model in terms of price-performance, offering well-rounded capabilities. 2.5 Flash is best for large scale processing, low-latency, high volume tasks that require thinking, and agentic use cases.
  - Gemini 2.5 Flash-Lite:Our fastest flash model optimized for cost-efficiency and high throughput.
- [Image](https://ai.google.dev/gemini-api/docs/imagen): High-fidelity image generation model, capable of generating realistic and high quality images from text prompts
- [Video](https://ai.google.dev/gemini-api/docs/video?example=dialogue) : State-of-the-art model for generating high-fidelity, 8-second 720p or 1080p videos from a text prompt,
- [Lyria RealTime](https://ai.google.dev/gemini-api/docs/music-generation): The Gemini API, using Lyria RealTime, provides access to a state-of-the-art, real-time, streaming music generation model
- [Gemini Robotics-ER 1.5](https://ai.google.dev/gemini-api/docs/robotics-overview): Gemini Robotics-ER 1.5 is a vision-language model (VLM) that brings Gemini's agentic capabilities to robotics.
- [Flow TV](https://labs.google/flow/tv/channel/off-season-santa/P1FR1GSn1mDHpCwAGqGp?random=true)
- [Cookbook](https://github.com/google-gemini/cookbook)
- https://github.com/googleapis/python-genai

## AWS 
- [bedrock](https://aws.amazon.com/es/bedrock/)
- [nova sonic](https://aws.amazon.com/es/ai/generative-ai/nova/speech/)

## Meta
- [Audiocraft](https://github.com/facebookresearch/audiocraft) At the moment, AudioCraft contains the training code and inference code for:
    - MusicGen: A state-of-the-art controllable text-to-music model.
    - AudioGen: A state-of-the-art text-to-sound model.
    - EnCodec: A state-of-the-art high fidelity neural audio codec.
    - Multi Band Diffusion: An EnCodec compatible decoder using diffusion.
    - MAGNeT: A state-of-the-art non-autoregressive model for text-to-music and text-to-sound.
    - AudioSeal: A state-of-the-art audio watermarking.
    - MusicGen Style: A state-of-the-art text-and-style-to-music model.
    - JASCO: "High quality text-to-music model conditioned on chords, melodies and drum tracks"
- [llama](https://ai.meta.com/)
    - [Llama 4](https://www.llama.com/models/llama-4/)
    - [Llama 3](https://www.llama.com/models/llama-3/)
    - [Llama API](https://www.llama.com/products/llama-api/)
