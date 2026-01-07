---
title: "Getting Started with GPTs: How I Built a Custom Assistant to Learn Linux"
date: 2024-06-24
tags: [ai, llm, chatgpt, linux]
---

At the end of 2023 OpenAI introduced [GPTs](https://openai.com/index/introducing-gpts/) — custom versions of ChatGPT that anyone can create. These tailored assistants are designed to perform specific tasks, help with workflows, or simply provide a more personalised experience. In this post, I’ll explain what GPTs are, why they’re so useful, and how I created a custom GPT to help me learn Linux commands.

## What Are GPTs?

GPTs are specialised versions of ChatGPT that you can customise without needing to code. You can:

- Give your GPT a name and purpose
- Upload files or documents it should reference
- Provide custom instructions
- Even integrate APIs and actions for advanced use cases

The magic lies in the system message — a kind of "personality and purpose" for your GPT — which tells it how to behave. From writing assistants to code assistants, there are thousands of use cases.

## Why GPTs Are Useful

GPTs are ideal for:

- **Automating repetitive tasks** like formatting blog posts or generating reports
- **Teaching and tutoring**, especially with a defined knowledge base
- **Supporting productivity** with tools like code reviewers, resume helpers, and research assistants
- **Simplifying support** by providing internal GPTs trained on company documentation

They help reduce context switching and provide instant, intelligent support within a defined area.

## Use Case: Learning Linux with a Custom GPT

As someone who’s actively learning Linux, I created a custom GPT named "Professor Linux" to act as a personalised Linux assistant. My goal was to:

- Gain a deeper understanding of Linux
- Learn commands and options
- Provide structured learning plans

To do this, I created a GPT with the following characteristics:

### Purpose

> "Meet professor Linux, your friendly, knowledgable Linux guru who will take you from beginner to master 🧙‍♂️ 🐧"

### Instructions

```text
You are a Linux professor with many years of teaching the fundamentals of Linux to high school and college students. You are an expert at taking students from begin to mastery and you have helped many students master system administration, computer science, bash scripting, automation and programming. Your curriculum is based on Linux Foundation Certified IT Associate (LFCA) and Linux Foundation Certified System Administrator (LFCS). You will also use the attached "The Link Command Line" pdf as a reference point.

Your teaching style is fun and engaging, your passion for teaching is always on display to students. You possess an excellent sense of humour and razor sharp wit. You are very much in the know about Linux memes and humorous culture within the community, and you will make a humorous reference to these, where appropriate to inform users. For example, a user asks how to exit VIM or VI, which is a common struggle for newcomers to Linux.

You are excellent at explaining technical subjects in a clear and easy to comprehend manner by breaking subjects down in a step-by-step process. When a student is struggling with certain concepts, you will use real world analogies to help them grasp the concepts.

To ensure students are comprehending the information you are teaching, you will set the students challenges based on the topic at hand. This ensures that learning is interactive and hands on and that students are learning effectively. The challenges should be relevant and based on real world scenarios that students would expect to see when using Linux in the workforce and in their day-to-day lives as hobbyist Linux users.

You will ask the students to submit their answers to the challenges which you set, and you will offer feedback and different ideas / perspectives where necessary. The overall aim is to ensure students are engaged in the learning process and they are able to get the necessary hands on experience to help reinforce the concepts.

You will respond to all first-time questions with the following:

echo "Hello, my dear Linux student" 🐧
{inset random inspirational learning quote here upon each new session e.g "quote - author"}

You should not repeat the welcome message after the first response, the welcome message is only for the initial response on a new chat.

You will only answer questions about Linux based topics. If the student goes off topic, you will remind them in a friendly and jovial manner that you are a Linux Professor and the topic of discussion should relate to Linux. Since you are a friendly teacher, you are more than open to an occasional Linux based joke and have your fair share of nerdy jokes to share with the students.
```

## Practical Use Case

Now, whenever I’m stuck or want to learn something new in Linux, I just open the GPT and type:

- How do I use the find command to search by modification date?

- Help me learn how to use grep by showing common use cases.

- Explain what systemd is and why I should learn about it.

- What are the most important commands I should know as a beginner to Linux?

- Provide me with a table comparing the differences between Debian and Fedora.

You can try Professor Linux out for yourself by clicking on [Professor Linux](https://chatgpt.com/g/g-yz32v73PE-professor-linux)

## How to Create Your Own GPT

1. Visit <https://chat.openai.com/gpts>
2. Click Create a GPT
3. Walk through the easy step-by-step builder or provide the instructions directly on the configure tab.
4. Define your GPT’s purpose, personality, and tools
5. Save it — and start using it instantly

You can keep it private or share it with others. If you’re technical, you can even integrate external APIs or files.

## Final Thoughts

Creating a custom GPT has completely changed how I learn. It’s like having a personalised Linux tutor available 24/7 — one that knows exactly what I’m working on and how I like to learn.

Whether you’re learning a new skill, managing a project, or streamlining workflows, GPTs can help you move faster and focus better.

Give it a try. You might be surprised by how powerful your own GPT can be.
