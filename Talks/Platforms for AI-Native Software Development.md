---
title: "Platforms for AI-Native Software Development"
type: talk
event: "Öredev 2026"
date: 2026-11-04
description: "Internal developer platforms for orchestrating change when agents write the code."
tags: [talk, oredev-2026, platform-engineering, idp, agents]
topics: ["[[AI Agents]]", "[[Software Architecture and Platforms]]"]
source: Pocket
status: unreviewed
---
> [!summary]
> In this presentation, software engineer and leader Lilja explores the evolving role of Internal Developer Platforms (IDPs) in an era where AI agents are drastically increasing code volume. The core thesis is a paradigm shift: we are moving from **writing code** to **orchestrating change**.

## The Shift in Bottlenecks

The velocity of software production has increased significantly, with GitHub data showing a 3x increase in pull requests and issues year-over-year. Consequently, the bottleneck has shifted away from the act of writing code to two specific areas:

- **Upstream:** Defining product direction, refinement, and design intent.
- **Downstream:** Operations, maintenance, and the "unsustainable" volume of pull request reviews and merge conflicts.

## The Problem: Stochastic Fragmentation

Large Language Models (LLMs) are probabilistic, not deterministic. If left unconstrained, agents naturally produce fragmented codebases.

- **Cost of Fragmentation:** Complexity is expensive, leading to high maintenance debt and increased cognitive load.
- **Sustainability Rule:** As total output volume increases, system complexity must be forced downward to remain manageable.

## Architecting AI-Native Platforms

A modern IDP must serve three distinct user types: professional developers, "citizen developers" (non-technical staff building tools), and AI agents.

### 1. Deterministic Guardrails

Agents require clear, fast feedback loops. Lilja advocates for using linters and static analysis tools triggered on file save. This provides instant feedback to the agent before code even reaches a human reviewer, saving expensive token costs and CI/CD time.

### 2. The CLI as Context Provider

While agents struggle with massive documentation, they excel at using command-line tools.

- **Just-in-Time Knowledge:** Instead of loading an entire "Golden Path" into an LLM’s context window, provide a CLI wrapper. The agent can search the CLI for specific services (e.g., storage, buckets) and receive only the relevant, approved patterns.
- **Service-Side Logic:** Avoid keeping platform logic on local machines. Centralizing the Golden Path in a service ensures that updates are immediately propagated to all users and agents.

### 3. Human Agency and Parity

Humans must never be "locked out" of the system. The platform should offer the same tooling to agents and humans. If an agent provider goes down during a production incident, the human developer must be able to use the same CLI tools and platform APIs to resolve the issue manually.

## Implementation Directives

- **Reduce Cognitive Load:** Standardize logging, error handling, and observability across all applications so that 1,000 applications look identical to a maintainer.
- **Paved Roads over Strict Enforcement:** The "Golden Path" should be the easiest default, but developers should retain the ability to step off the path if justified by cost or specific requirements, provided they stay within safety guardrails.
- **Invest in API-First IDPs:** If a platform is already self-service and API-first for humans, it is essentially ready for agents.

## Mind map

![[Platforms for AI-Native Software Development - mind map.png]]

## Sources

- [[Platforms for AI-Native Software Development - summary.pdf]]

## My notes

- 
