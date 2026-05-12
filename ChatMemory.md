# Mastering Chat Memory

LLMs (Large Language Models) are stateless by default.

This means the model does not automatically remember previous conversations, user preferences, or earlier interactions. Every new request is treated like a completely fresh conversation.

Example:

User: My name is Ayush
AI: Nice to meet you

User: What is my name?
AI: I don’t know

Even though the user already shared their name earlier, the model cannot remember it because there is no persistent conversation memory.

This is one of the biggest challenges while building production-grade AI applications.

Spring AI solves this problem using ChatMemory.

ChatMemory allows AI applications to store, manage, and reuse conversation history across multiple interactions. Instead of treating every request independently, Spring AI injects previous messages back into the prompt so the LLM understands the ongoing context of the conversation.

Because of ChatMemory, AI systems can:

- Remember previous discussions
- Maintain conversation continuity
- Understand user preferences
- Generate context-aware responses
- Build personalized AI experiences
- Support long-running conversations

Example with ChatMemory enabled:

User: My name is Ayush
AI: Nice to meet you

User: I am learning Spring AI
AI: That’s great

User: Suggest a project for me
AI: You can build an AI chatbot using Spring AI and Vector Search.

In this case, the AI understands the earlier discussion and generates a more relevant response.

Spring AI internally stores conversation history and reuses it during future interactions. This makes the AI behave more like a real assistant instead of a simple question-answering system.

Spring AI provides multiple memory strategies depending on the use case.

1. MessageChatMemoryAdvisor

Stores the complete conversation as structured messages.

Best for:
- Real-time chat applications
- AI assistants
- Customer support chatbots

2. PromptChatMemoryAdvisor

Converts previous memory into summarized plain text and appends it to the system prompt.

Best for:
- Token optimization
- Lightweight memory management
- Smaller context windows

3. VectorStoreChatMemoryAdvisor

Stores conversation memory inside vector databases using embeddings. During new requests, it retrieves the most semantically relevant memories.

Best for:
- Long-running conversations
- Enterprise AI systems
- Knowledge-based AI applications
- Semantic memory retrieval

Spring AI also supports multiple storage options for chat memory.

1. InMemoryChatMemoryRepository

Stores memory inside application RAM.

Features:
- Fast
- Simple setup
- Temporary storage

2. JdbcChatMemoryRepository

Stores memory inside relational databases like:
- MySQL
- PostgreSQL
- H2

Features:
- Persistent storage
- Scalable memory handling

3. Vector Databases

Supported vector databases:
- Qdrant
- Pinecone
- Weaviate
- ChromaDB

Used for:
- Semantic search
- Long-term AI memory
- Retrieval-augmented systems

Real-world applications of ChatMemory:

AI Customer Support Systems
AI remembers previous support tickets, customer issues, and ongoing discussions.

AI Coding Assistants
The assistant remembers earlier code discussions, project architecture, and implementation context.

Healthcare AI Systems
Patient interaction history and previous medical discussions can be maintained.

AI Learning Platforms
AI tracks student learning progress, completed topics, and preferred learning patterns.

Enterprise AI Agents
AI agents manage long-running workflows, contextual business operations, and multi-step tasks.

Personal AI Assistants
AI remembers user preferences, schedules, and recurring tasks.

Chat Memory is one of the most important building blocks for creating intelligent and production-ready AI systems.

Without memory:
AI behaves like a new assistant every time.

With ChatMemory:
AI becomes contextual, personalized, and much more human-like.
