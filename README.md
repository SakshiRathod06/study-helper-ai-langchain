<div align="center">

# 🎓 StudyBot — AI Study Assistant

### Powered by LangChain + TypeScript + Groq + LangSmith

An interactive AI-powered study assistant built with LangChain that demonstrates the core concepts required to create modern AI applications using TypeScript.

---

![TypeScript](https://img.shields.io/badge/Language-TypeScript-blue)
![LangChain](https://img.shields.io/badge/Framework-LangChain-green)
![Groq](https://img.shields.io/badge/LLM-Groq-orange)
![LangSmith](https://img.shields.io/badge/Tracing-LangSmith-purple)

</div>

---

# 📖 Project Overview

StudyBot is a simple AI-powered educational assistant developed using LangChain and TypeScript.

The project demonstrates how Large Language Models (LLMs) can be connected to applications using LangChain while implementing:

- Prompt Engineering
- Chains
- Memory
- Context Management
- Agents
- Tools
- LangSmith Tracing

Users can ask educational questions, receive AI-generated explanations, and perform calculations through an agent-driven workflow.

---

# 🚀 Features

✅ AI-powered study assistant

✅ Prompt templates using LangChain

✅ Conversation memory

✅ Context-aware responses

✅ Agent-based tool selection

✅ Calculator tool integration

✅ Groq LLM integration

✅ LangSmith tracing and debugging

✅ TypeScript implementation

---

# 📸 Demo Screenshots

<img width="1792" height="873" alt="Responce1" src="https://github.com/user-attachments/assets/80ce89dd-3c05-42a0-8934-6479c5374e37" />


<img width="1813" height="791" alt="Responce2" src="https://github.com/user-attachments/assets/74da88e5-ef67-4497-943e-1e2de002e253" />


# 🤔 What Problem Does LangChain Solve?

Large Language Models are powerful but difficult to manage directly.

Without LangChain, developers must manually handle:

- Prompt creation
- Memory management
- Context passing
- Tool calling
- Agent decisions
- Output processing

LangChain provides a structured framework that simplifies these tasks and allows developers to build scalable AI applications faster.

---

# 💡 Why Developers Use LangChain

Developers use LangChain because it offers:

### Prompt Management

Reusable prompt templates.

### Memory Support

Maintains conversation history.

### Tool Integration

Allows AI systems to use external tools.

### Agents

Enables AI to decide which action to take.

### Context Handling

Provides additional information to models.

### Multi-Step Workflows

Supports complex AI pipelines.

---

# 🏗 Project Architecture

```text
User Input
    │
    ▼
Prompt Template
    │
    ▼
Conversation Memory
    │
    ▼
Groq LLM
    │
    ▼
Generated Response
    │
    ▼
Agent
    │
    ▼
Tool Execution
    │
    ▼
Final Output
```

---

# 📂 Project Structure

```text
studybot/

│
├── src/
│   ├── index.ts
│   ├── model.ts
│   ├── chain.ts
│   ├── memory.ts
│   ├── tools.ts
│   ├── agent.ts
│   └── test.ts
│
├── .env
├── package.json
├── tsconfig.json
└── README.md
```

---

# ⚙ Technologies Used

| Technology | Purpose |
|------------|----------|
| TypeScript | Programming Language |
| LangChain | AI Framework |
| Groq | LLM Provider |
| LangSmith | Tracing & Debugging |
| Node.js | Runtime |
| dotenv | Environment Variables |

---

# 🔑 Environment Setup

Create a `.env` file:

```env
GROQ_API_KEY=YOUR_GROQ_API_KEY

LANGCHAIN_TRACING_V2=true

LANGCHAIN_API_KEY=YOUR_LANGSMITH_API_KEY

LANGCHAIN_PROJECT=StudyHelper
```

---

# 📦 Installation

Clone repository:

```bash
git clone <repository-url>
```

Move into project:

```bash
cd studybot
```

Install dependencies:

```bash
npm install
```

---

# ▶ Running the Project

Start application:

```bash
npm run dev
```

Example:

```bash
You: What is LangChain?
```

---

# 🔗 Model Connection

The application connects to Groq using LangChain.

Example:

```ts
import { ChatGroq } from "@langchain/groq";

export const model = new ChatGroq({
  model: "llama-3.1-8b-instant",
  temperature: 0.7,
});
```

The model receives prompts and generates responses.

---

# 📝 Prompt Flow

Prompt templates define how the AI behaves.

Example:

```ts
const prompt = ChatPromptTemplate.fromTemplate(`
You are StudyBot.

History:
{history}

Question:
{question}
`);
```

Flow:

```text
User Question
      ↓
Prompt Template
      ↓
LLM
      ↓
Response
```

---

# 🧠 Memory Handling

Memory stores previous conversation history.

Example:

```ts
const messages: string[] = [];

export function saveMessage(
  role: string,
  message: string
){
  messages.push(`${role}: ${message}`);
}
```

Benefits:

- Maintains context
- Creates natural conversations
- Improves user experience

---

# 🌍 Context Management

Context helps the AI understand previous interactions.

Example:

```text
User:
Explain recursion

User:
Give another example
```

Because history is stored, the model knows the user is still discussing recursion.

---

# ⛓ Chains in LangChain

Chains connect multiple components together.

Example:

```ts
const chain = prompt.pipe(model);
```

Workflow:

```text
Prompt
   ↓
Model
   ↓
Response
```

Advantages:

- Modular design
- Easy maintenance
- Reusable logic

---

# 🤖 Agents in LangChain

Agents decide which action should be taken.

Instead of always calling the model, the agent can:

- Use tools
- Search information
- Perform calculations
- Execute workflows

Example:

```ts
if(needsMath){
   return calculatorTool.invoke(query);
}
```

---

# 🧰 Tools

StudyBot includes a calculator tool.

Example:

```text
Input:
25 * 45

Output:
1125
```

The agent automatically detects mathematical expressions and invokes the calculator.

---

# 🔍 LangSmith Tracing

LangSmith helps developers inspect every AI execution step.

It records:

- Prompts
- Inputs
- Outputs
- Tool Calls
- Agent Decisions
- Errors

Benefits:

✅ Debug prompt issues

✅ Inspect chain execution

✅ Understand agent workflows

✅ Analyze failures

✅ Improve application quality

---

# Example LangSmith Trace

```text
User Input
      ↓
Prompt Created
      ↓
Model Invoked
      ↓
Response Generated
      ↓
Agent Decision
      ↓
Tool Execution
      ↓
Final Output
```

---

# 🐞 Debugging with LangSmith

Suppose the AI gives an incorrect answer.

LangSmith allows developers to inspect:

1. User Input
2. Generated Prompt
3. Model Response
4. Agent Decision
5. Tool Output

This makes debugging significantly easier.

---

# 📈 Future Improvements

Possible enhancements:

- Web Search Tool
- PDF Question Answering
- File Upload Support
- Vector Database Integration
- Retrieval-Augmented Generation (RAG)
- Multi-Agent Architecture
- Voice Assistant Support
- Document Summarization

---

# 🎯 Learning Outcomes

After completing this project, students will understand:

- What LangChain is
- Why LangChain is useful
- How LLM applications work
- Prompt Engineering
- Memory Systems
- Context Management
- Chains
- Agents
- Tools
- LangSmith Tracing

---

# ✅ Conclusion

StudyBot demonstrates the fundamentals of building AI applications using LangChain and TypeScript.

The project integrates prompts, memory, chains, agents, tools, and LangSmith tracing into a single application, providing a practical introduction to modern AI development workflows.

It serves as a strong foundation for building more advanced applications such as document assistants, customer support bots, research assistants, and Retrieval-Augmented Generation (RAG) systems.
