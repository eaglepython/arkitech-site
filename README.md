# Arkitech Quant Research Studio

Public browser-based learning app for quantitative research, trading, and engineering practice.

Learner progress is stored locally in the browser on this device. The static site does not sync progress or send work to a model unless you explicitly choose a coach and ask a question.

## Local Ollama models

Install and start Ollama, then download `local-llm-bridge.mjs` from this repository to your computer and run `node local-llm-bridge.mjs` (Node.js 18 or newer). In the app choose **This computer · Ollama** and select **Find local models**. The bridge binds to loopback, allows this site’s exact origin, stores no learner data, and calls only Ollama on the same computer. Do not expose its port to a network.

## Remote models and phones

Choose **Remote · mobile ready** and enter an HTTPS OpenAI-compatible endpoint, model, and your own API key. The key stays in the current tab’s memory and is cleared when the tab reloads. Asking a question sends that prompt and any selected lesson/code context to the remote provider; it may charge or retain data. Providers must permit browser CORS requests. If remote access fails, the app tries local Ollama when a bridge is available, then falls back to built-in offline agents. Phones without a local model use the built-in agents.

The private `arkitech` source repository contains the account server and learner-progress sync implementation. This public site repository publishes the static app and the standalone, local-model-only bridge.
