# Building AI Agents with n8n: Complete Learning Guide
## Week 1: Days 1-4

---

## Table of Contents

1. [Introduction](#introduction)
2. [Day 1: Getting Started](#day-1-getting-started)
3. [Day 2: Understanding Agentic AI](#day-2-understanding-agentic-ai)
4. [Day 3: Integrations - Google Services](#day-3-integrations-google-services)
5. [Day 4: Data, JSON, and Advanced Integrations](#day-4-data-json-and-advanced-integrations)
6. [Day 5: Business Project - Portfolio Rebalancer](#day-5-business-project-portfolio-rebalancer).

---

## Introduction

### Course Overview

This is a hands-on, practical course designed to help you build AI agents that deliver real business value in just three weeks. Whether you're technical or completely non-technical, you'll be creating powerful workflow automation systems using n8n.

**Course Philosophy:**
- **Action-first learning**: Build first, understand later
- **Business impact focused**: Every project solves real problems
- **Inclusive approach**: Works for all skill levels

### Three-Week Structure

The course follows a clear progression:

**Week 1: Automate**
- Focus: Using n8n Cloud to create workflows for your business
- Goal: Build foundational automation skills

**Week 2: Accelerate**
- Focus: Add voice agents and RAG (Retrieval Augmented Generation)
- Goal: Level up your automation capabilities

**Week 3: Amplify**
- Focus: Multi-agent systems and MCP (Model Context Protocol)
- Goal: Scale your business with advanced AI systems

### Who This Course Is For

**Two Primary Personas:**

1. **Business and Product People**
   - Want to work with cutting-edge generative AI
   - Need to build products with business impact
   - Don't want to write code
   - Can deliver value immediately

2. **AI Engineers**
   - Want to rapidly deliver business functionality
   - Need to work collaboratively with non-technical stakeholders
   - Want to build systems clients can maintain
   - Can prototype in minutes instead of days

**Important**: The course works for everyone on the technical spectrum, from complete beginners to experienced programmers.

### What You'll Achieve

By the end of this course, you will:

- Create AI agents and voice agents that solve real business problems
- Be able to apply for jobs involving AI agent development
- Build automation, acceleration, and amplification systems
- Have a portfolio of practical, working projects

### Instructor Background

**Ed Donner**
- Co-founder & CTO of Nebula (AI startup)
- Former Managing Director at JP Morgan (led 300+ engineers and data scientists)
- Co-founder & CEO of Untapped (AI startup, acquired)
- 300,000+ students across 190 countries
- Focus: Practical AI implementation, not theory

---

## Day 1: Getting Started

### Instant Gratification: Building Your First AI Agent

The course starts with immediate action - building a working AI agent in minutes.

#### Step 1: Setting Up OpenRouter

**What is OpenRouter?**
- A platform providing access to multiple AI models
- Offers both free and paid models
- Acts as a gateway to various AI providers
- Great for experimentation and learning

**Setup Process:**

1. **Create an Account**
   - Go to `openrouter.ai`
   - Click "Sign Up"
   - Use Google Auth or email/password
   - Accept terms and conditions

2. **Generate Your API Key**
   - Upon first login, you'll be prompted to create an API key
   - Give it a name (e.g., "n8n Integration")
   - Leave limit blank (no spending limit needed for free models)
   - Copy the key to clipboard
   - **Important**: Store it somewhere safe
   - The key starts with `sk-or-`

3. **Alternative Method**
   - Click your avatar (top right)
   - Select "Keys"
   - Click "Create API Key"
   - Can create multiple keys as needed

**Free Model Selection:**
- In OpenRouter, use the search box
- Type "free" to see all free models
- Recommended starting point: OpenAI GPT-4o mini (open source version)
- Model string: `openai/gpt-4o-20b:free`

#### Step 2: Setting Up n8n Cloud

**What is n8n?**
- Workflow automation platform
- Founded in Berlin (2019)
- Now a multibillion-dollar company
- Millions of users worldwide
- Makes AI and integrations incredibly simple

**n8n Modes:**

1. **n8n Cloud** (What we'll use first)
   - Managed installation
   - Quick setup
   - 14-day free trial
   - Then $24/month (or $20/month annually)

2. **Self-Hosted** (Week 3)
   - Download and run yourself
   - Completely free
   - Requires more technical setup
   - "Fair Code" license (not open source)

3. **White Label** (Enterprise)
   - Embed n8n in your products
   - Contact for commercial terms

**Fair Code License Explained:**

✅ **You CAN:**
- Use n8n for free (self-hosted)
- Build workflows for your business
- Create client projects
- Sell your services using n8n
- Modify the code

❌ **You CANNOT:**
- Sell n8n itself as a product
- Build a competing platform
- Resell modified versions of n8n

**Setting Up Your Account:**

1. **Initial Setup**
   - Go to `n8n.io`
   - Click "Get Started"
   - Enter your name, email, and password
   - Choose a screen name
   - Optionally subscribe to newsletter
   - Click "Start 14 Day Free Trial"

2. **Complete Profile**
   - Company size (can select "Only me")
   - Team (e.g., "Engineering")
   - Company description
   - How you heard about n8n
   - Skip team member invitations (for now)

3. **Wait for Workspace**
   - System will start your workspace
   - You'll see "Workspace is online"
   - Click "Start automating"

#### Step 3: Building Your First Workflow

**Understanding the Interface:**

When you first enter n8n, you'll see:
- Welcome screen
- "Create your first workflow" button
- Clean, intuitive canvas

**Three Hierarchy Levels:**

1. **Cloud Level**
   - Account/dashboard screen
   - URL: `app.n8n.cloud`
   - Manage billing, settings, instances

2. **Instance Level**
   - Your running n8n engine
   - Home/Overview screen
   - URL: `[your-instance].n8n.cloud/workflows`
   - Contains all your workflows

3. **Workflow Level**
   - Individual automation process
   - Editor/Canvas screen
   - URL: `[your-instance].n8n.cloud/workflow/[id]`
   - Where you build

**Creating Your First Workflow:**

1. **Start from Scratch**
   - Click "Start from scratch" or "New workflow"
   - You'll see the editor/canvas
   - Empty workspace ready for building

2. **Add First Node (Trigger)**
   - Click "Add first step"
   - Panel appears on right showing triggers
   - Select "On chat message"
   - Press Escape or click "Back to canvas"
   
   **Pro tip**: The Escape key is your friend - use it constantly

3. **Add AI Agent Node**
   - Click the + button to the right of the trigger
   - Navigate to: AI → AI Agent
   - Press Escape to return to canvas
   - You can drag nodes to reposition them

4. **Configure Chat Model**
   - Click + under "Chat model" in the AI Agent
   - Search for "Open Router"
   - Select "Open Router Chat Model"
   - Click "Create new credential"
   - Paste your OpenRouter API key
   - Click Save
   - Should show green "Connection tested successfully"
   - Click X to close

5. **Select Your Model**
   - In model dropdown, search for your chosen model
   - Type: `openai/gpt-4o-20b:free`
   - Select it
   - Press Escape to return

6. **Test Your Agent**
   - Click "Open chat" button
   - Type: "Hi there"
   - Watch the spinning indicator
   - Response appears: "Hey, how can I help you today?"

**Congratulations!** You've just built your first AI agent without writing a single line of code!

### Understanding What You Built

**Key Concept**: You didn't just use ChatGPT - you built your own ChatGPT-like system with a workflow architecture that can be expanded infinitely.

**Components of Your Workflow:**

1. **Trigger Node** (On chat message)
   - Starts the workflow
   - Captures user input

2. **AI Agent Node**
   - Orchestrates the AI interaction
   - Can be equipped with tools
   - Manages conversation flow

3. **Chat Model**
   - The actual LLM (Large Language Model)
   - Accessed through OpenRouter
   - Generates responses

**Why This Matters:**
- You can switch AI models easily
- You can add integrations and services
- You can orchestrate complex workflows
- All through a visual interface
- Takes minutes, not hours or days

---

## Foundational Concepts

### What is a Large Language Model (LLM)?

**Core Definition:**
An LLM is a data science model that:
- Takes text input (a prompt)
- Generates text output
- Works through pattern matching at massive scale

**Important Reality Check:**

LLMs are **NOT**:
- Conscious or self-aware
- Actually "thinking" or "reasoning"
- Remembering previous conversations (natively)
- Capable of independent action

LLMs **ARE**:
- Powerful statistical programs
- Excellent pattern matchers
- Trained on massive amounts of internet data
- Very good at predicting likely text sequences

**How They Work:**

1. **Training Phase**
   - Given tons of text data from the internet
   - Analyze patterns in the data
   - Build statistical model (trillions of parameters)

2. **Inference Phase**
   - Given input text
   - Predict most likely text to follow
   - Generate output based on patterns

**Key Insight**: The "intelligence" is emergent - it's a byproduct of massive scale, not actual understanding.

### GPT (Model) vs ChatGPT (Product)

This is a crucial distinction many people miss:

**GPT (The Model):**
- A Large Language Model
- The underlying AI engine
- Stateless (no memory between calls)
- Takes input → Generates output
- That's it. Nothing more.

**ChatGPT (The Product):**
- Software built by OpenAI
- Uses GPT model underneath
- Adds memory through clever engineering
- Can search the web
- Has a user interface
- Manages conversation context

**Your n8n Workflow:**
- Is like ChatGPT (a product)
- Uses an LLM (the model)
- Adds functionality on top
- Manages the conversation

### What is an API?

**Simple Definition:**
A way to connect different applications and services.

**More Technical Definition:**
- Application Programming Interface
- Standard way for software to talk to software
- Usually over HTTP (web protocol)
- Exchanges data in JSON format

**How APIs Work:**

1. **Your Application** sends a request
2. To an **Endpoint** (URL)
3. Using **HTTP** (web protocol)
4. Passing **Data** (usually JSON)
5. With **Authentication** (API key)
6. Receives **Response** (usually JSON)

**API Key:**
- Like a password
- Identifies you to the service
- May be tied to billing
- Keep it secret and safe

**Common API Standards:**
- REST APIs (most common)
- HTTP methods: GET, POST, PUT, DELETE
- JSON data format
- OAuth for authentication

---

## Understanding AI Agents

### Evolution of the Definition

The term "AI Agent" has evolved significantly:

**Phase 1: Independent Work (2023-early 2024)**
- Definition: "Systems that can do work for you independently"
- Example: OpenAI's Operator/ChatGPT agent
- Could perform tasks like making restaurant reservations
- Autonomous execution

**Phase 2: LLM Controls Workflow (Early 2024)**
- Definition: "Where an LLM orchestrates the workflow"
- LLM decides: Do A, then B, then C (or different order)
- LLM-driven decision making
- Influenced by Anthropic's research

**Phase 3: Current Definition (2025)**
- Definition: "An LLM that runs tools in a loop to achieve a goal"
- Most specific and practical
- Focus on tool usage
- Goal-oriented behavior

**Practitioner's View:**
For this course, an AI agent is any workflow using n8n's AI Agent node, but true agentic behavior requires:
- Tools
- Loop execution
- Goal achievement

### What Makes n8n Special?

**Two Major Strengths:**

1. **AI Integration**
   - AI woven throughout the platform
   - Easy to create agents
   - Visual workflow design
   - No coding required

2. **Third-Party Integrations**
   - Historically one of the hardest parts of software
   - n8n makes it "magical"
   - Hundreds of pre-built integrations
   - Simple authentication

**Comparison to Alternatives:**
- Similar to Zapier (but better for AI)
- More flexible than no-code tools
- Less complex than pure coding
- Perfect middle ground

---

## Setting Up OpenAI (Optional)

### Why OpenAI?

**Advantages:**
- Industry standard
- Widely recognized by employers/clients
- High quality models
- Good documentation

**Disadvantages:**
- Requires $5 minimum deposit
- Not completely free
- Can stick with OpenRouter instead

### OpenAI Setup Process

**Important Distinction:**
- `platform.openai.com` = API access (what we want)
- `chat.openai.com` = ChatGPT product (different)

**Step-by-Step:**

1. **Create Account**
   - Go to `platform.openai.com`
   - Click "Sign up"
   - Use Google/Apple/Microsoft Auth or email
   - Answer initial questions (organization, role, etc.)

2. **Create API Key**
   - Go to Settings → API Keys
   - Click "Create new secret key"
   - Name it (e.g., "n8n integration")
   - Select "Default project"
   - All permissions
   - Copy key immediately
   - Store safely
   - Begins with `sk-`

3. **Add Billing**
   - Go to Settings → Billing
   - Click "Add payment details"
   - Add credit card
   - Add $5 minimum balance
   - **Important**: Turn OFF auto-reload
   - May take time to clear (country-dependent)

4. **Monitor Usage**
   - Go to Settings → Usage
   - Track spending against $5
   - Very cheap for learning (fractions of a cent per call)
   - Good practice: Check regularly

**Cost Management:**
- Only add what you're comfortable losing
- Check usage frequently
- Turn off auto-reload
- Most course work costs pennies

### Free Alternatives

**OpenRouter** (Recommended Free Option)
- ✅ Completely free tier
- ✅ Access to multiple models
- ✅ No credit card required
- ❌ Rate limits on free models
- ❌ May need to wait between calls

**Anthropic Claude**
- ✅ High quality
- ✅ Good free tier
- ✅ Instructor's personal favorite

**Google Gemini**
- ✅ Good free tier
- ✅ Access through AI Studio
- ✅ Fast and capable

**Bottom Line:** All models work the same way in n8n. Pick what you're comfortable with.

---

## Day 2: Understanding Agentic AI

### The Philosophy Behind Agentic AI

**Core Principle:**
Most of the "magic" in Agentic AI comes down to clever prompting and understanding how LLMs actually work.

**What We'll Cover:**
- Five key "tricks" that make AI agents work
- One common "trap" to avoid
- How to think about AI agents correctly

### The Five Tricks of Agentic AI

#### Trick #1: The Illusion of Memory

**The Problem:**
LLMs are stateless - every call is fresh with no memory.

**Example:**
```
Prompt 1: "My name is Ed"
Response: "Hi, Ed"

Prompt 2: "What's my name?"
Response: "I don't know your name"
```

**The Solution:**
Send the entire conversation history with each call.

**How It Works:**

Instead of sending just: `"What's my name?"`

Send the full history:
```
My name is Ed
Hi, Ed
What's my name?
```

The LLM predicts what comes next based on this full context: `"Your name is Ed"`

**Why This Works:**
- LLMs were trained on conversational data
- They expect message-response patterns
- They generate text consistent with full context
- Creates the "illusion" of memory

**In ChatGPT:**
Every time you press enter, ChatGPT sends the entire conversation to GPT, which generates the next response.

**In n8n:**
The "Simple Memory" node handles this automatically.

#### Trick #2: Thinking and Reasoning

**The Discovery:**
Adding "Please think step by step" to prompts produces better results.

**Chain of Thought:**
- Early technique (2023)
- Ask LLM to describe its thought process
- Then generate the final answer
- Improves accuracy significantly

**Reasoning Models:**
- Specially trained to think before answering
- Generate "thinking trace" before final output
- Models like GPT-4.1, Claude Opus
- Better for complex problems

**How It Actually Works:**

LLMs generate text token by token (small chunks):
1. Generate first token
2. Add it to input
3. Generate next token
4. Repeat

When generating reasoning:
1. Generate tokens describing thought process
2. Those tokens become part of input
3. Final answer tokens are consistent with reasoning
4. Results in better outcomes

**Example Problem:**
```
Question: "Toss two coins. One is heads. 
          What's the chance the other is tails?"

Without reasoning: "50%" (WRONG)

With reasoning:
- "Wait, this is tricky"
- "Four possibilities: HH, HT, TH, TT"
- "We know one is heads, eliminates TT"
- "Leaves HH, HT, TH - two have tails"
- "Answer: 2/3" (CORRECT)
```

**Reasoning Budget:**
Some models let you control how long they think:
- None (chat mode)
- Minimal
- Low
- Medium
- High

**The Hacky Secret:**
To extend thinking, systems insert words like "Wait..." into the token stream, forcing the model to reconsider and explore more.

**When to Use:**

**Reasoning Models Good For:**
- Complex problems
- Novel situations
- When accuracy is critical

**Chat Models Good For:**
- Simple tasks
- Agentic workflows (already step-by-step)
- Speed is important

**Best Practice:** Experiment with both and measure results.

#### Trick #3: Chaining LLMs

**The Concept:**
Instead of one complex prompt, use multiple simple prompts in sequence.

**Example:**

**Single Prompt (Less Control):**
```
"Come up with a puzzle and then solve it"
```
- LLM has full autonomy
- Might create 2 puzzles, or skip solving
- Less predictable

**Chained Prompts (More Control):**
```
Prompt 1: "Come up with a hard puzzle"
→ Response: [puzzle]

Prompt 2: "Solve this puzzle: [puzzle]"
→ Response: [solution]
```

**Benefits:**
- More control over each step
- Can test each LLM call independently
- Easier to debug
- More consistent results

**Visual Representation:**
In n8n, this appears as separate nodes connected in sequence.

**Use Cases:**
- Content generation then editing
- Analysis then summarization
- Question generation then answering
- Multi-step reasoning

#### Trick #4: Tools (Tool Calling)

**The Illusion:**
It seems like LLMs can use tools, connect to APIs, and take actions.

**The Reality:**
LLMs only generate text. They can't actually DO anything.

**How Tool Calling Actually Works:**

**What Seems to Happen:**
```
User: "What's the stock price of Google?"
LLM: [connects to API, gets data]
LLM: "The stock price is $150"
```

**What Really Happens:**

**Step 1: Modified Prompt**
```
You can either:
A) Respond with an answer, OR
B) Request to use a tool

Available tools:
- look_up_stock_price(ticker)

User question: What's the stock price of Google?
```

**Step 2: LLM Response**
```
USE TOOL: look_up_stock_price("GOOGL")
```

**Step 3: System Executes Tool**
```
[System calls API, gets: $150]
```

**Step 4: Second LLM Call**
```
You can either respond with answer or use tool.

Available tools: look_up_stock_price(ticker)

Previous exchange:
User: What's the stock price of Google?
Assistant: USE TOOL: look_up_stock_price("GOOGL")
Tool result: $150

Now respond to user.
```

**Step 5: Final Response**
```
"The stock price of Google is $150"
```

**Key Insight:** It's all done through clever prompting and interpreting LLM output!

**You Can Test This:**
In ChatGPT, try:
```
You are a support agent. You answer questions,
or use tool to fetch ticket price for [city].

User: I'd like to go to Paris. How much is a flight?
```

ChatGPT will respond: `USE TOOL to fetch ticket price for Paris`

**In n8n:**
Tools are configured visually:
- Select tool (e.g., Google Sheets, Market Stack)
- Configure what the tool can do
- LLM automatically learns to use it

#### Trick #5: The Agent Loop

**The Concept:**
LLM calls tools repeatedly in a loop until the goal is achieved.

**Example Scenario:**

**Goal:** Find the current value of my portfolio

**Available Tools:**
1. retrieve_portfolio()
2. look_up_share_price(ticker)

**The Loop:**

**Iteration 1:**
```
Prompt: "Find value of my portfolio.
        Tools: retrieve_portfolio, look_up_share_price"

LLM: "USE TOOL: retrieve_portfolio"
Result: "3 shares of Google"
```

**Iteration 2:**
```
Prompt: "Find value of my portfolio.
        Previous: Retrieved portfolio (3 Google shares)
        Tools: retrieve_portfolio, look_up_share_price"

LLM: "USE TOOL: look_up_share_price(GOOGL)"
Result: "$150 per share"
```

**Iteration 3:**
```
Prompt: "Find value of my portfolio.
        Previous: 3 Google shares @ $150
        Tools: retrieve_portfolio, look_up_share_price"

LLM: "The value of your portfolio is $450"
[No tool call - we're done!]
```

**This is Agentic AI:**
- LLM running tools
- In a loop
- To achieve a goal

**Key Points:**
- Each call includes full history (Trick #1: Memory)
- LLM decides what to do next
- Continues until task is complete
- All through text generation and interpretation

### The One Trap: Anthropomorphization

**The Human Trap:**
Treating LLMs as if they were human team members.

**Common Mistake:**

People create "agent architectures" with roles:
- "Researcher Agent" - gathers information
- "Analyst Agent" - analyzes data
- "Writer Agent" - creates content
- "Reviewer Agent" - checks quality

**Why This Is Problematic:**

**Remember:** LLMs are good at generating realistic-sounding content.

If you say: "You are a reviewer. Rate this work 1-10 and explain why."

The LLM will:
- ✅ Generate a rating (e.g., "7/10")
- ✅ Generate a realistic explanation
- ❌ Not actually evaluate quality
- ❌ Not align with your true objectives

**The Danger:**
- Looks like it's working
- Sounds convincing
- Might be completely wrong
- Could be "LLM slop" (plausible nonsense)

**The Right Way:**

**Don't:** Assign roles because they sound right

**Do:** Divide tasks because it improves measurable outcomes

**Process:**
1. Start simple (one agent)
2. Try dividing the task
3. **Measure results** (this is key!)
4. Keep changes that improve performance
5. Discard changes that don't help

**The Magic Word: Evaluate**

You MUST have:
- Clear success metrics
- Objective evaluation
- Experimental approach
- Measurement-driven decisions

**Example:**

❌ Wrong: "I need a researcher and analyst because that's how humans work"

✅ Right: "I tried splitting research and analysis - accuracy improved from 75% to 85%"

**Bottom Line:**
- Be scientific, not anthropomorphic
- Measure everything
- Let data guide your architecture
- Don't assume human organizational patterns work for AI

---

## Navigating n8n

### The Three Levels of Hierarchy

Understanding where you are in n8n is crucial:

#### Level 1: Cloud Dashboard (Admin Panel)

**What It Is:**
- Account-level view
- Billing and settings
- Instance management

**URL Pattern:** `app.n8n.cloud`

**What You See:**
- Your plan details
- Days left in trial
- Billing information
- Export options
- Running instances

**How to Access:**
- Sign in to n8n.cloud
- This is your first view
- Or click "Admin Panel" from inside instance

#### Level 2: Instance Home (Overview)

**What It Is:**
- Your running n8n engine
- List of all workflows
- Execution history
- Templates

**URL Pattern:** `[your-name].n8n.cloud/workflows`

**What You See:**
- Workflow list
- Execution statistics
- Projects
- Templates
- AI features

**Navigation:**
- From dashboard: Click "Open Instance"
- From workflow: Click project name or "Overview"

#### Level 3: Workflow Editor (Canvas)

**What It Is:**
- Individual workflow editing
- Where you build automations
- Visual workflow design

**URL Pattern:** `[your-name].n8n.cloud/workflow/[id]`

**What You See:**
- Canvas (main workspace)
- Nodes (workflow steps)
- Execution panel
- Chat interface (for AI agents)

**Navigation:**
- From home: Click "Create Workflow" or select existing workflow
- Between workflows: Click project name to go back

### Essential Keyboard Shortcuts

**Master These:**

- **Escape**: Close panels, return to canvas
- **Tab**: Open node list
- **+**: Zoom in
- **-**: Zoom out
- **0**: Reset zoom
- **Ctrl/Cmd + S**: Save workflow
- **Ctrl/Cmd + Click-Drag**: Pan around canvas

### Key Terminology

**Node:**
- A single step in your workflow
- Visual building block
- Two types: Triggers and Actions

**Trigger:**
- Starts a workflow
- Examples: On chat message, On schedule, On webhook
- Always the first node

**Action:**
- Does something in the workflow
- Examples: AI Agent, Send email, Update spreadsheet
- Comes after trigger

**Connection (Connector):**
- Links nodes together
- Passes data from one node to another
- Shown as lines between nodes

**Workflow:**
- Collection of nodes + connections
- Represents one business process
- Can be active (running) or inactive (testing)

**Execution:**
- One run of a workflow
- Can be manual (testing) or automatic (active)
- History is preserved

**Template:**
- Pre-built workflow
- Starting point for your work
- Community-contributed

### Working in the Editor

**Basic Operations:**

1. **Adding Nodes**
   - Click + button
   - Or press Tab
   - Search for node type
   - Click to add

2. **Connecting Nodes**
   - Drag from + on one node
   - Drop on another node
   - Or click + between nodes

3. **Moving Nodes**
   - Click and drag
   - Arrange for clarity
   - Use "Tidy Up" button

4. **Configuring Nodes**
   - Double-click node
   - Or single click then click details
   - Configure settings
   - Press Escape when done

5. **Deleting Nodes**
   - Select node
   - Press Delete/Backspace
   - Or click trash icon

**Pro Tips:**
- Use Escape constantly
- Organize nodes left-to-right
- Group related nodes visually
- Name workflows descriptively
- Save frequently (Ctrl/Cmd + S)

---

## Building Your First Complete Agent

### Adding Memory to Your Agent

**What Memory Does:**
- Stores conversation history
- Passes history to LLM with each call
- Creates illusion of continuous conversation

**How to Add:**

1. In AI Agent node, click + under "Memory"
2. Select "Simple Memory"
3. Press Escape

**That's it!** Now your agent remembers the conversation.

### Adding a System Prompt

**What is a System Prompt?**
- Sets the context for the LLM
- Defines its role and behavior
- Provides background information
- Sets the tone

**How to Add:**

1. Double-click AI Agent node
2. Click "Add Option"
3. Select "System Message"
4. Enter your prompt

**Example System Prompts:**

**Helpful Assistant:**
```
You are a helpful assistant who provides clear,
accurate information and helps users accomplish
their goals.
```

**Snarky Assistant:**
```
You are a snarky, humorous assistant that makes
fun of whoever you are chatting with in a playful way.
```

**Domain Expert:**
```
You are a financial advisor specializing in stock
portfolio management. Provide professional advice
based on current market data.
```

### Adding Tools

**What Are Tools?**
- External capabilities for your agent
- APIs the agent can call
- Data sources it can access

**Example Tool: Market Stack (Stock Prices)**

**Setup Process:**

1. **Get API Key**
   - Sign up at marketstack.com
   - Get free API key
   - Copy to clipboard

2. **Add Tool to Agent**
   - Click + under "Tool" in AI Agent
   - Search "Market Stack"
   - Select it

3. **Configure Authentication**
   - Click "Create new credential"
   - Paste API key
   - Click Save
   - Should turn green

4. **Configure Tool**
   - Resource: "End of day"
   - Operation: "Get many"
   - Ticker: Click "Let model define"
   - Add filter: "Latest" = Yes

5. **Test It**
   - In chat: "What's the stock price of Google?"
   - Watch agent use the tool
   - See real stock price returned

**How It Works Behind the Scenes:**

1. Your question goes to LLM
2. LLM is told about available tools in system prompt
3. LLM responds: "USE TOOL: market_stack(GOOGL)"
4. n8n executes the tool
5. Result goes back to LLM
6. LLM formats response for user

### Viewing Execution Details

**Why It's Important:**
- Understand what's happening
- Debug issues
- Learn how agents work

**How to View:**

1. **Editor vs Executions Tab**
   - Bottom of screen
   - Switch between them
   - See all runs

2. **Inspect Individual Nodes**
   - Double-click any node in execution
   - See input (left side)
   - See output (right side)
   - View in JSON or Table format

3. **Multiple Tool Calls**
   - Dropdown shows "1 of 3" etc.
   - Click through each execution
   - See exactly what was called

**What to Look For:**

- **System Prompt**: Full context sent to LLM
- **User Messages**: Conversation history
- **Tool Calls**: Which tools were requested
- **Tool Results**: What data came back
- **Final Response**: What user sees

**Pro Tip:** Examine failed executions to understand errors!

---

## Day 3: Integrations - Google Services

### The Power of Integrations

**Why Integrations Matter:**

Historically, connecting different software systems has been:
- Extremely difficult
- Time-consuming
- Error-prone
- Expensive to maintain

**n8n Changes This:**
- Makes integrations simple
- Often just a few clicks
- Visual configuration
- Handles authentication

### Important Integration Principles

**You Are In Control:**

✅ **You Decide:**
- Which integrations to use
- What to spend money on
- How to configure access
- Which alternatives to try

❌ **You Don't Have To:**
- Follow my exact examples
- Use paid services
- Spend any money
- Stick to my script

**Integration Challenges:**

**Be Prepared For:**
- Some frustration
- Trial and error
- Reading documentation
- Multiple attempts

**Common Issues:**
- API keys copied wrong
- Text editor changing characters
- Authentication timing out
- Permissions not set correctly

**Survival Guide:**

1. **If It Fails:**
   - Try again (2-3 times normal)
   - Read the error messages
   - Check the documentation
   - Create new API key

2. **If Still Stuck:**
   - Post in course forum
   - Include screenshots
   - Describe exact steps
   - Check community solutions

3. **If All Else Fails:**
   - Try a different integration
   - n8n has hundreds of options
   - One will work for you

### Google Drive Integration

**Why Google Drive?**
- Nearly universal (most people have Gmail)
- Free (for personal use)
- Easy authentication with n8n Cloud
- Great for learning

**If You Don't Have It:**
- Consider setting up free Gmail account
- Google Workspace (business) also works
- Alternative: Use Microsoft OneDrive, Dropbox, etc.

### Building Stock Portfolio Tracker

This project demonstrates:
- Reading from Google Sheets
- Using external API (Market Stack)
- Writing back to Google Sheets
- Agent coordinating multiple tools

**Project Overview:**

**Goal:** Agent reads portfolio, gets stock prices, updates sheet

**Components:**
1. Google Sheet with portfolio
2. AI Agent
3. Market Stack API
4. Tools to read/write sheets

#### Step 1: Create the Google Sheet

**Setup:**

1. Go to Google Drive (drive.google.com)
2. Create folder (optional): "n8n Projects"
3. Create new Google Sheet
4. Name it: "Portfolio"

**Sheet Structure:**

| Ticker | Quantity | Price |
|--------|----------|-------|
| GOOGL  | 3        |       |
| AAPL   | 2        |       |
| TSLA   | 3        |       |

**Note:** Leave Price column empty - agent will fill it!

#### Step 2: Build the Workflow

**Basic Structure:**

1. On Chat Message (trigger)
2. AI Agent
3. Simple Memory
4. OpenAI Chat Model (or Open Router)
5. Three Tools:
   - Google Sheets (read)
   - Market Stack (get prices)
   - Google Sheets (update)

**Detailed Steps:**

**1. Create Workflow**
- New workflow
- Name: "Stock Portfolio Updater"

**2. Add Trigger**
- Add first step
- Select: On Chat Message

**3. Add AI Agent**
- Click + after trigger
- Navigate: AI → AI Agent

**4. Add Memory**
- Click + under Memory
- Select: Simple Memory

**5. Add Chat Model**
- Click + under Chat Model
- Select: OpenAI Chat Model (or your choice)
- Use existing credential

#### Step 3: Add Google Sheets Read Tool

**Authentication (n8n Cloud):**

**The Easy Way:**
1. Click + under Tool
2. Search: "Google Sheets"
3. Select: Google Sheets tool
4. Credential: Click "Create new credential"
5. Click: "Sign in with Google"
6. Select your Google account
7. Click: "Continue" to grant permissions
8. See: "Account connected" (green)
9. Click: X to close

**Congratulations!** That's OAuth 2.0 done in seconds!

**Tool Configuration:**

**Resource:** Sheet within a document
**Operation:** Get rows
**Document:** Select "Portfolio" from dropdown
**Sheet:** Select "Sheet1"

**How It Works:**
- n8n Cloud has pre-configured OAuth with Google
- You just sign in with your Google account
- n8n gets permission to access your sheets
- No API keys to manage!

#### Step 4: Add Market Stack Tool

**Setup:**

1. Click + to add another tool
2. Search: "Market Stack"
3. Select it
4. Use existing credential (from Day 2)
5. Resource: "End of day"
6. Operation: "Get many"
7. Ticker: Click purple "Let model define" button
8. Add filter: Latest = Yes

#### Step 5: Add Google Sheets Update Tool

**Setup:**

1. Click + to add third tool
2. Search: "Google Sheets" again
3. Select: Google Sheets tool
4. Credential: Select existing (already authenticated!)
5. Resource: "Sheet within a document"
6. Operation: "Update row"
7. Document: Select "Portfolio"
8. Sheet: Select "Sheet1"

**Critical Configuration:**

**Column to Match On:** Ticker
- This is how it knows which row to update

**Values to Update:**
- Remove "Quantity" (uncheck it)
- Keep "Ticker" - click purple "Let model define"
- Keep "Price" - click purple "Let model define"

**What This Means:**
- Agent will match rows by ticker symbol
- Agent can specify which ticker to update
- Agent can set the new price
- Quantity stays unchanged

#### Step 6: Test the Workflow

**Testing Process:**

1. **Arrange Windows**
   - Open Google Sheet in separate window
   - Position next to n8n
   - Watch both simultaneously!

2. **Send Command**
   In chat: 
   ```
   Please update the prices in my equity portfolio 
   sheet to reflect the latest market prices.
   ```

3. **Watch the Magic**
   - Agent thinks
   - Calls Get Rows (reads sheet)
   - Calls Market Stack 3 times (GOOGL, AAPL, TSLA)
   - Calls Update Row 3 times
   - Watch prices populate in real-time!

**Expected Result:**
```
Ticker | Quantity | Price
GOOGL  | 3        | $150.23
AAPL   | 2        | $178.45
TSLA   | 3        | $242.67
```

### Understanding What Happened

**Inspecting Tool Calls:**

**1. Double-Click Update Tool**
- See dropdown: "1 of 3", "2 of 3", "3 of 3"
- Each represents one update

**2. View Input (Left Side)**
```json
{
  "column_to_match": "Ticker",
  "value_to_match": "AAPL",
  "ticker": "AAPL",
  "price": 178.45
}
```

**3. View Output (Right Side)**
```json
{
  "success": true,
  "updated": {
    "ticker": "AAPL",
    "price": 178.45
  }
}
```

**Switching Between Views:**
- JSON: Raw data structure
- Table: Formatted for humans
- Schema: Data structure definition

**Learn from This:**
- Each tool call is logged
- You can see exact inputs/outputs
- Great for debugging
- Helps understand agent behavior

### Gmail Integration

**Project:** Agent reads and drafts email replies

**Safety First:**
Only give agents access to tools you're comfortable with!

**Best Practice:**
- Start with read-only access
- Test thoroughly
- Add write access cautiously
- Use drafts before sending

#### Step 1: Create Workflow

1. New workflow
2. Name: "Email Assistant"
3. Add: On Chat Message trigger
4. Add: AI Agent
5. Add: Simple Memory
6. Add: Chat Model

#### Step 2: Add Gmail Read Tool

**Authentication:**
1. Click + under Tool
2. Search: "Gmail"
3. Select: Gmail tool
4. Credential: "Create new credential"
5. Click: "Sign in with Google"
6. Select account
7. Grant all permissions (or just read if preferred)
8. Click: "Continue"
9. See: "Connection successful"

**Tool Configuration:**

**Resource:** Messages
**Operation:** Get many
**Filters:** Received after

**Using Expressions:**

Instead of fixed date, use dynamic:
- Click toggle: "Fixed" → "Expression"
- Enter code:
  ```javascript
  {{ DateTime.now().minus({ days: 1 }) }}
  ```

**What This Does:**
- Uses Luxon library (built into n8n)
- Gets current date/time
- Subtracts one day
- Returns emails from last 24 hours

**Why Expressions Matter:**
- Dynamic values
- Calculated at runtime
- Like Excel formulas
- More powerful than fixed values

#### Step 3: Test Reading Email

**Send Test Email:**
1. Send yourself an email
2. Subject: "Important News"
3. Body: "My agent can read my email! This is huge."

**Test in Agent:**
```
Please read the most recent email I received 
and summarize what it contains.
```

**Expected Response:**
```
The most recent email you received is from 
[Your Name] with the subject "Important News". 
The content indicates exciting news that your 
agent can now read email, which opens up many 
possibilities.
```

**Success!** Your agent can read emails!

#### Step 4: Add Gmail Draft Tool

**Why Drafts?**
- Safer than auto-sending
- You review before sending
- Maintains control
- Good for learning

**Configuration:**

1. Click + to add another tool
2. Search: "Gmail" again
3. Select: Gmail tool
4. Uses same credential (already connected)
5. Resource: "Draft"
6. Operation: "Create"
7. Subject: Click purple "Let model define"
8. Message: Click purple "Let model define"
9. To: Enter your email (FIXED, not model-defined)

**Why Fix the "To" Address?**
Safety! During testing, only allow emails to yourself.

#### Step 5: Test Drafting Reply

**Command:**
```
Please draft an email that says I very much 
agree with this sentiment. This is huge news.
```

**What Happens:**
1. Agent creates draft in Gmail
2. Check your Gmail drafts
3. See drafted reply:

```
Subject: Re: Important News

Hi [Your Name],

I very much agree with your sentiment. This is 
huge news. The possibilities ahead are truly exciting.

Best regards,
[Your Name]
```

**The Telltale Sign:**
Note the em-dash (—) - typical GPT formatting!

### Expanding the Project

**Ideas to Try:**

1. **Add More Columns**
   - 52-week high/low
   - Daily change percentage
   - Market cap

2. **Multiple Sheets**
   - Different portfolios
   - Historical tracking
   - Performance analysis

3. **Scheduled Updates**
   - Change trigger to "Schedule"
   - Run daily at market close
   - Automatic portfolio tracking

4. **Email Notifications**
   - Add Gmail send tool
   - Email when prices update
   - Daily summary reports

---

## Day 4: Data, JSON, and Advanced Integrations

### Understanding JSON

**Why JSON Matters:**
- Universal data format for APIs
- How n8n passes data between nodes
- Human-readable and machine-readable
- Essential for working with integrations

**JSON Stands For:**
JavaScript Object Notation

**But You Don't Need JavaScript:**
- JSON is just a data format
- Used across all programming languages
- Think of it like a structured way to write data

### The Four Building Blocks of JSON

#### 1. Key-Value Pairs

**The Foundation:**
Everything in JSON is a key-value pair.

**Examples:**
```json
"name": "Alice"
"age": 30
"is_student": false
"middle_name": null
```

**Rules:**

**Keys:**
- Always use double quotes (not single)
- No spaces (use underscores: `first_name`)
- Case sensitive

**Values Can Be:**
- Strings (text): `"Alice"` - needs quotes
- Numbers: `30` - no quotes
- Booleans: `true` or `false` - lowercase, no quotes
- null: `null` - represents empty

**Common Mistakes:**

❌ Wrong:
```json
'name': 'Alice'        // Single quotes
"first name": "Alice"  // Space in key
"is_student": False    // Capital F
```

✅ Right:
```json
"name": "Alice"
"first_name": "Alice"
"is_student": false
```

#### 2. Objects

**What Is an Object?**
A collection of key-value pairs wrapped in curly braces `{}`

**Example:**
```json
{
  "name": "Alice",
  "age": 30,
  "is_student": false,
  "middle_name": null
}
```

**Rules:**

- Open with `{`
- Key-value pairs separated by commas
- Last pair has NO comma
- Close with `}`

**Formatting:**

**Expanded (human-readable):**
```json
{
  "name": "Alice",
  "age": 30
}
```

**Compressed (machine-optimized):**
```json
{"name":"Alice","age":30}
```

Both are valid! Machines don't care about whitespace.

**Common Mistake:**

❌ Wrong:
```json
{
  "name": "Alice",
  "age": 30,    // Extra comma!
}
```

✅ Right:
```json
{
  "name": "Alice",
  "age": 30
}
```

#### 3. Arrays

**What Is an Array?**
An ordered list of items wrapped in square brackets `[]`

**Examples:**

**Simple Array:**
```json
["apple", "banana", "orange"]
```

**Mixed Types:**
```json
[1, 2, 3, 5, 8]
```

**Array as Value:**
```json
{
  "favorite_fruits": ["apple", "banana", "orange"]
}
```

**Rules:**
- Open with `[`
- Items separated by commas
- Last item has NO comma
- Close with `]`

**Formatting Options:**

**Horizontal:**
```json
["apple", "banana", "orange"]
```

**Vertical:**
```json
[
  "apple",
  "banana",
  "orange"
]
```

Both valid!

#### 4. Nesting

**The Power of JSON:**
Objects can contain objects, arrays can contain objects, etc.

**Example 1: Object in Object**

**Address object:**
```json
{
  "street": "123 Main St",
  "city": "New York",
  "country": "USA"
}
```

**Person object containing address:**
```json
{
  "name": "Alice",
  "age": 30,
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "country": "USA"
  }
}
```

**Example 2: Array of Objects**

```json
[
  {
    "name": "Alice",
    "age": 30
  },
  {
    "name": "Bob",
    "age": 35
  }
]
```

**Example 3: Complex Nesting**

```json
{
  "company": "TechCorp",
  "employees": [
    {
      "name": "Alice",
      "role": "Engineer",
      "skills": ["Python", "JavaScript"]
    },
    {
      "name": "Bob",
      "role": "Designer",
      "skills": ["Figma", "Photoshop"]
    }
  ]
}
```

### Working with JSON in n8n

**Viewing JSON:**

In n8n execution view:
- Click any node
- See "JSON", "Table", "Schema" tabs
- JSON shows raw data
- Table shows formatted data
- Schema shows structure

**Why This Matters:**
- Understand what data flows between nodes
- Debug issues
- Learn data structures
- Configure expressions

### Expressions in n8n

**What Are Expressions?**
- Like Excel formulas
- Calculate values dynamically
- Reference data from other nodes
- Surrounded by double curly braces: `{{ }}`

**Why Use Expressions?**

❌ **Fixed Value:**
```
Date: 2025-01-15
```
Problem: Hardcoded, needs manual updates

✅ **Expression:**
```
Date: {{ DateTime.now() }}
```
Benefit: Always current, automatic

### Basic Expression Syntax

**Accessing Incoming Data:**

**The Magic Variable:** `$json`
- Represents data from previous node
- Always available
- Most common starting point

**Example:**

**Incoming Data:**
```json
{
  "name": "Alice",
  "age": 30
}
```

**Expression:**
```
{{ $json.name }}
```

**Result:** `Alice`

### Navigating Nested Data

**Using Dots to Drill Down:**

**Data:**
```json
{
  "name": "Alice",
  "age": 30,
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "country": "USA"
  }
}
```

**Expressions:**

```
{{ $json.name }}            → "Alice"
{{ $json.age }}             → 30
{{ $json.address }}         → [entire address object]
{{ $json.address.city }}    → "New York"
{{ $json.address.country }} → "USA"
```

**The Pattern:**
- Start with `$json`
- Add dot `.`
- Add key name
- Repeat for nested objects

### Advanced Expression Techniques

**Accessing Other Nodes:**

Instead of previous node (`$json`), access any specific node:

```
{{ $node["Node Name"].json.key }}
```

**Example:**
```
{{ $node["Google Sheets"].json.ticker }}
```

**Converting JSON to String:**

When you need to pass JSON to an LLM or API as text:

```
{{ JSON.stringify($json) }}
```

**Practical Example:**
```
System prompt: Here is user data:
{{ JSON.stringify($json) }}

Please analyze it.
```

**Date/Time Operations:**

Using Luxon library (built into n8n):

```
Current time:
{{ DateTime.now() }}

Yesterday:
{{ DateTime.now().minus({ days: 1 }) }}

Next week:
{{ DateTime.now().plus({ weeks: 1 }) }}

Formatted:
{{ DateTime.now().toFormat('yyyy-MM-dd') }}
```

**Best Practices:**

1. **Don't Memorize**
   - Look up as needed
   - Use n8n documentation
   - Ask ChatGPT/Claude

2. **Test Expressions**
   - n8n shows result preview
   - Verify before saving
   - Check with real data

3. **Start Simple**
   - Build expressions gradually
   - Test each part
   - Combine when working

---

## Authentication Methods

### The Spectrum of Complexity

**From Easiest to Hardest:**

1. API Key (simple password)
2. Pre-configured OAuth2 (one-click in n8n Cloud)
3. Full OAuth2 (multi-step setup)

### Method 1: API Key Authentication

**How It Works:**
- Service gives you a secret key
- You paste key into n8n
- n8n includes key with every request
- Service validates and responds

**Characteristics:**
- ✅ Very simple
- ✅ Quick setup
- ✅ Easy to replace if compromised
- ❌ Less secure than OAuth
- ❌ Full access (not user-specific)

**Examples:** OpenRouter, OpenAI, Market Stack, Pushover

**Typical Flow:**
1. Sign up for service
2. Generate API key in their dashboard
3. Copy key
4. Paste into n8n credential
5. Save
6. Done!

**Security Tips:**
- Never share API keys
- Don't commit to git repositories
- Regenerate if exposed
- Use separate keys for different projects

### Method 2: Pre-configured OAuth2

**How It Works:**
1. n8n Cloud has pre-built integration
2. Click "Sign in with [Service]"
3. Authorize n8n to access your account
4. Done!

**Characteristics:**
- ✅ Very easy (just click and sign in)
- ✅ Secure (industry standard)
- ✅ User-specific access
- ✅ Can revoke anytime
- ❌ Only works with n8n Cloud
- ❌ Only for supported services

**Examples:** Google Sheets, Gmail, Google Drive

**Under the Hood:**
- n8n has OAuth app registered with Google
- Google trusts n8n
- You trust both
- Secure token exchange happens automatically

**What's Really Happening:**
1. You click "Sign in with Google"
2. Redirected to Google
3. Google asks: "Allow n8n to access your Gmail?"
4. You approve
5. Google gives n8n a special token
6. Token is tied to your account
7. n8n uses token to access only your data

**User Experience:**
- Click button
- Sign in
- Approve permissions
- Green checkmark
- Done in seconds!

### Method 3: Full OAuth2 Setup

**When You Need This:**
- Self-hosted n8n (no pre-configured integrations)
- Services not pre-configured in n8n Cloud
- Custom applications

**Why It's Complex:**
- Multiple steps
- Two-way configuration
- Callback URLs
- Client IDs and secrets
- Easy to make mistakes

**General Process:**

**Step 1: Register Your App**
- Go to service's developer portal
- Create new OAuth application
- Get Client ID
- Get Client Secret

**Step 2: Configure Callback**
- Tell service where to send user after auth
- URL format: `https://your-n8n.com/callback`
- Must be exact or it fails

**Step 3: Configure n8n**
- Enter Client ID
- Enter Client Secret
- Enter callback URL
- Save

**Step 4: Test Connection**
- Click "Connect"
- Redirected to service
- Approve permissions
- Redirected back
- Should see "Connected"

**Common Issues:**
- Wrong callback URL (most common!)
- Typos in client ID/secret
- Forgot to enable OAuth in service
- Permissions not granted

**Survival Tips:**
1. **Read Documentation Carefully**
   - Every service is slightly different
   - Follow exact steps
   - Don't skip anything

2. **Be Patient**
   - May take 2-3 attempts
   - Normal to fail first time
   - Don't give up!

3. **Check Everything Twice**
   - Copy/paste carefully
   - No extra spaces
   - Exact URLs

4. **When Stuck**
   - Start over
   - Try different browser
   - Clear cookies
   - Generate new credentials

---

## Communication Integrations

### Project 1: Pushover (Push Notifications)

**What Is Pushover?**
- Simple push notification service
- Sends alerts to phone
- Free for first month
- Then small one-time fee
- Great for automation alerts

**Use Cases:**
- Workflow completion alerts
- Error notifications
- Daily summaries
- Important events

**Setup Process:**

**Step 1: Create Pushover Account**
1. Go to `pushover.net`
2. Sign up
3. Note your **User Key** (starts with `u-`)
4. Visible on homepage after login

**Step 2: Create Application**
1. Click "Create an Application/API Token"
2. Give it a name (e.g., "n8n Notifications")
3. Create
4. Note your **API Token** (starts with `a-`)

**Step 3: Install Phone App**
1. Download Pushover app
2. iOS or Android
3. Sign in with your account
4. Device will appear in dashboard

**Step 4: Configure in n8n**

**Create Workflow:**
1. New workflow
2. Add: On Chat Message
3. Add: AI Agent
4. Add: Simple Memory
5. Add: Chat Model

**Add Pushover Tool:**
1. Click + under Tool
2. Search: "Pushover"
3. Select Pushover
4. Credential: Create new
5. API Key: Paste Application Token (`a-...`)
6. Save (should be green)
7. User Key: Paste User Key (`u-...`)
8. Message: Click "Let model define"
9. Priority: Set to High (for sound)
10. Save

**Add Date Tool (Optional but fun):**
1. Click + for another tool
2. Search: "Date and Time"
3. Select it
4. Operation: Get Current Date

**Step 5: Test**

In chat:
```
Please send me a push notification with today's date
```

**Result:**
- Phone buzzes!
- Notification appears
- Shows today's date

**Magic!** You've integrated phone notifications!

### Project 2: Telegram Bot

**What Is Telegram?**
- Messaging app (like WhatsApp)
- Great API for bots
- Free
- Very bot-friendly

**Use Cases:**
- Personal assistant bot
- Customer service
- Notifications with two-way interaction
- Command-based automation

**Setup Process:**

**Step 1: Create Bot with BotFather**

**In Telegram:**
1. Search for: `@BotFather`
2. Start conversation: `/start`
3. Create bot: `/newbot`
4. Choose name: "My n8n Assistant"
5. Choose username: `my_n8n_bot` (must end in `bot`)
6. Receive API token (copy it!)

**Security Note:** Don't scroll too far - API key is visible in chat!

**Step 2: Create Workflow**

1. New workflow
2. Add first step
3. Search: "Telegram"
4. Select: "On message" (trigger)

**Configure Trigger:**
1. Credential: Create new
2. Access Token: Paste bot API token
3. Save
4. Should turn green

**Step 3: Add AI Agent**

1. Click + after trigger
2. AI → AI Agent
3. Add: Simple Memory
4. Add: Chat Model (OpenAI or your choice)
5. Add tool: Date and Time (optional)

**Step 4: Add Response**

1. Click + after AI Agent
2. Search: "Telegram"
3. Select: "Send a Text Message"
4. Credential: Uses same one (already set up!)

**Step 5: Configure Dynamic Response**

**Problem:** How do we send the AI response?

**The Challenge:**
- Chat ID: Need to respond to same conversation
- Message: Need to use AI output

**Solution: Expressions!**

**First, Test to See What Data We Have:**

1. Disable send node (click power icon above it)
2. Disable memory node (causes issues in testing)
3. Click "Execute Workflow" button
4. Go to Telegram, open your bot
5. Send: `/start`

**What Happens:**
- Error! (Expected)
- But we can see the data

**Step 6: Fix the Prompt**

**Problem:** AI Agent expects `chatInput` but Telegram sends `message.text`

**Solution:**
1. Double-click AI Agent
2. Find "Source for prompt"
3. Change from "Chat trigger" to "Define below"
4. Click and drag `message.text` into prompt field
5. Should show: `{{ $json.message.text }}`

**Alternative:** Type manually:
```
{{ $json.message.text }}
```

**Step 7: Test Again**

1. Click "Execute Workflow"
2. In Telegram, send: "Hi there"
3. Check n8n: Workflow executes!
4. Double-click AI Agent
5. Input shows: "Hi there"
6. Output shows: "Hello! How can I assist you today?"

**Step 8: Add Response**

**Now configure Send Message node:**

**Chat ID:**
- Expression: `{{ $json.message.chat.id }}`
- Or drag and drop from data

**Text:**
- This needs AI response
- But AI response is from previous node!
- Expression: `{{ $node["AI Agent"].json.output }}`

**Actually, simpler way:**
- n8n usually auto-fills this
- But understand what it's doing!

**Step 9: Activate Everything**

1. Re-enable Send Message node (power button)
2. Re-enable Memory node
3. Click "Execute Workflow"
4. In Telegram, send: "Hi there"

**Result:**
- Bot responds!
- Two-way conversation
- Full AI agent in Telegram!

**Test Conversation:**
```
You: Hi there
Bot: Hello! How can I assist you today?

You: What's today's date?
Bot: Today is January 31, 2025.
```

**Congratulations!** You've built a Telegram bot with AI!

### Understanding What Happened

**Key Concepts You Learned:**

1. **Expressions for Dynamic Data**
   - `$json` for current node data
   - `$node["Name"]` for specific node data
   - Drilling down with dots

2. **Data Flow**
   - Telegram → AI Agent → Telegram
   - Each node transforms data
   - Pass data with expressions

3. **Debugging**
   - Disable nodes to isolate issues
   - Examine data structures
   - Fix configuration based on actual data

---

## Summary of Days 1-4

### Day 1: Foundation
- Set up OpenRouter and n8n Cloud
- Built first AI agent (minutes!)
- Learned n8n hierarchy (Cloud → Instance → Workflow)
- Understood the "fair code" license

### Day 2: Theory
- Five tricks of Agentic AI
  - Memory illusion
  - Reasoning/thinking
  - Chaining LLMs
  - Tool calling
  - Agent loop
- One trap: Anthropomorphization
- n8n navigation and terminology

### Day 3: Google Integrations
- Stock portfolio tracker
  - Read Google Sheets
  - Get stock prices
  - Update sheet
- Gmail integration
  - Read emails
  - Draft responses
- OAuth2 (the easy way)

### Day 4: Data and Communication
- JSON fundamentals
  - Key-value pairs
  - Objects
  - Arrays
  - Nesting
- Expressions
  - $json
  - Navigation
  - Date/time
- Pushover notifications
- Telegram bot

---

## Next Steps

**What's Coming:**

**Day 5:** Business project combining everything

**Week 2:**
- Voice agents
- RAG (Retrieval Augmented Generation)
- Advanced integrations

**Week 3:**
- Self-hosting n8n
- Multi-agent systems
- MCP (Model Context Protocol)
- Capstone project

**How to Succeed:**

1. **Practice**
   - Rebuild the examples
   - Modify them
   - Break them (and fix them)
   - Experiment!

2. **Explore**
   - Try different integrations
   - Look at templates
   - Read documentation
   - Ask questions

3. **Build Real Projects**
   - Solve your own problems
   - Automate your tasks
   - Create value

4. **Community**
   - Share your work
   - Help others
   - Learn together

**You're 20% through and already building real automation. Keep going!**

---

## Quick Reference

### Essential Shortcuts
- `Escape`: Close panels
- `Tab`: Open node list
- `+/-/0`: Zoom controls
- `Ctrl/Cmd+S`: Save
- `Ctrl/Cmd+Drag`: Pan canvas

### Common Expressions
```javascript
// Current data
{{ $json.key }}

// Specific node
{{ $node["Node Name"].json.key }}

// Current date
{{ DateTime.now() }}

// Yesterday
{{ DateTime.now().minus({ days: 1 }) }}

// JSON to string
{{ JSON.stringify($json) }}
```

### Authentication Quick Guide

**API Key:**
1. Get key from service
2. Paste in n8n
3. Done

**Pre-configured OAuth (n8n Cloud):**
1. Click "Sign in with [Service]"
2. Approve
3. Done

**Full OAuth:**
1. Register app in service
2. Get Client ID/Secret
3. Configure callback URL
4. Configure in n8n
5. Test connection

### Troubleshooting Checklist

- [ ] API key copied correctly (no spaces)
- [ ] Authentication shows green checkmark
- [ ] Workflow saved
- [ ] Nodes connected properly
- [ ] Required fields filled in
- [ ] Expressions syntax correct
- [ ] Test with simple case first
- [ ] Check execution history for errors
- [ ] Read error messages carefully
- [ ] Consult documentation

---

## Resources

**n8n:**
- Documentation: `docs.n8n.io`
- Community: `community.n8n.io`
- Templates: Inside n8n or `n8n.io/workflows`

**APIs:**
- OpenRouter: `openrouter.ai`
- OpenAI: `platform.openai.com`
- Market Stack: `marketstack.com`
- Pushover: `pushover.net`

**Learning:**
- Course forums
- n8n YouTube channel
- Practice, practice, practice!

---

---

## Day 4 Continued: Advanced Telegram and Slack Integration

### Completing the Telegram Integration

After setting up the basic Telegram bot, we need to connect the AI agent's response back to Telegram for true two-way communication.

#### Configuring the Response Flow

**The Challenge:**
- Need to send AI response back to Telegram
- Must respond in the same conversation (chat ID)
- Need to extract correct data from incoming message

**Step-by-Step Configuration:**

**1. Add Telegram Send Node**

After the AI Agent:
1. Click + after AI Agent
2. Search: "Telegram"
3. Select: "Send a Text Message"
4. Credential: Uses existing (already authenticated)

**2. Configure Dynamic Text (Using Expressions)**

**Problem:** How to send the AI's response?

**Solution: Use Expression**

In the "Text" field:
- Toggle from "Fixed" to "Expression"
- The easy way: Drag `output` from AI Agent node
- Manual way: Type `{{ $json.output }}`

**What This Does:**
```javascript
{{ $json.output }}
```
- `$json` = incoming data from previous node (AI Agent)
- `.output` = the AI's response text
- Result: AI response automatically inserted

**3. Configure Chat ID (Responding to Correct Conversation)**

**Problem:** Need to respond in the same Telegram conversation

**Solution: Reference the trigger data**

In the "Chat ID" field:
1. Click dropdown above the input area
2. Select "Telegram Trigger" (the first node)
3. Now viewing: Data from the trigger
4. Find: `message` → `chat` → `id`
5. Drag and drop the `id` value into Chat ID field

**Result:**
```javascript
{{ $('Telegram Trigger').item.json.message.chat.id }}
```

**Why This Works:**
- `$('Telegram Trigger')` = get data from specific node
- `.item.json` = the actual data
- `.message.chat.id` = drill down to chat ID
- Bot responds to whoever sent the message

#### Testing the Two-Way Integration

**Test Process:**

1. **Click "Execute Workflow"**
   - Starts listening for Telegram messages
   - Indicator shows "Waiting for trigger event"

2. **Send Message in Telegram**
   - Open your bot in Telegram
   - Send: "Hi there"

3. **Observe Workflow**
   - Sees message come in
   - AI Agent processes
   - Response sent back to Telegram
   - Bot replies: "Hello! How can I assist you today?"

**Success!** Full two-way communication!

#### Adding Memory to Telegram Bot

**The Problem:**
Simple Memory node needs a session key - how to identify this specific conversation?

**Solution: Use Chat ID as Session Key**

**Configuration:**

1. **Double-click Simple Memory node**
2. **Change "Source"**
   - From: "Chat Trigger"
   - To: "Define below"

3. **Set Session Key Expression**
   - Toggle to "Expression"
   - Drag Chat ID from Telegram Trigger
   - Result: `{{ $('Telegram Trigger').item.json.message.chat.id }}`

**Why This Works:**
- Each Telegram conversation has unique chat ID
- Memory tied to that specific chat
- Different users = different chat IDs = separate memories

**Alternative Approach:**
Use Telegram username instead:
```javascript
{{ $('Telegram Trigger').item.json.message.from.username }}
```
- Memory persists across different chat sessions with same user
- Depends on your use case

#### Testing Memory

**Test Conversation:**

```
You: Hi there. My name is Ed.
Bot: Hi Ed. Nice to meet you. How can I assist you today?

You: What's my name?
Bot: Your name is Ed. How may I assist you further?
```

**Success!** Bot remembers the conversation!

#### Publishing to Production

**Why Publish?**
- Up until now: Testing mode (manual execution)
- Publishing: Makes workflow live and automatic
- No more "Execute Workflow" button needed

**How to Publish:**

1. **Save First**
   - Ctrl/Cmd + S
   - Or click "Save"

2. **Click "Publish"**
   - Top-right corner
   - Enter version name (optional)
   - Describe changes (optional)
   - Click "Publish"

3. **Confirmation**
   - "Workflow is now published"
   - "Will listen for events from Telegram"

**What Changes:**
- ❌ No more green boxes lighting up
- ✅ Workflow runs automatically
- ✅ Always listening for Telegram messages
- ✅ Real production environment

#### Testing Published Workflow

**In Telegram:**

```
You: Hi there
Bot: Hello, [your name]. How can I help you today?

You: What's the current date?
Bot: [Uses Date tool] The current date is December 15, 2024.
```

**Key Differences:**
- Don't press "Execute Workflow"
- Bot responds automatically
- Works 24/7
- No visual feedback in n8n (check Executions tab)

#### Unpublishing (When Done Testing)

**To Stop Workflow:**

1. Click triple dots (⋯) top-right
2. Select "Unpublish"
3. Confirmation: "Unpublished successfully"

**Why Unpublish:**
- Stops consuming resources
- Prevents accidental triggers
- Good practice when not actively using

### Best Practices Summary

**Telegram Integration:**

✅ **Do:**
- Test thoroughly before publishing
- Use chat ID for memory
- Drag-and-drop to create expressions
- Check executions after publishing

❌ **Don't:**
- Forget to reactivate disabled nodes
- Leave test workflows published
- Expose API keys in screenshots
- Skip testing memory functionality

---

## Slack Integration (Advanced OAuth2)

### Understanding the Challenge

**Why Slack is Harder:**
- Full OAuth2 setup required
- Multiple configuration screens
- Scopes (permissions) management
- Webhook configuration
- Two-way synchronization needed

**Time Investment:**
- Expect 30-60 minutes
- Multiple attempts normal
- Patience required
- Most complex integration in course

### Prerequisites

**What You Need:**
1. Slack workspace where you have admin permissions
2. Ability to create apps in workspace
3. Time and patience
4. Note-taking for tracking IDs and URLs

**If You Don't Have Admin:**
- Follow along without doing
- Understand OAuth2 concepts
- Apply to other integrations later
- Not required for course completion

### Step 1: Creating the Slack App

**Navigate to App Management:**

1. **In Slack Desktop/Web**
   - Click workspace name (top-left)
   - Go to: Apps & Workflows
   - Opens web browser

2. **Go to Build Section**
   - Top-right corner: "Build" button
   - Don't miss this - easy to overlook!

3. **Create New App**
   - Click "Create New App"
   - Choose: "From scratch"
   - App name: "n8n3" (or your choice)
   - Select your workspace
   - Click "Create App"

**Success:** You now have a Slack app (but it doesn't do anything yet)

### Step 2: Configuring OAuth & Permissions

**Navigate to OAuth:**
1. Left sidebar: "OAuth & Permissions"
2. This is THE most important section

**Add Bot Token Scopes:**

These scopes define what your bot can do. Add these 6 scopes:

1. **app_mentions:read**
   - Read messages that directly mention @yourbot

2. **channels:history**
   - View messages in channels bot is added to

3. **channels:read**
   - View basic channel information

4. **chat:write**
   - Send messages as @yourbot

5. **im:history**
   - View direct messages with bot

6. **users:read**
   - View people in workspace

**Adding Scopes:**
- Scroll to "Scopes" section
- Click "Add an OAuth Scope"
- Type scope name (filters as you type)
- Repeat for all 6

**Critical:** Don't skip any scopes - missing ones cause failures later

### Step 3: Installing App to Workspace

**Install the App:**

1. **Scroll to Top**
   - "OAuth Tokens for Your Workspace" section

2. **Click "Install to [Workspace Name]"**
   - Permissions screen appears
   - Shows what app can do
   - Click "Allow"

3. **Copy Bot User OAuth Token**
   - Appears after installation
   - Starts with `xoxb-`
   - Copy to clipboard immediately
   - **Store safely** - you'll need it multiple times

**What This Does:**
- Creates the bot user in your workspace
- Generates authentication token
- Bot appears in workspace (but isn't in any channels yet)

### Step 4: Setting Up n8n Workflow

**Create Workflow in n8n:**

1. **New Workflow**
   - Name it "Slack Bot"

2. **Add Slack Trigger**
   - Add first step
   - Search: "Slack"
   - Select: "On Bot/App Mention"

3. **Configure Credentials**
   - Click "Create new credential"
   - **Access Token:** Paste the `xoxb-` token
   - Click "Save"
   - Should show green ✓

**Optional Security (Can Skip):**
- Signing Secret adds extra verification
- Found in: Basic Information → App Credentials
- Can cause issues - skip if you encounter problems

### Step 5: Creating and Configuring Channel

**In Slack:**

1. **Create Channel**
   - Click + next to Channels
   - Name: "convo3" (or your choice)
   - Make it public
   - Click "Create"

2. **Invite Bot to Channel**
   - In the new channel
   - Type: `/invite @n8n3` (your bot name)
   - Bot joins channel

3. **Get Channel ID**
   - Channel name dropdown (top)
   - Select: More → View channel details
   - Scroll to bottom
   - Copy Channel ID (starts with `C`)

**Back in n8n:**

1. **Configure Trigger**
   - Select Channel: "By ID"
   - Paste Channel ID
   - This tells n8n which channel to watch

### Step 6: Configuring Event Subscriptions (The Tricky Part)

**Why This is Needed:**
Slack needs to know WHERE to send messages when events happen (someone mentions your bot).

**In n8n:**

1. **Open Webhook URLs**
   - In Slack Trigger node
   - Expand: "Webhook URLs"
   - See two options: Test URL and Production URL

2. **Copy Test URL**
   - Start with test
   - Click copy icon
   - Keep this copied

3. **Execute Step**
   - Click "Execute Step" button
   - **Leave this running** (critical!)
   - n8n now listening for webhook

**In Slack (App Configuration):**

1. **Navigate to Event Subscriptions**
   - Left sidebar: "Event Subscriptions"

2. **Enable Events**
   - Toggle: ON

3. **Set Request URL**
   - Paste the Test URL from n8n
   - Wait for verification
   - Should show: "Verified" ✓
   - If not verified: n8n Execute Step wasn't running

**Common Issue:** "Not Verified"
- Make sure Execute Step is running in n8n
- Try copying URL again
- Refresh both pages
- May need multiple attempts

4. **Subscribe to Bot Events**
   - Scroll down: "Subscribe to bot events"
   - Click "Add Bot User Event"
   - Add: `app_mention`
   - This = "notify me when bot is @mentioned"

5. **Save Changes**
   - **CRITICAL:** Scroll to bottom
   - Click "Save Changes"
   - Easy to forget this step!

**Success:** Webhook configured - Slack can now notify n8n

### Step 7: Building the Complete Workflow

**Add Remaining Nodes:**

1. **AI Agent**
   - After Slack Trigger
   - Add OpenAI Chat Model (or your choice)
   - Skip memory for now
   - Skip tools for now

2. **Slack Send Message**
   - After AI Agent
   - Search: "Slack"
   - Select: "Send a Message"
   - Uses same credential (already set up)

**Configure Send Message:**

**Resource:** Message
**Operation:** Send
**Send to:** Channel
**Channel:** By ID (paste same Channel ID)
**Message Type:** Simple text

**Message Text:** Leave as "bananas" for now (we'll fix this)

### Step 8: Testing and Fixing

**First Test (Expected to Fail):**

1. **Execute Workflow** (in n8n)
2. **In Slack:** Mention your bot
   - Type: `@n8n3 hi there`
3. **Check n8n:** Should show error

**Error: "No prompt specified"**
- Same issue as Telegram
- AI Agent expects chat trigger
- Needs to be fixed

**Fix the Prompt:**

1. **Double-click AI Agent**
2. **Source for prompt:** Change to "Define below"
3. **User Message:** Need to extract text from Slack JSON

**Understanding Slack's JSON:**

Look at incoming data (left side):
```json
{
  "message": {
    "text": "@n8n3 hi there",
    "user": "U123...",
    "channel": "C456..."
  }
}
```

**Better Approach:** Send entire JSON to LLM

Instead of extracting just text, send full context:

```
Please respond to this message from Slack:

{{ JSON.stringify($json) }}
```

**What This Does:**
- `JSON.stringify($json)` = converts incoming JSON to text
- LLM sees full context
- LLM smart enough to understand Slack JSON format
- More robust solution

### Step 9: Connecting the Response

**Configure Message Text:**

1. **Double-click "Send a Message" node**
2. **Message Text:** Change from "bananas" to expression
3. **Toggle to Expression**
4. **Drag** `output` from AI Agent OR type:
   ```javascript
   {{ $json.output }}
   ```

**Test Again:**

1. **Execute Workflow**
2. **In Slack:** `@n8n3 hi there`
3. **Expected:** Bot responds!
4. **Check:** "Hi there! How can I assist you today?"

**Success!** Two-way Slack communication working!

### Step 10: Publishing to Production

**Update Webhook URL:**

**The Issue:**
- Test URL only works during testing
- Production needs different URL

**Fix:**

1. **In n8n:** Slack Trigger node
   - Webhook URLs section
   - Switch to: "Production URL"
   - Copy this URL

2. **In Slack:** Event Subscriptions
   - Change Request URL
   - Paste Production URL
   - Should NOT verify yet (workflow not published)

3. **In n8n:** Publish workflow
   - Click "Publish" button
   - Give it a name/version
   - Click "Publish"

4. **Back to Slack:**
   - Event Subscriptions
   - Click "Retry" or refresh
   - Should now show: "Verified" ✓
   - **Don't forget:** Save Changes!

**Test Production:**

1. **In Slack:** `@n8n3 what's the current date?`
2. **Bot responds** (if you have Date tool configured)
3. **No Execute button needed** - fully automated!

### Slack Integration Troubleshooting

**Common Issues:**

**1. "Not Verified" on webhook**
- Execute Step not running in n8n
- Wrong URL copied
- Need to wait 30 seconds sometimes
- Try different browser

**2. Bot doesn't respond**
- Check bot is in channel (`/invite @bot`)
- Verify scopes are correct
- Check Event Subscriptions saved
- Look at n8n Executions tab for errors

**3. "No prompt specified"**
- Source for prompt = "Define below"
- Check JSON.stringify expression
- Verify data is flowing through

**4. Multiple error messages**
- Old webhook configurations lingering
- Disable other test workflows
- Check only one workflow active

**5. Forgot to Save Changes**
- Most common mistake!
- Always scroll down and click "Save Changes"
- In multiple Slack screens

### What You Learned

**OAuth2 Deep Dive:**
- Multi-step authentication
- Scopes and permissions
- Token management
- App installation process

**Webhook Mastery:**
- How webhooks work
- Test vs Production URLs
- Verification process
- Bidirectional communication

**Advanced n8n:**
- JSON.stringify for complex data
- Referencing specific nodes
- Expression building
- Production deployment

**Resilience:**
- Patience with complex integrations
- Reading error messages
- Iterative troubleshooting
- When to move on

---

## Day 5: Business Project - Portfolio Rebalancer

### Project Overview

**What We're Building:**
An AI-powered equity portfolio rebalancer that:
- Reads portfolio from Google Sheets
- Gets current stock prices
- Makes rebalancing decisions
- Updates the spreadsheet
- Emails trade recommendations
- Sends push notification

**Real-World Application:**
- People pay financial advisors for this service
- Automating a real business process
- Could charge clients for this
- Demonstrates commercial viability

**Skills Combined:**
- Google Sheets integration
- Market data APIs
- Email automation
- Push notifications
- Form submissions
- Conditional logic
- AI decision-making

### Understanding the Business Problem

**Portfolio Management Basics:**

**Asset Allocation:**
- **Equity (stocks):** Higher risk, higher reward
- **Fixed Income (bonds):** Lower risk, lower reward
- **Target:** Maintain desired balance (e.g., 60% equity / 40% bonds)

**Why Rebalancing Needed:**
- Markets fluctuate
- Portfolio drifts from target allocation
- Need periodic adjustments
- Usually done quarterly or annually

**Manual Process:**
1. Calculate current allocation
2. Determine needed trades
3. Execute trades
4. Verify new allocation

**Our Automation:**
Does all of this automatically with AI!

### Setting Up the Google Sheet

**Create Portfolio Sheet:**

**Columns:**
- **Ticker:** Stock symbol (e.g., GOOGL, AAPL, SPY)
- **Quantity:** Number of shares owned
- **Equity %:** Percentage that is stocks
- **Fixed Income %:** Percentage that is bonds
- **Price:** (Empty - AI will fill)
- **New Quantity After Rebalancing:** (Empty - AI will fill)

**Example Data:**

| Ticker | Quantity | Equity % | Fixed Income % | Price | New Qty |
|--------|----------|----------|----------------|-------|---------|
| VTI    | 10       | 100      | 0              |       |         |
| BND    | 15       | 0        | 100            |       |         |
| GOOGL  | 5        | 100      | 0              |       |         |
| AGG    | 20       | 0        | 100            |       |         |

**Additional Calculations:**

Add formulas to show:
- Total value of each position (=Quantity * Price)
- Total portfolio value
- Current equity percentage
- Current fixed income percentage

**Why This Structure:**
- Clear for AI to understand
- Easy to calculate allocations
- Shows before/after comparison
- Validates rebalancing worked

### Building the Workflow: Step-by-Step

#### Step 1: Create Form Trigger

**Why a Form?**
- User-friendly input method
- Allows custom instructions
- Easy to deploy as web page
- Professional appearance

**Setup:**

1. **New Workflow**
   - Name: "Equity Portfolio Rebalancer"
   - Save (Ctrl/Cmd + S)

2. **Add Trigger**
   - Click "Add first step"
   - Select: "On form submission"

3. **Configure Form**
   - **Title:** Portfolio Rebalancer
   - **Description:** (optional) "Enter rebalancing instructions"

4. **Add Form Field**
   - Click: "Add element"
   - **Type:** Text
   - **Label:** "How would you like to rebalance your portfolio?"
   - **Default value:** "Ensure the portfolio is 60% equity and 40% fixed income"
   - **Required:** Yes

**Result:** Clean form interface for users

#### Step 2: Add AI Agent with Chat Model

**Basic Setup:**

1. **Add AI Agent**
   - Click + after form trigger
   - Select: AI → AI Agent

2. **Add Chat Model**
   - Click + under "Chat Model"
   - Select: OpenAI Chat Model (or your choice)
   - **Recommended:** GPT-4.1 (not 4o or 5.x)
   - **Why:** Right balance of speed and intelligence

**Model Selection Notes:**

**GPT-4.1:**
- ✅ Fast enough
- ✅ Smart enough for this task
- ✅ Reliable for financial calculations
- ❌ Costs ~$0.01-0.05 per run

**GPT-4o-mini:**
- ✅ Much cheaper
- ✅ Very fast
- ⚠️ May be less reliable for complex math

**GPT-5.1/5.2:**
- ⚠️ Too much reasoning (slow)
- ⚠️ Sometimes overthinks
- ❌ Not worth the extra cost here

**Skip Memory:**
- Not needed (one-time form submission)
- No conversation to remember

#### Step 3: Configure AI Agent Prompt

**The Challenge:**
Form submission data needs to become the AI prompt.

**Initial Issue:**
Execute workflow → Submit form → Error: "No prompt specified"

**Why:**
- AI Agent expects chat trigger
- Form trigger has different data structure
- Need to extract form response

**Solution:**

1. **Double-click AI Agent**
2. **Source for prompt:** Change to "Define below"
3. **Build the prompt:**

```
You have access to the user's equity portfolio, which is in a Google Sheet.
You also have access to market data.

The user has asked you to rebalance their portfolio with this instruction:

{{ $json['How would you like to rebalance your portfolio?'] }}

In order to achieve this:
1. Read the portfolio from the sheet
2. Fetch the latest prices of the positions
3. Update the table with the prices
4. Make decisions on portfolio rebalancing
5. Update the table with the portfolio rebalancing decisions
6. Read the table again to check that your rebalancing met the objectives
7. If needed, make further changes to improve the rebalancing
8. Send an email with the trading decisions and a concise push notification

Important: You must confirm you've achieved your goal.
Only respond "OK" when your mission is complete.
```

**Key Elements:**

**Context Setting:**
- "You have access to..."
- Sets up what tools are available

**User Instruction:**
- Expression pulls form response
- Dynamic based on user input

**Step-by-Step Guidance:**
- Numbered steps (AI-friendly)
- High-level instructions
- Leaves room for autonomy

**Completion Criteria:**
- "Only respond OK when complete"
- Used for conditional logic later

#### Step 4: Add Tools - Google Sheets (Read)

**Purpose:** Let AI read the portfolio

**Setup:**

1. **Click + under Tool**
2. **Search:** "Google Sheets"
3. **Resource:** Sheet within a document
4. **Operation:** Get rows
5. **Document:** Select "Portfolio" from dropdown
6. **Sheet:** Select "Sheet1"
7. **Filters:** None (read all rows)

**Enhance with Better Description:**

Instead of auto-generated description:

```
This tool provides details of the user's portfolio in a Google Sheet.
It includes the positions and the equity/fixed income breakdown.

Use this tool to retrieve the Google Sheet to see the positions 
before updating prices and making rebalancing decisions.

IMPORTANT: You must also use this tool AFTER rebalancing to check
the breakdown achieves your goal. If not, keep iterating.
```

**Why Better Description:**
- Tells AI WHEN to use tool
- Emphasizes verification step
- Encourages iteration
- Part of "context engineering"

#### Step 5: Add Tools - Market Stack

**Purpose:** Get current stock prices

**Setup:**

1. **Click + for another tool**
2. **Search:** "Market Stack"
3. **Resource:** End of day
4. **Operation:** Get many
5. **Ticker:** Click "Let model define" (purple button)
6. **Add Filter:** Latest = Yes

**What This Does:**
- AI can request any ticker symbol
- Gets most recent closing price
- Returns price data
- AI extracts what it needs

**Note on Free Tier:**
- 100 free lookups/month
- Should be enough for testing
- Can upgrade if needed ($10/month)

#### Step 6: Add Tools - Google Sheets (Update Price)

**Purpose:** Let AI write stock prices to sheet

**Setup:**

1. **Click + for another tool**
2. **Search:** "Google Sheets"
3. **Resource:** Sheet within document
4. **Operation:** Update row
5. **Document:** Portfolio
6. **Sheet:** Sheet1

**Critical Configuration:**

**Column to Match On:** Ticker
- This is the "key" - how to find the row

**Values to Update:**
- Uncheck "Quantity" (don't change)
- Check "Ticker" - click "Let model define"
- Check "Price" - click "Let model define"

**What This Means:**
- AI specifies which ticker to update
- AI specifies what price to set
- Sheet gets updated automatically

#### Step 7: Add Tools - Google Sheets (Update Quantities)

**Purpose:** Let AI write rebalancing decisions

**Setup:** Same as above but different field

1. **Another Google Sheets tool**
2. **Operation:** Update row
3. **Document:** Portfolio, **Sheet:** Sheet1

**Values to Update:**
- **Match on:** Ticker
- **Update:** "New Quantity After Rebalancing"
- Both: "Let model define"

**Now AI Can:**
- Match ticker
- Set new quantity (after rebalancing)
- Make trade recommendations

#### Step 8: Add Tools - Gmail

**Purpose:** Send rebalancing recommendations via email

**Setup:**

1. **Click + for another tool**
2. **Search:** "Gmail"
3. **Resource:** Message
4. **Operation:** Send
5. **Authenticate:** Sign in with Google

**Configuration:**

**To:** Your email (FIXED - not model-defined)
- Safety measure
- During testing, only email yourself
- Can expand later

**Subject:** (FIXED)
```
Equity Rebalancer Trading Decisions
```

**Message:** Click "Let model define"
- AI will compose email body
- Will include trade recommendations

**Message Type:** HTML
- Prettier formatting
- AI can use formatting

**Why This Approach:**
- Safe (only emails you)
- Professional
- Audit trail
- Can forward to broker if desired

#### Step 9: Add Tools - Pushover

**Purpose:** Quick notification on phone

**Setup:**

1. **Click + for another tool**
2. **Search:** "Pushover"
3. **Operation:** Push a message

**Configuration:**

**API Key:** Application token (starts with `a-`)
**User Key:** User token (starts with `u-`)
**Message:** Click "Let model define"
**Priority:** High (for sound/vibration)

**Two Notifications:**
- This one: AI-generated status
- Later: Workflow-controlled (success/fail)

#### Step 10: Configure Advanced Settings

**Max Iterations:**

**Problem:** Default = 10 iterations may not be enough

**Solution:**

1. **Double-click AI Agent**
2. **Scroll down:** "Options"
3. **Click:** "Add Option"
4. **Select:** "Max Iterations"
5. **Set:** 30

**Why:**
- Needs multiple tool calls:
  - Read sheet
  - Get 4+ stock prices
  - Update 4+ price rows
  - Update 4+ quantity rows
  - Read sheet again (verify)
  - Possibly iterate
  - Send email
  - Send notification
- Could easily be 15-20 calls
- 30 gives room for iteration

### Testing the Workflow

#### First Test (Expect Improvements Needed)

**Execute:**

1. **Click "Execute Workflow"**
2. **Form appears in popup**
3. **Submit with default instruction**
4. **Watch workflow run**

**What Happens:**

You'll see in the executions:
- Form trigger ✓
- AI Agent starts
- Multiple tool calls
- Prices get filled in sheet
- Quantities get calculated
- Email sent
- Notification received

**Common First-Run Issues:**

**Issue 1: AI doesn't achieve target**
- Initial quantities don't match 60/40
- Needs iteration

**Issue 2: AI stops too early**
- Doesn't verify its work
- Need clearer prompt

**Issue 3: Calculation errors**
- Rounding issues
- Need to tune prompts

**Issue 4: Timeout**
- Too many iterations
- Simplify or optimize

#### Reviewing Results

**Check Google Sheet:**

**Price Column:**
- Should be filled with current prices
- All positions have values

**New Quantity Column:**
- Should show recommended trades
- Changes to achieve target allocation

**Totals:**
- Check if close to 60/40 target
- May not be exact (rounding)

**Check Email:**

Should contain:
- List of current positions
- Recommended trades
- Expected new allocation
- Clear action items

**Example:**
```
Current Portfolio:
VTI: 10 shares @ $220 = $2,200
BND: 15 shares @ $85 = $1,275
...

Recommended Trades:
SELL 2 shares of VTI
BUY 5 shares of BND
...

New Allocation:
Equity: 60.2%
Fixed Income: 39.8%
```

**Check Push Notification:**

Should be concise:
```
Portfolio rebalanced to 60/40 split. 
Check email for details.
```

### Improving the Workflow: Balancing Autonomy vs. Instructions

**The Balancing Act:**

**Too Little Guidance:**
```
Rebalance the portfolio to 60/40.
```
- ❌ Too vague
- ❌ AI might not know how
- ❌ Inconsistent results

**Too Much Guidance:**
```
1. Read cell A2
2. Multiply by cell B2
3. Store result in C2
4. ...
```
- ❌ Not using AI strengths
- ❌ Could just write code
- ❌ Inflexible

**Right Balance (What We Have):**
```
1. Read the portfolio from the sheet
2. Fetch latest prices
3. Make rebalancing decisions
4. Verify you achieved the goal
5. Iterate if needed
```
- ✅ High-level steps
- ✅ Room for AI judgment
- ✅ Guidance without micromanagement
- ✅ Verification built in

**Philosophy:**

Think of it like delegating to a human:
- Give clear objectives
- Provide necessary tools
- Let them figure out details
- Ask them to verify their work

**Iterative Refinement:**

Start simple → Test → Identify issues → Add guidance

Don't try to perfect it on first attempt.

### Adding Conditional Logic with If Nodes

**The Goal:**
Send different notifications based on success/failure.

**Why:**
- Emergency alert if something goes wrong
- Quiet success notification if all good
- Professional workflow management

#### Understanding Node Types

**Core Node:**
- Regular workflow step
- Always executes (unless skipped)
- Example: Send email, update sheet

**Sub-Node:**
- Part of another node (like a tool)
- Only executes when LLM decides
- Example: Tools in AI Agent

**Cluster Node:**
- Group of related nodes
- Example: AI Agent + its tools + memory

#### If Node: Branching Logic

**Purpose:** Route workflow based on conditions

**Setup:**

1. **Click + after AI Agent**
2. **Search:** "If"
3. **Select:** "If" node

**Configuration:**

**Condition:**

**Value 1:** Expression
```javascript
{{ $json.output }}
```
(The AI's final response)

**Operator:** Is equal to

**Value 2:** Fixed
```
OK
```

**What This Creates:**

Two branches:
- **True branch:** If AI responded "OK"
- **False branch:** If AI responded anything else

**Remember:** We told AI to only respond "OK" when mission complete!

#### Adding Success Notification

**On True Branch:**

1. **Click + on "true" branch**
2. **Search:** "Pushover"
3. **Operation:** Push a message

**Configuration:**

**API Key:** (your application token)
**User Key:** (your user token)
**Message:** (FIXED)
```
Rebalancing successful
```
**Priority:** Low (no sound)

**Why Low Priority:**
- Everything worked
- No urgent action needed
- Quiet notification

#### Adding Failure Notification

**On False Branch:**

1. **Click + on "false" branch**
2. **Search:** "Pushover"
3. **Operation:** Push a message

**Configuration:**

**API Key:** (same)
**User Key:** (same)
**Message:** (FIXED)
```
Rebalancer failed - check logs
```
**Priority:** Emergency
- **Requires acknowledgment**
- **Repeats until acknowledged**
- **Bypasses quiet hours**

**Why Emergency:**
- Something went wrong
- Financial decisions involved
- Need immediate attention

#### Core Node vs. Tool: The Distinction

**These Pushover nodes are CORE NODES:**

**Characteristics:**
- Regular workflow steps
- Always execute when reached
- No LLM decision involved
- Fixed message (we decided)
- Traditional workflow logic

**Contrast with Tools:**

**The earlier Pushover tool was different:**
- Sub-node (inside AI Agent)
- LLM decides when to use
- LLM decides message content
- Part of agent's "toolbox"
- Agentic AI pattern

**Example Comparison:**

**As Tool (Earlier):**
```
AI Agent → Decides to use Pushover tool →
Composes message → Sends
```

**As Core Node (Now):**
```
If condition met → Always send this exact message
```

**When to Use Each:**

**Use Tools When:**
- AI should decide when to act
- Message content should vary
- Part of AI's decision-making
- Flexible, autonomous behavior

**Use Core Nodes When:**
- Always execute at this point
- Fixed message/action
- Traditional workflow logic
- Guaranteed behavior

### Testing Complete Workflow

**Clear the Sheet:**
- Remove all values from Price column
- Remove all values from New Quantity column
- Keep original quantities

**Execute:**

1. **Click "Execute Workflow"**
2. **Submit form**
3. **Watch it run**

**What to Observe:**

**In Google Sheet (watch in real-time!):**
- Prices populate one by one
- New quantities appear
- Calculations update
- Fascinating to watch!

**In n8n:**
- Multiple tool calls shown
- If node evaluates
- Correct branch taken
- Success/failure notification sent

**Expected Result:**

**If Successful:**
- ✅ All prices filled
- ✅ Quantities calculated
- ✅ Close to 60/40 target
- ✅ Email received
- ✅ Low-priority notification

**If Issues:**
- ⚠️ Emergency notification
- ⚠️ Check logs
- ⚠️ Review AI's reasoning
- ⚠️ Adjust prompts

### Debugging with Logs

**Access Logs:**

1. **Go to Executions tab**
2. **Click most recent execution**
3. **Click "Logs"** (bottom)

**Two Views:**

**Overview:**
- Visual representation
- Node execution counts
- Green = success, Red = error
- Quick status check

**Details:**
- Click "Details" tab
- Chronological log
- Every tool call
- AI's reasoning
- Full conversation

**What to Look For:**

**Successful Runs:**
- AI reads sheet
- Gets all prices
- Calculates rebalancing
- Verifies result
- Responds "OK"

**Failed Runs:**
- Where did it stop?
- What was last tool call?
- Did it run out of iterations?
- Did calculation go wrong?

**Token Usage:**

Hover over AI Agent node:
- **Prompt tokens:** Input size
- **Completion tokens:** Output size
- **Total:** Combined

**Why This Matters:**
- Cost calculation
- Context window management
- Performance optimization

### Publishing to Production

**Preparation:**

1. **Test thoroughly** (3-5 successful runs)
2. **Clear the sheet** (fresh start)
3. **Note the Production URL:**
   - Form Submission trigger
   - Webhook URLs section
   - Copy Production URL

**Publish:**

1. **Click "Publish"** (top-right)
2. **Version name:** "v1.0" or "Initial Production"
3. **Describe changes:** "First production deployment"
4. **Click "Publish"**

**What Happens:**
- Workflow goes live
- Form accessible via URL
- No more manual execution
- Runs automatically on submission

**Test in Production:**

1. **Open Production URL** in browser
2. **Shows your form** (public webpage!)
3. **Submit form**
4. **Wait** (don't watch n8n)
5. **Check results:**
   - Google Sheet updates
   - Email arrives
   - Notification received

**Success:** Fully automated workflow running!

### Making It Better: Your Challenges

#### Challenge 1: Improve Accuracy

**Problem:** Larger portfolios (10+ positions) struggle

**Why:**
- More complex calculations
- Context window fills up
- AI loses track

**Solutions to Try:**

**A. Add Calculator Tool**
- Let AI use calculator for math
- Reduces mental load
- More accurate calculations

**B. Simplify Sheet**
- Remove unnecessary columns
- Clearer structure
- Less for AI to process

**C. Add Helper Formulas**
- Sheet calculates current allocation
- AI just needs to read result
- Offload computation to spreadsheet

**D. Provide Examples**
- Show sample calculation in prompt
- Guide AI's approach
- Reduce trial-and-error

#### Challenge 2: Add Scheduling

**Current:** Manual form submission

**Better:** Automatic daily/weekly runs

**How:**

1. **Change Trigger:**
   - Remove "On form submission"
   - Add "Schedule" trigger
   - Set: Daily at market close (e.g., 4:30 PM EST)

2. **Adjust Prompt:**
   - No user input
   - Use default: "Rebalance to 60/40"
   - Or read target from sheet

3. **Add Date Check:**
   - Only run on trading days
   - Skip weekends/holidays

**Result:** Set it and forget it!

#### Challenge 3: Multiple Portfolios

**Idea:** Manage multiple portfolios

**Approach:**

**A. Form Dropdown**
- "Which portfolio?" field
- Options: "Retirement", "Taxable", "529"
- AI reads appropriate sheet

**B. Multiple Sheets**
- One sheet per portfolio
- Form passes sheet name
- Dynamic tool configuration

**C. User Authentication**
- If node checks user
- Routes to their portfolio
- Multi-tenant system

#### Challenge 4: Risk Tolerance

**Enhancement:** Different targets for different risk levels

**Form Field:**
```
Risk Tolerance: [Conservative/Moderate/Aggressive]
```

**Allocation Targets:**
- Conservative: 40/60 (equity/fixed income)
- Moderate: 60/40
- Aggressive: 80/20

**Prompt Adjustment:**
```
Based on risk tolerance, target allocation is:
{{ ... calculate target based on form input ... }}
```

#### Challenge 5: Transaction Costs

**Real-World Consideration:**

Rebalancing costs money:
- Trading commissions (rare now)
- Bid-ask spread
- Tax implications

**Add to Prompt:**
```
Only recommend trades if the portfolio is more than 5% away
from target allocation. Minor drifts are acceptable.
```

**More Advanced:**
- Calculate cost of trades
- Only rebalance if benefit > cost
- Consider tax lots

#### Challenge 6: Performance Reporting

**Add Features:**

**A. Historical Tracking**
- Save each rebalancing to new sheet
- Track performance over time
- Generate reports

**B. Charts**
- Allocation over time
- Value growth
- Trade history

**C. Summary Email**
- Year-to-date performance
- Total value change
- Fees saved vs. advisor

### Key Takeaways from Project

**Technical Skills:**

✅ Multi-step AI workflows
✅ Complex tool orchestration
✅ Form-based triggers
✅ Conditional logic (If nodes)
✅ Production deployment
✅ Professional error handling

**Conceptual Understanding:**

✅ Context engineering (not just prompting)
✅ Balancing autonomy vs. guidance
✅ Iterative refinement process
✅ When to use AI vs. traditional logic
✅ Real-world business automation

**Best Practices:**

✅ Start simple, add complexity
✅ Test extensively before production
✅ Use logs for debugging
✅ Clear success criteria
✅ Professional error handling
✅ Graceful failure modes

**Business Value:**

✅ Automates real paid service
✅ Saves time and money
✅ Scalable solution
✅ Portfolio piece for clients
✅ Foundation for other projects

---

## Week 1 Wrap-Up

### What You've Accomplished

**Day 1: Foundation**
- Set up n8n Cloud and OpenRouter
- Built first AI agent (minutes!)
- Understood the n8n platform
- Learned about LLMs and APIs

**Day 2: Theory**
- Five tricks of Agentic AI
- One trap (anthropomorphization)
- Deep understanding of how agents work
- n8n navigation mastery

**Day 3: Integration Foundations**
- Google Sheets automation
- Gmail integration
- OAuth2 (the easy way)
- Stock portfolio tracker

**Day 4: Advanced Integration**
- JSON and data structures
- Expressions and dynamic values
- Pushover notifications
- Telegram bot (full OAuth2)
- Slack bot (hardcore OAuth2)
- Webhooks and production deployment

**Day 5: Business Project**
- Complete portfolio rebalancer
- Form-based workflows
- Conditional logic (If nodes)
- Professional error handling
- Production deployment
- Real commercial value

### Progress Check

**You are 33% through the course!** 🎉

**You can now:**
- Build AI agents from scratch
- Integrate with multiple services
- Deploy production workflows
- Solve real business problems
- Charge clients for automation

**You understand:**
- How LLMs actually work
- Agent loops and tool calling
- OAuth2 authentication
- JSON and expressions
- Context engineering
- Iterative development

### Looking Ahead: Week 2 - Accelerate

**What's Coming:**

**Voice Agents:**
- 11 Labs integration
- Voice input and output
- Phone call automation
- Interactive voice responses

**RAG (Retrieval Augmented Generation):**
- Vector databases
- Knowledge bases
- Document search
- Semantic similarity

**Advanced Projects:**
- Voice-powered assistant
- Knowledge base chatbot
- Multi-modal interactions

**Platform:** Still using n8n Cloud (self-hosting in Week 3)

### Week 1 Checklist

Before moving to Week 2, ensure you can:

- [ ] Create workflows from scratch
- [ ] Add and configure nodes
- [ ] Set up OAuth2 integrations
- [ ] Write basic expressions
- [ ] Use If nodes for logic
- [ ] Deploy to production
- [ ] Debug using logs
- [ ] Read and understand JSON

**If any of these are shaky:** Review those sections!

### Common Misconceptions Addressed

**1. "I need to memorize all the expressions"**
❌ No! Look them up as needed. Understand the pattern.

**2. "I should replicate exactly what Ed does"**
❌ No! Experiment with different integrations and approaches.

**3. "Failed integrations mean I'm doing it wrong"**
❌ No! Integrations are inherently tricky. Patience is key.

**4. "AI agents should work perfectly first try"**
❌ No! Iteration and refinement are essential.

**5. "I need coding experience"**
✅ Helpful but not required. This is low-code, not no-code.

### Tips for Success

**1. Practice Daily**
- Even 15 minutes
- Build small workflows
- Try different integrations

**2. Break Things**
- Deliberately cause errors
- Learn from debugging
- Build resilience

**3. Use the Community**
- Post questions
- Share workflows
- Learn from others

**4. Document Your Work**
- Keep notes
- Screenshot working configs
- Save successful workflows

**5. Think Business Value**
- Every workflow should solve a problem
- Consider: "Would someone pay for this?"
- Build portfolio pieces

### Keyboard Shortcuts Reminder

**Essential:**
- `Escape`: Close panels
- `Tab`: Open node list
- `+/-/0`: Zoom controls
- `Ctrl/Cmd + S`: Save
- `Ctrl/Cmd + Drag`: Pan canvas

**Pro Tips:**
- Double-click nodes to configure
- Drag-and-drop to create expressions
- Use Tidy Up button frequently

### Resources to Bookmark

**n8n:**
- Docs: `docs.n8n.io`
- Community: `community.n8n.io`
- Templates: `n8n.io/workflows`

**AI Models:**
- OpenRouter: `openrouter.ai`
- OpenAI: `platform.openai.com`
- Anthropic: `console.anthropic.com`

**Integration Docs:**
- Google: `console.cloud.google.com`
- Slack: `api.slack.com`
- Telegram: `core.telegram.org/bots`

### Troubleshooting Quick Reference

**Workflow Won't Run:**
- Check all nodes have green checkmark
- Verify authentication (re-authenticate if needed)
- Look at Executions → Logs
- Check If nodes have correct conditions

**AI Agent Not Working:**
- Verify prompt source configured
- Check Max Iterations (increase if needed)
- Look at tool descriptions
- Review system prompt

**Integration Failing:**
- Generate new API key
- Check scopes/permissions
- Verify webhook URLs
- Re-authenticate

**Expressions Not Working:**
- Check syntax: `{{ }}`
- Verify node names match
- Use drag-and-drop
- Check data structure in JSON view

### Next Steps

**Before Week 2:**

1. **Review your Week 1 workflows**
   - Do they still work?
   - Can you explain each part?
   - What would you improve?

2. **Try one new integration**
   - Pick from n8n's integration list
   - Build something simple
   - Document what you learned

3. **Improve the portfolio rebalancer**
   - Try one of the challenges
   - Make it more robust
   - Add a feature you want

4. **Share your work**
   - Post in community
   - Get feedback
   - Help others

**Get Excited for Week 2:**
Voice agents are incredibly fun and satisfying to build. The "wow factor" is huge, and clients love voice-powered automation!

---

## Appendix: Complete Reference

### JSON Quick Reference

**Basic Structure:**
```json
{
  "string": "text value",
  "number": 42,
  "boolean": true,
  "null_value": null,
  "array": [1, 2, 3],
  "object": {
    "nested": "value"
  }
}
```

**Arrays:**
```json
["item1", "item2", "item3"]
```

**Nested:**
```json
{
  "user": {
    "name": "Alice",
    "address": {
      "city": "NYC"
    }
  }
}
```

### Expression Quick Reference

**Basic:**
```javascript
{{ $json.key }}
```

**Nested:**
```javascript
{{ $json.user.address.city }}
```

**Other Node:**
```javascript
{{ $node["Node Name"].json.key }}
```

**JSON to String:**
```javascript
{{ JSON.stringify($json) }}
```

**Date/Time:**
```javascript
{{ DateTime.now() }}
{{ DateTime.now().minus({ days: 1 }) }}
{{ DateTime.now().toFormat('yyyy-MM-dd') }}
```

### Authentication Types

| Type | Complexity | Examples | Use When |
|------|------------|----------|----------|
| API Key | ⭐ Easy | OpenAI, OpenRouter | Simple service access |
| Pre-configured OAuth2 | ⭐⭐ Medium | Google Sheets, Gmail | n8n Cloud + supported services |
| Full OAuth2 | ⭐⭐⭐ Hard | Slack, custom apps | Self-hosted or unsupported services |

### Node Types Summary

| Type | Description | Example | Can Stand Alone? |
|------|-------------|---------|------------------|
| Core Node | Regular workflow step | Send Email, If | Yes |
| Sub-Node | Part of another node | Tool in AI Agent | No |
| Cluster Node | Group of related nodes | AI Agent + tools | Yes |
| Trigger | Starts workflow | On form submission | Yes (first node) |
| Action | Does something | Update spreadsheet | Yes |

### Common Error Messages

**"No prompt specified"**
- **Cause:** AI Agent expects chat trigger
- **Fix:** Change source to "Define below"

**"Authentication failed"**
- **Cause:** Invalid or expired credentials
- **Fix:** Regenerate API key, re-authenticate

**"Node not found"**
- **Cause:** Referenced node doesn't exist or renamed
- **Fix:** Update expression with correct node name

**"Webhook not verified"**
- **Cause:** Execute Step not running or wrong URL
- **Fix:** Start Execute Step, regenerate webhook URL

**"Max iterations reached"**
- **Cause:** AI didn't complete task in time
- **Fix:** Increase Max Iterations in agent settings

### Best Practices Checklist

**Before Building:**
- [ ] Clear goal defined
- [ ] Required integrations identified
- [ ] Authentication credentials ready
- [ ] Test data prepared

**During Building:**
- [ ] Save frequently (Ctrl/Cmd + S)
- [ ] Test after each major addition
- [ ] Use descriptive node names
- [ ] Add comments in prompts
- [ ] Check logs after failed executions

**Before Publishing:**
- [ ] Test thoroughly (3+ successful runs)
- [ ] Check all credentials valid
- [ ] Verify webhook URLs (if applicable)
- [ ] Review error handling
- [ ] Document how to use

**After Publishing:**
- [ ] Test in production
- [ ] Monitor first few executions
- [ ] Document any issues
- [ ] Plan improvements
- [ ] Share with users

---

**End of Week 1 - Complete Documentation**

*You've completed the foundation of n8n AI agent development. Week 2 will build on these skills with voice agents and RAG. Week 3 will cover advanced topics like self-hosting and multi-agent systems.*

**Congratulations on completing Week 1! 🎉**
