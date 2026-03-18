# CSAI 320 - Instructor Teaching Notes

## How to Use This Guide
This guide is for instructors. It separates facilitation, coaching strategies, common misconceptions, and classroom flow from the student-facing lesson material.

## Week 1 - Build Your First AI Feature

### Teaching Approach
- Assume students know nothing about frontend, backend, APIs, or LLMs.
- Use short sentences and repeat key vocabulary often.
- Define one new term at a time, then show it in the code.
- Use a concrete scenario before showing technical structure.

### Suggested Classroom Flow
1. Start with a real-world story, such as a college help chatbot.
2. Draw a simple diagram on the board:
   user -> webpage -> backend -> AI model -> webpage -> user
3. Ask students to describe the flow in their own words.
4. Show one small working example before asking them to build.
5. Pause often and ask check-for-understanding questions.

### Recommended Instructor Language
- The frontend is what people see.
- The backend is what the app does in the background.
- The prompt is the instruction we give the AI.
- We do not trust AI output automatically. We test it.

### Common Beginner Misunderstandings to Address
- Students may think the AI is inside the browser.
- Students may think GitHub Copilot always gives correct code.
- Students may confuse the model response with the application logic.
- Students may think changing one word in a prompt does not matter.

### ESL-Friendly Teaching Supports
- Pre-teach vocabulary before coding.
- Pair every term with one example.
- Use visual flow diagrams.
- Encourage students to explain concepts orally before writing them.
- Give sentence frames such as:
  - The user types...
  - The frontend sends...
  - The backend receives...
  - The AI returns...

## Week 2 - Data and Memory

### Teaching Approach
- Assume students have never used a database.
- Start with real objects and relationships before showing schema code.
- Use pictures and tables before using technical syntax.
- Repeat the difference between plan, structure, and stored data.

### Suggested Classroom Flow
1. Start with a real-world example, such as a school advising chatbot that should remember student questions.
2. Ask students what the app must remember to be useful.
3. Draw three boxes on the board: User, Session, Message.
4. Draw arrows showing how they connect.
5. Only after the visual model is clear, show the Prisma schema.
6. Walk through one migration and one saved message example.

### Recommended Instructor Language
- The database is where the app stores important information.
- The schema is the plan for the database.
- A relationship shows how one record connects to another.
- Memory makes the app feel continuous instead of forgetful.

### Common Beginner Misunderstandings to Address
- Students may think the database stores only one big block of text.
- Students may confuse a model in Prisma with an AI model.
- Students may think memory only means sending old messages back to the LLM.
- Students may not understand why IDs and relationships matter.

### ESL-Friendly Teaching Supports
- Use one consistent example all week, such as student advising chat.
- Put vocabulary on the board with a simple meaning and one example.
- Let students label an ERD before they write schema code.
- Give sentence frames such as:
  - The app stores...
  - This message belongs to...
  - This relationship means...
  - Memory helps because...

## Week 3 - Tools and External APIs

### Teaching Notes
- Model tool design using explicit input/output contracts.
- Require students to show at least one negative test case.
- Highlight integrity in handling uncertain or missing external data.

## Week 4 - Retrieval and Context Quality

### Teaching Notes
- Focus evaluation on answer grounding quality, not just generation fluency.
- Ask students to explain retrieval misses and corrective changes.
- Encourage thoughtful, not excessive, context expansion.

## Week 5 - Agent Rules and Orchestration

### Teaching Notes
- Require explicit boundaries for agent behavior and tool usage.
- Evaluate traceability: can students explain why each step happened?
- Reinforce respectful collaboration in pair programming and review.

## Week 6 - Production Readiness

### Teaching Notes
- Use a short deployment incident drill (broken env var or failed test).
- Confirm students separate secrets from source control.
- Connect quality and reliability to responsible stewardship.

## Week 7 - Capstone Delivery and Defense

### Teaching Notes
- Score with rubric first on outcomes, then polish.
- Ask evidence-based defense questions tied to CLOs.
- Close with growth-focused feedback and next-step career guidance.

## Weekly Timebox Template (Suggested)
- 20% concept and demonstration
- 55% guided build and coaching
- 15% checkpoint and troubleshooting
- 10% reflection and submission prep
