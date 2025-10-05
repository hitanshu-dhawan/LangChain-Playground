# Getting Set Up


## **Introduction**

Welcome to LangChain Academy’s Deep Agents with LangGraph course!

There are now several successful examples of long-running, highly capable agents. We've given the name 'Deep Agents' to these, as they are distinctly different than previous generations of agents. In this course, you will learn what makes them different and will build your own Deep Agent.

At LangChain, we've built a [**Deep Agent**](https://github.com/langchain-ai/deepagents) that is simple and configurable, allowing users to build long-running agents quickly and simply.

In this course, you'll build a deep research agent using a Deep Agent.  This course is divided into seven modules.

Each module includes a video lesson to walk you through key concepts, along with corresponding notebooks.

A special thank you to Dmitry Labazkin for his contributions and feedback on this course.


## **Background**

[Deep Research](https://academy.langchain.com/courses/deep-research-with-langgraph) broke out as one of the first major agent use-cases, along with coding.

Now, we're seeing an emergence of general-purpose agents that can be used for a wide range of tasks. For example, [Manus](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus) has gained significant attention and popularity for long-horizon tasks; the average Manus task uses ~50 tool calls!

As a second example, Claude Code is being used generally for tasks beyond coding.

Careful review of the [context engineering patterns](https://docs.google.com/presentation/d/16aaXLu40GugY-kOpqDU4e-S0hD1FmHcNyF0rRRnb1OU/edit?slide=id.p#slide=id.p) across these popular "deep" agents shows some common approaches:

*   Task planning (e.g., todo), often with recitation
*   Context offloading to file systems
*   Context isolation through sub-agent delegation

This course will show how to implement these patterns from scratch using LangGraph.


## **Organization**

### **Tutorial Overview**

This repository contains five progressive notebooks that teach you to build advanced AI agents:

**`0_create_agent.ipynb` - Create Agent Component**

Learn to use the create_agent component. This component:

*   Implements a ReAct (Reason-Act) loop that is the foundation for many agents
*   Is easy to use and quick to set up
*   Is the core building block for the Deep Agent

**`1_todo.ipynb` - Task Planning Foundations**

Learn to implement structured task planning using TODO lists. This notebook introduces:

*   Task tracking with status management (pending/in_progress/completed)
*   Progress monitoring and context management
*   The `write_todos()` tool for organizing complex multi-step workflows
*   Best practices for maintaining focus and preventing task drift

**`2_files.ipynb` - Virtual File Systems**

Implement a virtual file system stored in agent state for context offloading:

*   File operations: `Is()`, `read_file()`, `write_file()`
*   Context management through information persistence
*   Enabling agent "memory" across conversation turns
*   Reducing token usage by storing detailed information in files

**`3_subagents.ipynb` - Context Isolation**

Master sub-agent delegation for handling complex workflows:

*   Creating specialized sub-agents with focused tool sets
*   Context isolation to prevent confusion and task interference
*   The `task()` delegation tool and agent registry patterns
*   Parallel execution capabilities for independent research streams

**`4_full_agent.ipynb` - Complete Research Agent**

Combine all techniques into a production-ready research agent:

*   Integration of TODOs, files, and sub-agents
*   Real web search with intelligent context offloading
*   Content summarization and strategic thinking tools
*   Complete workflow for complex research tasks

Each notebook builds on the previous concepts, culminating in a sophisticated agent architecture capable of handling real-world research and analysis tasks.

