# CSAI 320 - Weekly Student and Instructor Guides

## How to Use This Guide
- Students: follow the weekly section in order and submit the listed evidence.
- Instructors: use facilitation notes to pace activities and support consistent grading.

## Week 1 - Build Your First AI Feature

### Week 1 Lesson Goal
This week, students learn one big idea:

An AI feature is not magic. It is a software feature that takes user input, sends it to a model, receives a response, and shows that response in a useful way.

By the end of the week, students should be able to build a simple chat app, explain what happens when a user sends a message, and describe how AI tools like GitHub Copilot can help with coding when used carefully.

### Beginner-Friendly Big Picture
Imagine a business website for a college, a small store, or a doctor office.

A visitor types:
I need help. Where do I start?

The application does four simple things:
- It shows a chat box on the screen.
- It sends the user message to the backend.
- The backend sends the message to an AI model.
- The app shows the AI response back to the user.

That is the first AI feature students will build.

### Real-World Scenarios Students Can Relate To
- A student support chatbot helps a new student know what classes to take first.
- A small business website helps a customer find the right product.
- A church or community organization helps visitors find event times and contact information.
- A tutoring app helps a learner ask simple questions and get quick explanations.

These examples help students see that a chat feature is useful because it helps real people complete real tasks.

### Scaffolding - Concepts in Simple Language
Core concepts:
- Frontend: the part the user sees and clicks.
- Backend: the part that does work behind the scenes.
- AI model: the system that reads a message and creates a response.
- User input: what the person types into the app.
- Response: what the app sends back.
- Prompt: the instruction or message given to the AI model.
- Context: helpful information given to the model so it can answer better.
- Verification: checking whether the answer or code is correct.

### Technical Terms with Student-Friendly Meanings
- Next.js: a tool that helps developers build web applications.
- TypeScript: JavaScript with extra safety checks.
- Component: one part of a screen, like a button, chat box, or header.
- API call: a message from one computer system to another asking for data or action.
- GitHub Copilot: an AI coding assistant that can suggest code, explain code, and help a student start faster.
- Model provider: the company or service that gives access to the AI model.
- Token: a small piece of text counted by the AI system.
- System message: hidden instructions that guide the AI behavior.
- User message: the message typed by the user.
- Temperature: a setting that changes how creative or predictable the AI response is.

### What Students Need to Understand Before Coding
Before students build the chat app, they should be able to explain these ideas in plain language:
- The screen the user sees is not the same as the code that talks to the AI.
- The app should not talk directly from the browser to every secret service.
- A good prompt gives the AI a clear job.
- AI output can be wrong, incomplete, or confusing, so students must check it.
- GitHub Copilot is an AI coding assistant that can help students write and explain code, but it is not a replacement for understanding.

### Student Guide
Lesson sequence:
1. Start with the question: What problem is this chat feature solving for a real person?
2. Open the starter project and identify the page, input box, send button, and response area.
3. Trace the path of one message from the user to the AI and back to the screen.
4. Build a simple chat flow that sends one message and returns one response.
5. Improve the prompt so the response is more useful, clear, and focused.
6. Use GitHub Copilot to suggest code, then read it carefully and change anything you do not understand or trust.
7. Test the app with simple user questions.

What students should practice saying:
- The frontend collects the message.
- The backend sends the message to the model.
- The model returns a response.
- The app displays the response to the user.

Simple success checklist:
- I can run the project locally.
- I can explain what the chat input does.
- I can explain where the AI response comes from.
- I can change a prompt and describe the difference in the output.
- I can describe one thing GitHub Copilot helped me do and one thing I still had to think through myself.

Submit:
- running chat demo (video or live demo)
- short AI usage log (what was generated, what you changed, why)

### Instructor Facilitation
Teaching approach:
- Assume students know nothing about frontend, backend, APIs, or LLMs.
- Use short sentences and repeat key vocabulary often.
- Define one new term at a time, then show it in the code.
- Use a concrete scenario before showing technical structure.

Suggested classroom flow:
1. Start with a real-world story, such as a college help chatbot.
2. Draw a simple diagram on the board:
   user -> webpage -> backend -> AI model -> webpage -> user
3. Ask students to describe the flow in their own words.
4. Show one small working example before asking them to build.
5. Pause often and ask check-for-understanding questions.

Recommended instructor language:
- The frontend is what people see.
- The backend is what the app does in the background.
- The prompt is the instruction we give the AI.
- We do not trust AI output automatically. We test it.

Common beginner misunderstandings to address:
- Students may think the AI is inside the browser.
- Students may think GitHub Copilot always gives correct code.
- Students may confuse the model response with the application logic.
- Students may think changing one word in a prompt does not matter.

ESL-friendly teaching supports:
- Pre-teach vocabulary before coding.
- Pair every term with one example.
- Use visual flow diagrams.
- Encourage students to explain concepts orally before writing them.
- Give sentence frames such as:
  - The user types...
  - The frontend sends...
  - The backend receives...
  - The AI returns...

Reflection prompt:
- How does this chat feature help a real person complete a real task?

## Week 2 - Data and Memory

### Week 2 Lesson Goal
This week, students learn another big idea:

If an app does not remember anything, it cannot grow into a useful product.

By the end of the week, students should be able to explain how data is stored, why relationships matter, and how memory helps an AI conversation feel more helpful and natural.

### Beginner-Friendly Big Picture
Imagine a student support chat app from Week 1.

In Week 1, the app can answer one message.
In Week 2, the app should remember things like:
- who the user is
- what the user asked before
- which conversation the message belongs to

Without memory, the chat feels like talking to a person who forgets everything after every sentence.

With memory, the app can respond in a more helpful way.

### Real-World Scenarios Students Can Relate To
- A student asks, I need help choosing classes. Later they ask, What about online options? The app should remember the earlier topic.
- A customer starts shopping, leaves, and comes back later. The app should still know their saved information.
- A tutoring app remembers a learner's last topic so it can continue helping instead of starting over.

These examples help students understand that data storage is not just technical. It helps people continue a task without repeating themselves.

### Scaffolding - Concepts in Simple Language
Core concepts:
- Data: information the app needs to keep.
- Database: the place where the app stores information.
- Data model: the plan for what information will be stored.
- Relationship: how one piece of data connects to another piece of data.
- Memory: stored information that helps the app continue a conversation.
- Persistence: data stays saved even after the app closes or reloads.
- Schema: the written structure of the data.

### Technical Terms with Student-Friendly Meanings
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

### What Students Need to Understand Before Coding
Before students build data and memory features, they should be able to explain these ideas in plain language:
- The app needs a plan before storing data.
- A user, a chat session, and a message are different things.
- Messages must belong to the correct user and conversation.
- Memory is not only for the AI model. It is also a software design choice.
- If data is stored badly, the app becomes confusing, unreliable, and hard to improve.

### Student Guide
Lesson sequence:
1. Start with the question: What information should this app remember to help the user better?
2. List the main parts of the app's data, such as user, session, and message.
3. Draw a simple ERD before writing code.
4. Open the Prisma schema and connect the ERD to the code structure.
5. Create the database models and relationships.
6. Run a migration so the database matches the schema.
7. Add seed data if needed for testing.
8. Save messages so the chat has memory.
9. Test whether the app can remember earlier conversation details.

What students should practice saying:
- A user has conversations.
- A conversation has messages.
- The database stores those records.
- Memory helps the app continue the conversation.

Simple success checklist:
- I can explain what data my app stores.
- I can explain why messages need to connect to a user or session.
- I can describe what a migration does.
- I can show that the app remembers previous messages.
- I can explain the difference between a schema and the actual stored data.

Submit:
- ERD artifact
- migration evidence
- memory behavior demonstration

### Instructor Facilitation
Teaching approach:
- Assume students have never used a database.
- Start with real objects and relationships before showing schema code.
- Use pictures and tables before using technical syntax.
- Repeat the difference between plan, structure, and stored data.

Suggested classroom flow:
1. Start with a real-world example, such as a school advising chatbot that should remember student questions.
2. Ask students what the app must remember to be useful.
3. Draw three boxes on the board: User, Session, Message.
4. Draw arrows showing how they connect.
5. Only after the visual model is clear, show the Prisma schema.
6. Walk through one migration and one saved message example.

Recommended instructor language:
- The database is where the app stores important information.
- The schema is the plan for the database.
- A relationship shows how one record connects to another.
- Memory makes the app feel continuous instead of forgetful.

Common beginner misunderstandings to address:
- Students may think the database stores only one big block of text.
- Students may confuse a model in Prisma with an AI model.
- Students may think memory only means sending old messages back to the LLM.
- Students may not understand why IDs and relationships matter.

ESL-friendly teaching supports:
- Use one consistent example all week, such as student advising chat.
- Put vocabulary on the board with a simple meaning and one example.
- Let students label an ERD before they write schema code.
- Give sentence frames such as:
  - The app stores...
  - This message belongs to...
  - This relationship means...
  - Memory helps because...

Reflection prompt:
- How does memory make the app more helpful for a real person?

## Week 3 - Tools and External APIs

### Scaffolding - Concepts and Technical Terms
Core concepts:
- Tool calling: letting an agent invoke functions/services outside the model.
- API contract: explicit input/output structure for reliable integrations.
- Resilience patterns: handling timeout, invalid data, and provider failure.
- Trust boundaries: validating data crossing external system boundaries.

Technical terms:
- REST endpoint: URL-based interface for HTTP operations.
- JSON schema or payload contract: expected request/response structure.
- Retry and timeout: failure handling controls for network calls.
- Fallback response: graceful alternative when external data is unavailable.
- Idempotency: safely repeating an operation without unintended side effects.
- HTTP status codes: standardized success/error indicators.

### Student Guide
- Implement at least one tool call to an external API.
- Add validation and fallback handling for API failure scenarios.
- Connect tool results into UI and backend workflows.
- Submit:
  - tool execution demo
  - error handling evidence
  - brief safety rationale

### Instructor Facilitation
- Model tool design using explicit input/output contracts.
- Require students to show at least one negative test case.
- Highlight integrity in handling uncertain or missing external data.

## Week 4 - Retrieval and Context Quality

### Scaffolding - Concepts and Technical Terms
Core concepts:
- Retrieval-Augmented Generation (RAG): grounding model responses in retrieved documents.
- Embedding-based similarity: matching query meaning to relevant passages.
- Context quality control: selecting high-signal evidence and limiting noise.
- Evaluation loop: compare non-RAG vs RAG output for grounded accuracy.

Technical terms:
- Embedding: numeric vector representation of text semantics.
- Vector database: storage optimized for similarity search.
- Chunking: splitting documents into retrieval-sized units.
- Metadata: structured attributes used for filtering and ranking context.
- Top-k retrieval: number of candidate passages returned.
- Hallucination: plausible but unsupported model output.

### Student Guide
- Build ingestion and embedding flow for a small domain corpus.
- Implement vector retrieval and context injection.
- Compare outputs with and without retrieval grounding.
- Submit:
  - ingestion and retrieval evidence
  - quality comparison summary
  - metadata plan

### Instructor Facilitation
- Focus evaluation on answer grounding quality, not just generation fluency.
- Ask students to explain retrieval misses and corrective changes.
- Encourage thoughtful, not excessive, context expansion.

## Week 5 - Agent Rules and Orchestration

### Scaffolding - Concepts and Technical Terms
Core concepts:
- Agent orchestration: coordinating multi-step reasoning and action flows.
- State transitions: controlled movement between workflow nodes.
- Rule design: defining what the agent may do, must do, and must never do.
- Observability and traceability: seeing why and how decisions were made.

Technical terms:
- LangGraph node and edge: processing unit and transition path.
- State object: shared data carried across workflow steps.
- Guardrail: policy or check that blocks unsafe or invalid behavior.
- Human-in-the-loop: requiring user/instructor confirmation at critical points.
- Tool router: logic selecting which tool to call next.
- Escalation path: fallback route when confidence or safety is low.

### Student Guide
- Implement workflow orchestration using LangGraph or similar framework.
- Define agent rules, role boundaries, and escalation paths.
- Add multi-step execution with observable state transitions.
- Submit:
  - workflow diagram
  - rules and skills specification
  - orchestration demo

### Instructor Facilitation
- Require explicit boundaries for agent behavior and tool usage.
- Evaluate traceability: can students explain why each step happened?
- Reinforce respectful collaboration in pair programming and review.

## Week 6 - Production Readiness

### Scaffolding - Concepts and Technical Terms
Core concepts:
- Deployment pipeline: automated path from commit to validated release.
- Reliability engineering: reducing failure likelihood and blast radius.
- Secure configuration: separating secrets from source code.
- UX quality gates: validating usability, error clarity, and accessibility basics.

Technical terms:
- CI/CD: continuous integration and continuous delivery/deployment.
- GitHub Actions workflow: automation definition for checks and tests.
- Environment variable: runtime configuration external to code.
- Secret manager: secure storage for sensitive keys.
- Build artifact: packaged output generated by build/test process.
- Health check: quick signal that a deployed service is operational.

### Student Guide
- Improve UI clarity, navigation, and input validation.
- Finalize CI pipeline and run all integration tests.
- Deploy to Vercel and verify production accessibility.
- Submit:
  - deployed URL
  - CI run evidence
  - production readiness checklist

### Instructor Facilitation
- Use a short deployment incident drill (broken env var or failed test).
- Confirm students separate secrets from source control.
- Connect quality and reliability to responsible stewardship.

## Week 7 - Capstone Delivery and Defense

### Scaffolding - Concepts and Technical Terms
Core concepts:
- Technical defense: evidence-backed explanation of architecture and tradeoffs.
- Design rationale: why specific choices were made under constraints.
- Ethics in AI delivery: privacy, bias, transparency, and accountability in product decisions.
- Outcome alignment: proving how implementation satisfies course competencies.

Technical terms:
- Architecture diagram: visual of components, data flow, and integration boundaries.
- Tradeoff analysis: explicit comparison of alternatives and consequences.
- Non-functional requirements: quality targets such as reliability, latency, and security.
- Threat model: structured view of possible abuse/failure scenarios.
- Postmortem or retrospective: structured reflection on what worked and what to improve.
- Reproducibility: ability for others to run, validate, and verify your solution.

### Student Guide
- Finalize integrated full-stack AI product.
- Present architecture, tradeoffs, and evidence of competency growth.
- Defend ethical and security decisions.
- Submit:
  - final demo
  - architecture document
  - engineering and ethics reflection

### Instructor Facilitation
- Score with rubric first on outcomes, then polish.
- Ask evidence-based defense questions tied to CLOs.
- Close with growth-focused feedback and next-step career guidance.

## Weekly Timebox Template (Suggested)
- 20% concept and demonstration
- 55% guided build and coaching
- 15% checkpoint and troubleshooting
- 10% reflection and submission prep

## Reflection Prompts (Reusable)
- What changed in your implementation after AI assistance, and why?
- Which design decision most improved reliability this week?
- Where did you practice integrity, stewardship, or service in your engineering work?
