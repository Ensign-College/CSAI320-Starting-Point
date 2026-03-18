# CSAI 320 - Student Guide

## How to Use This Guide
This guide is written for you. It is designed to be self-contained, which means it gives you the key ideas, vocabulary, and weekly tasks you need in order to complete the course work.

Read each week in order.

## Week 1 - Build Your First AI Feature

### Week 1 Lesson Goal
This week, you learn one big idea:

An AI feature is not magic. It is a software feature that takes user input, sends it to a model, receives a response, and shows that response in a useful way.

By the end of the week, you should be able to build a simple chat app, explain what happens when a user sends a message, and describe how AI tools like GitHub Copilot can help with coding when used carefully.

### Beginner-Friendly Big Picture
Imagine a business website for a college, a small store, or a doctor office.

A visitor types:
I need help. Where do I start?

The application does four simple things:
- It shows a chat box on the screen.
- It sends the user message to the backend.
- The backend sends the message to an AI model.
- The app shows the AI response back to the user.

That is the first AI feature you will build.

### Real-World Scenarios You Can Relate To
- A student support chatbot helps a new student know what classes to take first.
- A small business website helps a customer find the right product.
- A church or community organization helps visitors find event times and contact information.
- A tutoring app helps a learner ask simple questions and get quick explanations.

### Scaffolding - Concepts in Simple Language
- Frontend: the part the user sees and clicks.
- Backend: the part that does work behind the scenes.
- AI model: the system that reads a message and creates a response.
- User input: what the person types into the app.
- Response: what the app sends back.
- Prompt: the instruction or message given to the AI model.
- Context: helpful information given to the model so it can answer better.
- Verification: checking whether the answer or code is correct.

### Technical Terms in Simple Language
- Next.js: a tool that helps developers build web applications.
- TypeScript: JavaScript with extra safety checks.
- Component: one part of a screen, like a button, chat box, or header.
- API call: a message from one computer system to another asking for data or action.
- GitHub Copilot: an AI coding assistant that can suggest code, explain code, and help you start faster.
- Model provider: the company or service that gives access to the AI model.
- Token: a small piece of text counted by the AI system.
- System message: hidden instructions that guide the AI behavior.
- User message: the message typed by the user.
- Temperature: a setting that changes how creative or predictable the AI response is.

### What You Need to Know Before Coding
- The screen you see is not the same as the code that talks to the AI.
- The app should not talk directly from the browser to every secret service.
- A good prompt gives the AI a clear job.
- AI output can be wrong, incomplete, or confusing, so you must check it.
- GitHub Copilot is an AI coding assistant that can help you write and explain code, but it is not a replacement for understanding.

### Your Lesson Sequence
1. Start with the question: What problem is this chat feature solving for a real person?
2. Open the starter project and identify the page, input box, send button, and response area.
3. Trace the path of one message from the user to the AI and back to the screen.
4. Build a simple chat flow that sends one message and returns one response.
5. Improve the prompt so the response is more useful, clear, and focused.
6. Use GitHub Copilot to suggest code, then read it carefully and change anything you do not understand or trust.
7. Test the app with simple user questions.

### What You Should Practice Saying
- The frontend collects the message.
- The backend sends the message to the model.
- The model returns a response.
- The app displays the response to the user.

### Simple Success Checklist
- I can run the project locally.
- I can explain what the chat input does.
- I can explain where the AI response comes from.
- I can change a prompt and describe the difference in the output.
- I can describe one thing GitHub Copilot helped me do and one thing I still had to think through myself.

### Submit
- running chat demo (video or live demo)
- short AI usage log (what was generated, what you changed, why)

### Reflection Prompt
- How does this chat feature help a real person complete a real task?

## Week 2 - Data and Memory

### Week 2 Lesson Goal
This week, you learn another big idea:

If an app does not remember anything, it cannot grow into a useful product.

By the end of the week, you should be able to explain how data is stored, why relationships matter, and how memory helps an AI conversation feel more helpful and natural.

### Beginner-Friendly Big Picture
Imagine a student support chat app from Week 1.

In Week 1, the app can answer one message.
In Week 2, the app should remember things like:
- who the user is
- what the user asked before
- which conversation the message belongs to

Without memory, the chat feels like talking to a person who forgets everything after every sentence.

With memory, the app can respond in a more helpful way.

### Real-World Scenarios You Can Relate To
- A student asks, I need help choosing classes. Later they ask, What about online options? The app should remember the earlier topic.
- A customer starts shopping, leaves, and comes back later. The app should still know their saved information.
- A tutoring app remembers a learner's last topic so it can continue helping instead of starting over.

### Scaffolding - Concepts in Simple Language
- Data: information the app needs to keep.
- Database: the place where the app stores information.
- Data model: the plan for what information will be stored.
- Relationship: how one piece of data connects to another piece of data.
- Memory: stored information that helps the app continue a conversation.
- Persistence: data stays saved even after the app closes or reloads.
- Schema: the written structure of the data.

### Technical Terms in Simple Language
- ERD (Entity Relationship Diagram): a picture that shows what data exists and how it connects.
- Entity: one kind of thing in the system, such as User, Message, or Session.
- Prisma: a tool that helps developers define and use database structure in code.
- Prisma schema: the file where the developer defines models and relationships.
- Migration: an update that changes the database structure.
- Seed data: starter data used for testing and setup.
- Primary key: the unique ID for one record.
- Foreign key: a field that links one record to another.
- One-to-one: one item is connected to one other item.
- Many-to-one: many items connect back to one item.

### What You Need to Know Before Coding
- The app needs a plan before storing data.
- A user, a chat session, and a message are different things.
- Messages must belong to the correct user and conversation.
- Memory is not only for the AI model. It is also a software design choice.
- If data is stored badly, the app becomes confusing, unreliable, and hard to improve.

### Your Lesson Sequence
1. Start with the question: What information should this app remember to help the user better?
2. List the main parts of the app's data, such as user, session, and message.
3. Draw a simple ERD before writing code.
4. Open the Prisma schema and connect the ERD to the code structure.
5. Create the database models and relationships.
6. Run a migration so the database matches the schema.
7. Add seed data if needed for testing.
8. Save messages so the chat has memory.
9. Test whether the app can remember earlier conversation details.

### What You Should Practice Saying
- A user has conversations.
- A conversation has messages.
- The database stores those records.
- Memory helps the app continue the conversation.

### Simple Success Checklist
- I can explain what data my app stores.
- I can explain why messages need to connect to a user or session.
- I can describe what a migration does.
- I can show that the app remembers previous messages.
- I can explain the difference between a schema and the actual stored data.

### Submit
- ERD artifact
- migration evidence
- memory behavior demonstration

### Reflection Prompt
- How does memory make the app more helpful for a real person?

## Week 3 - Tools and External APIs

### Key Concepts
- Tool calling: letting an agent use functions or services outside the model.
- API contract: clear structure for what goes in and what comes out.
- Resilience: handling errors, timeouts, or missing data.
- Trust boundaries: checking outside data before using it.

### Technical Terms
- REST endpoint
- JSON payload
- Timeout
- Retry
- Fallback response
- HTTP status code

### Your Tasks
- Implement at least one tool call to an external API.
- Add validation and fallback handling for API failure scenarios.
- Connect tool results into UI and backend workflows.

### Submit
- tool execution demo
- error handling evidence
- brief safety rationale

## Week 4 - Retrieval and Context Quality

### Key Concepts
- Retrieval-Augmented Generation (RAG)
- Embedding-based similarity
- Context quality control
- Grounded answers

### Technical Terms
- Embedding
- Vector database
- Chunking
- Metadata
- Top-k retrieval
- Hallucination

### Your Tasks
- Build ingestion and embedding flow for a small domain corpus.
- Implement vector retrieval and context injection.
- Compare outputs with and without retrieval grounding.

### Submit
- ingestion and retrieval evidence
- quality comparison summary
- metadata plan

## Week 5 - Agent Rules and Orchestration

### Key Concepts
- Agent orchestration
- State transitions
- Rule design
- Traceability

### Technical Terms
- LangGraph node
- Edge
- State object
- Guardrail
- Human-in-the-loop
- Escalation path

### Your Tasks
- Implement workflow orchestration using LangGraph or similar framework.
- Define agent rules, role boundaries, and escalation paths.
- Add multi-step execution with observable state transitions.

### Submit
- workflow diagram
- rules and skills specification
- orchestration demo

## Week 6 - Production Readiness

### Key Concepts
- Deployment pipeline
- Reliability
- Secure configuration
- UX quality checks

### Technical Terms
- CI/CD
- GitHub Actions workflow
- Environment variable
- Secret manager
- Build artifact
- Health check

### Your Tasks
- Improve UI clarity, navigation, and input validation.
- Finalize CI pipeline and run all integration tests.
- Deploy to Vercel and verify production accessibility.

### Submit
- deployed URL
- CI run evidence
- production readiness checklist

## Week 7 - Capstone Delivery and Defense

### Key Concepts
- Technical defense
- Design rationale
- Ethics in AI delivery
- Outcome alignment

### Technical Terms
- Architecture diagram
- Tradeoff analysis
- Non-functional requirements
- Threat model
- Retrospective
- Reproducibility

### Your Tasks
- Finalize integrated full-stack AI product.
- Present architecture, tradeoffs, and evidence of competency growth.
- Defend ethical and security decisions.

### Submit
- final demo
- architecture document
- engineering and ethics reflection

## Reflection Prompts (Reusable)
- What changed in your implementation after AI assistance, and why?
- Which design decision most improved reliability this week?
- Where did you practice integrity, stewardship, or service in your engineering work?
