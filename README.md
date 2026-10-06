# Multi-Agent-Code-Review-and-Refactoring-Assistant

Software development involves several repetitive activities such as reviewing code, identifying issues, improving the implementation, and writing tests. The **Multi-Agent Code Review and Refactoring Assistant** is an AI-based system designed to bring these activities together into a single workflow using multiple specialized AI agents.

Instead of asking one AI agent to handle the entire software engineering process, the system assigns different responsibilities to different agents. Each agent focuses on a particular task and passes its results to the next stage. This creates a structured workflow where the agents work together to analyze and improve a given codebase.

The system primarily consists of three specialized agents:

* **Code Reviewer Agent** – examines the source code and identifies potential code-quality, security, and complexity issues.
* **Refactoring Agent** – analyzes the identified issues and suggests suitable changes to improve the code.
* **Test Generation Agent** – generates unit tests for the relevant code after the proposed changes.

Static-analysis tools can be used alongside the Code Reviewer Agent to provide additional information about the code. For example, **Pylint** can be used for code-quality analysis, while **Bandit** can help identify common security-related issues in Python code. The AI agents can then use these results as part of their reasoning and recommendations.

A key part of the system is the **human approval step**. The system does not simply make changes to the repository without review. Instead, the developer can examine the detected issues and proposed refactoring before deciding whether the changes should be accepted. This keeps the developer involved in the process while still reducing repetitive work.

Once the changes are approved, the Test Generation Agent can generate appropriate unit tests for the modified code. These tests provide an additional way to verify that the changes behave as expected.

The overall flow can be understood as:

**Codebase → Code Review → Issue Detection → Refactoring Suggestions → Human Approval → Test Generation**

The project follows a **multi-agent specialist orchestration pattern**, where each agent has a clearly defined responsibility. The agents are coordinated through an orchestration workflow rather than operating independently.

The project is developed primarily using **Python**, with **LangGraph** and **CrewAI** used for agent orchestration and collaboration. An **LLM API** provides the language-model capabilities required for understanding source code and generating recommendations. Tools such as **Pylint** and **Bandit** support the static-analysis part of the workflow.

The system uses existing language models and development tools rather than training a new AI model from scratch. The focus is on designing an effective workflow in which existing AI capabilities can be combined with software-analysis tools to support developers.

The initial project is intended to demonstrate this workflow on a selected repository or codebase. The architecture can later be extended with additional programming languages, analysis tools, and specialized agents.

By combining code review, refactoring assistance, and test generation in one workflow, the project explores how **Agentic AI can be applied to software development**. The goal is not to replace developers, but to provide structured AI assistance that can make routine software-engineering tasks more efficient while keeping the developer in control of the final changes.

