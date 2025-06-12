# Master AI Agentic Engineering – Build Autonomous AI Agents

This course is your comprehensive guide to mastering agentic AI engineering, focusing on building, evaluating, and deploying autonomous AI agents using both open-source and frontier Large Language Models (LLMs). Through hands-on labs, real-world projects, and in-depth technical notes, you’ll gain the skills to design, implement, and optimize agentic systems for a wide range of applications.

[Enroll in the course on Udemy](https://www.udemy.com/course/the-complete-agentic-ai-engineering-course)

## Table of Contents

- [Master AI Agentic Engineering – Build Autonomous AI Agents](#master-ai-agentic-engineering--build-autonomous-ai-agents)
  - [Table of Contents](#table-of-contents)
  - [Course Overview](#course-overview)
    - [Week 1 - Foundations of AI Agent Engineering](#week-1---foundations-of-ai-agent-engineering)
      - [Day 1 - Environment Setup and First Steps with Agentic Workflows](#day-1---environment-setup-and-first-steps-with-agentic-workflows)
      - [Day 2 - Understanding Agentic Architecture and Design Patterns](#day-2---understanding-agentic-architecture-and-design-patterns)
      - [Day 3 - Multi-Model Interaction and Evaluation](#day-3---multi-model-interaction-and-evaluation)
      - [Day 4 - Building a Personal AI Assistant with Evaluation Loop](#day-4---building-a-personal-ai-assistant-with-evaluation-loop)
      - [Day 5 - Tool Integration and Deploying a Personal AI Assistant](#day-5---tool-integration-and-deploying-a-personal-ai-assistant)
    - [Week 2 - OpenAI Agents SDK](#week-2---openai-agents-sdk)
      - [Day 6 - Introduction to OpenAI Agents SDK and Asynchronous Python](#day-6---introduction-to-openai-agents-sdk-and-asynchronous-python)
      - [Day 7 - Building AI Sales Agents and Tool Usage](#day-7---building-ai-sales-agents-and-tool-usage)
      - [Day 8 - Heterogeneous Agents, Structured Outputs, and Input Guardrails](#day-8---heterogeneous-agents-structured-outputs-and-input-guardrails)

---

## Course Overview

### Week 1 - Foundations of AI Agent Engineering

#### Day 1 - Environment Setup and First Steps with Agentic Workflows

**What I did today:**

- Successfully configured the development environment for AI agent engineering, including installing Git, the AI-powered Cursor IDE, and the fast, Rust-based UV package manager, and securely managing API keys using a `.env` file.
- Gained hands-on experience with UV by using `uv sync` to create an isolated Python virtual environment and install project dependencies, and `uv run` to execute Python scripts.
- Executed the first practical lab by interacting with the OpenAI API via Python in a Jupyter notebook, correctly selecting the UV-managed kernel and utilizing `python-dotenv` to load API keys.
- Developed and successfully ran a multi-step "agentic workflow" by orchestrating multiple LLM calls, where one LLM call generated a question/topic and a subsequent call provided an answer/elaboration.
- Observed a foundational element of AI agent autonomy as the LLM independently selected a business sector for analysis within an exercise, demonstrating an ability to make choices within a given framework.
- Learned about the core components of an AI agent through an n8n demo, including triggers, agent nodes, underlying LLMs (OpenAI, Olama as alternative), and the critical role of "tools" (e.g., Philips Hue) for external interactions.
- Received an overview of the six-week course structure, which will progressively introduce various AI agent frameworks including the OpenAI Agents SDK, CrewAI, LangGraph, Microsoft Autogen, and Anthropic's Model Context Protocol.
- Understood the course's practical approach, focusing on building a portfolio of eight commercially relevant projects, such as an agentic software engineering team and a financial markets trading simulation.
- Familiarized myself with the course's supportive learning ecosystem, including comprehensive GitHub guides, supplementary videos, and an emphasis on community engagement via LinkedIn.
- Recognized the importance of patience and problem-solving during the setup of cutting-edge data science environments and the value of using modern tools like Cursor and UV for enhanced productivity.
- Applied the multi-step LLM pattern to a practical exercise, prompting an LLM to identify a business area ripe for AI, a specific pain point, and a proposed AI solution.
- Utilized `IPython.display.Markdown` to render formatted LLM responses within Jupyter notebooks, improving the readability of outputs.

**Resources:**

- [day 1 notes.ipynb](./1_foundations/notes/day1.ipynb)
- [day 1 lab.ipynb](./1_foundations/notebooks/1_lab1.ipynb)

#### Day 2 - Understanding Agentic Architecture and Design Patterns

**What I did today:**

- Explored the concept of AI agents and agentic architecture, understanding that agentic AI involves LLMs controlling workflows, using tools, and exhibiting autonomy.
- Differentiated between "workflows" (predefined paths) and "agents" (dynamic self-direction) within "agentic systems," based on Anthropic's classifications.
- Learned about key hallmarks of agentic AI, including multiple LLM calls, tool usage, inter-LLM communication, LLM-based planners, and LLM autonomy.
- Understood the importance of LLM autonomy in enabling adaptive and intelligent behavior for complex, multi-step tasks where the exact sequence of operations isn't known beforehand.
- Studied five essential LLM workflow design patterns identified by Anthropic:
  - **Prompt Chaining:** Sequential LLM calls for task decomposition.
  - **Routing:** An LLM directing tasks to specialist LLMs.
  - **Parallelization:** Code-driven concurrent task execution by multiple LLMs.
  - **Orchestrator-Worker:** An LLM dynamically breaking down and synthesizing tasks for worker LLMs.
  - **Evaluator-Optimizer (Validation Agents):** An LLM validating and providing iterative feedback on another LLM's output.
- Recognized that many "workflow" patterns exhibit forms of autonomy typically associated with more flexible "agents," indicating a spectrum of capabilities.
- Contrasted "agent" patterns (open-ended, dynamic, LLM plots its own path) with "workflow" patterns (structured, predefined steps).
- Acknowledged the increased power of agent patterns for solving complex problems and the associated challenges of unpredictability (path, output, cost, completion).
- Identified essential mitigation strategies for agentic systems: comprehensive monitoring (e.g., LangSmith) and software-defined guardrails to ensure safe and effective deployment.
- Understood the core interaction loop of an agent: receiving input, performing actions on an environment, receiving feedback, and deciding subsequent actions.

**Resources:**

- [day 2 notes.ipynb](./1_foundations/notes/day2.ipynb)

#### Day 3 - Multi-Model Interaction and Evaluation

**What I did today:**

- Gained hands-on experience interacting with a variety of Large Language Model (LLM) APIs, including OpenAI, Anthropic, Google Gemini, DeepSeek, and Groq.
- Learned how to load API keys and instantiate clients for different LLM providers.
- Implemented a workflow to send the same prompt (a nuanced question) to multiple LLMs to compare their responses and evaluate their intelligence.
- Set up and utilized Olloma to run LLMs locally, including pulling models like Llama 3.2 and interacting with the local Ollama server endpoint.
- Practiced collecting responses from different models and organizing them for comparison.
- Developed a prompt to instruct an LLM (acting as a judge) to evaluate and rank the collected responses from various competitor LLMs based on clarity and strength of argument.
- Processed the judge LLM's JSON output to display a ranked list of the competitor models.
- Understood the practical application of using multiple models and an evaluator LLM to improve the quality and reliability of LLM-generated content, a common pattern in business projects where accuracy is critical.
- Identified that the lab exercise demonstrated a combination of Prompt Chaining (generating a question, then answers, then evaluation) and an Evaluator-Optimizer pattern.

**Resources:**

- [2_lab2.ipynb](./1_foundations/notebooks/2_lab2.ipynb)
- [day 3 notes.ipynb](./1_foundations/notes/day3.ipynb)

#### Day 4 - Building a Personal AI Assistant with Evaluation Loop

**What I did today:**

- Developed a personal AI assistant with a Gradio web interface, designed to answer questions based on personal background information.
- Extracted text from a LinkedIn profile PDF using the `pypdf` library and combined it with a text-based summary to create a comprehensive context for the LLM.
- Programmed the AI assistant to respond "in character" (e.g., as "Ed Donner") using the provided personal documents.
- Implemented an LLM-based evaluator using a locally run Ollama model (`llama3.2`) to assess the quality and acceptability of the assistant's responses.
- Utilized Pydantic to define a structured format for the evaluator's output, ensuring consistent feedback (is_acceptable, feedback).
- Created an iterative refinement loop (Evaluator-Optimizer pattern): if the initial response was rejected by the evaluator, the assistant would regenerate the response, taking the evaluator's feedback into account.
- Applied Prompt Chaining by structuring the workflow: user interaction, initial response generation, evaluation, and potential response regeneration.
- Gained experience with building interactive AI applications using Gradio and integrating multiple LLM services (OpenAI for primary responses, Ollama for evaluation) in a single workflow.

**Resources:**

- [3_lab3.ipynb](./1_foundations/notebooks/3_lab3.ipynb)
- [day4.ipynb](./1_foundations/notes/day4.ipynb)

#### Day 5 - Tool Integration and Deploying a Personal AI Assistant

**What I did today:**

- Integrated "Pushover" to enable the AI assistant to send real-time push notifications.
- Defined and implemented tools for the LLM, specifically `record_user_details` (to capture contact information) and `record_unknown_question` (to log questions the assistant couldn't answer).
- Developed the logic within the chat application to handle LLM tool calls, allowing the assistant to execute these predefined functions.
- Enhanced the personal AI assistant ("Professionally You!" project) by incorporating these tool-using capabilities, making it more interactive and functional.
- Updated the system prompt to instruct the LLM on when and how to use the available tools.
- Modified the core chat function to manage the tool-calling loop: sending tool definitions to the LLM, processing its requests to use tools, executing the tools, and sending results back to the LLM.
- Learned and documented the process for deploying the Gradio-based AI assistant to HuggingFace Spaces, including managing API keys and other secrets.

**Resources:**

- [4_lab4.ipynb](./1_foundations/notebooks/4_lab4.ipynb)
- [day5.ipynb](./1_foundations/notes/day5.ipynb)

### Week 2 - OpenAI Agents SDK

#### Day 6 - Introduction to OpenAI Agents SDK and Asynchronous Python

**What I did today:**

- Established a foundational understanding of asynchronous Python, including the `asyncio` event loop and the use of `async`/`await` for managing I/O-bound tasks in agentic systems.
- Learned the core concepts of the OpenAI Agents SDK, differentiating its "unopinionated" philosophy from other frameworks and understanding the roles of the `Agent`, `Runner`, and `Trace` classes.
- Gained hands-on experience by instantiating a basic AI agent, defining its system prompt and model, and correctly executing it using the asynchronous `await Runner.run()` method.
- Implemented observability for agent workflows by using the `with Trace(...)` context manager to log interactions, enabling debugging and monitoring via the OpenAI platform.
- Outlined a disciplined "vibe coding" methodology for LLM-assisted development, incorporating best practices like incremental generation, cross-model verification, and AI-powered code validation.
- Successfully completed the conceptual overview of the Agents SDK, preparing for the practical application of building a multi-agent system in the upcoming sessions.

**Resources:**

- [day1.ipynb](./2_openai/notes/day1.ipynb)
- [1_lab1.ipynb](./2_openai/notebooks/1_lab1.ipynb)

#### Day 7 - Building AI Sales Agents and Tool Usage

**What I did today:**

- Explored a multi-layered agentic architecture for a sales system, defining agent personas (professional, humorous, concise) through system prompts.
- Manually orchestrated agents in Python and implemented streaming responses for an improved user experience.
- Set up SendGrid for an agent to use as an external tool for sending emails.
- Implemented parallel agent execution using `asyncio.gather` to efficiently generate multiple sales email drafts.
- Utilized a "picker" agent to evaluate and select the best email draft from the options generated by other agents.
- Leveraged the `@function_tool` decorator to simplify making Python functions (like `send_email`) available to agents, automating JSON schema generation.
- Wrapped the multi-step workflow in a single trace for observability and debugging.
- Created a hierarchical agent system by converting specialized agents into tools using the `.as_tool()` method, allowing a "manager" agent to orchestrate them.
- Implemented "handoffs" for sequential, one-way transfer of control between agents, such as passing a drafted email to a specialist `Emailer Agent` for formatting and sending.
- Distinguished between "agent-as-a-tool" (request-response) and "handoff" (one-way delegation) for different collaboration patterns.
- Executed a complex workflow where a manager agent autonomously used multiple writer agent-tools, selected the best output, and handed off to an emailer agent.
- Understood the transition to "agentic" behavior when the system moves from scripted calls to goal-oriented, autonomous decision-making by a manager agent.

**Resources:**

- [day2.ipynb](./2_openai/notes/day2.ipynb)
- [2_lab2.ipynb](./2_openai/notebooks/2_lab2.ipynb)

#### Day 8 - Heterogeneous Agents, Structured Outputs, and Input Guardrails

**What I did today:**

- Integrated multiple non-OpenAI language models, including Gemini, Deep Seek, and Llama 3, into the OpenAI Agents SDK by configuring clients with model-specific, OpenAI-compatible API endpoints.
- Developed a heterogeneous multi-agent system by instantiating separate agents, each powered by a different underlying model, to leverage their unique capabilities for distinct tasks within a single workflow.
- Implemented structured outputs using Pydantic classes to enforce a reliable and machine-readable data format for agent responses, ensuring predictable and consistent data handling.
- Designed and deployed LLM-powered input guardrails to act as a dynamic safety layer, successfully preventing agent execution when prompts contained sensitive or non-compliant data like personally identifiable information (PII).
- Analyzed and debugged agent behavior, leveraging execution traces to understand the SDK's asynchronous parallel processing and diagnose issues like non-deterministic loops.
- Explored solutions for integrating models without native OpenAI-compatible endpoints, identifying proxy services like OpenRouter as a viable workaround for incorporating models such as Anthropic's Claude.
- Practically demonstrated the guardrail exception handling mechanism, confirming that a triggered tripwire correctly halts the agent workflow by design to ensure data safety and policy enforcement.

**Resources:**

- [day3.ipynb](./2_openai/notes/day3.ipynb)