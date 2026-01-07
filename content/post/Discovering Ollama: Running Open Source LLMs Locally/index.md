---
title: "Discovering Ollama: Running Open Source LLMs Locally"
date: 2024-02-25
tags: [ai, llm]
---

I recently discovered **Ollama** ([ollama.com](https://ollama.com/)), a platform that allows you to run open-source Large Language Models (LLMs) directly on your local machine. As someone with an M1 Pro MacBook Pro, I was intrigued by the idea of leveraging my hardware to run advanced AI models privately. After exploring Ollama and experimenting with open-source models like **Llama**, **Mistral**, and **Phi**, I’ve been amazed at the speed and quality these models deliver—especially considering they’re running locally.

## Why Run LLMs Locally?

Running LLMs locally comes with several benefits, but privacy is the standout advantage. When you use cloud-based AI models, your queries and data are processed on remote servers, raising concerns about data security and privacy. With locally hosted models, everything stays on your device, giving you full control over your inputs and outputs.

Another reason for the growing interest in local LLMs is the **open-source movement**. The community’s drive to democratise AI ensures that powerful tools aren’t locked behind paywalls or controlled by a handful of corporations. Instead, they’re accessible to developers, researchers, and enthusiasts worldwide, encouraging innovation and collaboration.

## Hardware Requirements for Running Local LLMs

Running LLMs locally at an acceptable speed will require high-performing GPUs and plenty of RAM to function efficiently. Here’s what you will need to consider:

- **Model Parameters**: A model’s parameters are essentially its "weights"—the values it learns during training. Larger models have more parameters, enabling them to handle complex tasks but requiring more computational resources. For example, a 7-billion-parameter model might run smoothly on a modern laptop, while a 65-billion-parameter model would demand a high-end GPU and significant memory.
- **Hardware**: While smaller models can run on devices like my M1 Pro MacBook Pro, larger ones need GPUs with high VRAM (e.g., NVIDIA RTX 3090 or better) and sufficient system RAM to store and process the model data efficiently.

For those with the right hardware, the performance of these models can be incredible, and they are often optimised to maximise efficiency on consumer devices.

## The Hugging Face Community

I also discovered the [Hugging Face community](https://huggingface.co/) and found that they play a huge part in the open-source AI revolution. It’s a hub where developers collaborate on models, datasets, and tools to advance open-source AI. The Hugging Face community has made it easier than ever to discover, fine-tune, and deploy models for various use cases.

From chatbots to image generation, Hugging Face has become a playground for experimentation and innovation. It’s exciting to see how people are collaborating globally to create powerful models that rival proprietary ones—and all while sharing their advancements openly for the benefit of everyone.

## My Experience with Llama, Mistral, and Phi

I’ve been experimenting with **Llama**, **Mistral**, and **Phi** models on my MacBook Pro, and the results have been impressive. The **speed** at which these models perform locally is remarkable, and while they aren’t quite on par with ChatGPT for general-purpose conversations, they excel in specific use cases.

For example:

- **Llama**: A versatile model that handles a wide range of tasks well.
- **Mistral**: Particularly fast and efficient, making it a great choice for devices with limited resources.
- **Phi**: Another lightweight option with surprisingly robust capabilities.

It’s truly amazing how quickly the open-source community is iterating on these models, making them small and efficient enough to run locally without sacrificing too much performance.

## Why Ollama Stands Out

Setting up these models locally might sound daunting, but **Ollama** makes it incredibly easy. The platform provides clear instructions for getting started, and the installation process is smooth and straightforward. Within minutes, I was up and running, testing different models and pushing the limits of my MacBook Pro.

## Final Thoughts

The AI landscape is evolving at a staggering pace, and the open-source movement is a huge part of this revolution. Platforms like Hugging Face and tools like Ollama are empowering individuals to explore the possibilities of AI on their own terms, without relying on cloud services.

Running LLMs locally is a glimpse into the future of AI—a future where privacy, accessibility, and community-driven innovation take centre stage. If you’re curious about exploring this space, I highly recommend checking out [Ollama](https://ollama.com/) and diving into the world of open-source LLMs.
