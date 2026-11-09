---
title: "AI Adoption in Public Sector"
type: talk
event: "Öredev 2026"
date: 2026-11-05
description: "Organizational readiness, shared 'Lego-brick' AI services and governance in Swedish public agencies."
tags: [talk, oredev-2026, ai-adoption, public-sector, governance]
topics: ["[[AI in Organizations]]"]
source: Pocket
status: unreviewed
---
> [!summary]
> Two AI leads from Swedish public agencies explain that scaling AI is limited less by technology than by organizational readiness — governance, shared capability building, trust and realistic expectations — and show how reusable "Lego-brick" services, a shared platform and a three-tier use framework turn pilots into reliable everyday services.

## The core message

- The hard part is not getting a pilot to work but making AI reliable and safe enough that people trust and use it in everyday work.
- In McKinsey's 2025 survey, almost nine out of ten respondents reported using AI in at least one business function, but only around seven percent reported having it fully rolled out; the majority were still testing or running pilots.
- Moving beyond pilots needs reliable operations, users who understand and trust the services, and changed processes and ways of working — not just more tools.
- "Most of the challenges that we see are not really about technology. They are about readiness" — how ready the organization is to use AI in practice.
- The biggest risk ahead is expecting the wrong things from AI; clear rules and realistic expectations are what make services people can rely on.
- The closing metaphor: technology makes the journey possible, but leadership determines whether an organization actually moves forward.

## Forsäkringskassan: agency context and strategy

- The agency's role is to help the state make decisions and pay social insurance benefits, using public resources carefully.
- It has around fourteen thousand employees across Sweden and pays out over two hundred and fifty billion Swedish crowns per year; it also provides secure ID operations for other agencies.
- Together with the Swedish Tax Agency it is to establish AI Lab Sweden, including shared infrastructure and support for AI development across the rest of the Swedish public sector.
- The stated direction: AI is a tool for meeting goals, not a goal in itself; it may improve an existing process or create a new one, and not every case should become fully automated.
- Three strategic priorities that must all be pursued at the same time:
  - **Skills** — staff and managers need enough knowledge to use AI responsibly in their own roles; without a shared understanding, moving beyond pilots is hard.
  - **Widening** — make AI useful in everyday work, starting with suitable tasks where risk can be managed.
  - **Advanced use** — explore complex, essential services such as AI-enabled support to prevent incorrect payments, with careful risk assessment and mitigation.
- Early examples cited include analyzing medical reports and translating documents.
- The agency has led its applied AI work since 2019.
- Experts must lead the change and stay involved, both to prepare data and assess results; users must stay involved too, since AI can make mistakes just as people can.
- Business side holds clear ownership and works jointly with IT on data quality, model training where needed, testing and release.
- Even a good tool creates risk if people don't use it or use it wrongly; technical skills matter, but staff also need to understand the tool and its legal and ethical limits.

## The Tax Agency's shared-capability model

- The Swedish Tax Agency has worked systematically on AI since 2019, when it set up its first applied AI unit as the main point for shared AI capabilities, data storage and making data available based on business needs.
- The work sits together in one area within IT, combining technical skills, understanding of business needs, and knowledge of legal and ethical questions.
- Rationale for shared solutions: develop once, let different business teams reuse for their own needs, and maintain fewer near-duplicate solutions; what usually differs between solutions is the data or the models for specific tasks.
- The work covers both shared AI capabilities and the underlying data services they depend on.
- The "Lego bricks" model: instead of building separate solutions each time, combine shared AI capabilities into different applications; business teams provide and classify data and help evaluate whether results are useful.
- Two benefits claimed: faster delivery by building on already developed and tested capabilities, and retained control by reusing security, governance and monitoring as the number of applications grows.
- Infrastructure: shared CPUs, storage and data processing together with security, governance and compliance, plus a shared AI platform for training, testing and running models in a controlled environment — the foundation for moving from a working pilot to a reliable service.

## Three groups of AI use, matched to control

- AI use is organized into three groups based on two things: the value to create and the controls needed; these are not legal risk categories, and legal obligations can apply across all three.
- **Innovation and pilots** — test ideas and build prototypes; the main value is learning. Risk must be kept as low as possible, but internal use doesn't automatically make something low risk: data, access and intended use still matter.
- **AI in daily work** — AI directly supports processes such as analyzing documents, preparing data or working with transcripts; value may be better quality, fewer error hours or faster handling, but privacy protection, quality checks and bias checks are needed.
- **Decision support** — support for case handling and redrafting where consequences can be significant; requires particular attention to legal requirements, fair decisions and meaningful human review.
- All three rest on the same foundation: quality-checked data with clear ownership, a shared AI platform, and governance for responsible AI.

## Practical examples and what each taught

- **Redaction** — finds personal information in text and masks it; made a shared capability rather than rebuilt into each solution, because much AI work involves unstructured information where legal and security requirements apply from the start. It supports tasks from preparing text for analysis to reviewing system logs and handling public-document requests; the rules and review needs still depend on the particular use, and it was the first AI service in the shared setup.
  - In the workflow, the user uploads a document, the service suggests information types, and the user reviews and corrects before exporting to PDF — staff decide what must actually be redacted.
  - The task looked very simple at the start (names, places, personal identity numbers), but users had different needs: case documents, recruitment documents, procurement and IT needs (including IT addresses and system logs), each with its own rules.
  - Lesson: finding personal information is not the same as it having to be hidden; involve users with different needs early and test with them throughout development.
- **Speech-to-text** — helps staff transcribe recorded speech and meetings; longer term, exploration of use for longer interviews is planned, subject to assessment of processes, legal requirements and information handling.
- **Digital assistant** — supports staff through chat and document search, and with retrieval-augmented generation (RAG) can use selected documents when preparing an answer; this helps ground answers in relevant sources but does not guarantee every answer is correct or fully supported, so users must still check important information.
  - It offers an option for groups working with information that cannot be sent to an external service.
  - Lesson: staff may expect the same experience as ChatGPT, so the agency must explain where the assistant is useful, what it can assist with, and what its limits are.
- **Translation** — helps staff understand documents in other languages; in the agency's test an earlier approach worked better than the newest or largest model with the medical documents at hand — a result of their use case, not a general rule about model size.
  - Many documents arrive as scanned PDFs and needed optical character recognition (OCR) to read the text in the images.
- **Medical report analysis** — highlights information about impairments and limits on daily activities so staff can assess a person's ability to work; the aim is to make relevant information easy to find and reduce friction. Staff still make the assessment.
  - An early AI tool for case officers developed around 2019, using supervised machine learning prepared and labelled by the agency's own team; an important test of the technology, the user experience and the organization's readiness at the time.
  - A new version using newer methods is in progress; it still needs testing to show whether results are better and more accurate for case officers.
- **Recruitment (decision support)** — AI that analyzes applications or evaluates candidates falls under the recruitment category, and expected requirements depend on the use and applicable rules. The category is about what the system does, not who makes the final decision.
  - The tool helps recruiters compare CVs with the requirements for a job; recruitment decisions at a government agency must follow the rules for public employment, and the process must be demonstrably fair and compliant.
  - It works with personal information and assesses fit to job requirements, so recruiters must check the evidence and assessment behind the decision.
  - A score may look precise without being correct, so the agency needs to understand how the tool behaves and check for unseen differences.
- **AI agents and MCP** — an exploratory area. Agents can work toward a goal, plan steps and use tools, for example gathering information from different systems, preparing a summary or suggesting an action, rather than answering one question at a time.
  - MCP is described as one option / a standard way to connect AI applications to tools and data, but each system still needs its own integration and access controls.
  - Open questions raised: who is responsible when a task spans several steps and systems, whether the agent's actions can be explained, how to verify it took the right action, and how to control its access to systems and data. People also need ways to review and stop an agent's action.
  - For now the agency continues through pilots and innovation in a controlled setting; the next step is working out how to use the technology with clear responsibility and appropriate controls.
- Why build in-house rather than buy: operating services in the agency's own environment and controlling sensitive information handling, reusing components across services, and adapting quickly to users' needs — while similar services exist on the market.

## Scaling, governance and expectations

- Making AI work across everyday operations is a much bigger task than getting a pilot into production.
- AI, including agents, will increasingly be part of workflows rather than something used on the side, bringing more users, processes and dependencies — making operation, maintenance and data management critical, and that is where the bottleneck starts to appear.
- AI governance provides structure for managing models, data, risk and responsibility, helping more people work with AI while keeping quality high and following the law.
- IT can't do this alone: developers, case officers, legal teams and IT operations all have a role; clear roles speed up decisions and avoid unnecessary delays.
- AI cannot solve everything at once; it needs active management, review and continuous improvement.
- Readiness comes down to three things: expand what works, take responsibility for what is put into operation, and set realistic expectations.
- "AI doesn't scale on its own. People make that happen" — with clear roles, clear responsibility and cooperation; the business must own the solution beyond the end of the project, and both managers and users must understand what AI can actually do.

## Audience engagement and speaker background

- The presenters opened on shared generational experience of technology change: early online banking in the Nordics (where colleagues doubted anyone would want to pay bills on the bus) and 1990s school computer labs where Clippy-style tips felt more annoying than helpful — an early AI assistant whose value got lost between the technology and the users.
- The speaker leading the Forsäkringskassan portion introduced themselves as head of AI in the IT department, with a background as a developer on one of the first online banking services in the Nordic countries; the co-presenter introduced themselves as a business developer focusing on AI with a mainly business-side background.
- No audience questions are captured in the recording; the session closed with thanks for listening.

## Questions and reflections

- Open questions left visible by the presenters rather than resolved: responsibility and explainability for multi-step agent actions, access control, and how human review and stop mechanisms should work.
- Unresolved: whether the newer medical report analysis approach is measurably better and more accurate for case officers — still to be tested.
- Open: how to handle the expectation gap where staff compare internal assistants to ChatGPT.
- For reflection: the pattern of reusable, centrally governed capabilities with business-owned applications maps closely onto the standardized-over-bespoke architecture approach and the IDP direction of building self-serve platforms with thin local wrappers.

## Mind map

![[AI Adoption in Public Sector - mind map.png]]

## Sources

- [[AI Adoption in Public Sector - summary.pdf]]

## My notes

- 
