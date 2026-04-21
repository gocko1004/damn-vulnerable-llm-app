# damn-vulnerable-llm-app

A deliberately vulnerable LLM-powered customer service chatbot for studying the OWASP LLM Top 10.

## Why this exists

Customer service chatbots are the most common production LLM use case right now. Most CTOs reading this have shipped one. They also have the widest attack surface: system prompt, RAG documents, user input, output rendering.

This lab builds that exact shape, on purpose, with the holes left in.

Week 1 covers LLM01 to LLM03: direct prompt injection, indirect prompt injection through uploaded documents, and insecure output handling. Month 1 extends to all ten OWASP LLM Top 10 categories. Each module ships with the vulnerable code, the exploit that breaks it, the detection signal, and the fix.

## Stack

FastAPI app with two endpoints. `POST /chat` sends user input to Claude behind a weak system prompt for a fictional "CustomerBot for Acme Corp." `POST /search` hits a ChromaDB vector store seeded with 20 fake company documents, including a planted coupon code and fake credentials. The chat endpoint does RAG, pulling relevant docs into context before answering.

## About me

Goce Petrov. Security consultant based in Canton Jura, Switzerland. Currently at DevSecAI working on ARKO, an LLM security plugin for VS Code and Cursor. Background in brand strategy and design, 170+ shipped projects, now bringing both into AI security consulting.

## Disclaimer

This application contains deliberate security vulnerabilities. Do not deploy, expose to the internet, or run against production systems or real API keys. Run only in isolated local environments.
