---
title: "Building Offline-First AI Agents in JavaScript"
type: talk
event: "Öredev 2026"
date: 2026-11-04
description: "Running LLM agents in the browser, offline, for privacy, cost and connectivity."
tags: [talk, oredev-2026, javascript, browser, local-llm, offline-first, agents]
topics: ["[[AI Agents]]", "[[Web Platform]]"]
source: Pocket
status: unreviewed
---
> [!summary]
> Ndaza Lai Ingosi, a lead researcher at PBD and advocate for the web platform, delivered a keynote on bridging the gap between web applications and native mobile experiences through browser-based AI. The central thesis is that the browser is now a viable, high-performance execution environment for agentic workflows, capable of running complex LLMs offline to solve privacy, cost, and connectivity challenges.

## Key Takeaways

- **The Agentic Shift:** Current AI interaction is stalled in a "chat and wait" paradigm. The next phase is the **Agent Loop**, where applications observe their environment, make autonomous decisions, act, and reflect on outputs without constant user prompting.
- **WebLLM and Hardware Acceleration:** The emergence of the WebGPU API allows browsers to abstract complex GPU instructions, enabling high-performance, in-browser inference. This permits quantized models (like Microsoft’s Phi or Llama) to run locally, bypassing the latency and cost of frontier model APIs.
- **Local-First and Offline Utility:** In regions like South Africa, where data is expensive and infrastructure is inconsistent (e.g., hospital operating rooms with signal interference), in-browser AI provides critical utility without requiring an internet connection.
- **Closing the Native Gap:** Modern Web APIs—specifically the File System Access API (direct local file editing), IndexedDB (persistent storage), and Web Workers (background processing)—now provide the ingredients necessary to build web apps that are indistinguishable from native desktop or mobile software.

## Speaker Insights

- **Atwood’s Law in the AI Era:** Ingosi reinforces Jeff Atwood’s principle that anything that can be written in JavaScript eventually will be. He views JavaScript’s flexibility as the primary tool for "fixing" the broken experiences of the modern web.
- **Economic Realities of AI:** Large-scale AI deployment is currently subsidized by major corporations. As these companies seek profitability, API costs will escalate, making local, in-browser inference a strategic necessity for enterprise sustainability.
- **The Hype Cycle Cautionary Tale:** Referring to the Gartner Hype Cycle, Ingosi warns that the "Peak of Inflated Expectations" often leads to failures like McDonald’s bacon-topped ice cream errors or Zillow’s overpayment for properties. Success requires moving toward the "Plateau of Productivity" by solving specific, grounded user needs rather than just "adding AI."

## Technical Implementation

The demonstration showcased a 2GB Microsoft Phi model running entirely in the browser. The architecture utilized:

- **Web Workers:** To delegate inference tasks away from the main thread, ensuring the UI remains responsive.
- **Quantization:** Reducing model size to fit within browser memory constraints while maintaining substantive reasoning capabilities.
- **Web MCP (Model Context Protocol):** Proposing a way for AI agents to interact with web application services through simplified, intuitive interfaces.

## Audience Engagement

- **The Gartner Poll:** Ingosi used a show of hands to gauge familiarity with technology hype cycles, noting that while the euphoria around AI is high, the "Trough of Disillusionment" is inevitable for companies failing to understand user requirements.
- **Developer Sentiment:** He touched on the "React stagnation," noting that the industry-wide obsession with AI has slowed the pace of new web framework development, which he views as both a sign of maturity and a missed opportunity for platform innovation.
- **The "Spinner Verb" Critique:** Humor was used to highlight the current state of AI UX—apps that use creative loading states ("discombobulating," "dreaming") to mask the latency of remote inference, a problem solved by moving to local-first models.

## Mind map

![[Building Offline-First AI Agents in JavaScript - mind map.png]]

## Sources

- [[Building Offline-First AI Agents in JavaScript - summary.pdf]]

## My notes

- 
