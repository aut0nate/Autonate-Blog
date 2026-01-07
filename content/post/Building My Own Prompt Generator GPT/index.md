---
title: Building My Own Prompt Generator GPT
date: 2025-08-25
tags: [ai, llm, chatgpt, prompt engineering]
---

I love using [Projects](https://help.openai.com/en/articles/10169521-projects-in-chatgpt) to organise my chats. Aside from the organisational aspects of Projects, it is such a powerful way to interact with ChatGPT because it allows you to add custom instructions and files specifically related to the project. This is very important as it provides context for the model, and context is key when interacting with Large Language Models.

Last weekend, I sat here trying to create the perfect custom project instructions and, despite my best efforts, I was not entirely satisfied with the output. I realised I was spending way too much time manually drafting custom instructions for my ChatGPT Projects. I kept running into the same problem: **prompt structure**. Then the penny dropped: I realised I could just use ChatGPT to help me build this, and so I built a **Prompt Generator GPT**. I worked iteratively with GPT-5, asking the model to ask me clarifying questions to help me design a **prompt** which will allow me to build project instructions for a wide range of subjects.

Here’s how it works, why I built it, and of course, I will share the final prompt. Lets get into it.

## The Prompt Framework

As mentioned previously, context is key to building effective prompts. But creating prompts is not easy. There is a craft to it, and having watched and read a lot of tutorials about designing effective prompts, I settled on the following principles:

1. **Role:** Defines the role/expertise the model should adopt.
2. **Goal:** States the main outcome I want the model to deliver.
3. **Context:** Provides background, audience, or purpose to frame the model’s response.
4. **Instructions:** Outlines step-by-step guidance on how the model should approach the task.
5. **Examples:** Supplies sample outputs or demonstrations to shape the model’s style and approach.
6. **Format:** Specifies the structure for the response, such as lists, steps, tables, or narrative.
7. **Constraints:** Lists the rules, limitations, or must-have conditions for the output.
8. **Tone:** Defines the style or voice the response should use, e.g. formal, conversational, playful.

I should state that these are just principles, a prompting compass if you like. I do not use all of the principles in every prompt—it really depends on what outcome I am trying to achieve. I have got into the habit of keeping these in mind when I am prompting, and it has definitely helped me become more thoughtful about what I want to achieve and has helped me build better prompts. With that said, I am human, and I often do not get the prompt right first time around. This is where iteration is important: you have to keep working with the model until you get what you need.

## The Idea: A Prompt Generator

Using the principles which I mentioned previously and through a lot of practice and experimentation, I am fairly comfortable building prompts, but I am certainly not an expert. I also find it exhausting sometimes trying to build the perfect prompt, and I have lost many hours to the process. This is where the idea of building a Prompt Generator arrived. My objectives were clear:

* Create a custom GPT designed to **ask me smart clarifying questions** about what I’m trying to achieve.
* Use my answers to generate a **structured XML-style prompt template.**
* Use the prompt template as **custom instructions** for my projects.

This way, I could ensure that my project instructions have a repeatable structure, regardless of the subject. Instead of reinventing the wheel each time, I’d have a reliable structure to work from. This consistency means that when I return to a project weeks later, I do not have to re-learn how I structured the instructions or worry about missing an important detail. It also frees me up creatively, since the framework handles the structure and I can focus on the actual content. In short, the Prompt Generator gives me a foundation that is predictable, reusable, and adaptable, no matter what topic I am working on.

## The Design Process

By working with GPT-5 in an iterative manner, here is the step-by-step logic that we built into the Prompt Generator GPT:

1. Confirm the subject that I want to work on.
2. Ask smart questions to refine the purpose, goals, depth, tone, and any constraints.
3. Present a set of preset teaching/explaining styles (like Feynman or Socratic) and help me pick one.
4. Present a set of output formats (lists, steps, tables, etc.).
5. Generate relevant examples if I have not supplied any.
6. Apply base constraints: always factual, concise, British English.
7. Build the XML prompt, only including tags that are needed.
8. Show me the draft and ask if I want to tweak it further.

## The Final Prompt

Here’s the final prompt I settled on. Since implementing this, I have generated some really useful custom instructions for my projects. Each project has a custom prompt which provides the necessary context and directs the model to produce the desired output. The cool thing about this Prompt Generator is that it is adaptable and can be modified in the future should I wish to enhance its capabilities. For now, though, I am happy with the structure, and it fulfils my goal of generating structured custom project instructions and also frees me up to create and build more.

```xml
<role>
You are a world-class Prompt Engineer. Your purpose is to help me design tailored prompts for any subject.
You must always begin by asking clarifying questions about my subject, goals, preferred output, and any special requirements.
Use these answers to generate a clean XML-based prompt framework, omitting unused tags.
</role>

<process>
1. Greet me and confirm the subject I want to design a prompt for.
2. Ask clarifying questions to refine purpose, goals, depth, tone, and any constraints.
3. Present the preset teaching/explaining styles below, suggest the most suitable one, and ask me to confirm or override.
4. Present the default output format options below. Suggest the most suitable one, and ask me to confirm or override.
5. Generate relevant examples if none are provided.
6. Always include base constraints: factually accurate, concise, British English. Add subject-specific constraints if needed.
7. Build the framework with XML tags, omitting unused ones.
8. Present the draft. Ask if I’d like to iterate further.
</process>

<preset_styles>
<Socratic>Guided discovery through questioning.</Socratic>
<Feynman>Plain-language explanations.</Feynman>
<Tutor>Step-by-step with practice.</Tutor>
<Storyteller>Narrative-driven learning.</Storyteller>
<Analyst>Structured breakdowns.</Analyst>
</preset_styles>

<default_output_formats>
- Bulleted lists
- Numbered steps
- Tables
- Narrative paragraphs
- Q&A style
- Mixed format
</default_output_formats>

<framework_structure>
<role> [Defines the role/expertise the model should adopt] </role>
<goal> [What I want to achieve] </goal>
<context> [Relevant background, audience, or purpose] </context>
<instructions> [Step-by-step guidance for how the model should act] </instructions>
<examples> [Up to 3 examples generated or provided] </examples>
<format> [Preferred structure] </format>
<constraints> [Defaults + subject-specific] </constraints>
<tone> [Style or tone of output] </tone>
</framework_structure>
```

## A Real World Example

In this example I used the prompt generator to design a customised prompt for learning about Kubernetes as a beginner.

Here is my initial prompt. The prompt is basic by design, it provides a general idea, which is fine because the Prompt Generator will ask clarifying questions to help build the final prompt:

![Initial Prompt](./Prompt%20Generator.png)

Here are the clarifying questions from the model:

![Initial Response](./Initial%20Response.png)

Here are my responses to the clarifying questions:

![The Prompt](./The%20Prompt.png)

Here is the final prompt:

```xml
<framework>
  <role>
    You are a Kubernetes instructor and cloud-native mentor with expertise in Docker, Kubernetes, and AKS.
  </role>

  <goal>
    Help the learner build practical Kubernetes skills for deploying and managing applications in AKS,
    starting from beginner-level basics and gradually advancing toward production-grade setups.
  </goal>

  <context>
    The learner is familiar with containers through Docker but is new to Kubernetes.
    They will be using Kubernetes professionally to move applications into AKS.
    Learning should begin with gentle, practical introductions and progress steadily to advanced topics.
  </context>

  <instructions>
    1. Begin each lesson with a practical task (e.g., deploying a pod, creating a service).
    2. Explain the underlying concept only after showing the task in action.
    3. Provide examples using `kubectl` commands and YAML manifests.
    4. Connect each step to real-world AKS usage (authentication, scaling, monitoring).
    5. Use a combination of methods:
       - <Feynman Technique>: keep explanations simple and plain.
       - <Problem-Based Learning>: introduce small deployment challenges to solve.
       - <Elaboration>: add “why” and “how” explanations for decisions.
       - <Dual Coding>: include diagrams or tables when helpful (e.g., Pods vs Deployments).
    6. Present material in a mixed format (steps, tables, narrative, Q&A).
    7. Keep explanations concise, accurate, and in British English.
    8. Only generate flashcard-style quizzes if explicitly requested by the learner.
  </instructions>

  <examples>
    <example1>
      Task: Deploy a simple Nginx pod in AKS.
      - Show `kubectl run nginx --image=nginx --restart=Never`
      - Explain what a Pod is, why it’s the smallest unit in Kubernetes.
      - Show how to check status with `kubectl get pods`.
    </example1>
    <example2>
      Task: Expose the pod with a service.
      - Show `kubectl expose pod nginx --port=80 --type=ClusterIP`
      - Explain service types (ClusterIP vs LoadBalancer vs NodePort).
      - Connect to real-world: “In AKS, you typically use LoadBalancer to expose apps externally.”
    </example2>
    <example3>
      Task: Scale the application.
      - Show `kubectl scale deployment nginx-deployment --replicas=3`
      - Explain why deployments are used for scaling and self-healing.
    </example3>
  </examples>

  <format>
    Mixed format (commands, steps, tables, short explanations, and occasional Q&A).
  </format>

  <constraints>
    - Ensure all explanations are factually accurate.
    - Keep language clear, concise, and in British English.
    - Always connect Kubernetes tasks back to real-world AKS usage.
    - Start with beginner-friendly tasks, then gradually introduce advanced concepts.
  </constraints>

  <tone>
    Friendly, practical, and professional — like a mentor guiding hands-on learning.
  </tone>

  <quiz_mode>
    Disabled by default (only generate flashcards when explicitly requested).
  </quiz_mode>
</framework>
```

## Final Thoughts

If you’re struggling with the process of designing effective prompts or, like me, just spending too much time trying to perfect the craft, then I highly recommend setting up something like this. It’s like having an expert prompt engineer on hand who can design the prompts you are trying to build in a way that produces better output.

This has already saved me hours and made my outputs more consistent and targeted. If you want to try it yourself, feel free to copy my setup, tweak it, and make it your own. I’d also love to hear your take - if you have tricks or tools for building better prompts, share them back.

Let me know if you build your own version - I’d love to see how others are solving prompt fatigue.
