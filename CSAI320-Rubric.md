# CSAI 320 - Rubric (Draft)

## 1. Rubric Purpose
This rubric evaluates technical proficiency, responsible AI engineering practice, and product readiness in a 7-week full-stack AI development course.

## 2. Weighting Summary
- Weekly milestones (Weeks 1-6): 60%
- Final capstone (Week 7): 30%
- Professional practice and reflection: 10%

## 3. Performance Levels
- Exemplary (4): Exceeds expected performance with clear technical depth and strong justification.
- Proficient (3): Meets expected performance and demonstrates reliable implementation.
- Developing (2): Partially meets expectations; notable gaps in implementation or explanation.
- Beginning (1): Limited evidence of competency; major functionality or quality gaps.

## 4. CLO and Competency Criteria

### CLO1 - Deploy an application onto AWS and confirm public access
Associated competencies: CC1, CC2, CC4
Weight in course: 12%

| Criteria | 4 - Exemplary | 3 - Proficient | 2 - Developing | 1 - Beginning |
|---|---|---|---|---|
| Deployment readiness (CC1) | App is deployed, stable, and clearly production-configured; no blocking defects in key flows. | App is deployed and accessible; minor non-blocking issues. | Deployment exists but critical paths fail intermittently or require manual intervention. | Deployment incomplete or not publicly accessible. |
| CI/CD pipeline integrity (CC2) | GitHub to Vercel pipeline is fully automated with clear status checks and repeatable outcomes. | Pipeline works for normal flow and reports status correctly. | Pipeline only partially automated; inconsistent execution or missing checks. | No functional CI/CD pipeline. |
| Secrets and environment security (CC4) | Secrets are managed correctly across environments; no sensitive leakage risk; documented policy. | Secrets are stored in secure locations with minor documentation gaps. | Mixed handling of secrets; potential exposure risk due to weak process. | Secrets mishandled or hardcoded in repository. |

### CLO2 - Create a tiered full-stack app (frontend, backend, database, AI agents)
Associated competencies: CC3, CC6, CC7, CC10, CC11, CC14, CC19
Weight in course: 24%

| Criteria | 4 - Exemplary | 3 - Proficient | 2 - Developing | 1 - Beginning |
|---|---|---|---|---|
| Tiered architecture implementation | Frontend, backend, DB, and agent services are modular, coherent, and maintainable. | All tiers are implemented and integrated with acceptable structure. | Core tiers exist but integration is fragile or unclear. | Missing key tiers or non-functional end-to-end architecture. |
| Data modeling and persistence (CC6, CC10, CC11, CC14) | Prisma schema reflects robust relationships and constraints; data operations are reliable and performant. | Data model supports required use cases and persists data correctly. | Data model has structural issues or incomplete persistence logic. | Data model and persistence are substantially incomplete or broken. |
| AI integration and chat interface (CC3, CC19) | Model integration is reliable; chat UX supports practical multi-turn interactions with clear response handling. | AI responses are integrated and usable in UI for required tasks. | AI integration works inconsistently or lacks usability polish. | AI feature not operational in the application flow. |
| Frontend-backend data flow (CC7) | Data contracts are explicit and resilient; strong error handling and response integrity. | Data retrieval and processing function correctly for core workflows. | Data handling is partially correct but brittle under edge cases. | Data flow is largely non-functional or incorrect. |

### CLO3 - Develop and assess a UI that enables task completion
Associated competencies: CC15, CC16, CC17, CC18
Weight in course: 14%

| Criteria | 4 - Exemplary | 3 - Proficient | 2 - Developing | 1 - Beginning |
|---|---|---|---|---|
| Visual structure and styling (CC15) | UI is clean, consistent, and purposeful; hierarchy supports user goals. | UI is readable and functional with acceptable consistency. | UI is usable but inconsistent or visually unclear in places. | UI hinders task completion due to design or formatting issues. |
| Navigation and interaction design (CC16, CC17) | Navigation is intuitive; controls are clear, discoverable, and task-aligned. | Navigation and controls support expected tasks with minor friction. | Navigation or controls cause confusion in repeated use. | Navigation/controls are missing or significantly confusing. |
| Input validation and error handling (CC18) | Validation is robust with graceful feedback and recovery pathways. | Validation works for required fields and core error states. | Validation is partial and does not handle key error scenarios. | Minimal or absent validation and error handling. |

### CLO4 - Use AI coding tools with effective context and prompt engineering
Associated competencies: CC__ context/memory/prompt engineering
Weight in course: 10%

| Criteria | 4 - Exemplary | 3 - Proficient | 2 - Developing | 1 - Beginning |
|---|---|---|---|---|
| Prompt and context design quality | Prompts are structured, reusable, and evidence-based; context windows are managed intentionally. | Prompts and context are purposeful and generally effective. | Prompt/context use is ad hoc with uneven outcomes. | Little evidence of deliberate prompt/context engineering. |
| AI-assisted development discipline | Student critically reviews AI output, verifies behavior, and documents changes clearly. | Student uses AI responsibly with routine verification. | Limited verification of AI-generated code or weak traceability. | Overreliance on unverified AI output. |

### CLO5 - Apply and defend AI engineering best practices and ethics decisions
Associated competencies: CC8, CC21, CC__ agent rules/skills
Weight in course: 16%

| Criteria | 4 - Exemplary | 3 - Proficient | 2 - Developing | 1 - Beginning |
|---|---|---|---|---|
| Architecture and decision documentation | Decisions are clear, justified, and connected to requirements, risk, and constraints. | Documentation explains key technical decisions sufficiently. | Documentation exists but lacks depth or clear rationale. | Documentation is missing or not useful for review. |
| Responsible AI and ethics posture | Risks, bias, privacy, and misuse considerations are identified with concrete mitigations. | Ethical considerations are addressed with practical safeguards. | Ethical discussion is present but superficial or unlinked to implementation. | Ethical considerations absent or unsupported. |
| Agent governance (rules and skills) | Agent boundaries, escalation paths, and failure controls are explicit and tested. | Core agent rules and controls are defined and applied. | Rules are incomplete or weakly enforced. | Agent behavior has no defined governance controls. |

### CLO6 - Design and implement AI-powered applications
Associated competencies: CC5, CC9, CC12, CC20, CC22
Weight in course: 14%

| Criteria | 4 - Exemplary | 3 - Proficient | 2 - Developing | 1 - Beginning |
|---|---|---|---|---|
| End-to-end AI feature delivery | AI features create clear user value and integrate coherently into product workflows. | AI features are integrated and functional for expected use cases. | AI features are partially implemented or weakly integrated. | AI features are incomplete or not demonstrably functional. |
| Retrieval/knowledge strategy (CC9, CC12) | Metadata, vector strategy, and retrieval quality are measured and iteratively improved. | Retrieval setup is functional with reasonable grounding. | Retrieval setup exists but with quality or reliability weaknesses. | Retrieval strategy missing or non-functional. |
| Automation and orchestration depth (CC20, CC22) | Intelligent routing and automation are robust, explainable, and aligned to goals. | Orchestration supports required multi-step behavior. | Orchestration is simplistic or unstable under realistic scenarios. | No meaningful automation/orchestration implemented. |

## 5. Professional Practice and Reflection (10%)

| Criteria | 4 - Exemplary | 3 - Proficient | 2 - Developing | 1 - Beginning |
|---|---|---|---|---|
| Collaboration and contribution quality | Commits, reviews, and team communication show strong ownership and constructive professionalism. | Collaboration is consistent and supports team outcomes. | Collaboration is inconsistent or minimally effective. | Collaboration habits limit team progress. |
| Reflection quality | Reflection is specific, honest, and linked to technical evidence and growth decisions. | Reflection addresses key learning points with useful detail. | Reflection is generic or weakly connected to evidence. | Reflection is missing or lacks substance. |

## 6. Evidence Requirements by Week
- Week 1: Chat feature + initial AI usage log
- Week 2: ERD + Prisma schema + memory behavior proof
- Week 3: Tool/API integration + error-path validation
- Week 4: RAG pipeline + retrieval quality comparison
- Week 5: Agent rules + workflow orchestration demonstration
- Week 6: CI/CD evidence + deployment URL + security checklist
- Week 7: Final demo + architecture defense + ethics and design report

## 7. Light-Touch Faith Integration in Assessment
Faith-informed values are assessed through practical behavior, not separate theological content blocks:
- Service orientation in UX and accessibility choices
- Integrity in attribution of AI-assisted work
- Stewardship in security, maintainability, and data handling
- Respectful collaboration in peer and team interactions
