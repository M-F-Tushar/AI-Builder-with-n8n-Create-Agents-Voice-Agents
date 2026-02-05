# Week 2: AI Voice Agents and RAG - Complete Course Guide

**Course:** Agentic AI Builder - AI Agents and Voice Agents in n8n  
**Week Focus:** Accelerate - Using frontier technology to do more, faster

---

## Overview

This week covers two major technologies:
1. **ElevenLabs Voice Agents** - Building professional conversational AI with voice
2. **RAG (Retrieval-Augmented Generation)** - Giving AI agents expert knowledge

By the end of this week, you'll build a voice-enabled expert agent that can answer detailed questions about a product catalog using RAG.

---

## Table of Contents

- [Day 1: Introduction to ElevenLabs Voice Agents](#day-1-elevenlabs)
- [Day 2: Integrating ElevenLabs with n8n](#day-2-integration)
- [Day 3: Understanding RAG](#day-3-rag)
- [Day 4: Building RAG Pipelines](#day-4-implementation)

---

<a name="day-1-elevenlabs"></a>
## Day 1: Introduction to ElevenLabs Voice Agents

### What is ElevenLabs?

ElevenLabs is the leading platform for AI voice generation and conversational voice agents.

**Company Overview:**
- Founded in 2022
- Already achieved unicorn status
- Industry leader in audio quality
- Founded by ex-Google and Palantir team members

**Platform Structure:**

Two main products:

1. **Creative Platform**
   - Text-to-speech generation
   - Audio book creation
   - Voice cloning
   - Music generation
   - Image and video audio

2. **Agents Platform** ← Our focus
   - Build conversational voice agents
   - Real-time voice interactions
   - Multi-agent workflows
   - Tool integrations

**Pricing:**
- Free tier available (generous for learning)
- Starter: $5/month
- Creator and Pro tiers for power users
- Annual plans available (2 months free)

### Getting Started

**Sign Up Process:**

1. Visit elevenlabs.io
2. Click Sign Up
3. Choose **Agents Platform** during onboarding
4. Can switch platforms later if needed

**Interface Navigation:**

Top-level structure:
```
┌──────────────────────────────────┐
│  Creative Platform | Agents Platform │ ← Toggle here
└──────────────────────────────────┘
```

Main sections in Agents Platform:
- **Configure** - Build and edit agents
- **Monitor** - Track performance
- **Deploy** - Publish agents

**Developer Resources:**
- Documentation for both platforms
- API references
- Code examples
- Pricing calculator

### Creating Your First Voice Agent

**Basic Setup:**

Click: New Agent → Blank Agent

Required configuration:

**1. Agent Name**
```
Example: "First Agent"
Purpose: Identifies your agent
```

**2. System Prompt**
```
Default: "You are a helpful assistant"

What it does:
- Defines agent personality
- Sets behavior guidelines
- Provides context and knowledge
- Determines response style

Example custom prompt:
"You are a helpful assistant for an airline. 
You assist customers with their travel needs. 
A return ticket from New York to London costs $599."
```

**3. First Message**
```
Default: "Hello. How can I help you today?"

Customization:
- Supports variables: {{ variable_name }}
- Can reference user data
- Sets conversation tone
```

**4. Voice Selection**

Available voices with distinct personalities:

| Voice | Characteristics |
|-------|----------------|
| Eric | Smooth and trustworthy |
| Miss Walker | Warm, reassuring, round |
| Jason | Calm, meditative, soothing |
| Russell | Outgoing and excited |
| Stokes | Relaxing, casual, warm |

Choose based on use case:
- Customer service → Miss Walker
- Meditation app → Jason  
- Sales/Marketing → Russell

**5. Language**
```
Options: English, Spanish, French, etc.
Can specify per agent
```

**6. Model Selection**

LLM powering the agent:

```
Available:
- Gemini 2.5 Flash (default)
- Gemini 3 Flash Preview
- Gemini 3 Pro
- GPT-4o (experimental)

Choose based on:
- Performance needs
- Cost considerations
- Feature requirements
```

**Testing Your Agent:**

1. Click **Preview**
2. Avatar (orb) appears
3. Click "Call AI Agent"
4. Speak naturally
5. Agent responds in real-time

Example interaction:
```
User: "Tell me a fun fact"
Agent: "Did you know that a group of flamingos 
        is called a flamboyance?"

User: "Tell me a joke about flamingos"
Agent: "Why did the flamingo cross the road? 
        Because it was the chicken's day off!"
```

**Key Observations:**
- Response speed is excellent
- Voice quality is natural
- Turn-taking feels smooth
- No noticeable latency

### Knowledge Bases

Knowledge bases give your agent domain expertise without additional training.

**Concept:**

Instead of training a model on your data (expensive, time-consuming), you provide documents that the agent can reference during conversations.

**This is your first glimpse of RAG (Retrieval-Augmented Generation)!**

**Setting Up a Knowledge Base:**

1. Navigate to **Knowledge Base** section
2. Click **Add Document**
3. Choose **Create Text**
4. Name your document

Example - Apple Product Details:
```
Document Name: Apple Product Details

Content:
Apple Watch Series 11
- Launch price: ~$399
- Latest features...

Apple Watch SE 3
- More affordable option
- Key features...

Apple Watch Ultra 3
- Designed for rugged use
- Premium features...
```

5. Click **Create**

**Using Knowledge Base:**

Update system prompt:
```
"You are able to answer questions on Apple products."
```

The agent will automatically:
- Search knowledge base when relevant
- Extract pertinent information
- Formulate accurate responses

Example interaction:
```
User: "What's the latest Apple Watch and its price?"

Agent: "The latest version is the Apple Watch Series 11, 
        which has a reported launch price of around $399. 
        There are also other models available, such as the 
        Apple Watch SE 3, which is more affordable, and the 
        Apple Watch Ultra 3, which is designed for rugged use."
```

**How It Works (Preview of RAG):**

```
User Question
    ↓
Agent searches knowledge base
    ↓
Finds relevant information
    ↓
Includes in context for LLM
    ↓
Generates informed response
```

### Platform Features Deep Dive

#### 1. Workflow Builder

Visual canvas for creating multi-agent conversations.

**Purpose:**
- Connect multiple specialized agents
- Route conversations based on user needs
- Create complex interaction flows

**When to Use:**
- Simple multi-agent scenarios
- Quick prototyping
- Self-contained voice systems

**When NOT to Use:**
- Complex business logic (use n8n)
- Heavy external integrations
- Advanced workflow requirements

**Components:**
- Agent nodes (conversation handlers)
- Condition nodes (routing logic)
- Tool nodes (external actions)

**Example Template: Qualification Flow**

```
Main Agent (Entry Point)
    ↓
Analyzes user question
    ↓
Routes to appropriate specialist:
├─→ Technical Support (Product questions)
└─→ Billing Support (Payment questions)
```

#### 2. Branches

Version control for your agents.

**Use Cases:**
- A/B testing different prompts
- Experimenting with configurations
- Maintaining multiple versions
- Rollback capabilities

**Workflow:**
```
Create branch → Make changes → Test → Merge or discard
```

#### 3. Analysis

Performance monitoring and conversation analytics.

**Metrics Available:**
- Total conversations
- Success/failure rates
- Average duration
- Error tracking
- User satisfaction

**Use For:**
- Identifying problem areas
- Measuring improvements
- Understanding usage patterns
- Quality assurance

#### 4. Tools

Extend agent capabilities with external integrations.

**Built-in System Tools:**

**End Conversation**
```
Purpose: Gracefully terminate calls
When: Natural conversation conclusion
Prevents: Awkward hanging situations
```

**Detect Language**
```
Purpose: Auto-detect user language
Then: Switch agent language accordingly
Supports: Multilingual conversations
```

**Transfer to Agent**
```
Purpose: Route to specialized agents
Based on: User needs and context
Example: Tech support → Billing
```

**Custom Webhook Tools:**

Create tools that call external APIs:

```
Tool Name: equity_portfolio_question_tool
Description: Query user's stock portfolio
Method: POST
URL: https://your-n8n-workflow.com/webhook
Body: { "question": "user question here" }
```

**How Custom Tools Work:**

1. Agent decides tool is needed
2. LLM formulates tool parameters
3. Tool makes HTTP request
4. External system processes
5. Result returns to agent
6. Agent speaks response

This is how we'll integrate with n8n tomorrow!

#### 5. Widget Configuration

Customize how your agent appears on websites.

**Avatar Options:**

1. **Orb (Default)**
   - Animated blue circle
   - Modern, professional
   - Built-in animations

2. **Custom Image**
   - Upload your image
   - Brand consistency
   - Personal touch

3. **URL Image**
   - Link to hosted image
   - Dynamic updates possible
   - CDN optimization

**Embedding Code:**

```html
<!-- Copy this snippet -->
<script src="elevenlabs-widget.js"></script>
<div id="elevenlabs-agent"></div>

<!-- Paste into your website -->
<!-- Agent appears and works immediately -->
```

**Deployment Platforms:**
- WordPress
- Squarespace
- Custom websites
- Any HTML-capable platform

**Advanced Configuration:**
- Styling (colors, sizes, positions)
- Headers and footers
- Custom messages
- Widget behavior settings
- V2 widgets (enhanced features)

#### 6. Security Settings

**Authentication:**
```
Require users to log in
Protect sensitive information
Integrate with your auth system
```

**User Controls:**
```
Text-only mode toggle
Voice interaction preferences
Privacy settings
```

**Webhooks:**
```
Call URL at conversation start
Call URL at conversation end
Use for: Logging, analytics, CRM integration
```

**Usage Limits:**
```
Max conversations per day
Rate limiting per user
Prevent abuse
Cost control
```

#### 7. Advanced Settings

**Speech Recognition:**

**Scribe Feature**
- New automatic speech recognition
- Improved accuracy
- Better handling of accents

**Keywords**
```
Add likely words/phrases:
- Product names: "MacBook Pro"
- Company terms: "SuperApp"
- Industry jargon: "Kubernetes"

Benefit: Improved recognition accuracy
Especially useful for: Unusual terms
```

**Conversation Behavior:**

**Interruption Sensitivity**
```
Low: Agent waits for pauses
High: Agent jumps in quickly

Adjust based on:
- Conversation style
- User feedback
- Use case requirements
```

**Silence Timeout**
```
How long before "Are you still there?"
Range: 3-30 seconds
Default: 10 seconds
```

**Auto-cutoff**
```
Terminate after X seconds of silence
Prevents: Open connections
Saves: Resources and costs
```

### Building a Multi-Agent Workflow

Let's build a practical example: Apple product store support.

**Business Scenario:**

Customer support for store selling Apple products:
- General product questions
- Stock availability queries
- Need specialized knowledge for each

**Architecture:**

```
Main Agent (Router)
    ↓
Analyzes question type
    ↓
    ├─→ Product Support (Specifications, features)
    └─→ Stock Specialist (Availability, inventory)
```

**Step-by-Step Setup:**

**1. Create Knowledge Bases**

Stock Information:
```
Document: Stock

Content:
- Apple Watch Series 11
- iPhone 13 Pro Max  
- MacBook Pro M4
```

Product Details:
```
Document: Apple Product Details

Content:
- Apple Watch Series 11 specifications
- Detailed features and capabilities
- Technical information
- Pricing tiers
```

**2. Configure Main Agent**

```
Name: Main Agent
System Prompt: "You're a customer support rep at a store 
                that sells Apple products. You direct the 
                user's question as appropriate."
Voice: Miss Walker
Knowledge Base: None (routing only, no direct answers)
```

**3. Configure Product Support Agent**

```
Name: Product Support
System Prompt: "You're able to answer general questions 
                about Apple products."
Voice: Russell (outgoing and excited)
Knowledge Base: Apple Product Details
Override Prompt: Yes (replaces main prompt)
```

**4. Configure Stock Specialist Agent**

```
Name: Stock Specialist
System Prompt: "You can answer questions about what Apple 
                products the store has in stock."
Voice: Stokes (relaxing, casual)
Knowledge Base: Stock
Override Prompt: Yes
```

**5. Set Up Routing Logic**

**Edge 1: Product Questions**
```
Type: LLM Condition
Label: Product Question
Condition: "The user has a general question about Apple products"
Routes To: Product Support Agent
```

**Edge 2: Stock Questions**
```
Type: LLM Condition
Label: Stock Question
Condition: "The user has a question about what Apple products 
           the store has in stock"
Routes To: Stock Specialist Agent
```

**How LLM Conditions Work:**

The main agent's LLM:
1. Receives user question
2. Reads condition descriptions
3. Determines which condition matches
4. Uses corresponding tool to transfer
5. Passes full conversation context

**Testing the Workflow:**

**Test 1: Product Question**
```
User: "I'm interested in buying an Apple Watch. 
       What's the latest version and price?"

Flow:
Main Agent → Analyzes → Product Question
           → Transfers to Product Support
           
Product Support: "The latest version is the Apple Watch 
                  Series 11, which has a reported launch 
                  price of around $399..."
```

**Test 2: Stock Question**
```
User: "What models of MacBook Pro do you have in stock?"

Flow:
Main Agent → Analyzes → Stock Question
           → Transfers to Stock Specialist
           
Stock Specialist: "We currently have the MacBook Pro M4 in stock."
```

**Test 3: Multi-turn Conversation**
```
User: "What's the latest Apple Watch?"
Product Support: "The Apple Watch Series 11..."

User: "Do you have it in stock?"
[Currently requires transfer back to main, then to stock]
[More advanced workflow would allow direct transfer]
```

**Workflow Limitations:**

Current simple flow doesn't handle:
- Agent-to-agent transfers (only main → specialist)
- Return to main agent
- Context sharing between specialists

**Solutions:**
- Add bidirectional transfer tools
- Create more complex edge logic
- Use n8n for sophisticated routing (tomorrow's lesson!)

### Key Takeaways from Day 1

**What We Accomplished:**

1. ✅ Set up ElevenLabs account
2. ✅ Created first voice agent
3. ✅ Configured knowledge bases
4. ✅ Built multi-agent workflow
5. ✅ Tested real-time voice interactions

**Skills Developed:**

- Voice agent configuration
- Knowledge base management
- Multi-agent routing logic
- Tool and webhook setup
- Widget deployment
- Security and advanced settings

**Strengths of ElevenLabs:**

| Feature | Benefit |
|---------|---------|
| Voice Quality | Industry-leading naturalness |
| Speed | Real-time, low latency |
| Ease of Use | Intuitive interface |
| Knowledge Bases | Simple RAG implementation |
| Multi-agent | Conversation routing |
| Deployment | Easy website embedding |

**Limitations:**

- Premium pricing (though free tier available)
- Workflow tool less robust than n8n
- Best for voice-specific use cases
- Complex logic better in dedicated platform

**Tomorrow's Preview:**

We'll integrate ElevenLabs with n8n using two different approaches:
1. n8n orchestrates (simple)
2. ElevenLabs orchestrates (recommended)

We'll build end-to-end voice agents with complex business logic!

---

<a name="day-2-integration"></a>
## Day 2: Integrating ElevenLabs with n8n

### Integration Approaches Overview

Two completely different patterns for combining ElevenLabs and n8n:

**Approach 1: n8n Orchestrates**
```
Linear workflow controlled by n8n

User speaks → n8n captures audio
           → Calls ElevenLabs (speech-to-text)
           → Processes in LLM
           → Calls ElevenLabs (text-to-speech)
           → Returns audio to user
```

**Approach 2: ElevenLabs Orchestrates** ⭐ Recommended
```
Voice agent workflow controlled by ElevenLabs

User speaks → ElevenLabs processes (real-time)
           → Agent decides to use tool
           → Tool calls n8n webhook
           → n8n executes business logic
           → Returns result to ElevenLabs
           → ElevenLabs speaks response
```

### Detailed Comparison

#### Approach 1: n8n Orchestrates

**Workflow Diagram:**

```
┌───────────────┐
│  Audio Input  │ User recording
└───────┬───────┘
        ↓
┌───────────────────────┐
│  n8n Workflow Start   │
└───────┬───────────────┘
        ↓
┌───────────────────────┐
│  ElevenLabs API       │ Speech → Text
│  (Speech-to-Text)     │
└───────┬───────────────┘
        ↓
┌───────────────────────┐
│  AI Agent (Gemini)    │ Process question
│  with Tools           │ Execute logic
└───────┬───────────────┘
        ↓
┌───────────────────────┐
│  ElevenLabs API       │ Text → Speech
│  (Text-to-Speech)     │
└───────┬───────────────┘
        ↓
┌───────────────────────┐
│  Return Audio File    │
└───────────────────────┘
```

**Advantages:**

✅ **Simplicity**
- All workflow on one canvas
- Easy to understand flow
- Linear, predictable execution

✅ **Visibility**
- See entire process
- Debug easily
- Clear data flow

✅ **Vendor Flexibility**
- Can swap ElevenLabs for alternatives
- Not locked into one provider
- Easy to change TTS/STT providers

✅ **Full Control**
- n8n manages everything
- Custom error handling
- Detailed logging

**Disadvantages:**

❌ **Higher Latency**
- Sequential processing required
- Must wait for audio collection
- API call overhead
- Not truly real-time

❌ **No Streaming**
- Batch processing only
- User waits for complete response
- Poor conversational feel

❌ **Misses ElevenLabs Features**
- No phone integration
- No advanced voice features
- Limited real-time capabilities

❌ **Complex Audio Handling**
- Need web interface for recording
- Audio file management
- Format conversions

**Best For:**
- Learning and experimentation
- Non-real-time use cases
- When vendor flexibility is crucial
- Simpler requirements

#### Approach 2: ElevenLabs Orchestrates ⭐

**Workflow Diagram:**

```
┌────────────────────────┐
│  ElevenLabs Agent      │ User speaks
│  (Real-time Voice)     │ Agent listens & understands
└────────┬───────────────┘
         ↓
         Agent analyzes question
         Decides tool needed
         ↓
┌────────────────────────┐
│  Tool: Webhook Call    │ POST to n8n
│  to n8n                │ Include question in body
└────────┬───────────────┘
         ↓
┌────────────────────────┐
│  n8n Workflow          │
│  ├─ Receive webhook    │
│  ├─ Process with AI    │
│  ├─ Use tools          │
│  │   └─ Google Sheets  │
│  └─ Return result      │
└────────┬───────────────┘
         ↓
         Result JSON
         ↓
┌────────────────────────┐
│  ElevenLabs Agent      │ Receives result
│  (Speaks Response)     │ Converts to speech
└────────────────────────┘ User hears answer
```

**Advantages:**

✅ **Low Latency** ⭐ Most Important
- Real-time audio processing
- Streaming transcription
- Immediate responses
- Natural conversation flow

✅ **Professional Voice Features**
- Phone system integration
- Advanced voice controls
- Enterprise-grade reliability
- Telephony support

✅ **Best of Both Platforms**
- ElevenLabs: Voice expertise
- n8n: Business logic power
- Each does what it's best at
- Modular architecture

✅ **Scalability**
- n8n handles complex workflows
- Easy to add integrations
- Update logic without changing voice
- Separate concerns

**Disadvantages:**

❌ **More Complex Setup**
- Two platforms to configure
- Webhook coordination required
- Distributed debugging

❌ **Less Linear Flow**
- Harder to visualize initially
- Multiple moving parts
- Requires understanding both systems

❌ **Initial Learning Curve**
- More concepts to grasp
- Tool configuration
- Webhook mechanics

**Best For:**
- Production applications ⭐
- Real-time voice interactions
- Professional deployments
- Scalable solutions
- Best user experience

### Recommendation

**Use Approach 2 (ElevenLabs Orchestrates)** for:
- Any production voice agent
- Customer-facing applications
- When user experience matters
- Scalable systems

**Use Approach 1 (n8n Orchestrates)** for:
- Learning and experimentation
- Non-real-time use cases
- When you need maximum flexibility
- Budget constraints (free alternatives to ElevenLabs)

### API Fundamentals Refresher

Before building, let's review essential API concepts:

**What is "Calling an API"?**

```
Making an HTTP request to an endpoint

Components:
- HTTP: Web communication protocol
- Endpoint: URL/web address
- Request: What you send
- Response: What comes back
```

**Example:**
```javascript
// Making an API call
fetch('https://api.example.com/users')
  .then(response => response.json())
  .then(data => console.log(data));
```

**HTTP Methods:**

**GET - Retrieve Information**
```
Purpose: Fetch data
Direction: Request data, receive response
Example: Get user profile
```

**POST - Send Information**
```
Purpose: Submit data
Direction: Send data in body, receive confirmation
Example: Create new user
Contains: JSON body with data
```

**Webhooks Explained:**

**Definition:**
> A webhook is a URL endpoint that receives HTTP requests to notify you about events. It's a "reverse API" - instead of you calling out, others call in.

**How Webhooks Work:**

```
You → Create endpoint (URL)
     ↓
You → Give URL to external service
     ↓
Event happens in external service
     ↓
Service → Calls your webhook URL
         ↓
Your system → Receives notification
             ↓
Your system → Takes action
```

**Common Webhook Uses:**
- Email received → Trigger workflow
- Slack message → Process and respond
- File uploaded → Start processing
- Payment completed → Update database

**n8n Integration Patterns:**

**For Integrated Platforms (Slack, Google, etc.):**
```
Dedicated Trigger Node (receives webhooks)
+
Dedicated Action Node (makes API calls)
```

**For Non-Integrated Platforms:**
```
Generic Webhook Node (receives any webhook)
+
Generic HTTP Request Node (calls any API)
```

**These generic nodes let you integrate with ANY service!**

### Building Approach 1: n8n Orchestrates

Let's build this step-by-step to understand the concepts.

#### Prerequisites

**1. ElevenLabs API Key**

Steps:
1. Go to elevenlabs.io
2. Sign in to your account
3. Navigate to: Developers
4. Click: API Keys tab
5. Click: Create Key

Configuration:
```
Name: n8n Integration (or any name)

Monthly Limit: 500 credits
(Recommended starting point)

Permissions:
- Text-to-Speech: Read
- Speech-to-Text: Read  
- Voice Library: Read
- Other APIs: Read access as needed

Security: Enable restrict key
```

6. Click: Create Key
7. Copy key immediately (shown once)
8. Store in password manager

**Cost Note:**
- Free tier includes credits
- Paid plans include thousands of credits
- 500 credit limit is safe for testing
- Most calls use 30-60 credits

**2. Google Gemini API Key**

Steps:
1. Visit: ai.studio.google.com
2. Sign in with Google account
3. Click: Get API Key
4. Create new key or use existing
5. Copy and store safely

**Why Gemini?**
- Excellent free tier
- Good performance
- Different from previous examples
- Gemini 3 Flash now available

#### Building the Workflow

**Step 1: Create Workflow**

1. Sign into n8n
2. Click: Create Workflow
3. Name: "n8n Orchestrates Voice Agent"

**Step 2: Add Chat Trigger (Temporary)**

For initial testing:
```
Add: On Chat Message trigger
Purpose: Easy testing during development
Later: Will replace with webhook
```

**Step 3: Add AI Agent**

Configuration:
```
Chat Model: Google Gemini

Credential: Create New
  - Paste Gemini API key
  - Save
  - Test connection ✅

Model: Gemini 3 Flash Preview
(Or latest available)

Tools: None (for now)
Memory: None (for now)
```

**Test Basic Setup:**
```
Open chat
Type: "Hi there"
Expected: "Hello! How can I help you today?"
```

**Step 4: Add Text-to-Speech**

1. Click + after AI Agent
2. Search: "ElevenLabs"
3. Note: May need to install community node
   - Click: Install
   - Wait for installation
   - Refresh if needed

Configuration:
```
Operation: Convert Text to Speech

Credential: Create New
  - Paste ElevenLabs API key
  - Save
  - Test connection ✅

Voice: Miss Walker
(Or your preferred voice)

Text to Say: Expression
  - Must be dynamic, not fixed
  - Drag "output" from AI Agent
  - Or type: {{ $json.output }}
```

**Understanding the Expression:**

```javascript
{{ $json.output }}

Breakdown:
- {{ }} = Expression markers
- $json = Incoming JSON data
- .output = The "output" field
- Result: "Hello! How can I help you today?"
```

**Alternative Input Method:**

```
1. Click in "Text to Say" field
2. Toggle to Expression mode
3. Drag "output" field from left panel
4. Automatically creates: {{ $json.output }}
```

**Test Text-to-Speech:**

1. Reset chat session
2. Type: "Hi there"
3. Workflow executes:
   ```
   Chat Input ✅
   AI Agent ✅  
   ElevenLabs TTS ✅
   ```
4. Result: Audio file generated

**Download and Listen:**

1. Click on ElevenLabs node
2. See output data
3. Find: data field (audio file)
4. Click: Download button
5. Play audio file

**Try Different Voices:**

Change voice to Jason:
```
Voice: Jason (calm, meditative)
Run again
Download new audio
Compare: Miss Walker vs Jason
```

**Step 5: Replace with Webhook**

Now for the real implementation:

**Remove:** Chat trigger

**Add:** Webhook node

Configuration:
```
HTTP Method: POST
(We'll be sending audio data)

Path: Auto-generated
(e.g., /webhook/abc123)

Response Mode: Respond to webhook node
(We'll add this node at the end)
```

**Two URLs Generated:**

**Test URL:**
```
https://your-n8n.app/webhook-test/abc123
Use during development
Only works when "Execute Workflow" is active
```

**Production URL:**
```
https://your-n8n.app/webhook/abc123
Use after publishing workflow
Always available
```

**Step 6: Add Speech-to-Text**

After webhook, add:

```
Node: ElevenLabs
Operation: Speech to Text

Audio Field: Will configure after seeing data
```

**Step 7: Add Response Node**

At end of workflow:

```
Node: Respond to Webhook

Respond With: First incoming item
Property: data
(This sends the generated audio back)
```

**Complete Linear Workflow:**

```
Webhook (receives audio)
    ↓
ElevenLabs Speech-to-Text
    ↓
AI Agent (Gemini)
    ↓
ElevenLabs Text-to-Speech
    ↓
Respond to Webhook (returns audio)
```

#### Testing with HTML Interface

**Create Test Page:**

Save as `voice.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Voice Agent Test</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 50px auto;
            padding: 20px;
        }
        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
        }
        button {
            padding: 10px 20px;
            margin: 5px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <h1>Voice Agent Tester</h1>
    
    <label>n8n Webhook URL:</label>
    <input type="text" id="webhookUrl" 
           placeholder="Paste test URL here">
    
    <div>
        <button id="startRecord">Start Recording</button>
        <button id="stopRecord" disabled>Stop Recording</button>
        <button id="sendAudio" disabled>Send to n8n</button>
    </div>
    
    <audio id="responseAudio" controls style="width: 100%; margin-top: 20px;"></audio>
    
    <p><em>Tip: Use test URL while building, switch to production URL when ready</em></p>
    
    <script>
        let mediaRecorder;
        let audioChunks = [];
        
        document.getElementById('startRecord').addEventListener('click', async () => {
            const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
            mediaRecorder = new MediaRecorder(stream);
            
            mediaRecorder.ondataavailable = (event) => {
                audioChunks.push(event.data);
            };
            
            mediaRecorder.onstop = () => {
                document.getElementById('sendAudio').disabled = false;
            };
            
            audioChunks = [];
            mediaRecorder.start();
            
            document.getElementById('startRecord').disabled = true;
            document.getElementById('stopRecord').disabled = false;
        });
        
        document.getElementById('stopRecord').addEventListener('click', () => {
            mediaRecorder.stop();
            document.getElementById('startRecord').disabled = false;
            document.getElementById('stopRecord').disabled = true;
        });
        
        document.getElementById('sendAudio').addEventListener('click', async () => {
            const audioBlob = new Blob(audioChunks, { type: 'audio/wav' });
            const formData = new FormData();
            formData.append('audio', audioBlob);
            
            const webhookUrl = document.getElementById('webhookUrl').value;
            
            try {
                const response = await fetch(webhookUrl, {
                    method: 'POST',
                    body: formData
                });
                
                const audioResponse = await response.blob();
                const audioUrl = URL.createObjectURL(audioResponse);
                document.getElementById('responseAudio').src = audioUrl;
            } catch (error) {
                console.error('Error:', error);
                alert('Error sending audio');
            }
            
            document.getElementById('sendAudio').disabled = true;
        });
    </script>
</body>
</html>
```

**How to Generate This File:**

> Ask ChatGPT or Claude: "Create an HTML page that records audio from microphone, posts it to a webhook URL via POST request, and plays the returned audio file."

**Testing Steps:**

1. Open `voice.html` in browser
2. Go to n8n workflow
3. Copy test URL from webhook node
4. Paste into input field on webpage
5. In n8n, click "Execute Workflow"
6. On webpage, click "Start Recording"
7. Speak clearly: "Well hi there. What is two plus two?"
8. Click "Stop Recording"
9. Click "Send to n8n"

**Expected First Result: ERROR ❌**

This is intentional! We need to see the data structure.

#### Debugging and Configuration

**Error 1: Speech-to-Text Field**

Double-click webhook node to see incoming data:

```json
{
  "audio": "base64-encoded-audio-data"
}
```

Fix in ElevenLabs Speech-to-Text node:
```
Input Binary Field: audio
(Not "data" - that was wrong assumption)
```

**Error 2: AI Agent Input**

Double-click AI Agent node:

```
Current: Source = Connected to chat trigger
Problem: We removed chat trigger!

Fix:
  Chat Input Source: Define below
  Expression: {{ $json.text }}
```

This pulls the transcribed text from ElevenLabs output.

**Test Again:**

1. Execute Workflow
2. Record: "Well hi there. What is two plus two?"  
3. Send to n8n
4. Result: SUCCESS ✅

**Verify:**

1. Audio plays in browser
2. Check workflow execution:
   ```
   Webhook ✅ (received audio)
   Speech-to-Text ✅ (transcribed)
   AI Agent ✅ (answered: "Two plus two is four")
   Text-to-Speech ✅ (generated audio)
   Respond to Webhook ✅ (returned audio)
   ```

**Example Output:**
```
Transcription: "Well hi there what is two plus two"
AI Response: "Two plus two is four"
Audio Response: Jason saying "Two plus two is four"
```

#### Enhancements

**Add Memory:**

```
Node: Simple Memory (Window Buffer Memory)
Configuration:
  - Session ID: Could use user ID
  - Context Window: 10 messages
Attach to: AI Agent
```

**Add Tools:**

Example - Google Sheets for portfolio data:

```
Node: Google Sheets Tool
Description: "Use this tool to retrieve the equity portfolio"
Configuration:
  - Connect to your sheet
  - Set up read access
Attach to: AI Agent
```

**Test with Tools:**

```
User: "How many shares of SPY do I hold?"

Flow:
1. Voice → Text transcription
2. AI Agent receives question
3. Agent uses Google Sheets tool
4. Tool queries spreadsheet
5. Returns: "2 shares"
6. Agent responds: "You currently hold 2 shares of SPY"
7. Text → Voice conversion
8. User hears response
```

**Limitations of Approach 1:**

Despite working well for this demo:
- Noticeable latency (2-4 seconds)
- Not truly real-time
- Sequential processing delays
- Better solutions exist (Approach 2)

### Building Approach 2: ElevenLabs Orchestrates ⭐

This is the **recommended production approach**.

#### Overview

```
User ←→ ElevenLabs Voice Agent (manages conversation)
              ↓ (when needed)
        Calls n8n webhook
              ↓
        n8n executes business logic
              ↓
        Returns result
              ↓
        ElevenLabs speaks answer
```

**Key Difference:**

ElevenLabs handles ALL voice interaction.
n8n is called ONLY for business logic via tools.

#### Part 1: Build n8n Business Logic

**Step 1: Create New Workflow**

Name: "ElevenLabs Agent Integration"

**Step 2: Add Webhook Trigger**

```
Node: Webhook
HTTP Method: POST
Response Mode: Respond to webhook node
```

**Step 3: Add AI Agent**

```
Chat Model: Google Gemini
  - Use existing credential
  - Model: Gemini 3 Flash Preview

Input Source: Define below (NOT chat trigger)
Expression: Will configure after testing

Memory: None (single-shot queries from voice agent)
```

**Step 4: Add Business Logic Tool**

Example: Google Sheets for portfolio:

```
Node: Google Sheets Tool

Description (Important!):
"Use this tool to retrieve the equity portfolio of the user to answer questions about their holdings"

Configuration:
  - Connect to portfolio spreadsheet
  - Read access
  - Set up columns mapping
```

**Why Description Matters:**

This tells the LLM:
- When to use the tool
- What the tool does
- What information it provides

**Step 5: Add Response Node**

```
Node: Respond to Webhook
Respond With: First incoming item (JSON from AI Agent)
```

**Temporary Testing Setup:**

Before connecting to ElevenLabs:

```
1. Add: On Chat Message (parallel to webhook)
2. Disable: Webhook trigger
3. Test via chat interface
4. Verify tool works
5. Re-enable: Webhook
6. Disable: Chat trigger
```

**Test in Chat:**

```
User: "Hi there"
Agent: "Hello! How can I help? If you'd like to check your equity portfolio..."

User: "How many SPY shares do I hold?"
Agent: [Uses Google Sheets tool]
       "You currently hold 2 shares of SPY"
```

#### Part 2: Configure ElevenLabs Agent

**Step 1: Create Agent**

In ElevenLabs:

```
Click: New Agent
Type: Blank Agent
Name: n8n Agent

System Prompt: "You are a helpful assistant"
Voice: Russell (outgoing and excited)
```

**Step 2: Add Webhook Tool**

Navigate to: Tools section

Click: Add Tool

Select: Webhook

**Configuration:**

```
Tool Name: equity_portfolio_question_tool
(No spaces - it's a function identifier)

Description:
"Use this tool to ask any question about the user's equity portfolio to a specialist assistant who should be able to answer"

Method: POST

URL: [Paste test URL from n8n webhook]

Timeout: 60 seconds
(Higher for complex queries)

Pre-tool Speech: Force agent to say something
(Prevents awkward silence: "Let me check that for you...")
```

**Step 3: Configure POST Body**

This is how we pass information to n8n:

**Body Description:**
```
"This contains a description of the question to ask the equity portfolio specialist"
```

**Field Configuration:**

```
Add Field:

Type: String
Identifier: question
Description: "The specific question about the user's equity portfolio for the specialist to answer"

Required: Yes
```

**How This Works:**

1. User asks question to ElevenLabs agent
2. Agent's LLM analyzes question
3. Decides to use equity_portfolio_question_tool
4. LLM fills in "question" field
5. Tool makes POST request:

```json
POST to n8n webhook
Body: {
  "question": "How many shares of SPY do I have?"
}
```

6. n8n receives, processes, responds
7. ElevenLabs speaks the answer

**Important Notes:**

The description tells the LLM:
- WHEN to use the tool (portfolio questions)
- WHAT to put in the question field (specific question)
- HOW the specialist will help (answer the question)

Clear, detailed descriptions = better tool usage!

#### Part 3: Connect and Test

**Step 1: Configure n8n Webhook Input**

We know the POST body will have a "question" field.

Update AI Agent:
```
Chat Input Source: Define below
Expression: {{ $json.body.question }}
```

This extracts the question from: `{"body": {"question": "..."}}`

**Step 2: Start n8n Listening**

Click: Execute Workflow

Workflow now waiting for webhook calls.

**Step 3: Test from ElevenLabs**

1. In ElevenLabs, click: Preview
2. Click: Call AI Agent
3. Speak: "How many shares of SPY do I have in my portfolio?"

**What Happens Behind the Scenes:**

```
1. ElevenLabs captures your speech
2. Transcribes to text (real-time)
3. LLM analyzes: "This is a portfolio question"
4. Decides: Use equity_portfolio_question_tool
5. Fills field: {"question": "How many shares of SPY do I have in my portfolio?"}
6. POSTs to n8n webhook
7. n8n workflow triggers
8. Webhook node receives POST
9. Extracts: $json.body.question
10. Passes to AI Agent
11. AI Agent uses Google Sheets tool
12. Tool queries spreadsheet
13. Returns: "2 shares"
14. Respond to Webhook sends back:
    {"output": "You currently hold 2 shares of SPY"}
15. ElevenLabs receives response
16. Agent formulates natural reply
17. Converts to speech
18. You hear: "You currently hold 2 shares of SPY in your portfolio"
```

**Expected First Test: Might Error**

If error, check:
- AI Agent input is configured ({{ $json.body.question }})
- Google Sheets tool is working
- Webhook is receiving data

**Second Test: Should Work!**

Everything flows smoothly.

**Try Follow-up Questions:**

```
User: "What other stocks do I have?"

Agent: "Let me check..."
       [Uses tool again]
       "Besides SPY, your portfolio includes BND, AOA..."
```

**Multiple Tool Calls Work!**

Each question triggers a new tool call, independently.

#### Part 4: Deploy to Production

**Step 1: Publish n8n Workflow**

1. Save workflow
2. Click: Publish
3. Copy: Production URL
4. Store safely

**Production URL Example:**
```
https://your-n8n.app/webhook/prod-abc123
```

**Step 2: Update ElevenLabs Tool**

1. Go to: Tools section in ElevenLabs
2. Edit: equity_portfolio_question_tool
3. Replace: Test URL with Production URL
4. Save (DON'T FORGET!)

**Step 3: Publish ElevenLabs Agent**

1. Click: Publish in ElevenLabs
2. Get: Shareable link
3. Copy link

**Step 4: Test Production**

Open shareable link in new browser tab:

```
User: "How many shares of SPY do I have?"
Agent: "Let me quickly check... You currently hold 2 shares of SPY"

User: "What other stocks do I have apart from SPY?"
Agent: "Let me check... Besides SPY, your portfolio includes BND, AOA, and AOR"

User: "What's the total value?"
Agent: [If tool supports] "Your total portfolio value is $X,XXX"
```

**Production Benefits:**

✅ No need to click "Execute Workflow"
✅ Always available
✅ Multiple conversations simultaneously
✅ Stable URLs
✅ Real-world ready

### Complete Data Flow Analysis

Let's trace one complete interaction:

**User Question: "How many SPY shares do I have?"**

```
┌─────────────────────────────────────┐
│ STEP 1: User Speaks                 │
├─────────────────────────────────────┤
│ Browser/app captures audio          │
│ Streams to ElevenLabs              │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 2: ElevenLabs Speech → Text   │
├─────────────────────────────────────┤
│ Real-time transcription             │
│ Output: "How many SPY shares do I   │
│         have?"                      │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 3: ElevenLabs LLM Processing  │
├─────────────────────────────────────┤
│ Analyzes question                   │
│ Identifies: Portfolio query         │
│ Decision: Use tool                  │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 4: Tool Execution             │
├─────────────────────────────────────┤
│ POST https://n8n.app/webhook/...   │
│ Body: {                             │
│   "question": "How many SPY shares  │
│                do I have?"          │
│ }                                   │
│ Timeout: 60s                        │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 5: n8n Webhook Receives       │
├─────────────────────────────────────┤
│ Trigger activates                   │
│ Extracts: $json.body.question       │
│ Value: "How many SPY shares do I    │
│        have?"                       │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 6: n8n AI Agent Processes     │
├─────────────────────────────────────┤
│ Receives question                   │
│ Analyzes: Need stock data           │
│ Decision: Use Google Sheets tool    │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 7: Google Sheets Query        │
├─────────────────────────────────────┤
│ Connects to spreadsheet             │
│ Searches for "SPY"                  │
│ Finds row with SPY data             │
│ Returns: Quantity = 2               │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 8: n8n Response Formation     │
├─────────────────────────────────────┤
│ AI Agent formats answer             │
│ Creates: {                          │
│   "output": "You currently hold 2   │
│             shares of SPY"          │
│ }                                   │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 9: Respond to Webhook         │
├─────────────────────────────────────┤
│ Sends JSON back to ElevenLabs      │
│ Tool call completes                 │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 10: ElevenLabs Receives       │
├─────────────────────────────────────┤
│ Tool result: "You currently hold 2  │
│              shares of SPY"         │
│ LLM formulates natural response     │
│ Adds conversational elements        │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 11: Text → Speech             │
├─────────────────────────────────────┤
│ Converts to audio (Russell's voice) │
│ Streams back to user                │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│ STEP 12: User Hears Response       │
├─────────────────────────────────────┤
│ "You currently hold 2 shares of SPY │
│  in your portfolio"                 │
└─────────────────────────────────────┘

Total Time: ~2-3 seconds ⚡
```

**Why This is Fast:**

- ElevenLabs handles voice in real-time (streaming)
- n8n business logic is quick (simple query)
- Tool call is single HTTP request
- No audio file transfers
- Optimized for conversation

### Key Advantages of Approach 2

**1. Superior Latency**

```
Approach 1 (n8n Orchestrates):
  4-6 seconds typical response time
  
  Why slower:
  - Collect complete audio
  - Upload to n8n
  - Call ElevenLabs API
  - Wait for transcription
  - Process in LLM
  - Call ElevenLabs API again
  - Wait for audio generation
  - Download audio file

Approach 2 (ElevenLabs Orchestrates):
  2-3 seconds typical response time ⚡
  
  Why faster:
  - Real-time speech processing
  - Streaming transcription
  - Parallel processing
  - Optimized voice pipeline
  - Only n8n logic adds time
```

**2. Professional Features**

ElevenLabs offers:
- Phone system integration (PSTN)
- WebRTC support
- Advanced voice controls
- Interruption handling
- Enterprise reliability
- Global voice delivery

These aren't available in Approach 1.

**3. Scalability**

```
n8n workflow can be:
- As complex as needed
- Hundreds of nodes
- Multiple integrations
- Sophisticated logic

Voice layer stays:
- Simple and consistent
- Optimized
- Reliable
```

**4. Maintainability**

```
Separation of concerns:
- Voice expertise → ElevenLabs
- Business logic → n8n
- Each platform does what it's best at
- Update one without breaking the other
```

### Troubleshooting Guide

**Common Issues and Solutions:**

**Issue: Webhook not triggering**

Symptoms:
- ElevenLabs tool times out
- n8n workflow never executes
- No error message

Check:
```
✓ n8n workflow in "Execute" mode (for test URL)
✓ n8n workflow published (for prod URL)
✓ Correct URL in ElevenLabs tool
✓ HTTP method is POST (not GET)
✓ ElevenLabs tool saved after changes
✓ Network connectivity
```

Fix:
```
1. Verify URL copied correctly
2. Test URL in Postman/curl first
3. Check n8n execution logs
4. Ensure no firewall blocking
```

**Issue: AI Agent can't find input**

Symptoms:
- Error: "Cannot read property 'question'"
- Agent gets undefined input
- Tool executes but fails

Check:
```
✓ Input source set to "Define below"
✓ Expression: {{ $json.body.question }}
✓ POST body structure correct
```

Fix:
```
1. Click AI Agent node
2. Chat Input → Define below
3. Set expression to match POST structure
4. Test with Execute Workflow
```

**Issue: Timeout errors**

Symptoms:
- ElevenLabs says "tool timed out"
- Long pauses before response
- Inconsistent behavior

Check:
```
✓ Timeout set high enough (60s+)
✓ n8n workflow complexity
✓ External API response times
✓ Network latency
```

Fix:
```
1. Increase timeout in ElevenLabs tool
2. Optimize n8n workflow
3. Add caching for slow APIs
4. Consider async processing
```

**Issue: Tool not being used**

Symptoms:
- Agent responds without calling tool
- Makes up answers instead
- Says it can't help

Check:
```
✓ Tool description clear and detailed
✓ Describes WHEN to use tool
✓ Describes WHAT tool does
✓ Question matches tool purpose
```

Fix:
```
1. Improve tool description
2. Add examples to description
3. Make trigger conditions explicit
4. Test with obvious questions first
```

**Issue: Audio quality problems**

Symptoms:
- Choppy audio
- Distortion
- Delay

Check:
```
✓ Internet connection quality
✓ Browser compatibility
✓ Microphone permissions
✓ Sample rate settings
```

Fix:
```
1. Test on different browser
2. Check network speed
3. Verify microphone works
4. Try different audio settings
```

### Best Practices

**Development Workflow:**

```
1. Build in test mode first
   - Use test URLs
   - Execute Workflow button
   - Easy debugging

2. Test thoroughly
   - Multiple scenarios
   - Edge cases
   - Error conditions

3. Switch to production
   - Update URLs
   - Publish workflows
   - Final testing

4. Monitor and iterate
   - Watch for issues
   - Collect feedback
   - Improve continuously
```

**Error Handling:**

```javascript
// In n8n workflows, add error handling

try {
  // Main logic
  const result = await executeBusinessLogic();
  return result;
} catch (error) {
  // Graceful degradation
  return {
    output: "I'm having trouble accessing that information right now. Please try again."
  };
}
```

**Security:**

```
✓ Never expose API keys in code
✓ Use environment variables in n8n
✓ Rotate keys regularly
✓ Monitor usage for anomalies
✓ Set appropriate rate limits
✓ Validate all inputs
✓ Sanitize outputs
```

**Optimization:**

```
✓ Minimize external API calls
✓ Cache frequently accessed data
✓ Use efficient database queries
✓ Monitor latency metrics
✓ Optimize for critical path
✓ Consider CDNs for static data
```

**Testing Checklist:**

```
Before deploying to production:

□ Test all conversation paths
□ Verify tool usage in various contexts
□ Check error handling
□ Test with poor network conditions
□ Verify timeout handling
□ Test concurrent users
□ Check webhook reliability
□ Verify production URLs
□ Test on multiple devices
□ Get user feedback
```

### Day 2 Summary

**What We Built:**

1. **Approach 1** - n8n orchestrates everything
   - Complete audio workflow
   - Used ElevenLabs APIs
   - Learned API patterns
   - Understood limitations

2. **Approach 2** ⭐ - ElevenLabs orchestrates (Recommended)
   - Professional voice agent
   - n8n business logic
   - Webhook integration
   - Production-ready

**Skills Developed:**

✅ API credential management
✅ HTTP methods (GET/POST)
✅ Webhook configuration
✅ POST body structure
✅ Expression writing
✅ Multi-platform integration
✅ Testing and debugging
✅ Production deployment

**Key Concepts:**

- **APIs** - Making HTTP requests to endpoints
- **Webhooks** - Receiving HTTP requests as triggers
- **POST Bodies** - Sending data in HTTP requests
- **Tools** - Extending AI capabilities
- **Real-time Voice** - ElevenLabs streaming advantage
- **Business Logic** - Complex workflows in n8n

**Why Approach 2 is Better:**

| Aspect | Approach 1 | Approach 2 |
|--------|-----------|------------|
| Latency | 4-6 seconds | 2-3 seconds ⚡ |
| Voice Features | Basic | Professional |
| Scalability | Limited | Excellent |
| Complexity | Simple | Moderate |
| Best For | Learning | Production |

**Tomorrow's Preview:**

We dive into RAG (Retrieval-Augmented Generation):
- Understanding embeddings
- Vector databases
- Semantic search
- Building knowledge bases
- Agentic RAG patterns

Get ready to make your voice agents truly expert!

---

*End of Part 1*
*Continuing in next message with Day 3 and Day 4...*
# Week 2: AI Voice Agents and RAG - Part 2

**Days 3-5: RAG Theory, Supabase Implementation, and Final Integration**

---

<a name="day-3-rag"></a>
## Day 3: Understanding RAG (Retrieval-Augmented Generation)

### Introduction to RAG

**What is RAG?**

RAG stands for **Retrieval-Augmented Generation**. It's a technique that makes LLMs appear more knowledgeable by providing them with relevant context from external knowledge bases.

**The Core Philosophy:**

> RAG is fundamentally a clever "hack" - we enhance LLM responses by inserting relevant information into their prompts. It's simple, practical, and remarkably effective.

**Why RAG Matters:**

Traditional approach (expensive):
```
Custom LLM Training
├─ Requires massive datasets
├─ Very expensive ($$$$$)
├─ Time-consuming (months)
├─ Difficult to update
└─ Needs ML expertise
```

RAG approach (practical):
```
Existing LLM + Dynamic Context
├─ Much cheaper ($$)
├─ Fast to implement (days/weeks)
├─ Easy to update (just update documents)
├─ No ML training needed
└─ Scales efficiently
```

### The Small Idea Behind RAG

**Basic Concept:**

Make an LLM more knowledgeable by adding relevant information to the prompt.

**Simple Example:**

Without RAG:
```
User: "How much does a ticket to London cost?"

Prompt to LLM:
"How much does a ticket to London cost?"

LLM Response:
"I don't have access to current pricing information for flights."
```

With RAG:
```
User: "How much does a ticket to London cost?"

Prompt to LLM:
"How much does a ticket to London cost?

Background information:
- New York to London round-trip economy: $599
- New York to Paris round-trip economy: $699
- Los Angeles to London round-trip economy: $850

Please answer based on this information."

LLM Response:
"A round-trip economy ticket from New York to London costs $599."
```

**The Mechanism:**

```
┌─────────────────┐
│ User Question   │
└────────┬────────┘
         ↓
┌─────────────────────────────┐
│ Find Relevant Information   │
│ from Knowledge Base         │
└────────┬────────────────────┘
         ↓
┌─────────────────────────────┐
│ Add to Prompt as Context    │
└────────┬────────────────────┘
         ↓
┌─────────────────────────────┐
│ LLM Generates Response      │
│ Using Provided Context      │
└─────────────────────────────┘
```

**You Can Try This Now!**

Open ChatGPT and experiment:

```
"How much does it cost to fly from New York to London?

By the way, here's some current pricing:
- NYC to London economy round-trip: $599
- NYC to London business class: $2,499
- NYC to Paris economy round-trip: $699

Please answer based on this information."
```

The LLM will use the provided context even though it doesn't have this data in its training!

### The Problem: Scalability

**The Challenge:**

What if you have pricing for 1,000 destinations? Or product details for 60,000 items?

**Naive Approach (Doesn't Work):**

```
Prompt:
"How much to fly to London?

Here's pricing for every city we serve:
- New York to London: $599
- New York to Paris: $699
- New York to Tokyo: $1,299
- New York to Sydney: $1,599
- New York to Dubai: $899
... [995 more cities with pricing]
- New York to Auckland: $1,799

Please find the London pricing."

Problems:
✗ Overwhelming amount of irrelevant data
✗ Hard for LLM to locate the right answer
✗ May exceed context window limits (tokens)
✗ Wastes processing power and money
✗ Slower response times
✗ Dilutes attention on relevant information
```

**What We Actually Need:**

A way to intelligently select only the **most relevant** subset of information.

### The Big Idea: Semantic Search

**The Solution:**

Use advanced techniques to find information that's **semantically similar** to the question, even when exact words don't match.

**Traditional Keyword Search vs. Semantic Search:**

```
Question: "How much to fly to Heathrow?"

Traditional Keyword Search:
  Search for: "Heathrow"
  Problem: Database only has "London"
  Result: ✗ No matches found
  Limitation: Brittle, word-dependent

Semantic Search:
  Understands: Heathrow = London's airport
  Finds: "London" pricing information
  Result: ✓ Returns relevant context
  Benefit: Fuzzy, meaning-based matching
```

**Real-World Examples:**

| User Query | Traditional Search | Semantic Search |
|------------|-------------------|-----------------|
| "Laptop repair cost" | Searches for exact words | Finds "computer maintenance pricing" |
| "CEO contact" | Searches "CEO" | Finds "Chief Executive Officer" |
| "Heathrow pricing" | Searches "Heathrow" | Finds "London airport" rates |

**This Requires Understanding Embedding Models**

### Embedding Models Explained

#### What is an Embedding Model?

**Standard LLMs We Use:**
```
Input: Text
Process: Predict next tokens
Output: Generated text (words/sentences)
Purpose: Conversation, answers, content creation
```

**Embedding Models (Different Type):**
```
Input: Text  
Process: Encode meaning into numbers
Output: Vector (list of numbers)
Purpose: Convert meaning → numerical representation
```

**Also Known As:**
- Encoder
- Encoding model
- Embedder
- Vector embedding model
- Embedding LLM

**All these terms refer to the same concept!**

#### How Embedding Models Work

**The Process:**

```
Input Text:
"How much does it cost to fly to London?"
         ↓
┌────────────────────────────┐
│   Embedding Model          │
│ (e.g., text-embedding-     │
│       3-small)             │
└────────┬───────────────────┘
         ↓
Output Vector:
[0.234, -0.451, 0.783, 0.128, -0.392, ...]
         ↑
   1,536 numbers (for text-embedding-3-small)
```

**What These Numbers Represent:**

The numbers encode the **semantic meaning** of the text. Think of them as coordinates in multi-dimensional space.

**Simplified Analogy (3D Space):**

```
If model outputs 3 numbers: [2, 5, 3]
  - X coordinate: 2
  - Y coordinate: 5  
  - Z coordinate: 3
  - Point in 3D space: ●
  
Actual models output 1,000-1,500 numbers:
  - Point in 1,000-dimensional space
  - Hard to visualize but same concept
  - Called a "vector" or "embedding"
```

**Visual Representation (Simplified to 2D):**

```
        Y axis
         ↑
         │
    [B]  │     ← "What's the price to Heathrow?"
         │     (Similar meaning to A)
    [A]  │     ← "How much to fly to London?"
         │     (Close together = similar meaning)
         │
         │
         │________________→ X axis
                      [C] ← "Best pizza in Chicago"
                           (Far away = different topic)
```

#### The Magic: Similar Meanings = Close Vectors

**Key Principle:**

Text with similar meanings produces vectors that are **close together** in multidimensional space.

**Example Vectors:**

```
Text A: "How much does it cost to fly to London?"
Vector A: [0.234, -0.451, 0.783, 0.128, ...]

Text B: "What's the ticket price to Heathrow Airport?"
Vector B: [0.241, -0.448, 0.779, 0.135, ...]
         ↑ Very similar numbers!
         ↑ Semantically similar → geometrically close

Text C: "Best deep-dish pizza restaurants in Chicago"
Vector C: [0.912, 0.347, -0.521, -0.783, ...]
         ↑ Very different numbers!
         ↑ Different topic → geometrically distant
```

**Measuring Closeness:**

Mathematically: **Cosine Similarity** (a precise calculation)
Intuitively: Think of "distance between points in space"

```
Cosine Similarity Scale:
1.0 = Identical meaning
0.8-0.9 = Very similar
0.5-0.7 = Somewhat related
0.0-0.4 = Different topics
-1.0 = Opposite meaning
```

**Important Clarifications:**

**1. It's About Meaning, Not Words**
```
Similar meaning despite different words:
"cost to fly to London" ≈ "price of ticket to Heathrow"
Different words: ✓
Same meaning: ✓
Similar vectors: ✓
```

**2. Learned Through Massive Training**
```
Training Process:
├─ Billions of text examples
├─ Learns associations
│  ├─ Heathrow → London
│  ├─ ticket → price
│  └─ fly → flight
└─ Encodes semantic relationships
```

**3. Different Models, Different Dimensions**
```
Popular Embedding Models:

OpenAI text-embedding-3-small:  1,536 dimensions
OpenAI text-embedding-3-large:  3,072 dimensions
OpenAI text-embedding-ada-002:  1,536 dimensions (legacy)
Google text-embedding-004:      768 dimensions
Cohere embed-english-v3.0:      1,024 dimensions
```

### Semantic Search with Embeddings

Now we understand how to use embeddings for intelligent, "fuzzy" search.

#### Setup Phase (Done Once)

**Convert Knowledge Base to Vectors:**

```
Knowledge Base Documents:

Doc 1: "New York to London economy: $599"
Doc 2: "NYC to Paris business class: $1,200"  
Doc 3: "Heathrow Airport transit information..."
Doc 4: "London hotel recommendations near airport..."
Doc 5: "Tokyo to London routing via Dubai..."
... [1,000 more documents]

Step 1: Generate embeddings
├─ Doc 1 → [0.234, -0.451, 0.783, ...]
├─ Doc 2 → [0.567, 0.123, -0.341, ...]
├─ Doc 3 → [0.251, -0.438, 0.776, ...]
├─ Doc 4 → [0.263, -0.442, 0.759, ...]
└─ Doc 5 → [0.189, -0.523, 0.691, ...]

Step 2: Store in database
┌────┬──────────────────┬──────────────────────┐
│ ID │    Content       │      Vector          │
├────┼──────────────────┼──────────────────────┤
│ 1  │ "NYC→London $599"│ [0.234, -0.451, ...] │
│ 2  │ "NYC→Paris $1200"│ [0.567, 0.123, ...]  │
│ 3  │ "Heathrow info"  │ [0.251, -0.438, ...] │
│ 4  │ "London hotels"  │ [0.263, -0.442, ...] │
│ 5  │ "Tokyo→London"   │ [0.189, -0.523, ...] │
└────┴──────────────────┴──────────────────────┘
```

This is done once during **data ingestion**.

#### Query Phase (Every Question)

**Finding Relevant Information:**

```
User Question: "How much to fly to Heathrow?"

Step 1: Convert question to vector
├─ Input: "How much to fly to Heathrow?"
├─ Embedding Model processes
└─ Output: [0.247, -0.445, 0.781, ...]

Step 2: Compare to all document vectors
├─ Calculate similarity to each stored vector
├─ Use cosine similarity formula
└─ Rank by similarity score

Results:
┌────┬──────────────────┬────────────┐
│ ID │    Content       │ Similarity │
├────┼──────────────────┼────────────┤
│ 1  │ "NYC→London $599"│   0.98     │ ← Highest!
│ 3  │ "Heathrow info"  │   0.87     │
│ 4  │ "London hotels"  │   0.76     │
│ 5  │ "Tokyo→London"   │   0.54     │
│ 2  │ "NYC→Paris $1200"│   0.42     │
└────┴──────────────────┴────────────┘

Step 3: Retrieve top K matches
├─ Take top 3-5 most similar
├─ Get original text content
└─ Prepare for LLM

Step 4: Build enhanced prompt
"User question: How much to fly to Heathrow?

Relevant context:
1. New York to London economy round-trip: $599
2. Heathrow Airport is London's main international airport...
3. London hotel recommendations near Heathrow...

Please answer the user's question using this context."

Step 5: Send to LLM
├─ LLM reads question + context
├─ Generates informed response
└─ Response consistent with context

LLM Response:
"A round-trip economy ticket to Heathrow (London's main airport) 
from New York costs $599."
```

**Why This Works:**

```
Question mentions: "Heathrow"
Database has: "London"

Traditional search: ✗ No match
Semantic search:
  ├─ Understands Heathrow = London airport
  ├─ Finds semantically similar content
  └─ ✓ Returns relevant pricing
```

### Complete RAG Architecture

**Full End-to-End Flow:**

```
┌─────────────────────────────────────────────────────────┐
│                    USER INTERACTION                      │
│  User: "How much to fly to Heathrow?"                   │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│              STEP 1: VECTORIZE QUESTION                  │
├─────────────────────────────────────────────────────────┤
│  Embedding Model: text-embedding-3-small                 │
│  Input: "How much to fly to Heathrow?"                  │
│  Output: [0.247, -0.445, 0.781, ..., 0.331]            │
│         (1,536 numbers representing meaning)             │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│         STEP 2: SEMANTIC SEARCH IN VECTOR DB            │
├─────────────────────────────────────────────────────────┤
│  Vector Database Operations:                             │
│    1. Compare question vector to all stored vectors     │
│    2. Calculate cosine similarity for each              │
│    3. Rank by similarity score                          │
│    4. Return top K most similar (e.g., top 5)          │
│                                                          │
│  Search Results:                                        │
│    Doc 47: similarity 0.98 ← "NYC to London $599"      │
│    Doc 134: similarity 0.87 ← "Heathrow transit info"  │
│    Doc 89: similarity 0.76 ← "London hotels"           │
│    Doc 203: similarity 0.54 ← "European destinations"  │
│    Doc 12: similarity 0.51 ← "Airport parking"         │
└────────────────────┬────────────────────────────────────┘
                     ↓
        Retrieve ORIGINAL TEXT for top matches
                     ↓
┌─────────────────────────────────────────────────────────┐
│          STEP 3: CONSTRUCT ENHANCED PROMPT              │
├─────────────────────────────────────────────────────────┤
│  System: You are a helpful travel assistant.            │
│                                                          │
│  User: How much to fly to Heathrow?                     │
│                                                          │
│  Relevant Context:                                      │
│  - New York to London economy round-trip: $599         │
│  - Heathrow is London's main international airport     │
│  - London hotels near Heathrow available from $120/nt  │
│                                                          │
│  Please provide a helpful answer based on this context. │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│             STEP 4: LLM GENERATES RESPONSE              │
├─────────────────────────────────────────────────────────┤
│  LLM: GPT-4, Claude, Gemini, etc.                       │
│    - Reads enhanced prompt with context                 │
│    - Generates answer using provided information        │
│    - Response is contextually accurate                  │
└────────────────────┬────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────────────────┐
│                  FINAL RESPONSE                         │
│                                                          │
│  "A round-trip economy ticket from New York to          │
│   Heathrow Airport (London) costs $599. Heathrow is     │
│   London's main international airport. If you need      │
│   accommodation, hotels near the airport start at       │
│   around $120 per night."                               │
└─────────────────────────────────────────────────────────┘
```

### Critical Clarifications

#### 1. The Answering LLM Never Sees Vectors

**Common Misconception:**

```
❌ WRONG:
Prompt sent to answering LLM:
"Question: How much to fly to Heathrow?
Context vectors: [0.234, -0.451, 0.783, ...]
                 [0.251, -0.438, 0.776, ...]"
```

**Reality:**

```
✓ CORRECT:
Prompt sent to answering LLM:
"Question: How much to fly to Heathrow?
Context: New York to London economy: $599
         Heathrow is London's main airport..."
```

**The Complete Truth:**

```
Embedding Model Role:
  ├─ ONLY used for finding similar content
  ├─ Converts text → numbers for comparison
  └─ Never involved in answering

Answering LLM Role:
  ├─ ONLY sees text (never vectors)
  ├─ Receives enhanced prompt with context
  └─ Generates human-readable response

These are SEPARATE processes!
```

#### 2. Two Completely Different LLMs

**Embedding Model:**
```
Purpose: Text → Numbers (for searching)
Input: Any text
Output: Vector (list of numbers)
Example: text-embedding-3-small (OpenAI)
Capabilities: Semantic encoding only
```

**Answering Model:**
```
Purpose: Text → Text (for conversation)
Input: Text prompt with context
Output: Human-readable answer
Example: GPT-4, Claude, Gemini
Capabilities: Understanding, reasoning, generation
```

**They Are Completely Independent:**

```
Can be from different companies: ✓
Example combinations:
  ├─ Embedding: Google text-embedding-004
  └─ Answering: Claude from Anthropic
  
  ├─ Embedding: OpenAI text-embedding-3-small
  └─ Answering: Gemini from Google
  
  ├─ Embedding: Cohere embed-english-v3
  └─ Answering: GPT-4 from OpenAI

All work perfectly fine together!
```

**Interaction Flow:**

```
Embedding Model ────┐
                    ├─→ Never interact
Answering Model ────┘

Workflow:
1. Embedding model: Question → Vector
2. Database: Find similar vectors
3. Database: Return original TEXT
4. Answering model: Generate response from TEXT
```

### Vector Databases

#### What is a Vector Database?

A database specifically optimized for storing and querying high-dimensional vectors (embeddings).

**Special Capabilities:**

**1. Efficient Vector Storage**
```
Traditional Database:
  Great for: Exact matches
  Query: WHERE name = 'London'
  Result: ✓ Fast exact match
  
Vector Database:
  Great for: Similarity searches
  Query: WHERE vector SIMILAR TO [0.247, -0.445, ...]
  Result: ✓ Fast approximate nearest neighbors
```

**2. Fast Similarity Calculations**
```
Capability:
  ├─ Compare to millions of vectors quickly
  ├─ Optimized algorithms (ANN - Approximate Nearest Neighbors)
  ├─ Returns top K matches in milliseconds
  └─ Scales to billions of vectors
```

**3. High-Dimensional Support**
```
Handles efficiently:
  ├─ 384 dimensions (lightweight models)
  ├─ 768 dimensions (BERT-style models)
  ├─ 1,536 dimensions (OpenAI models)
  └─ 3,072 dimensions (large models)
  
Regular databases: ✗ Very slow at this scale
```

#### Popular Vector Databases

**Specialized Vector Databases:**

| Database | Type | Best For |
|----------|------|----------|
| Pinecone | Cloud-native | Managed service, easy scaling |
| Weaviate | Open-source | Self-hosted, ML-native |
| Milvus | Open-source | Large-scale production |
| Qdrant | Open-source | Fast similarity search |
| Chroma | Open-source | Embedded, lightweight |

**Traditional Databases with Vector Support:**

| Database | Extension/Feature | Notes |
|----------|------------------|-------|
| PostgreSQL | pgvector | Most popular, production-ready |
| MongoDB | Vector Search | Good for existing MongoDB users |
| Elasticsearch | Dense Vector | Search + vectors combined |
| Redis | Vector Similarity | Fast in-memory operations |
| MySQL | Vector type (8.0.31+) | Newer, less mature |

**For This Course: Supabase**

```
Supabase = Managed PostgreSQL + pgvector

Why we chose it:
  ✓ Built on PostgreSQL (battle-tested)
  ✓ pgvector extension (mature, reliable)
  ✓ Generous free tier
  ✓ Popular in startup/agency world
  ✓ Great n8n integration
  ✓ Easy to use
  ✓ Scalable from hobby to enterprise
```

### Advanced RAG Concepts

#### Chunking Strategy

**The Problem:**

Large documents need to be broken into smaller, searchable pieces.

**Example Scenario:**

```
Document: 50-page product manual (25,000 words)

Challenge:
  ├─ Too large for single embedding
  ├─ Mixed topics throughout
  ├─ Need granular retrieval
  └─ Want relevant sections only
```

**Chunking Options:**

**1. One Giant Chunk (Entire Document)**
```
Pros:
  ✓ Simple
  ✓ Preserves all context
  
Cons:
  ✗ Too much irrelevant information
  ✗ May exceed embedding limits
  ✗ Poor retrieval precision
  ✗ Wastes tokens when used
```

**2. Sentence-Level Chunks**
```
Pros:
  ✓ Very granular
  ✓ Precise matching
  
Cons:
  ✗ Not enough context
  ✗ Breaks thought flow
  ✗ May miss broader meaning
```

**3. Paragraph-Level Chunks** ✓ Recommended
```
Pros:
  ✓ Good balance
  ✓ Sufficient context
  ✓ Manageable size
  ✓ Natural breaks
  
Cons:
  ~ May still break mid-topic
  ~ Needs overlap for continuity
```

**4. Semantic Chunks** (Advanced)
```
Pros:
  ✓ Topic-aware grouping
  ✓ Preserves meaning
  ✓ Optimal retrieval
  
Cons:
  ~ More complex to implement
  ~ Requires additional ML
  ~ Slower processing
```

**Common Chunking Strategies:**

**Fixed-Size Chunking:**
```python
Settings:
  ├─ Chunk size: 1,000 characters
  ├─ Overlap: 200 characters
  └─ Split on: Character count

Example:
  Chunk 1: chars 0-1000
  Chunk 2: chars 800-1800 (200 overlap)
  Chunk 3: chars 1600-2600 (200 overlap)
  
Pros: Simple, predictable
Cons: May break mid-sentence
```

**Sentence-Aware Chunking:**
```python
Settings:
  ├─ Target size: ~1,000 chars
  ├─ Split on: Sentence boundaries
  ├─ Overlap: 1-2 sentences
  └─ Respect: Paragraph breaks

Pros: Natural breaks, better context
Cons: Variable chunk sizes
```

**Paragraph Chunking:**
```python
Settings:
  ├─ Split on: Paragraph breaks
  ├─ Combine: 1-2 paragraphs per chunk
  ├─ Max size: ~1,500 characters
  └─ Overlap: Partial paragraphs

Pros: Preserves document structure
Cons: Highly variable sizes
```

**Semantic Chunking:**
```python
Process:
  ├─ Analyze: Text semantics with ML
  ├─ Detect: Topic/theme changes
  ├─ Split: At semantic boundaries
  └─ Optimize: For meaning preservation

Pros: Most intelligent grouping
Cons: Computational overhead
```

**Best Practice:**

> There's no universal "best" chunking strategy. Test different approaches and measure which works best for YOUR specific data and query patterns.

**Default Recommendation:**

```
Start with:
  ├─ Size: 1,000 characters
  ├─ Overlap: 200 characters
  ├─ Split: On sentence boundaries
  └─ Test and adjust based on results
```

#### Metadata in RAG

**What is Metadata?**

Additional information tagged to each chunk for filtering and context.

**Structure:**

```json
{
  "content": "MacBook Pro M4 features advanced...",
  "metadata": {
    "product_category": "laptops",
    "brand": "Apple",
    "price_range": "premium",
    "last_updated": "2024-01-15",
    "department": "electronics",
    "in_stock": true
  }
}
```

**Use Cases:**

**1. Pre-Filtering Before Search**
```
Query: "Show me affordable laptops under $1000"

Without metadata:
  ├─ Semantic search ALL products
  ├─ Hope budget laptops rank highest
  └─ May return expensive laptops if semantically similar

With metadata:
  ├─ Filter: price_range IN ("budget", "mid-range")
  ├─ Filter: product_category = "laptops"
  ├─ Then: Semantic search only filtered results
  └─ Guaranteed relevant results
```

**2. Providing Context to LLM**
```
Enhanced context sent to LLM:
"MacBook Pro M4 specifications and features...

[Metadata]
Category: Laptops
Brand: Apple
Price Range: Premium ($2000-$3000)
Last Updated: January 2024
Stock Status: Available
"
```

**3. Access Control**
```json
{
  "content": "Q4 financial projections...",
  "metadata": {
    "department": "finance",
    "access_level": "executive",
    "classification": "confidential"
  }
}

Filter by user permissions:
  ├─ User role: "marketing" → Skip this doc
  ├─ User role: "executive" → Include this doc
  └─ Ensures data security
```

**4. Multi-Tenancy**
```json
{
  "content": "Customer support ticket...",
  "metadata": {
    "company_id": "acme-corp",
    "client_type": "enterprise"
  }
}

Filter by company:
  ├─ Each customer sees only their data
  ├─ Shared vector database
  └─ Efficient resource usage
```

**5. Temporal Filtering**
```json
{
  "content": "Product pricing information...",
  "metadata": {
    "valid_from": "2024-01-01",
    "valid_until": "2024-12-31",
    "version": "2024-Q1"
  }
}

Query with time awareness:
  ├─ Only include current pricing
  ├─ Exclude outdated information
  └─ Version-specific results
```

### Traditional RAG vs. Agentic RAG

#### Traditional RAG (Linear Workflow)

**Architecture:**

```
┌──────────────┐
│ User Question│
└──────┬───────┘
       ↓
┌──────────────────────┐
│ Hardcoded Retrieval  │ ← Fixed workflow
│ - Always same method │   No decision-making
│ - Fixed parameters   │   Code controls everything
│ - Vector search only │
└──────┬───────────────┘
       ↓
┌──────────────────────┐
│ LLM Generates        │
│ Response             │
│ (Using context)      │
└──────────────────────┘
```

**Characteristics:**

```
✓ Simple and predictable
✓ Fast (no decision overhead)
✓ Easy to debug
✓ Deterministic behavior

✗ Inflexible
✗ Can't adapt to query types
✗ May retrieve too much/too little
✗ One-size-fits-all approach
```

**Example Flow:**

```
User: "What's the cheapest laptop?"

Traditional RAG Process:
1. Vectorize question
2. Search vector DB for similar content
3. Return top 5 matches
4. Send to LLM
5. Generate answer

Problem:
  ├─ May not find actual prices effectively
  ├─ Semantic match ≠ price sorting
  └─ Relies on luck to find cheapest
```

#### Agentic RAG (Adaptive Workflow)

**Architecture:**

```
┌──────────────┐
│ User Question│
└──────┬───────┘
       ↓
┌─────────────────────────────────────────┐
│           AI AGENT (LLM-Driven)         │
│                                         │
│  Analyzes question and decides:         │
│    - What retrieval method(s)?          │
│    - How many searches?                 │
│    - What search parameters?            │
│    - Need to combine methods?           │
│    - Should I try again?                │
│                                         │
│  Available Tools:                       │
│    ├─ Vector Search                     │
│    ├─ SQL Query                         │
│    ├─ Keyword Search                    │
│    ├─ Graph Traversal                   │
│    └─ Re-ranking                        │
└──────┬──────────────────────────────────┘
       │
       ├─ Tool 1: Vector Search
       │    ↓
       │  ┌──────────────────────┐
       │  │ Semantic similarity  │
       │  │ Top K results        │
       │  │ Threshold filtering  │
       │  └──────────────────────┘
       │
       ├─ Tool 2: SQL Query
       │    ↓
       │  ┌──────────────────────┐
       │  │ Structured queries   │
       │  │ Price comparisons    │
       │  │ Exact filtering      │
       │  └──────────────────────┘
       │
       ↓
   ┌──────────────────────┐
   │ Agent evaluates      │
   │ retrieved context:   │
   │   - Sufficient?      │
   │   - Need more?       │
   │   - Try different?   │
   └──────┬───────────────┘
          ↓
   ┌──────────────────────┐
   │ Generate Response    │
   │ (Optimal context)    │
   └──────────────────────┘
```

**Example Decision-Making:**

**Query 1: "What's the cheapest laptop?"**

```
Agent Reasoning:
"This is a price comparison query requiring:
 1. Access to structured price data
 2. Sorting by price
 3. Product details for context"

Agent Actions:
1. Use SQL query tool
   - SELECT * FROM products
   - WHERE category = 'laptop'
   - ORDER BY price ASC
   - LIMIT 1

2. Get cheapest: Dell Inspiron at $499

3. Use vector search for product details
   - Query: "Dell Inspiron specifications"
   - Get: Full product description

4. Combine results

Response:
"The most affordable laptop is the Dell Inspiron at $499. 
It features an Intel i3 processor, 8GB RAM, and 256GB SSD..."
```

**Query 2: "Tell me about our AI ethics policy"**

```
Agent Reasoning:
"This is a policy question that may span multiple documents:
 1. AI policy document
 2. Ethics guidelines
 3. Related ML standards"

Agent Actions:
1. Vector search: "AI policy"
   - Returns: Main AI policy doc

2. Vector search: "artificial intelligence ethics"
   - Returns: Ethics guidelines

3. Vector search: "machine learning standards"
   - Returns: ML best practices

4. Vector search: "data science governance"
   - Returns: Governance framework

5. Synthesize all results

Response:
"Our AI ethics policy emphasizes [synthesis of 4 documents]..."
```

**Query 3: "Laptops with 16GB RAM under $1500"**

```
Agent Reasoning:
"This combines metadata filtering and price range:
 1. Need exact RAM specification
 2. Need price filtering
 3. Then semantic ranking for best matches"

Agent Actions:
1. Use metadata filter
   - RAM = "16GB"
   - price < 1500

2. Vector search within filtered results
   - Query: "best laptops for productivity"
   - Semantic ranking

3. Return top matches

Response:
"I found 5 laptops with 16GB RAM under $1500: [detailed list]"
```

**Comparison Table:**

| Aspect | Traditional RAG | Agentic RAG |
|--------|----------------|-------------|
| Decision Making | Hardcoded | LLM-driven |
| Flexibility | Fixed workflow | Adaptive |
| Tools | Single method | Multiple tools |
| Iteration | One-shot | Can retry/refine |
| Query Adaptation | None | Per query type |
| Complexity | Low | Higher |
| Latency | Faster | Slower (more steps) |
| Accuracy | Good | Better |
| Cost | Lower | Higher |
| Best For | Simple queries | Complex queries |

### Is RAG Dead?

A common debate in the AI community. Let's examine the arguments.

#### Argument 1: "Context Windows Are Huge Now"

**The Claim:**
```
"Modern LLMs have 100K-1M+ token context windows.
Just dump everything into the prompt!
No need for sophisticated retrieval anymore."
```

**The Counter-Arguments:**

**1. Scalability Limits**
```
Realistic Enterprise Scenario:
  ├─ Company: 10,000 documents
  ├─ Average: 500 pages each
  ├─ Total: 5 million pages
  ├─ Words: ~2.5 billion
  └─ Tokens: ~3.3 billion

Even with 1M token context:
  ├─ Can fit: 0.03% of data
  ├─ Still need: Selection mechanism
  └─ RAG essential: To choose that 0.03%
```

**2. Cost Considerations**
```
Token Pricing (approximate):
  ├─ Input: $0.003 per 1K tokens
  └─ Output: $0.015 per 1K tokens

With 1M token context per query:
  ├─ Cost per query: $3-$15
  ├─ 1,000 queries/day: $3,000-$15,000/day
  └─ vs RAG: $0.50-$2/day

Even at scale: Prohibitively expensive
```

**3. Performance Degradation**
```
Research shows:
  ├─ "Lost in the middle" problem
  ├─ Attention dilution with long contexts
  ├─ Recall drops with context length
  └─ Relevant info buried = lower quality

Optimal: Smaller, focused context
```

**4. Latency Issues**
```
Processing 1M tokens:
  ├─ Generation time: 30-60+ seconds
  ├─ Poor user experience
  └─ Timeout risks

With RAG (5K token context):
  ├─ Generation time: 2-5 seconds
  └─ Acceptable latency
```

**5. Environmental Impact**
```
Compute requirements:
  ├─ 1M token context: Massive GPU usage
  ├─ 5K token context: Minimal GPU usage
  └─ 200x difference in resources

Sustainability matters!
```

**Verdict:** ❌ **This argument doesn't hold**

Large context windows are useful but don't eliminate the need for RAG.

#### Argument 2: "Agentic RAG Replaced Traditional RAG"

**The Claim:**
```
"Agentic RAG is the new standard.
Traditional RAG is obsolete.
RAG is dead, long live Agentic RAG!"
```

**The Reality:**

**It's Evolution, Not Replacement:**

```
Traditional RAG (2020-2022)
        ↓
   Evolution
        ↓
Agentic RAG (2023-2024)
        ↓
   Still RAG!
```

**Like Saying:**

```
Manual Transmission → Automatic Transmission
  Still a car transmission!

Basic Calculator → Graphing Calculator
  Still a calculator!

Traditional RAG → Agentic RAG
  Still RAG!
```

**Both Have Their Place:**

```
Traditional RAG:
  ✓ Use when: Simple, predictable queries
  ✓ Benefits: Fast, cheap, deterministic
  ✓ Examples: FAQ, product catalog

Agentic RAG:
  ✓ Use when: Complex, varied queries
  ✓ Benefits: Adaptive, thorough, intelligent
  ✓ Examples: Research, multi-step reasoning
```

**Verdict:** ⚠️ **This is semantics, not substance**

Agentic RAG is still RAG - just more sophisticated.

### The Truth: RAG Is Alive and Essential

**Reality Check:**

```
RAG (all forms) is:
  ✅ Fundamental to enterprise AI
  ✅ Critical for domain expertise
  ✅ Enabling production applications
  ✅ Growing more sophisticated
  ✅ Here to stay

Future: Hybrid approaches
  ├─ Long context for recent conversation
  ├─ RAG for vast knowledge bases
  └─ Agentic orchestration for complex queries
```

**Industry Adoption:**

```
Companies using RAG:
  ├─ Customer support systems
  ├─ Internal knowledge bases
  ├─ Legal document analysis
  ├─ Medical diagnosis support
  ├─ Code generation with context
  └─ Countless other applications

Market size: Multi-billion dollar
Growth: Accelerating
```

**Conclusion:**

> **Long live RAG!** Traditional RAG, Agentic RAG, and future innovations all built on the same powerful principle: Enhance LLMs with relevant, retrieved context.

### The Two Phases of RAG

Every RAG system consists of two distinct operational phases:

#### Phase 1: Data Ingest (Setup/Maintenance)

**Purpose:** Populate the vector database with searchable knowledge

**ETL + Vectorization Pipeline:**

```
┌─────────────────┐
│    EXTRACT      │ Pull data from sources
└────────┬────────┘
         ↓
   Data Sources:
   ├─ PDF documents
   ├─ Google Sheets
   ├─ Text files
   ├─ Databases (SQL)
   ├─ Web pages (scraping)
   ├─ APIs
   ├─ Email archives
   └─ File storage (S3, Drive)
         ↓
┌─────────────────┐
│   TRANSFORM     │ Clean and format
└────────┬────────┘
         ↓
   Operations:
   ├─ Parse file formats
   ├─ Clean/normalize text
   ├─ Extract metadata
   ├─ Structure data
   ├─ Remove duplicates
   └─ Validate content
         ↓
┌─────────────────┐
│     CHUNK       │ Split into pieces
└────────┬────────┘
         ↓
   Chunking:
   ├─ Strategy: Paragraph-based
   ├─ Size: ~1,000 characters
   ├─ Overlap: 200 characters
   └─ Output: Discrete chunks
         ↓
   Example:
   50-page doc → 150 chunks
         ↓
┌─────────────────┐
│   VECTORIZE     │ Create embeddings
└────────┬────────┘
         ↓
   For each chunk:
   "MacBook Pro M4 features..."
       ↓
   Embedding Model
       ↓
   [0.234, -0.451, 0.783, ...]
         ↓
┌─────────────────┐
│      LOAD       │ Store in vector DB
└─────────────────┘
         ↓
   Database contains:
   ┌────┬──────────┬──────────┬──────────┐
   │ ID │ Content  │  Vector  │ Metadata │
   ├────┼──────────┼──────────┼──────────┤
   │ 1  │ "Mac..."  │[0.23...]│{cat:tech}│
   │ 2  │ "iPh..."  │[0.56...]│{cat:tech}│
   │... │ ...       │...       │...       │
   └────┴──────────┴──────────┴──────────┘
```

**Triggering Methods:**

```
Manual:
  ├─ Button press in n8n
  └─ On-demand execution

Scheduled:
  ├─ Daily: Full refresh
  ├─ Hourly: Incremental updates
  └─ Weekly: Deep sync

Event-Driven:
  ├─ File uploaded to Google Drive
  ├─ Database record updated
  ├─ Webhook called from CMS
  └─ API notification received

Continuous:
  ├─ Watch folder for new files
  ├─ Stream from message queue
  └─ Real-time synchronization
```

**Production Pattern:**

```
Recommended Setup:
  ├─ Initial: Full data load (one-time)
  ├─ Updates: Incremental (scheduled/event-driven)
  ├─ Monitoring: Track success/failures
  └─ Alerts: Notify on errors
```

#### Phase 2: Question Answering (Runtime)

**Purpose:** Answer user queries using the populated knowledge base

**Query → Retrieval → Generation Pipeline:**

```
┌───────────────────┐
│  User Question    │
└─────────┬─────────┘
          ↓
   "How much RAM does
    MacBook Pro have?"
          ↓
┌───────────────────────┐
│  Vectorize Question   │
└─────────┬─────────────┘
          ↓
    Embedding Model:
    Question → Vector
    [0.247, -0.445, ...]
          ↓
┌───────────────────────┐
│  Similarity Search    │
│  in Vector Database   │
└─────────┬─────────────┘
          ↓
    Find similar vectors:
    ├─ Doc 47: 0.95 similarity
    ├─ Doc 134: 0.82 similarity
    └─ Doc 89: 0.73 similarity
          ↓
    Retrieve original text
          ↓
┌───────────────────────┐
│  Build LLM Prompt     │
└─────────┬─────────────┘
          ↓
    "User: How much RAM?
     
     Context:
     - MacBook Pro M4: 16GB unified memory
     - Configurable up to 96GB
     - Shared by CPU and GPU"
          ↓
┌───────────────────────┐
│  LLM Generates Answer │
└─────────┬─────────────┘
          ↓
    "The MacBook Pro M4 comes with
     16GB of unified memory as standard,
     configurable up to 96GB."
```

**This happens for EVERY user question.**

**Agentic RAG Enhancement:**

In Agentic RAG, Phase 2 becomes more sophisticated:

```
┌───────────────────┐
│  User Question    │
└─────────┬─────────┘
          ↓
┌─────────────────────────────┐
│      AI AGENT               │
│  (Orchestrates retrieval)   │
└─────────┬───────────────────┘
          │
          │ Agent decides:
          │ - Which tools?
          │ - How many searches?
          │ - What parameters?
          │
          ├─ Vector Search
          │    (semantic similarity)
          │
          ├─ SQL Query
          │    (structured data)
          │
          ├─ Re-ranking
          │    (refine results)
          │
          ↓
    Agent evaluates:
    "Do I have enough context?"
          │
          ├─ Yes → Generate response
          └─ No → Search again
                 (different method)
```

### Introduction to Supabase

For this course, we're using **Supabase** as our vector database platform.

#### What is Supabase?

**Core Description:**

Supabase is a managed, cloud-based PostgreSQL database platform with built-in vector support.

**Technical Foundation:**

```
Supabase = PostgreSQL + Extensions + Cloud Management

Components:
  ├─ PostgreSQL: Industry-standard relational database
  ├─ pgvector: Vector similarity search extension
  ├─ PostgREST: Auto-generated REST API
  ├─ Realtime: WebSocket connections
  ├─ Auth: Built-in authentication
  └─ Storage: File storage buckets
```

**Key Features:**

**1. PostgreSQL-Based**
```
Benefits:
  ✓ Battle-tested reliability (30+ years)
  ✓ ACID compliance
  ✓ Rich SQL capabilities
  ✓ Massive ecosystem
  ✓ Well-documented
  ✓ Skilled developer pool
```

**2. Vector Support (pgvector)**
```
Capabilities:
  ✓ Store vector embeddings
  ✓ Similarity search functions
  ✓ Multiple distance metrics
  ✓ Index optimization
  ✓ Efficient for RAG
```

**3. Managed Service**
```
Includes:
  ✓ No server management
  ✓ Automatic backups
  ✓ Scaling handled
  ✓ Updates managed
  ✓ Monitoring built-in
  ✓ High availability
```

**4. Developer-Friendly**
```
Features:
  ✓ Easy setup (minutes)
  ✓ Auto-generated API
  ✓ Real-time subscriptions
  ✓ Good documentation
  ✓ Active community
  ✓ Multiple SDKs (JS, Python, etc.)
```

#### Why Supabase for This Course?

**Reasons:**

```
✅ Industry Relevance
   ├─ Popular in startup ecosystem
   ├─ Used by agencies
   └─ Production-ready

✅ Learning Value
   ├─ Real-world skill
   ├─ Transferable knowledge
   └─ Resume-worthy

✅ Practical Benefits
   ├─ Generous free tier
   ├─ Great n8n integration
   ├─ Scalable (hobby → production)
   └─ PostgreSQL = standard SQL

✅ Vector Database Ready
   ├─ pgvector pre-installed
   ├─ Optimized for similarity search
   └─ Production-tested at scale
```

**Alternatives We Could Have Used:**

```
Easier options:
  ├─ n8n built-in vector stores
  └─ (Simpler but less powerful/scalable)

Specialized vector DBs:
  ├─ Pinecone (great but paid service)
  ├─ Weaviate (powerful but more complex setup)
  └─ Qdrant (good but less familiar to most)

Traditional DBs:
  ├─ MongoDB (good but different query model)
  └─ Elasticsearch (search-focused, different use case)

Supabase strikes best balance:
  ✓ Power + Ease + Popularity
```

#### Supabase Pricing

**Free Tier:**
```
Includes:
  ├─ 500 MB database space
  ├─ 1 GB file storage
  ├─ 2 GB bandwidth
  ├─ 50,000 monthly active users
  ├─ Unlimited API requests
  ├─ Up to 2 projects
  └─ Community support

Perfect for:
  ✓ Learning and development
  ✓ Small projects
  ✓ Prototypes
  ✓ This course!
```

**Pro Tier: $25/month**
```
Includes:
  ├─ 8 GB database space
  ├─ 100 GB file storage
  ├─ 250 GB bandwidth
  ├─ No daily limits
  ├─ 7-day log retention
  ├─ Daily backups
  └─ Email support

Upgrade when:
  ├─ Outgrow free tier
  ├─ Need more projects
  └─ Production deployment
```

**Enterprise: Custom**
```
For: Large-scale production needs
```

### Tomorrow's Mission

**Day 4 Preview:**

We'll build the complete data ingest pipeline:

```
Tasks:
1. ✅ Set up Supabase account
2. ✅ Create vector database
3. ✅ Enable pgvector extension
4. ✅ Configure tables with SQL
5. ✅ Connect n8n to Supabase
6. ✅ Build data transformation
7. ✅ Implement chunking
8. ✅ Generate embeddings
9. ✅ Load into vector store
10. ✅ Verify and test
```

**What You'll Learn:**

```
Skills:
  ├─ Supabase project setup
  ├─ SQL for vector databases
  ├─ n8n data transformation
  ├─ Edit Fields node mastery
  ├─ Embedding configuration
  ├─ Vector store integration
  └─ End-to-end pipeline testing
```

### Day 3 Summary

**Concepts Mastered:**

✅ **RAG Fundamentals**
- Small idea: Add context to prompts
- Big idea: Smart retrieval via embeddings
- Real-world application: Expert systems

✅ **Embedding Models**
- Text → Numbers (vectors)
- Similar meaning → Similar vectors
- Enable semantic search
- Different from answering LLMs

✅ **Semantic Search**
- Meaning-based, not keyword
- Handles synonyms automatically
- Fuzzy matching
- Core RAG technology

✅ **Vector Databases**
- Store embeddings efficiently
- Fast similarity calculations
- Support high dimensions
- PostgreSQL + pgvector = Supabase

✅ **Traditional vs. Agentic RAG**
- Traditional: Fixed workflow
- Agentic: LLM-driven decisions
- Both have valid use cases
- Evolution, not replacement

✅ **Two-Phase Architecture**
- Phase 1: Data Ingest (ETL + Vectorization)
- Phase 2: Question Answering (Query + Retrieval)

✅ **Chunking & Metadata**
- Chunking: Break documents appropriately
- Metadata: Add filtering capabilities
- Both critical for performance

**Preparation for Tomorrow:**

```
Action Items:
□ Visit supabase.com
□ Create account
□ Explore interface
□ Read pricing page
□ Understand free tier limits
□ Get familiar with PostgreSQL basics (optional)
```

**Next Steps:**

Tomorrow we build the complete data ingest pipeline, transforming a Google Sheet of products into a fully searchable vector database!

---

*Continuing in final file with Days 4-5...*
# Week 2: AI Voice Agents and RAG - Part 3

**Days 4-5: Implementation and Integration**

---

<a name="day-4-implementation"></a>
## Day 4: Building RAG Pipelines with Supabase

### Day 4 Overview

**Mission:** Build the complete data ingest pipeline

**What We're Building:**

```
Google Sheets (Product Catalog)
         ↓
Extract with n8n Google Sheets node
         ↓
Transform with Edit Fields node
         ↓
Chunk text appropriately
         ↓
Vectorize with OpenAI embeddings
         ↓
Load into Supabase vector database
```

**Business Context:**

```
Scenario:
  ├─ Client has product catalog in Google Sheets
  ├─ 60 products (could be 60,000)
  ├─ Needs expert agent for product questions
  ├─ Must scale efficiently
  └─ Voice interface required

Solution:
  ├─ RAG system with vector search
  ├─ Voice agent integration
  ├─ Real-time question answering
  └─ Production-ready architecture
```

### Supabase Account Setup

#### Step 1: Create Account

**Process:**

1. Visit supabase.com
2. Click "Start your project"
3. Sign up with:
   - GitHub (recommended - fastest)
   - Email + password
4. Verify email if needed
5. Complete onboarding

#### Step 2: Create Organization

**Configuration:**

```
Organization Name: [YourName] Research
Example: "Donna Research"

Purpose: Education/Research
Type: Personal/Learning

Why this matters:
  ├─ Separates learning from business projects
  ├─ Appropriate terms of service
  ├─ Better organization
  └─ Clear project ownership
```

**Important Notes:**

```
✓ Use descriptive name
✓ Indicate research/education purpose
✓ Can create multiple organizations later
✓ Free tier applies per organization
```

#### Step 3: Navigate to Projects

**After organization setup:**

```
Interface Navigation:
  ├─ Left sidebar → Projects
  │  OR
  └─ Organization dropdown → Projects

Result: Empty projects list
Action: Click "New Project" button
```

### Creating the RAG Project

#### Project Configuration

**Click: New Project**

**Settings:**

```
Project Name: rag
(Keep it simple and descriptive)

Database Password:
  ├─ Generate strong password
  ├─ CRITICAL: Save in password manager
  ├─ You'll need this for:
  │  ├─ Direct database access
  │  ├─ Backup/restore operations
  │  └─ Advanced configurations
  └─ Cannot be recovered if lost!

Compute Size: Tiny
  ├─ Free tier: Perfect for learning
  ├─ Paid option: $0.01/hour
  └─ Can upgrade later if needed

Region: Choose closest to you
  ├─ Americas (US East, US West)
  ├─ Europe (Frankfurt, London)
  ├─ Asia Pacific (Singapore, Sydney)
  │
  └─ Consider: Where your n8n runs
     (Co-location reduces latency)
```

**Click: Create New Project**

**Wait Time:** 2-3 minutes for provisioning

**What's Being Created:**

```
Behind the scenes:
  ├─ PostgreSQL database instance
  ├─ API endpoints generation
  ├─ Authentication system setup
  ├─ Storage buckets creation
  ├─ Real-time listeners configuration
  └─ Monitoring infrastructure
```

#### Understanding the Supabase Interface

**Main Navigation Structure:**

```
Left Sidebar:
┌───────────────────┐
│ Home              │ ← Project overview
├───────────────────┤
│ Table Editor      │ ← View/edit data
├───────────────────┤
│ SQL Editor        │ ← Run SQL commands ⭐ We'll use this
├───────────────────┤
│ Database          │
│  ├─ Tables        │ ← Table structure ⭐ We'll use this
│  ├─ Extensions    │ ← Enable features ⭐ pgvector here!
│  ├─ Roles         │
│  └─ Replication   │
├───────────────────┤
│ Authentication    │ ← User management
├───────────────────┤
│ Storage           │ ← File storage
├───────────────────┤
│ Edge Functions    │ ← Serverless functions
├───────────────────┤
│ Project Settings  │ ← Configuration ⭐ API keys here!
│  ├─ General       │
│  ├─ API           │ ← URLs and keys
│  └─ Database      │
└───────────────────┘
```

**Key Sections for Our Use:**

1. **SQL Editor** - Run setup scripts
2. **Database → Extensions** - Enable vector support
3. **Database → Tables** - View our data
4. **Project Settings → API** - Get connection credentials

### Setting Up Vector Support

#### Enable pgvector Extension

**Purpose:** Add vector/embedding capabilities to PostgreSQL

**Steps:**

```
1. Navigate: Database → Extensions (left sidebar)

2. In search box: Type "vector"

3. Locate: pgvector extension

4. Toggle: Switch to ON

5. Confirm: Click "Enable Extension"

6. Wait: ~5-10 seconds for activation

7. Verify: Should show "Enabled" status
```

**What This Enables:**

```
PostgreSQL now has:
  ✅ VECTOR data type
     - Store embeddings as columns
     - Native vector operations
  
  ✅ Similarity functions
     - Cosine similarity (<=>)
     - L2 distance (<->)
     - Inner product (<#>)
  
  ✅ Vector indexing
     - IVFFlat indexes
     - HNSW indexes (coming)
     - Fast similarity search
  
  ✅ Distance calculations
     - Efficient computation
     - Optimized algorithms
```

**Troubleshooting:**

```
If extension doesn't appear:
  ├─ Refresh browser page
  ├─ Check project is fully initialized
  ├─ Verify on Supabase Pro plan (if needed)
  └─ Contact support if persistent
```

#### Create Vector Database Table

**Why SQL Code is Needed:**

n8n's Supabase node expects a specific table structure:
- Specific column names (`content`, `metadata`, `embedding`)
- Specific data types (TEXT, JSONB, VECTOR)
- Specific similarity search function (`match_documents`)

Supabase doesn't have a "one-click" setup for this exact structure, so we use SQL.

**The Complete SQL Script:**

Navigate: SQL Editor (left sidebar)

Copy and paste this script:

```sql
-- ============================================
-- RAG Vector Database Setup for n8n
-- ============================================

-- Create the main knowledge base table
CREATE TABLE IF NOT EXISTS knowledgebase (
    id BIGSERIAL PRIMARY KEY,
    content TEXT,
    metadata JSONB,
    embedding VECTOR(1536)  -- CRITICAL: Match your embedding model!
);

-- Create index for faster similarity search (optional but recommended)
CREATE INDEX ON knowledgebase 
USING ivfflat (embedding vector_cosine_ops)
WITH (lists = 100);

-- ============================================
-- Similarity Search Function for n8n
-- ============================================

CREATE OR REPLACE FUNCTION match_documents(
    query_embedding VECTOR(1536),  -- CRITICAL: Match dimensions!
    match_threshold FLOAT DEFAULT 0.5,
    match_count INT DEFAULT 5
)
RETURNS TABLE (
    id BIGINT,
    content TEXT,
    metadata JSONB,
    similarity FLOAT
)
LANGUAGE SQL STABLE
AS $$
    SELECT
        knowledgebase.id,
        knowledgebase.content,
        knowledgebase.metadata,
        1 - (knowledgebase.embedding <=> query_embedding) AS similarity
    FROM knowledgebase
    WHERE 1 - (knowledgebase.embedding <=> query_embedding) > match_threshold
    ORDER BY knowledgebase.embedding <=> query_embedding
    LIMIT match_count;
$$;

-- ============================================
-- Verification Query (Optional)
-- ============================================

-- Check table structure
SELECT column_name, data_type 
FROM information_schema.columns 
WHERE table_name = 'knowledgebase';
```

**CRITICAL: The Dimensions Number**

```
VECTOR(1536)
       ↑
This MUST match your embedding model's dimensions!

Common Embedding Models:
┌─────────────────────────────┬────────────┐
│ Model                        │ Dimensions │
├─────────────────────────────┼────────────┤
│ text-embedding-3-small       │    1,536   │ ← We're using this
│ text-embedding-3-large       │    3,072   │
│ text-embedding-ada-002       │    1,536   │
│ Google text-embedding-004    │      768   │
│ Cohere embed-english-v3.0    │    1,024   │
└─────────────────────────────┴────────────┘

If you use a different model:
  1. Find its dimension count
  2. Replace 1536 with that number in BOTH places:
     - Line: embedding VECTOR(1536)
     - Line: query_embedding VECTOR(1536)
  3. Re-run the entire script
```

**Understanding the Script Components:**

**Part 1: Create Table**

```sql
CREATE TABLE knowledgebase (
    id BIGSERIAL PRIMARY KEY,
    -- Auto-incrementing unique identifier
    -- Every row gets automatic sequential ID
    
    content TEXT,
    -- The actual text chunk
    -- This is what gets sent to LLM as context
    
    metadata JSONB,
    -- Extra information in JSON format
    -- Example: {"category": "laptops", "brand": "Apple"}
    
    embedding VECTOR(1536)
    -- The vector representation
    -- 1536 numbers representing semantic meaning
);
```

**Part 2: Create Index (Performance)**

```sql
CREATE INDEX ON knowledgebase 
USING ivfflat (embedding vector_cosine_ops)
WITH (lists = 100);

Purpose:
  ├─ Speeds up similarity searches
  ├─ IVFFlat = Inverted File Flat
  ├─ lists = 100: Cluster count
  └─ Trade-off: Speed vs accuracy
```

**Part 3: Similarity Search Function**

```sql
CREATE FUNCTION match_documents(...)

Purpose:
  ├─ n8n calls this function
  ├─ Takes query vector
  ├─ Returns top K similar chunks
  └─ With similarity scores

Parameters:
  ├─ query_embedding: The question vector
  ├─ match_threshold: Min similarity (0.5 = 50%)
  └─ match_count: How many results (5)

Returns:
  ├─ id: Database row ID
  ├─ content: The text chunk
  ├─ metadata: Extra info
  └─ similarity: Score 0-1 (higher = more similar)
```

**The "Janky" Part Explained:**

```sql
1 - (embedding <=> query_embedding) AS similarity

Why this formula?

PostgreSQL <=> operator:
  ├─ Returns: Distance between vectors
  ├─ Range: 0 (identical) to 2 (opposite)
  ├─ Lower = more similar

n8n expects:
  ├─ Similarity score (not distance)
  ├─ Range: 0 (different) to 1 (identical)
  ├─ Higher = more similar

Conversion:
  similarity = 1 - distance
  
  Examples:
  ├─ Distance 0 → Similarity 1.0 (100% match)
  ├─ Distance 0.5 → Similarity 0.5 (50% match)
  └─ Distance 1.0 → Similarity 0.0 (no match)
```

**Running the Script:**

```
1. Paste complete script in SQL Editor

2. Click "RUN" button (bottom right)

3. Wait for execution (~2-5 seconds)

4. Expected result: "Success. No rows returned"
   (This is correct - we created structure, not data)

5. If errors appear:
   ├─ Read error message carefully
   ├─ Common issues below
   └─ Fix and re-run
```

**Common Errors and Solutions:**

**Error: "type vector does not exist"**
```
Cause: pgvector extension not enabled

Fix:
  1. Go to Database → Extensions
  2. Search for "pgvector"
  3. Enable it
  4. Wait for activation
  5. Re-run SQL script
```

**Error: "relation 'knowledgebase' already exists"**
```
Cause: Table already created

Solution:
  This is actually fine!
  Script uses "CREATE TABLE IF NOT EXISTS"
  Just means table exists from previous run
  
  To recreate:
  1. Run: DROP TABLE IF EXISTS knowledgebase CASCADE;
  2. Then run main script again
```

**Error: "function match_documents already exists"**
```
Cause: Function already defined

Solution:
  This is also fine!
  Script uses "CREATE OR REPLACE FUNCTION"
  It will update the existing function
  No action needed
```

**Error: Dimension mismatch**
```
Cause: VECTOR(1536) doesn't match your embedding model

Fix:
  1. Identify your embedding model
  2. Find its dimension count
  3. Update both VECTOR(X) occurrences
  4. Re-run script
```

#### Verify Table Creation

**Navigate:** Database → Tables (left sidebar)

**You Should See:**

```
Tables List:
  ├─ knowledgebase ✓ (Your new table!)
  └─ (Other system tables)

Click on "knowledgebase" to view structure:

Columns:
┌──────────┬────────────┬──────────────┐
│ Name     │ Type       │ Description  │
├──────────┼────────────┼──────────────┤
│ id       │ bigint     │ Primary key  │
│ content  │ text       │ Text chunks  │
│ metadata │ jsonb      │ Extra info   │
│ embedding│ vector     │ 1536 dims    │
└──────────┴────────────┴──────────────┘

Row count: 0 (empty - we'll populate next)
```

**Visual Confirmation:**

```
Table Editor view should show:
  ├─ Table name: knowledgebase
  ├─ Columns: 4 (id, content, metadata, embedding)
  ├─ Rows: 0
  └─ Status: Ready for data
```

### Building the Data Ingest Pipeline in n8n

#### Source Data Overview

**Our Data Source:** Google Sheet with product information

**Sheet Structure:**

```
Columns:
┌──────────────┬──────────┬──────┬─────────┬─────────────────┐
│ Product Name │ Category │ SKU  │  Price  │  Description    │
├──────────────┼──────────┼──────┼─────────┼─────────────────┤
│ NovaKey...   │ Keyboard │ K001 │ $159.99 │ Vertical design │
│ MacBook Pro  │ Laptop   │ L003 │ $2499   │ Professional... │
│ ...          │ ...      │ ...  │ ...     │ ...             │
└──────────────┴──────────┴──────┴─────────┴─────────────────┘

Total: 60 products
(Designed to scale to 60,000+)
```

**Sample Row:**

```json
{
  "Product Name": "NovaKey Tactile Keyboard",
  "Category": "Keyboard",
  "SKU": "K001",
  "Price": "159.99",
  "Description": "A vertical design mechanical keyboard with ergonomic features for extended typing sessions. Features Cherry MX switches and customizable RGB backlighting."
}
```

**Access:**

- Provided in course resources
- Or create your own:
  1. Create Google Sheet
  2. Add columns as shown
  3. Fill with product data
  4. Share with n8n (or make public)

#### Create n8n Workflow

**Step 1: New Workflow**

```
1. Sign into n8n cloud
2. Click: "Create Workflow"
3. Name: "Data Ingest Pipeline"
4. Description: "Load products into Supabase vector DB"
```

**Step 2: Choose Trigger**

**For Now: Manual Trigger**

```
Add: Manual Trigger node

Why manual:
  ✓ Simple for learning
  ✓ On-demand execution
  ✓ Easy testing
  ✓ Full control

Future enhancements:
  ├─ Schedule Trigger (daily refresh)
  ├─ Webhook Trigger (API-driven)
  ├─ Google Drive Trigger (new files)
  └─ Database Trigger (data changes)
```

**Trigger Options Comparison:**

| Trigger Type | When to Use | Complexity |
|--------------|-------------|------------|
| Manual | Testing, one-time loads | Low |
| Schedule | Regular updates (daily/weekly) | Low |
| Webhook | Event-driven from external system | Medium |
| Google Drive | New file uploads | High |
| Database | Real-time sync | High |

#### Extract Data (Google Sheets Node)

**Step 3: Add Google Sheets Integration**

```
Click + after Manual Trigger
Search: "Google Sheets"
Select: Google Sheets node
```

**Configuration:**

```
Operation: Get Rows

Authentication:
  ├─ Click: "Create New Credential"
  ├─ Follow: OAuth flow
  ├─ Grant: Google Sheet permissions
  ├─ Test: Connection successful ✓

Spreadsheet:
  ├─ Select from dropdown: "Products"
  │  (Or paste sheet URL if not listed)
  └─ n8n auto-fetches your accessible sheets

Sheet: Sheet1
  (Default sheet name, adjust if different)

Range: 
  ├─ Leave empty for ALL rows
  ├─ Or specify: A1:F100 (for specific range)
  └─ Recommended: Leave empty

Options:
  ├─ RAW: No (format as JSON)
  └─ Header Row: Yes (first row is headers)
```

**Test Execution:**

```
1. Click: "Execute Node" button

2. Expected result:
   ├─ 60 items loaded
   ├─ Each item has all columns
   └─ Preview shows sample data

3. Verify in output:
   ├─ All column names present
   ├─ Data types look correct
   ├─ No missing fields
   └─ No obvious errors
```

**Sample Output:**

```json
[
  {
    "Product Name": "NovaKey Tactile Keyboard",
    "Category": "Keyboard",
    "SKU": "K001",
    "Price": "159.99",
    "Description": "A vertical design mechanical..."
  },
  {
    "Product Name": "MacBook Pro M4",
    "Category": "Laptop",
    "SKU": "L003",
    "Price": "2499.00",
    "Description": "Professional grade laptop..."
  }
  // ... 58 more items
]
```

#### Transform Data (Edit Fields Node)

**Step 4: Add Data Transformation**

**Purpose:** Convert raw sheet data into RAG-optimized format

**What We Need:**

```
Current format (from Google Sheets):
{
  "Product Name": "NovaKey Tactile Keyboard",
  "Category": "Keyboard",
  "SKU": "K001",
  "Price": "159.99",
  "Description": "A vertical design mechanical..."
}

Needed format (for vector database):
{
  "content": "Product Name: NovaKey Tactile Keyboard
              Category: Keyboard
              SKU: K001
              Price: $159.99
              Description: A vertical design mechanical...",
  "category": "Keyboard"
}
```

**Why This Format?**

```
content field:
  ✓ Rich text for LLM comprehension
  ✓ Natural language structure
  ✓ All relevant information combined
  ✓ Optimized for semantic search
  ✓ Will be vectorized and stored

category field:
  ✓ Metadata for filtering
  ✓ Enables category-specific searches
  ✓ "Show only keyboards"
  ✓ Not vectorized, just stored
```

**Add Edit Fields Node:**

```
Click + after Google Sheets
Search: "Edit Fields"
  (Formerly called "Set" - may show both names)
Select: Edit Fields (SQL)
```

**Configuration:**

```
Mode: Manual Mapping
(More control than automatic)

Click: "Add Field"
```

**Field 1: content (The Main Text)**

```
Click: Add Field

Field Name: content

Type: String

Value: Toggle to "Expression"

Expression Builder:
Product Name: {{ $json["Product Name"] }}

Category: {{ $json.Category }}

SKU: {{ $json.SKU }}

Price: ${{ $json.Price }}

Description: {{ $json.Description }}
```

**Visual Expression Builder Alternative:**

Instead of typing, you can:

```
1. Type label: "Product Name: "
2. Drag field from left panel
3. Drop into expression
4. Result: {{ $json["Product Name"] }}
5. Press Enter for new line
6. Repeat for each field
```

**Expression with Proper Formatting:**

```javascript
Product Name: {{ $json["Product Name"] }}
Category: {{ $json.Category }}
SKU: {{ $json.SKU }}
Price: ${{ $json.Price }}
Description: {{ $json.Description }}
```

**Result Preview:**

```
content: "Product Name: NovaKey Tactile Keyboard
          Category: Keyboard
          SKU: K001
          Price: $159.99
          Description: A vertical design mechanical keyboard with ergonomic features for extended typing sessions. Features Cherry MX switches and customizable RGB backlighting."
```

**Field 2: category (The Metadata)**

```
Click: Add Field

Field Name: category

Type: String

Value: Toggle to "Expression"

Expression:
{{ $json.Category }}

Or drag "Category" field from left panel

Result: "Keyboard"
```

**Why Two Separate Fields?**

```
content:
  ├─ Goes to embedding model
  ├─ Creates vector
  ├─ Used for semantic search
  └─ Full text for LLM context

category:
  ├─ Stored as metadata
  ├─ NOT vectorized
  ├─ Used for filtering
  └─ Enables scoped searches

Example use:
  User: "Show me affordable keyboards"
  Flow:
    1. Filter: category = "Keyboard"
    2. Then: Semantic search within keyboards
    3. Result: Only keyboard matches
```

**Test the Transform:**

```
1. Click: "Execute Step" (or "Test Step")

2. Verify output shows:
   ├─ 60 items transformed
   ├─ Each has "content" field (formatted text)
   ├─ Each has "category" field (single word)
   └─ No original Google Sheets columns

3. Inspect sample:
   ├─ Click on output item
   ├─ Check content formatting
   ├─ Verify all info present
   └─ Confirm looks LLM-friendly
```

**Common Issues:**

```
Issue: Extra $ signs in price
Fix: Remove $ from expression if price already has it

Issue: Fields missing
Fix: Check exact column names (case-sensitive)

Issue: Newlines not showing
Fix: Use actual Enter key, not \n in expression

Issue: Expression errors
Fix: Ensure field names in quotes if they have spaces
     {{ $json["Product Name"] }} ✓
     {{ $json.Product Name }}    ✗
```

### Connecting to Supabase

#### Retrieve Connection Credentials

**Step 1: Get Database URL**

In Supabase:

```
1. Navigate: Project Settings (left sidebar)
   ├─ Click project name dropdown
   └─ Select "Project Settings"

2. Left menu: API

3. Section: Configuration

4. Find: Project URL
   Example: https://abcdefghijk.supabase.co

5. Click: Copy icon

6. Important:
   ├─ Don't paste into Word/notepad (may alter characters)
   ├─ Paste directly into n8n
   ├─ Or use password manager
   └─ Keep safe - you'll need it multiple times
```

**Step 2: Get API Key**

Still in API settings:

```
1. Scroll to: Project API keys

2. Important: Use LEGACY keys
   ├─ Click: "Switch to legacy keys" tab
   │  (if you see "New API keys" tab)
   └─ n8n currently uses legacy format

3. Find: service_role key
   ├─ Marked with orange "secret" label
   ├─ Has "Reveal" button
   └─ This is the one you need!

4. Click: Reveal

5. Click: Copy

6. Store: Safely in password manager

7. Security note:
   ├─ This is a SECRET key
   ├─ Has full database access
   ├─ Never commit to Git
   ├─ Never expose publicly
   └─ Treat like a password
```

**Why Legacy Keys?**

```
Supabase New System:
  ├─ Separate publishable/secret keys
  ├─ More granular permissions
  └─ Better security model

n8n Current Support:
  ├─ Built for legacy key system
  ├─ Will update eventually
  └─ Legacy works perfectly fine

Result: Use legacy keys for now
```

#### Add Supabase Vector Store Node

**Step 3: Configure Supabase Integration**

In n8n workflow:

```
Click + after Edit Fields
Search: "Supabase Vector Store"
  (Not just "Supabase" - that's for regular DB)
Select: Supabase Vector Store
```

**Create Credentials:**

```
Click: "Create New Credential"

Configuration:
  ├─ Host: Paste database URL
  │  (https://your-project.supabase.co)
  │
  └─ Service Role Secret: Paste API key
     (The long secret key from legacy keys)

Click: Save

Expected result: 
  ✅ Green checkmark
  ✅ "Connected and tested successfully"
```

**Troubleshooting Connection:**

```
If you see red ✗:

Check:
  ✓ URL complete (includes https://)
  ✓ No extra spaces before/after
  ✓ Using service_role key (not anon key)
  ✓ Using legacy keys (not new format)
  ✓ Supabase project active/running
  ✓ Internet connection stable

Common mistakes:
  ✗ Copied partial URL
  ✗ Used anon key instead of service_role
  ✗ Pasted into Word first (altered characters)
  ✗ Project still initializing

Fix:
  1. Delete credential
  2. Get fresh copies of URL and key
  3. Paste directly from Supabase to n8n
  4. Try again
```

**Node Configuration:**

```
Operation: Add Documents to Vector Store
(This inserts our products into database)

Table Name: knowledgebase
  ├─ Type or select from dropdown
  ├─ Must match table created in SQL
  └─ Case-sensitive!
```

#### Configure Embedding Model

**Critical Component:** This creates the vectors!

**Step 4: Add Embeddings Sub-Node**

Under Supabase Vector Store node:

```
You'll see slots for:
  ├─ Embeddings (required) ← Configure this!
  └─ Document Loader (required) ← Configure next

Click: Select embeddings
```

**Choose OpenAI Embeddings:**

```
Available options:
  ├─ OpenAI Embeddings ← We'll use this
  ├─ Google Gemini Embeddings
  ├─ Cohere Embeddings
  ├─ Azure OpenAI Embeddings
  └─ Others...

Select: Embeddings OpenAI

Why OpenAI:
  ✓ Industry standard
  ✓ Excellent quality
  ✓ Very affordable ($0.13 per 1M tokens)
  ✓ 1536 dimensions (matches our database)
  ✓ Battle-tested at scale

Note:
  ⚠️ Requires $5 minimum OpenAI credit
  💰 Very cheap for 60 products (~$0.0001)
  🆓 Alternative: Gemini (may have free tier)
```

**Configure OpenAI Settings:**

```
Model: text-embedding-3-small
  (Current recommended model)

Why this model:
  ├─ Optimized quality/cost balance
  ├─ 1536 dimensions
  ├─ Fast inference
  └─ Widely supported

Other options:
  ├─ text-embedding-3-large: 3072 dims, better quality, 2x cost
  └─ text-embedding-ada-002: 1536 dims, legacy model

Credential: Create New Credential

OpenAI API Key Setup:
  1. Go to platform.openai.com
  2. Sign in / create account
  3. Add $5 minimum credit
  4. Navigate to API Keys
  5. Click: Create new secret key
  6. Name: "n8n Embeddings"
  7. Copy key
  8. Paste in n8n
  9. Save

Result: ✅ Green checkmark
```

**Alternative: Google Gemini Embeddings**

If you prefer free tier:

```
Select: Google Gemini Embeddings

Model: text-embedding-004 (or latest)

Dimensions: Check Google documentation
  ├─ Usually different from 1536
  ├─ Example: 768 dimensions
  └─ MUST update database if different!

If using Gemini:
  1. Get API key from ai.studio.google.com
  2. Check model dimensions
  3. If ≠ 1536:
     a. Go to Supabase SQL Editor
     b. Update VECTOR(1536) to VECTOR(XXX)
     c. Re-run SQL script
     d. Verify table structure updated
```

**Dimension Mismatch Prevention:**

```
Rule: Embedding Model Dimensions = Database VECTOR() size

Examples:
  ✓ Model: 1536 dims + DB: VECTOR(1536) → OK
  ✗ Model: 768 dims + DB: VECTOR(1536) → ERROR
  ✗ Model: 1536 dims + DB: VECTOR(768) → ERROR

If mismatch occurs:
  Error: "Dimension mismatch: expected X, got Y"
  
  Fix:
    1. Identify your embedding model's dimensions
    2. Update SQL script VECTOR(X)
    3. Re-run script in Supabase
    4. Confirm table structure
    5. Re-test in n8n
```

#### Configure Document Loader

**Step 5: Set Up Document Loader Sub-Node**

Still in Supabase Vector Store configuration:

```
Click: Select document loader
Choose: Default Document Loader
```

**Why Document Loader Needed:**

```
Purpose:
  ├─ Tells n8n how to prepare data
  ├─ What text to vectorize
  ├─ How to chunk it
  └─ What metadata to attach

Think of it as:
  Data preparation instructions
```

**Configuration:**

**Data Mode:**

```
Options:
  ├─ Load All Input Data
  │  └─ Sends everything (wasteful)
  │
  └─ Load Specific Data ← Choose this!
     └─ Sends only what we specify (efficient)

Select: Load Specific Data

Why:
  ✓ Only vectorize content field (not SKU, price separately)
  ✓ More efficient
  ✓ Better vector quality
  ✓ Reduced costs
```

**Input Data Field:**

```
Click: Expression toggle

Expression:
{{ $json.content }}

What this does:
  ├─ Extracts just "content" field
  ├─ This is the formatted text we created
  ├─ Ignores "category" and other fields
  └─ Only this text gets vectorized

Alternative (drag & drop):
  1. Drag "content" field from left panel
  2. Drops as {{ $json.content }}
```

**Text Splitting (Chunking):**

```
Splitting Mode: Simple
  (Good default for most use cases)

Chunk Size: 1000 characters
  ├─ Maximum characters per chunk
  └─ Our products are <1000, so no splitting

Chunk Overlap: 200 characters
  ├─ Prevents context loss at boundaries
  └─ Not applicable for our short products

Effect on Our Data:
  ├─ Each product ~500 characters
  ├─ Each becomes 1 chunk
  ├─ No actual splitting occurs
  └─ But ready for longer documents

If we had longer documents (5000 chars):
  ├─ Chunk 1: chars 0-1000
  ├─ Chunk 2: chars 800-1800 (200 overlap)
  ├─ Chunk 3: chars 1600-2600 (200 overlap)
  └─ etc.
```

**Add Metadata:**

```
Click: Options
Click: Add Option
Select: Metadata

Purpose:
  ├─ Tag each embedding with extra info
  ├─ Enables filtering searches
  ├─ Provides context to LLM
  └─ Stored alongside vector

Configuration:
  Click: Add Property
  
  Name: category
  
  Value: Expression toggle
  
  Expression:
  {{ $json.category }}
  
  (Or drag "category" field from left panel)
```

**Why Metadata Matters:**

```
Without metadata:
  Query: "Show affordable keyboards"
  Process:
    ├─ Semantic search ALL products
    ├─ Hope keyboards rank high
    └─ May get mice, laptops if similar

With metadata:
  Query: "Show affordable keyboards"
  Process:
    ├─ Filter: WHERE category = 'Keyboard'
    ├─ Semantic search within keyboards only
    ├─ Guaranteed relevant category
    └─ More accurate results

Future enhancements:
  ├─ Add price_range metadata
  ├─ Add brand metadata
  ├─ Add in_stock metadata
  └─ Enable complex filtering
```

**Final Supabase Vector Store Configuration:**

```
✅ Operation: Add Documents to Vector Store
✅ Table Name: knowledgebase
✅ Credentials: Connected to Supabase
✅ Embeddings: OpenAI text-embedding-3-small
✅ Document Loader:
   ├─ Mode: Load Specific Data
   ├─ Input: {{ $json.content }}
   ├─ Chunking: 1000 chars, 200 overlap
   └─ Metadata: category = {{ $json.category }}
```

### Complete Workflow and Testing

#### Final Workflow Structure

**Visual Overview:**

```
┌──────────────────┐
│ Manual Trigger   │ Click to start
└────────┬─────────┘
         ↓
┌──────────────────┐
│ Google Sheets    │ Load 60 products
└────────┬─────────┘
         ↓
┌──────────────────┐
│ Edit Fields      │ Transform to:
│                  │ - content (formatted text)
│                  │ - category (metadata)
└────────┬─────────┘
         ↓
┌─────────────────────────────────────┐
│ Supabase Vector Store               │
│  ├─ Embeddings: OpenAI              │ Create vectors
│  └─ Document Loader                 │ Prepare data
│      ├─ Content: formatted text     │
│      ├─ Metadata: category          │
│      └─ Chunking: 1000 char chunks  │
└────────┬────────────────────────────┘
         ↓
    Data in Supabase! ✓
```

**Click: Tidy** (arranges nodes neatly)

#### First Execution

**Prepare to Run:**

```
Pre-flight checklist:
  ✓ All nodes configured
  ✓ No red error indicators
  ✓ Credentials tested (green checkmarks)
  ✓ Google Sheets connected
  ✓ Supabase connected
  ✓ OpenAI API key valid
  ✓ Workflow saved

Ready to execute!
```

**Execute Workflow:**

```
1. Click: "Execute Workflow" button (top right)

2. Watch nodes execute:
   Manual Trigger ✓
   ↓
   Google Sheets ✓ (60 items loaded)
   ↓
   Edit Fields ✓ (60 items transformed)
   ↓
   Supabase Vector Store ⟳ (processing...)
   
3. Wait time: 30-60 seconds
   Why:
   ├─ 60 API calls to OpenAI
   ├─ Each text → embedding calculation
   ├─ Upload all to Supabase
   ├─ Build database indexes
   └─ Normal for first run

4. Completion:
   ✓ All nodes green
   ✓ No errors shown
   ✓ Success message
```

**Check Node Output:**

```
Click: Supabase Vector Store node

Output shows:
  ├─ 60 documents added
  ├─ Execution time: ~45s
  ├─ No errors
  └─ Success indicator

Each item shows:
  ├─ id: Database row ID
  ├─ content: The formatted text
  ├─ metadata: {"category": "Keyboard"}
  └─ embedding: [0.234, -0.451, ...]
```

#### Verify in Supabase

**Navigate to Supabase:**

```
1. Switch to Supabase browser tab
2. Go to: Database → Tables
3. Click: knowledgebase table
```

**Initial View:**

```
May show: "No rows"
Why: Database view doesn't auto-refresh

Action: Click refresh icon (top right)
        Or reload browser page (Ctrl+R / Cmd+R)
```

**Success! 60 Rows:**

```
Table view displays:
┌─────┬──────────────────┬───────────┬──────────────┐
│ id  │    content       │ metadata  │  embedding   │
├─────┼──────────────────┼───────────┼──────────────┤
│  1  │ Product Name:... │{cat:Key...│[0.234,...]  │
│  2  │ Product Name:... │{cat:Lap...│[0.567,...]  │
│  3  │ Product Name:... │{cat:Mou...│[0.189,...]  │
│ ... │ ...              │...        │...          │
│ 60  │ Product Name:... │{cat:Mon...│[0.912,...]  │
└─────┴──────────────────┴───────────┴──────────────┘

Total rows: 60 ✓
All fields populated: ✓
Embeddings present: ✓
```

**Inspect Sample Row:**

Double-click any row to see details:

**Content Field:**
```
Product Name: NovaKey Tactile Keyboard
Category: Keyboard
SKU: K001
Price: $159.99
Description: A vertical design mechanical keyboard with ergonomic features for extended typing sessions. Features Cherry MX switches and customizable RGB backlighting.
```

**Metadata Field:**
```json
{
  "category": "Keyboard",
  "loc": {
    "lines": {
      "from": 1,
      "to": 1
    }
  }
}

Note: "loc" is auto-added by document loader
      category is what we specified
```

**Embedding Field:**
```
Click to expand:
[
  0.234123,
  -0.451234,
  0.783456,
  0.128789,
  -0.392345,
  ... (1,536 numbers total)
  0.334567
]

Dimension count: 1,536 ✓
All numbers between -1 and 1: ✓
Represents semantic meaning ✓
```

#### Fixing a Typo (Example)

**Discovering the Issue:**

```
While reviewing, notice:
  "Description: $vertical design..."

Problem: Extra $ before description

Cause: Copy-paste error in Edit Fields expression
```

**Fix Process:**

**Step 1: Clean Database**

In Supabase SQL Editor:

```sql
-- Delete all rows to start fresh
DELETE FROM knowledgebase;

-- Verify empty
SELECT COUNT(*) FROM knowledgebase;
-- Should return: 0
```

**Step 2: Fix n8n Expression**

In n8n:

```
1. Go to Edit Fields node
2. Double-click to edit
3. Click on "content" field
4. Find expression with extra $
5. Remove the errant $
6. Save node
7. Save workflow
```

**Corrected Expression:**

```javascript
Product Name: {{ $json["Product Name"] }}
Category: {{ $json.Category }}
SKU: {{ $json.SKU }}
Price: ${{ $json.Price }}
Description: {{ $json.Description }}  ← No $ here!
```

**Step 3: Re-run Workflow**

```
1. Click: Execute Workflow
2. Wait for completion
3. Verify: All nodes green
4. Check: 60 documents added
```

**Step 4: Verify Fix**

```
1. Return to Supabase
2. Refresh table view
3. Double-click row
4. Check content field
5. Confirm: No extra $ signs ✓
```

**Lesson Learned:**

```
Pipeline Benefits:
  ✓ Easy to rerun
  ✓ Quick fixes
  ✓ Repeatable process
  ✓ Scales to thousands
  ✓ Automated when needed
```

### Day 4 Summary

**What We Accomplished:**

✅ Created Supabase account and project
✅ Enabled pgvector extension
✅ Created vector database table with SQL
✅ Built complete data ingest pipeline in n8n
✅ Extracted 60 products from Google Sheets
✅ Transformed data to RAG-optimized format
✅ Configured OpenAI embeddings
✅ Generated 1,536-dimensional vectors
✅ Loaded everything into Supabase
✅ Verified successful database population

**Skills Developed:**

```
Supabase:
  ├─ Account and project setup
  ├─ Extension management (pgvector)
  ├─ SQL for vector databases
  └─ Table structure verification

n8n:
  ├─ Google Sheets integration
  ├─ Edit Fields node mastery
  ├─ Expression writing
  ├─ Supabase Vector Store configuration
  ├─ Embedding model setup
  └─ Document loader configuration

RAG Concepts:
  ├─ Data transformation for vectorization
  ├─ Metadata strategy
  ├─ Chunking considerations
  └─ End-to-end pipeline design
```

**Tomorrow's Preview:**

We'll complete the project by:
1. Building the question-answering workflow
2. Testing RAG retrieval
3. Integrating with ElevenLabs voice agent
4. Deploying to production
5. Optional: Twilio phone integration

Get ready for the exciting conclusion!

---

## Day 5: Complete RAG Voice Agent Integration

### Day 5 Overview

**Mission:** Connect everything together for a complete RAG-powered voice agent

**What We're Building:**

```
Voice User
    ↓
ElevenLabs Voice Agent
    ↓ (uses tool)
n8n Webhook Workflow
    ├─ AI Agent (Gemini)
    └─ Supabase Vector Store Tool
        ├─ Retrieves relevant products
        └─ Returns context
    ↓
Response back to ElevenLabs
    ↓
Spoken answer to user
```

**Components Checklist:**

```
Already complete:
  ✅ Supabase vector database with 60 products
  ✅ Data ingest pipeline

Today's tasks:
  □ Build question-answering workflow in n8n
  □ Add Supabase vector store as AI agent tool
  □ Test RAG retrieval
  □ Create ElevenLabs voice agent
  □ Connect via webhook
  □ Test complete integration
  □ Deploy to production
  □ (Optional) Twilio phone integration
```

### Building the Question-Answering Workflow

#### Create New Workflow

**Step 1: Start Fresh**

```
1. In n8n, save data ingest workflow
2. Rename to: "Data Ingest Pipeline"
3. Return to workflows list
4. Click: "Create Workflow"
5. Name: "Agentic RAG"
```

#### Add Chat Interface (Temporary Testing)

**Step 2: Add Chat Trigger**

```
Add node: On Chat Message

Purpose:
  ├─ Easy testing during development
  ├─ Will replace with webhook later
  └─ Familiar interface for validation

Configuration:
  ├─ Default settings fine
  └─ No special setup needed
```

#### Configure AI Agent

**Step 3: Add AI Agent**

```
Click + after chat trigger
Search: "AI Agent"
Select: AI Agent
```

**Configuration:**

```
Chat Input:
  ├─ Source: Connected to chat trigger
  ├─ Mode: JSON chat input
  └─ This is correct for now (will change later)

Chat Model: Google Gemini
  ├─ Use existing credential
  │  (or create new with Gemini API key)
  └─ Model: Gemini 3 Flash Preview
     (or latest available)

Why Gemini:
  ✓ Good free tier
  ✓ Fast performance
  ✓ Excellent for this use case
  ✓ Variety from OpenAI

Memory: Simple Memory (Window Buffer Memory)
  ├─ Session-based conversation history
  ├─ Remember previous questions
  └─ For testing in chat interface

Note: Will remove memory for webhook version
```

#### Add Supabase Vector Store Tool

**Step 4: Connect RAG Knowledge Base**

**This is the critical step that enables RAG!**

```
In AI Agent node:
  Click: + to add tool
  Search: "Supabase"
  Select: Supabase Vector Store
```

**Tool Configuration:**

```
Operation: Retrieve Documents (from Vector DB for AI agent)
  
Why this operation:
  ├─ Makes vector DB available as tool
  ├─ Agent can call it when needed
  ├─ Performs similarity search
  └─ Returns relevant chunks

Credential:
  ├─ Select: Existing Supabase credential
  │  (Same one from data ingest)
  └─ Should show green checkmark

Table Name: knowledgebase
  ├─ Must match table created yesterday
  ├─ Case-sensitive
  └─ Dropdown should show it
```

**Tool Description:**

```
This is CRUCIAL - tells agent when to use the tool!

Description:
"Use this tool to look up any information that relates to products offered by the company."

Why important:
  ├─ LLM reads this to decide when to use tool
  ├─ Clear description = better tool usage
  ├─ Vague description = tool ignored
  └─ Specific triggers = accurate retrieval

Alternative descriptions:
  "Query product catalog for specifications and pricing"
  "Search company product database for detailed information"
  "Retrieve product details from knowledge base"
```

**Advanced Options:**

```
Limit: 10
  ├─ Maximum chunks to retrieve
  ├─ More = better context (usually)
  ├─ But also = more tokens = higher cost
  └─ 10 is good default

Include Metadata: Yes
  ├─ Send category info to agent
  ├─ Helps agent understand context
  └─ Can mention in response

Re-rank Results: No (for now)
  ├─ Advanced feature
  ├─ Uses LLM to re-order results
  ├─ Increases quality but slower/costlier
  └─ Not needed for this demo
```

**Add Embeddings Sub-Node:**

```
Just like data ingest pipeline:

Select: Embeddings OpenAI

Model: text-embedding-3-small
  ├─ MUST match what was used in data ingest
  ├─ Same model = same vector space
  └─ Different model = won't work properly

Credential: Use existing OpenAI credential

Why needed:
  ├─ Must vectorize user's question
  ├─ Compare to stored vectors
  ├─ Find similar products
  └─ Return relevant context
```

**Complete Configuration Check:**

```
AI Agent:
  ✓ Chat model configured
  ✓ Memory added (temporary)
  ✓ Tool added: Supabase Vector Store
     ├─ Description clear
     ├─ Table name correct
     ├─ Embeddings configured
     └─ Same model as data ingest

Ready to test!
```

#### Test RAG Retrieval

**Step 5: Verify Everything Works**

**Open Chat Interface:**

Click the chat icon in AI Agent node

**Test 1: Basic Greeting**

```
You: Hi there

Expected behavior:
  ├─ No tool usage (just greeting)
  ├─ Agent responds conversationally
  └─ Acknowledges ability to help with products

Agent: "Hello! If you're looking for specific products or have questions about what we have in stock, feel free to ask."
```

**Why No Tool Used:**

```
Agent reasoning:
  "This is a greeting, not a product question.
   Tool description says 'product information'.
   No need to query database."
   
Result: Direct response without tool call
```

**Test 2: Product Query**

```
You: Do you sell any keyboards?

Expected behavior:
  ├─ Agent recognizes product question
  ├─ Calls Supabase Vector Store tool
  ├─ Retrieves relevant keyboard products
  └─ Formulates comprehensive answer

Watch in execution:
  1. Question received
  2. Agent decides to use tool
  3. Tool call appears in logs
  4. Vector search happens
  5. Results returned
  6. Agent synthesizes response
```

**Agent Response:**

```
"Yes, we have a wide selection of keyboards to suit different needs. Here are some of our popular options:

Gaming and Performance:
- ProType RGB Gaming Keyboard ($129.99)
  Features: Mechanical switches, RGB backlighting

Productivity:
- NovaKey Tactile Keyboard ($159.99)
  Features: Vertical ergonomic design, Cherry MX switches

Office:
- TypeMaster Office Keyboard ($79.99)
  Features: Quiet operation, comfortable typing

Would you like more details on any specific keyboard?"
```

**Verify Tool Usage:**

```
In execution logs:
  ├─ Tool called: Supabase Vector Store ✓
  ├─ Query vectorized ✓
  ├─ Similarity search performed ✓
  ├─ Multiple keyboards returned ✓
  └─ Agent used results in response ✓
```

**Test 3: Specific Product Question**

```
You: How much does it cost to purchase more memory for my computer?

Agent process:
  1. Vectorize question
  2. Search for "memory" products
  3. Find RAM modules, memory cards
  4. Return specs and pricing
  5. Formulate helpful answer

Response:
"The cost depends on the type and capacity. We have several options:

Desktop RAM:
- ProSpeed DDR4 16GB: $89.99
- UltraRAM DDR5 32GB: $149.99

Laptop Memory:
- CompactRAM SO-DIMM 16GB: $79.99

What type of computer do you have?"
```

**Test 4: Follow-up Question**

```
You: What about keyboards under $100?

Agent reasoning:
  "Need keyboards filtered by price.
   Will retrieve keyboard products
   and filter/highlight affordable options."

Response:
"We have several keyboards under $100:

- TypeMaster Office Keyboard: $79.99
- CompactKey 60%: $69.99
- BasicType Standard: $49.99

All of these offer great value for their price point."
```

**Success Indicators:**

```
✓ Tool being called appropriately
✓ Relevant products returned
✓ Prices accurate (from database)
✓ Descriptions matching products
✓ Agent synthesizing well
✓ Follow-ups work smoothly
```

**What Just Happened:**

```
This is RAG in action!

Process:
  1. User asks about products
  2. Question vectorized (1,536 numbers)
  3. Compared to 60 product vectors
  4. Top similar products retrieved
  5. Original text sent to agent as context
  6. Agent generates informed response

Without RAG:
  ✗ Agent wouldn't know products
  ✗ Would say "I don't have that info"
  ✗ Couldn't answer specifically

With RAG:
  ✓ Agent appears to "know" all products
  ✓ Answers with specific details
  ✓ Scales to thousands of products
```

### Converting to Webhook-Based Architecture

Now we transition from chat testing to production webhook architecture.

#### Remove Chat Trigger

**Step 6: Prepare for Production**

```
1. Close chat interface
2. Delete "On Chat Message" node
3. Remove "Simple Memory" from AI Agent
   (Not needed for stateless webhook calls)
```

**Why Remove Memory:**

```
Webhook calls are stateless:
  ├─ Each call independent
  ├─ No conversation continuity needed
  ├─ May come from different conversations
  └─ Memory would cause confusion

Voice agent handles conversation:
  ├─ ElevenLabs manages dialogue
  ├─ n8n just answers single questions
  └─ Cleaner separation of concerns
```

#### Add Webhook Trigger

**Step 7: Create Webhook Endpoint**

```
Click: + to add trigger node
Search: "Webhook"
Select: On Webhook Call
```

**Configuration:**

```
HTTP Method: POST
  (Will receive question in POST body)

Path: Auto-generated
  (e.g., /webhook/abc123xyz)

Response Mode: Respond to webhook node
  (Will send answer back at end of workflow)

Authentication: None (for now)
  (Can add later for security)
```

**Two URLs Generated:**

```
Test URL:
  https://your-n8n.app/webhook-test/abc123xyz
  - For development
  - Only active when "Execute Workflow" running
  - Perfect for testing

Production URL:
  https://your-n8n.app/webhook/abc123xyz
  - For deployment
  - Always available
  - Use after publishing workflow
```

#### Configure AI Agent Input

**Step 8: Update Chat Input Source**

Remember: No longer connected to chat trigger!

```
In AI Agent node:
  
Chat Input Source: Define below
  (Not "Connected to chat trigger")

Input Type: Expression

Expression:
{{ $json.body.question }}

What this means:
  ├─ Incoming webhook POST request
  ├─ Body contains JSON
  ├─ Extract "question" field
  └─ Use as agent input

Example incoming data:
{
  "body": {
    "question": "Do you have any keyboards?"
  }
}

Extracted: "Do you have any keyboards?"
```

**Why This Structure:**

```
ElevenLabs will send:
  POST /webhook/abc123
  Body: {
    "question": "user's question here"
  }

n8n extracts:
  $json.body.question
  
  Breakdown:
  ├─ $json = Incoming JSON data
  ├─ .body = The POST body
  └─ .question = Our field name
```

#### Add Response Node

**Step 9: Return Answer to ElevenLabs**

```
Click + at end of workflow
Search: "Respond to Webhook"
Select: Respond to Webhook
```

**Configuration:**

```
Respond With: First incoming item

How it works:
  ├─ Receives AI Agent output
  ├─ Extracts response text
  ├─ Returns as JSON to webhook caller
  └─ ElevenLabs receives answer

Agent output format:
{
  "output": "The answer text here...",
  "other": "fields..."
}

Webhook returns:
{
  "output": "The answer text here..."
}

ElevenLabs reads "output" field
```

**Complete n8n Workflow:**

```
┌────────────────┐
│ Webhook        │ POST with question
└───────┬────────┘
        ↓
┌────────────────┐
│ AI Agent       │ Process question
│ └─ Tool:       │ Use vector store tool
│    Supabase    │ Retrieve context
└───────┬────────┘
        ↓
┌────────────────┐
│ Respond to     │ Return answer
│ Webhook        │
└────────────────┘
```

**Save Workflow!**

Don't forget: Ctrl+S / Cmd+S

### Creating ElevenLabs Voice Agent

#### Configure Voice Agent

**Step 10: Build in ElevenLabs**

Go to elevenlabs.io and sign in.

```
Navigate: Agents (left sidebar)
Click: New Agent
Select: Blank Agent
```

**Agent Configuration:**

```
Name: Electronics E-commerce Sales Expert
  (Descriptive, professional)

System Prompt:
"You are a knowledgeable online sales agent representing an e-commerce store for computer accessories. You answer the user's questions using your tool to look up any questions on the products offered by the store."

Voice: Miss Walker
  (Warm, reassuring - good for sales)

Alternatives:
  ├─ Russell: More energetic
  ├─ Jason: Calmer, professional
  └─ Your choice based on brand

Language: English

Model: Default (Gemini 2.5 Flash or current default)
```

#### Add Webhook Tool

**Step 11: Connect to n8n**

```
Navigate: Tools (in agent configuration)
Click: Add Tool
Select: Webhook
```

**Tool Configuration:**

```
Tool Name: ask_question_about_products
  (No spaces - it's a function identifier)

Description:
"Use this tool to ask a question related to the products offered by the store."

Method: POST

URL: [Get from n8n webhook - test URL first]
  ├─ Go to n8n workflow
  ├─ Click webhook node
  ├─ Copy TEST URL
  └─ Paste here

Timeout: 60 seconds
  (Allows time for RAG retrieval + LLM processing)

Pre-tool Speech: Don't force
  (Or add: "Let me check our catalog...")

Typing Sound: Enable
  ├─ Plays while tool executing
  ├─ Fills silence naturally
  └─ Better user experience

Sound Behavior: Always play
```

**Configure POST Body:**

Critical: Tell ElevenLabs what to send to n8n

```
Body Description:
"Provide the question for the product expert who will look up relevant context in a knowledge base."

Add Field:
  
  Type: String
  
  Identifier: question
    (Must match {{ $json.body.question }} in n8n)
  
  Description:
    "The question for the product expert"
  
  Required: Yes
```

**How This Works:**

```
User speaks: "Do you have keyboards?"
      ↓
ElevenLabs agent:
  ├─ Decides to use ask_question_about_products tool
  ├─ Fills "question" field with user's question
  └─ Makes POST request

POST to n8n:
  URL: https://n8n.app/webhook-test/abc123
  Body: {
    "question": "Do you have keyboards?"
  }

n8n processes:
  ├─ Extracts question
  ├─ Runs through AI agent
  ├─ Uses vector store tool
  ├─ Returns answer

Response to ElevenLabs:
  {
    "output": "Yes, we have several keyboards..."
  }

Agent speaks answer to user
```

**Save Tool!**

```
Click: Add Tool (bottom of configuration)
Verify: Tool appears in tools list
```

### Testing the Complete Integration

#### Start n8n Listening

**Step 12: Activate Webhook**

```
In n8n:
  1. Go to workflow
  2. Click: Execute Workflow
  3. Webhook now listening on test URL
  4. Keep this tab open and visible
```

**Optional: Arrange Windows**

```
Side by side:
  ├─ n8n on one side (to see execution)
  └─ ElevenLabs on other (to test agent)

Or:
  ├─ n8n minimized but visible
  └─ Focus on ElevenLabs
```

#### Test Voice Agent

**Step 13: Call the Agent**

```
In ElevenLabs:
  Click: Preview (top right)
  
Agent interface appears:
  ├─ Avatar (orb)
  └─ Call button

Click: Call AI Agent
```

**Test Conversation 1:**

```
Agent: "Hello. How can I help you today?"

You: "Hello, I'm wondering what keyboards you have."

Watch n8n:
  ├─ Webhook triggered ✓
  ├─ AI Agent processing ✓
  ├─ Vector store queried ✓
  ├─ Results retrieved ✓
  ├─ Response sent ✓

Agent: "Let me check that for you..."
       [typing sound plays]
       "We offer a wide variety of keyboards including gaming, mechanical, productivity, ergonomic, and office keyboards. Some popular models include the ProType RGB gaming keyboard, the ProType wireless mechanical keyboard, and the TypeMaster ergonomic split keyboard. We also have specialty tools like the NovaKey macro pad. Are you looking for a keyboard for a specific purpose like gaming or office work?"
```

**Success Indicators:**

```
✓ Agent understood question
✓ Called webhook successfully  
✓ n8n workflow executed
✓ Vector search performed
✓ Relevant products retrieved
✓ Natural response generated
✓ Spoken clearly by agent
```

**Test Conversation 2:**

```
You: "Yes, I'd like a mechanical keyboard please."

Agent: "Certainly. Let me narrow down the options..."
       [typing sound]
       "We have a variety of mechanical keyboards including gaming, productivity, and specialty options. Some popular choices are the ProType RGB gaming keyboard, the ProType wireless mechanical keyboard, and the NovaKey tactile keyboard. Do any of these sound interesting, or would you like more details on a specific model or switch type?"

You: "Yeah, the ProType RGB gaming please. How much is that?"

Agent: "Let me get the price for you..."
       [typing sound]
       "The ProType RGB gaming keyboard is $129.99."

You: "Thank you very much!"
```

**What We Observed:**

```
Multi-turn conversation: ✓
  ├─ Maintains context (ElevenLabs)
  ├─ Each query triggers n8n
  ├─ Independent tool calls
  └─ Coherent dialogue

RAG working perfectly: ✓
  ├─ Accurate product info
  ├─ Correct pricing
  ├─ Detailed descriptions
  └─ Helpful categorization

User experience: ✓
  ├─ Natural conversation flow
  ├─ Typing sound fills pauses
  ├─ No awkward silences
  └─ Feels like talking to human
```

**Limitations of Test Mode:**

```
Current limitation:
  ├─ "Execute Workflow" accepts one request
  ├─ Second question won't trigger
  ├─ Must re-click Execute Workflow
  └─ Not suitable for real conversations

Solution: Deploy to production!
```

### Deploying to Production

#### Publish n8n Workflow

**Step 14: Go Live**

```
In n8n workflow:

1. Save workflow (if not already)
   Ctrl+S / Cmd+S

2. Click: Publish button (top right)

3. Confirmation dialog:
   "Workflow is published"
   
4. Click: Got it

5. Copy: Production URL
   ├─ Click webhook node
   ├─ Find Production URL
   ├─ Click copy icon
   └─ Store safely

Production URL example:
https://your-n8n.app/webhook/abc123xyz
```

**What Changed:**

```
Before (Test Mode):
  ├─ Manual activation required
  ├─ Single request handling
  ├─ Development only

After (Production):
  ├─ Always available 24/7
  ├─ Unlimited concurrent requests
  ├─ Production-ready
  └─ Scalable
```

#### Update ElevenLabs Tool

**Step 15: Switch to Production URL**

```
In ElevenLabs:

1. Navigate: Tools

2. Find: ask_question_about_products

3. Click: Edit (pencil icon)

4. Update URL:
   ├─ Delete test URL
   ├─ Paste production URL
   └─ Verify no trailing spaces

5. Save: Click Save

IMPORTANT: Always save after URL change!
```

**Verification:**

```
Check:
  ✓ URL updated correctly
  ✓ Still says POST method
  ✓ Timeout still 60 seconds
  ✓ Body configuration unchanged
  ✓ Tool saved successfully
```

#### Publish ElevenLabs Agent

**Step 16: Deploy Voice Agent**

```
In ElevenLabs:

1. Navigate back to agent configuration

2. Click: Publish (top right)

3. Confirmation appears

4. Click: Copy shareable link

5. Store: Link for testing

Shareable link example:
https://elevenlabs.io/app/conversational-ai/abc123
```

### Production Testing

**Step 17: Final Verification**

Open shareable link in new browser tab:

**Full Production Test:**

```
Test 1: Product Inquiry

You: "Hello, I'm interested in getting a keyboard. What do you have?"

Agent: "Let me check our keyboard selection for you..."
       [typing sound]
       "We have a wide range of keyboards available including gaming, mechanical, productivity, office, and ergonomic options. Do you have a specific type of keyboard or feature in mind?"

You: "Yes, mechanical keyboard please."

Agent: "Certainly. Let me narrow down the options..."
       [typing sound]
       "We have a variety of mechanical keyboards including gaming, productivity, and specialty options. Some popular choices are the ProType RGB gaming keyboard, the ProType wireless mechanical keyboard, and the NovaKey tactile keyboard. Do any of these sound interesting?"

You: "Yeah, the ProType RGB gaming please. How much is that?"

Agent: "Let me get the price for you..."
       [typing sound]
       "The ProType RGB gaming keyboard is $129.99."

You: "Thank you very much!"
```

**Success Metrics:**

```
✓ Production URLs working
✓ No manual activation needed
✓ Multiple questions handled
✓ Conversation flows naturally
✓ Accurate information provided
✓ Professional voice quality
✓ Appropriate typing sounds
✓ No errors or timeouts
```

**What's Running:**

```
Complete Production Stack:

ElevenLabs (elevenlabs.io)
  ├─ Voice agent
  ├─ Speech recognition
  ├─ Voice synthesis
  └─ Conversation management
      ↓
      Tool call via webhook
      ↓
n8n (your-n8n.app)
  ├─ Webhook reception
  ├─ AI Agent (Gemini)
  └─ Business logic
      ↓
      Uses tool
      ↓
Supabase (supabase.co)
  ├─ Vector database
  ├─ Similarity search
  └─ Context retrieval
      ↓
      Returns data
      ↓
OpenAI (api.openai.com)
  ├─ Embedding model
  └─ Question vectorization

All connected and working! 🎉
```

### Optional: Twilio Phone Integration

**OPTIONAL Section** - Only if interested and willing to pay for phone number.

#### Twilio Account Setup

**Prerequisites:**

```
Requirements:
  ├─ Willing to pay ~$1-2 for phone number
  ├─ Have credit card for Twilio
  ├─ Interested in phone integration
  └─ Ready for some complexity

Skip if:
  ├─ Happy with web interface
  ├─ Don't need phone capability
  └─ Want to avoid extra setup
```

**Setup Process:**

```
1. Go to: twilio.com

2. Click: "Start for free" or "Sign up"

3. Complete registration:
   ├─ Email verification
   ├─ Phone verification
   ├─ Answer business questions
   └─ (May vary by region)

4. Add credit card:
   ├─ Navigate to billing
   ├─ Add payment method
   └─ Minimum: $1.25 for number

5. Get phone number:
   Navigate: Phone Numbers → Buy a Number
   ├─ Select: Country/region
   ├─ Choose: Available number
   ├─ Purchase: ~$1.25 one-time
   └─ Save: Phone number

6. Gather credentials:
   Go to: Console → Account Info
   Copy:
   ├─ Account SID
   ├─ Auth Token
   └─ Your Twilio phone number
```

**Twilio Navigation Tips:**

```
Twilio UI can be confusing:

Key locations:
  ├─ Phone Numbers: Left sidebar → # Phone Numbers
  ├─ Account Info: Top right → Account
  └─ Billing: Top right → Billing

If stuck:
  ├─ Use ChatGPT: "How do I find X in Twilio?"
  ├─ Very familiar with Twilio UI
  └─ Gives step-by-step clicks
```

#### Connect Twilio to ElevenLabs

**In ElevenLabs:**

```
Navigate: Deploy → Phone Numbers

Click: Import Number

Select: Import from Twilio

Configuration:
  
  Label: "Main Customer Line"
    (Or any descriptive name)
  
  Phone Number: +1234567890
    ├─ Your Twilio number
    ├─ Include country code
    └─ Copy from Twilio exactly
  
  Twilio Account SID:
    ├─ From Twilio console
    └─ Starts with "AC..."
  
  Auth Token:
    ├─ From Twilio console
    ├─ Click "Show" to reveal
    └─ Copy carefully

Click: Import
```

**Assign to Agent:**

```
After import:

1. Number appears in list

2. Click: Assign to Agent

3. Select: Electronics E-commerce Sales Expert

4. Confirm: Assignment successful

Ready to receive calls!
```

#### Test Phone Integration

**Place Test Call:**

```
From your phone:
  ├─ Dial Twilio number
  ├─ Wait for answer
  └─ Speak naturally

Example conversation:

Ring... ring...

Agent: "Hello. How can I help you today?"

You: "Hello, do you sell keyboards?"

Agent: "Let me quickly check our inventory for keyboards..."
       [brief pause]
       "Yes, we offer a wide variety of keyboards to suit different needs. We have mechanical and gaming keyboards like the ProType RGB gaming keyboard and the ProType wireless mechanical keyboard. We also have office and ergonomic keyboards such as the TypeMaster office keyboard and the TypeMaster ergonomic split keyboard. Additionally, we offer specialized and compact keyboards. Are you looking for a keyboard for gaming, office work, or a specific setup?"

You: "How much is the ProType RGB please?"

Agent: "I'll get that price for you right away..."
       "The ProType RGB gaming keyboard is priced at $129.99."

You: "Thank you very much!"

Agent: "You're welcome! Is there anything else I can help you with?"
```

**Success! 🎉**

```
What just happened:

1. Phone call to Twilio number
2. Twilio forwarded to ElevenLabs
3. Voice agent answered
4. Question detected
5. Webhook called to n8n
6. Vector search in Supabase
7. Relevant products retrieved
8. Answer generated
9. Spoken over phone
10. Natural conversation!

Technologies working together:
  ├─ Twilio (telephony)
  ├─ ElevenLabs (voice AI)
  ├─ n8n (workflow orchestration)
  ├─ Gemini (LLM reasoning)
  ├─ Supabase (vector database)
  └─ OpenAI (embeddings)

All in production! 🚀
```

### Celebration and Next Steps

**What You've Accomplished:**

```
Complete Production RAG Voice Agent:
  ✅ Vector database with 60 products
  ✅ Automated data ingest pipeline
  ✅ Semantic search capability
  ✅ Question-answering workflow
  ✅ Voice interface (ElevenLabs)
  ✅ Webhook integration
  ✅ Production deployment
  ✅ (Optional) Phone system

This is a REAL, SCALABLE system!
```

**Business Value:**

```
What you can do now:
  ├─ Scale to 60,000 products easily
  ├─ Update product catalog automatically
  ├─ Serve unlimited customers
  ├─ Answer questions 24/7
  ├─ Reduce support team workload
  ├─ Provide consistent information
  └─ Multilingual support (add more data)

Deployment options:
  ├─ Embed on website
  ├─ Phone system
  ├─ Mobile app
  ├─ WhatsApp/SMS
  └─ Any channel
```

**Your Assignment:**

```
Build something creative!

Ideas:
  
  Personal:
  ├─ Your resume as RAG agent
  ├─ Email archive Q&A
  ├─ Personal knowledge base
  └─ Recipe collection with voice

  Business:
  ├─ Company product catalog
  ├─ Internal knowledge base
  ├─ Customer support agent
  ├─ HR policy assistant
  └─ Technical documentation

  Client:
  ├─ Build for a client (free demo)
  ├─ Show them the power
  ├─ "Call this number, ask about your business"
  └─ Get feedback and refine

Share your creation:
  ├─ LinkedIn post
  ├─ Tag the course
  └─ Let's celebrate together!
```

### Week 2 Complete!

**Final Statistics:**

```
Progress: 67% through program
Skills: Dramatically expanded
Confidence: Through the roof!

You've mastered:
  ✅ Voice agent development (ElevenLabs)
  ✅ API integrations (webhooks, POST, GET)
  ✅ RAG architecture (embeddings, vectors)
  ✅ Vector databases (Supabase, pgvector)
  ✅ Data pipelines (ETL + vectorization)
  ✅ Agentic workflows (tool-using AI)
  ✅ Production deployment
  ✅ Multi-platform orchestration

You can now:
  ├─ Build expert AI assistants
  ├─ Create voice-enabled applications
  ├─ Implement semantic search
  ├─ Integrate multiple services
  ├─ Deploy production systems
  └─ Accelerate businesses
```

**Looking Ahead:**

Week 3 - Amplify:
- Advanced integrations
- Self-hosted n8n
- Professional deployment
- Enterprise patterns
- Production best practices

**You're on the path to being an n8n Pro!**

---

**End of Week 2 Documentation**

*Complete course materials covering ElevenLabs voice agents, n8n integration patterns, RAG fundamentals, Supabase implementation, and production deployment.*
