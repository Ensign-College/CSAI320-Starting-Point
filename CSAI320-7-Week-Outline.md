# CSAI 320 - 7-Week Thematic Outline and Activities

## Course Arc
Students build one capstone progressively: chat -> memory -> tools -> RAG -> orchestration -> deployment -> defense.

## Week 1 - Build Your First AI Feature
### Theme
From prompt to product: first deployed chat interaction.

### Outcomes Focus
- CLO4, CLO6 foundations
- CC3, CC19

### Activities
1. Set up starter app (Next.js 16 + TypeScript).
2. Build a minimal chat interface connected to OpenAI.
3. Use GitHub Copilot for structured context and prompt engineering.
4. Record first engineering log: what AI generated, what student changed, and why.

### Project Milestone
Working single-turn or short multi-turn chat experience in local development.

### Evidence
- Initial repository commit history
- Basic chat demo recording
- Reflection note (service-oriented user value)

## Week 2 - Model the Product and Add Memory
### Theme
Data shapes behavior: persistence and context continuity.

### Outcomes Focus
- CLO2, CLO6
- CC5, CC6, CC10, CC11, CC14

### Activities
1. Create ERD and implement Prisma schema.
2. Store users and conversation records.
3. Add memory strategy (session/conversation memory) to improve continuity.
4. Validate relational integrity and query patterns.

### Project Milestone
Chat app stores and retrieves user/session data with reliable schema relationships.

### Evidence
- ERD submission
- Prisma migration and query screenshots
- Memory behavior demonstration

## Week 3 - Add Tools and External Data
### Theme
Agents that can act: tools, APIs, and safeguards.

### Outcomes Focus
- CLO2, CLO4, CLO6
- CC7, CC21, CC22

### Activities
1. Define tool-calling interface for at least one external API.
2. Add backend route handlers and tool wrappers.
3. Implement validation and failure handling for tool responses.
4. Document guardrails for safe tool usage.

### Project Milestone
Agent can call at least one external API and return structured results to UI.

### Evidence
- Tool integration demo
- Error-path test scenario
- Decision log for safety and reliability

## Week 4 - Build Retrieval-Augmented Generation (RAG)
### Theme
From generic answers to grounded answers.

### Outcomes Focus
- CLO5, CLO6
- CC8, CC9, CC12, CC20

### Activities
1. Prepare domain documents and metadata strategy.
2. Build ingestion and embedding flow.
3. Configure vector storage and retrieval.
4. Evaluate answer quality with and without retrieval.

### Project Milestone
RAG-enabled responses with source-grounded context.

### Evidence
- Ingestion pipeline proof
- Retrieval quality comparison report
- Metadata plan artifact

## Week 5 - Design Agent Rules and Orchestration
### Theme
Beyond chat: planning, routing, and intelligent workflows.

### Outcomes Focus
- CLO4, CLO5, CLO6
- CC__ (agent rules/skills), CC__ (context/memory/prompt engineering)

### Activities
1. Implement workflow graph with LangGraph (or equivalent pattern).
2. Define agent rules, role boundaries, and escalation logic.
3. Introduce multi-step planning or decision routing.
4. Compare orchestration frameworks at a conceptual level.

### Project Milestone
Agent workflow handles multi-step tasks with explicit orchestration.

### Evidence
- Workflow diagram and implementation snapshot
- Rule set documentation
- Prompt/context strategy revisions

## Week 6 - Production Readiness and Deployment
### Theme
Ship with confidence: quality, security, and operations.

### Outcomes Focus
- CLO1, CLO3
- CC1, CC2, CC4, CC15, CC16, CC17, CC18

### Activities
1. Improve UX polish (layout, nav, controls, validation).
2. Configure GitHub Actions integration tests for push/PR.
3. Configure Vercel deployment and secure environment variables.
4. Run readiness checklist (security, error states, accessibility basics).

### Project Milestone
Publicly accessible app with green CI checks and production configuration.

### Evidence
- Deployed URL
- CI/CD pipeline run logs
- UI/UX checklist completion

## Week 7 - Capstone Delivery and Defense
### Theme
Integrated value: engineering quality and ethical clarity.

### Outcomes Focus
- All CLOs integrated

### Activities
1. Finalize end-to-end system behavior and documentation.
2. Present architecture, AI decisions, and tradeoffs.
3. Defend ethical, security, and data stewardship decisions.
4. Submit final repository and project artifacts.

### Project Milestone
Summative capstone submission and presentation.

### Evidence
- Final demo
- Architecture and decision documentation
- Ethics and discipleship-informed reflection (concise and practical)

## Suggested Weekly Rhythm
1. Concept briefing (short lecture + walkthrough)
2. Lab build block
3. Coach checkpoints
4. Submission and reflection

## Assessment Weighting (Suggested Draft)
- Weekly milestones (Weeks 1-6): 60%
- Capstone delivery and defense (Week 7): 30%
- Professional practices and reflective documentation: 10%
