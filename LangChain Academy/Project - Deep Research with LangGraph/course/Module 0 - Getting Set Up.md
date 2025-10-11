# Getting Set Up


## **Introduction**

Welcome to LangChain Academy’s Deep Research course!

Deep research has broken out as one of the most popular agent applications. [OpenAI](https://openai.com/index/introducing-deep-research/), [Anthropic](https://www.anthropic.com/engineering/built-multi-agent-research-system), [Perplexity](https://www.perplexity.ai/hub/blog/introducing-perplexity-deep-research), and [Google](https://gemini.google/overview/deep-research/?hl=en) all have deep research products that produce comprehensive reports using [various sources](https://www.anthropic.com/news/research) of context. There are also many [open](https://huggingface.co/blog/open-deep-research) [source](https://github.com/google-gemini/gemini-fullstack-langgraph-quickstart) implementations. We've seen many of our customers build their own deep research agents.

At LangChain, we've built an [open deep researcher](https://github.com/langchain-ai/open_deep_research) that is simple and configurable, allowing users to bring their own models, search tools, and MCP servers. In this course, we'll build a deep researcher together from scratch.

This course is divided into six modules. Each module includes a video lesson to walk you through key concepts, along with corresponding notebooks.

A special thank you to Dmitry Labazkin for his contributions and feedback on this course.


## **Background**

Research is an open-ended task; the best strategy to answer a user request can’t be easily known in advance. Requests can require different research strategies and varying levels of search depth. Consider this request.

[Agents](https://langchain-ai.github.io/langgraph/tutorials/workflows/#agent) are well suited to research because they can flexibly apply different strategies, using intermediate results to guide their exploration. Open deep research uses an agent to conduct research as part of a three step process:

1.  **Scope** – clarify research scope
2.  **Research** – perform research
3.  **Write** – produce the final report


## **Organization**

The course repo contains 5 tutorial notebooks that build a deep research system from scratch:

**1. User Clarification and Brief Generation (`notebooks/1_scoping.ipynb`)**

**Purpose**: Clarify research scope and transform user input into structured research briefs

**Key Concepts**:

*   **User Clarification**: Determines if additional context is needed from the user using structured output
*   **Brief Generation**: Transforms conversations into detailed research questions
*   **LangGraph Commands**: Using Command system for flow control and state updates
*   **Structured Output**: Pydantic schemas for reliable decision making

**Implementation Highlights**:

*   Two-step workflow: clarification → brief generation
*   Structured output models (ClarifyWithUser, ResearchQuestion) to prevent hallucination
*   Conditional routing based on clarification needs
*   Date-aware prompts for context-sensitive research

**What You'll Learn**: State management, structured output patterns, conditional routing

**2. Research Agent with Custom Tools (`notebooks/2_research_agent.ipynb`)**

**Purpose**: Build an iterative research agent using external search tools

**Key Concepts**:

*   **Agent Architecture**: LLM decision node + tool execution node pattern
*   **Sequential Tool Execution**: Reliable synchronous tool execution
*   **Search Integration**: Tavily search with content summarization
*   **Tool Execution**: ReAct-style agent loop with tool calling

**Implementation Highlights**:

*   Synchronous tool execution for reliability and simplicity
*   Content summarization to compress search results
*   Iterative research loop with conditional routing
*   Rich prompt engineering for comprehensive research

**What You'll Learn**: Agent patterns, tool integration, search optimization, research workflow design

**3. Research Agent with MCP (`notebooks/3_research_agent_mcp.ipynb`)**

**Purpose**: Integrate Model Context Protocol (MCP) servers as research tools

**Key Concepts**:

*   **Model Context Protocol**: Standardized protocol for AI tool access
*   **MCP Architecture**: Client-server communication via stdio/HTTP
*   **LangChain MCP Adapters**: Seamless integration of MCP servers as LangChain tools
*   **Local vs Remote MCP**: Understanding transport mechanisms

**Implementation Highlights**:

*   MultiServerMCPClient for managing MCP servers
*   Configuration-driven server setup (filesystem example)
*   Rich formatting for tool output display
*   Async tool execution required by MCP protocol (no nested event loops needed)

**What You'll Learn**: MCP integration, client-server architecture, protocol-based tool access

**4. Research Supervisor (`notebooks/4_research_supervisor.ipynb`)**

**Purpose**: Multi-agent coordination for complex research tasks

**Key Concepts**:

*   **Supervisor Pattern**: Coordination agent + worker agents
*   **Parallel Research**: Concurrent research agents for independent topics using parallel tool calls
*   **Research Delegation**: Structured tools for task assignment
*   **Context Isolation**: Separate context windows for different research topics

**Implementation Highlights**:

*   Two-node supervisor pattern (supervisor + supervisor_tools)
*   Parallel research execution using asyncio.gather() for true concurrency
*   Structured tools (ConductResearch, ResearchComplete) for delegation
*   Enhanced prompts with parallel research instructions
*   Comprehensive documentation of research aggregation patterns

**What You'll Learn**: Multi-agent patterns, parallel processing, research coordination, async orchestration

**5. Full Multi-Agent Research System (`notebooks/5_full_agent.ipynb`)**

**Purpose**: Complete end-to-end research system integrating all components

**Key Concepts**:

*   **Three-Phase Architecture**: Scope → Research → Write
*   **System Integration**: Combining scoping, multi-agent research, and report generation
*   **State Management**: Complex state flow across subgraphs
*   **End-to-End Workflow**: From user input to final research report

**Implementation Highlights**:

*   Complete workflow integration with proper state transitions
*   Supervisor and researcher subgraphs with output schemas
*   Final report generation with research synthesis
*   Thread-based conversation management for clarification

**What You'll Learn**: System architecture, subgraph composition, end-to-end workflows


## **Key Learning Outcomes**

*   **Structured Output**: Using Pydantic schemas for reliable AI decision making
*   **Async Orchestration**: Strategic use of async patterns for parallel coordination vs synchronous simplicity
*   **Agent Patterns**: ReAct loops, supervisor patterns, multi-agent coordination
*   **Search Integration**: External APIs, MCP servers, content processing
*   **Workflow Design**: LangGraph patterns for complex multi-step processes
*   **State Management**: Complex state flows across subgraphs and nodes
*   **Protocol Integration**: MCP servers and tool ecosystems

Each notebook builds on the previous concepts, culminating in a production-ready deep research system that can handle complex, multi-faceted research queries with intelligent scoping and coordinated execution.
