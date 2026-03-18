# CSAI 320 - GitHub Classroom Implementation Plan

## 1. Objective
Provide a repeatable assignment distribution and validation model using GitHub Classroom, starter repositories, integration tests, and GitHub Actions for CSAI 320.

## 2. Repository Strategy

### Organization Layout (Suggested)
- org: ensign-csai320
- template repos:
  - csai320-w1-chat-starter
  - csai320-w2-memory-starter
  - csai320-w3-tools-api-starter
  - csai320-w4-rag-starter
  - csai320-w5-agent-orchestration-starter
  - csai320-w6-prod-readiness-starter
  - csai320-w7-capstone-submission

### Classroom Assignment Naming
- assignment-01-chat-foundations
- assignment-02-memory-and-data
- assignment-03-tools-and-apis
- assignment-04-rag-grounding
- assignment-05-agent-workflows
- assignment-06-deployment-readiness
- assignment-07-capstone

## 3. Branching and Submission Rules
- Default branch: main
- Student workflow:
  1. Pull template via Classroom invitation
  2. Build feature in main or feature branch
  3. Push changes and review CI status
  4. Submit by tagged release or commit hash
- Recommendation: require pull request for capstone repository to capture review comments.

## 4. Starter Repository Standard
Each starter should include:
- Next.js 16 + TypeScript baseline
- package manager lockfile committed
- .env.example with required variables only
- tests/integration with grading-aligned checks
- .github/workflows/ci.yml
- docs/assignment.md (student instructions)
- docs/rubric-map.md (criteria mapping)

## 5. Integration Test Design

### Test Scope by Week
- Week 1: chat endpoint response and UI rendering smoke tests
- Week 2: Prisma schema/migrations and persistence tests
- Week 3: tool-calling contract and API fallback behavior tests, with Tavily as a recommended example tool
- Week 4: retrieval pipeline and grounding checks
- Week 5: agent orchestration state-transition tests
- Week 6: deployment readiness and validation tests
- Week 7: end-to-end acceptance tests

## 14. Week 3 Recommended Tool Example

### Why Tavily Works Well for Week 3
- Tavily gives students a clear, useful first tool for agent development: web search.
- The input/output shape is understandable for beginners.
- It supports structured results that are easier to validate than open-ended scraping.
- It creates a natural bridge from simple chat to tool-augmented agent behavior.

### Recommended Week 3 Use Case
Use Tavily to answer questions that require current web information, for example:
- Find recent information about an AI tool or framework.
- Search for a company, product, or policy and summarize the result.
- Return top search findings that the UI can display as titles, URLs, and short summaries.

### Recommended Week 3 Environment Variables
Add these to the Week 3 starter .env.example:
```env
TAVILY_API_KEY=
TAVILY_MAX_RESULTS=5
```

### Recommended Week 3 Test Focus with Tavily
- validate that the tool wrapper accepts a search query
- validate that the returned data shape is normalized before UI use
- validate fallback behavior when Tavily returns an error or no results
- validate that the learner does not expose the API key to the client

### Testing Principles
- Keep tests deterministic (mock external dependencies when possible).
- Isolate secret-dependent tests behind required env checks.
- Fail with clear messages aligned to competencies.

## 6. GitHub Actions Baseline

### Suggested CI Pipeline Steps
1. Checkout
2. Setup Node
3. Install dependencies
4. Type check
5. Lint
6. Run integration tests
7. Upload test artifacts

### Example Workflow Skeleton
```yaml
name: CI

on:
  push:
  pull_request:

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: 22
          cache: npm

      - name: Install
        run: npm ci

      - name: Type Check
        run: npm run typecheck

      - name: Lint
        run: npm run lint

      - name: Integration Tests
        run: npm run test:integration
        env:
          OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}
          NEXT_PUBLIC_APP_URL: ${{ vars.NEXT_PUBLIC_APP_URL }}

      - name: Upload Artifacts
        if: always()
        uses: actions/upload-artifact@v4
        with:
          name: test-results
          path: |
            test-results/**
            coverage/**
```

## 7. Environment and Secret Management

### Local Development
- Provide .env.example only
- Students create .env.local for local runs
- Required key categories:
  - model provider keys
  - vector DB credentials (if applicable)
  - application URLs and DB connection strings

### CI and Deployment
- GitHub Secrets for sensitive values
- GitHub Variables for non-sensitive environment configuration
- Vercel project environment variables for runtime deployment

### Security Guardrails
- No secrets in code or logs
- Add secret scanning and dependency alerts
- Require rotation guidance for exposed keys

## 8. Vercel Deployment Pattern
- Connect each student repository to Vercel project
- Deploy Preview on pull request, Production on main
- Add environment variable parity checks between local, CI, and Vercel
- Require deployed URL evidence at Weeks 6 and 7

## 9. Rubric-Driven Autograding Mapping

| Competency | Testable in CI | Human Review Needed |
|---|---|---|
| CC1, CC2 | Yes | Minimal |
| CC4 | Partial (scan/config checks) | Yes |
| CC5, CC6, CC14 | Yes | Minimal |
| CC7, CC19, CC20 | Yes | Yes |
| CC8, CC9, CC12 | Partial | Yes |
| CC15, CC16, CC17, CC18 | Partial | Yes |
| CC21, CC22 | Partial | Yes |
| Agent rules/skills | Partial | Yes |
| Context/memory/prompt engineering | No | Yes |

## 10. Instructor Operations Checklist
1. Publish weekly assignment before module start.
2. Verify template repo CI is green before release.
3. Confirm Classroom links are active.
4. Post required env list and troubleshooting guide.
5. Monitor CI failures and publish top-3 fixes weekly.
6. Tag exemplary submissions for anonymized teaching examples.

## 11. Student Operations Checklist
1. Accept Classroom assignment invitation.
2. Configure .env.local from .env.example.
3. Run local integration tests before push.
4. Push regularly and watch CI checks.
5. Deploy to Vercel and validate production URL.
6. Submit evidence package per weekly instructions.

## 12. Implementation Timeline (Setup Before Course Launch)
1. Week -4: Build template repos and baseline tests.
2. Week -3: Validate CI workflows and secret handling.
3. Week -2: Pilot with TA and tune test stability.
4. Week -1: Publish Classroom assignments and dry-run release process.

## 13. Week 1 Implementation Blueprint

### Assignment Identity
- Template repository: csai320-w1-chat-starter
- Classroom assignment: assignment-01-chat-foundations
- Week theme: Build Your First AI Feature
- Primary competencies supported: CC3, CC19, early CLO4 practice

### Week 1 Student Outcome
By the end of Week 1, the learner should be able to:
- run a Next.js 16 app locally
- send a chat message from a UI to a backend route
- receive an AI-generated response from a model provider
- explain the basic request flow from browser to backend to model and back
- document how GitHub Copilot was used and what was verified manually

### Week 1 Repository Purpose
This starter should remove setup friction so the learner can focus on first concepts:
- what the chat UI does
- how the backend sends a request to the model
- how to test a simple AI feature safely
- how to use GitHub Copilot as an assistant rather than as an autopilot

### Recommended Repository Structure
```text
csai320-w1-chat-starter/
├─ app/
│  ├─ api/
│  │  └─ chat/
│  │     └─ route.ts
│  ├─ layout.tsx
│  ├─ page.tsx
│  └─ globals.css
├─ components/
│  ├─ chat-form.tsx
│  ├─ chat-message-list.tsx
│  └─ ui/
├─ lib/
│  ├─ ai/
│  │  └─ client.ts
│  └─ utils.ts
├─ tests/
│  ├─ integration/
│  │  ├─ chat-api.test.ts
│  │  └─ chat-ui.test.ts
│  └─ fixtures/
├─ docs/
│  ├─ assignment.md
│  ├─ rubric-map.md
│  └─ ai-usage-log-template.md
├─ .github/
│  └─ workflows/
│     └─ ci.yml
├─ .env.example
├─ package.json
├─ tsconfig.json
├─ eslint.config.*
└─ README.md
```

### Week 1 Starter Code Expectations
The starter should already provide:
- a working Next.js 16 app shell
- a basic page layout with a visible chat area
- a placeholder form with input and submit button
- a server route file for chat requests
- a simple AI client wrapper in lib/ai/client.ts
- passing baseline tests before student edits

The starter should leave unfinished:
- final chat request wiring
- response rendering details
- prompt refinement
- user-facing polish
- AI usage log completion

### Required Environment Variables for Week 1
Add these to .env.example:
```env
OPENAI_API_KEY=
OPENAI_MODEL=gpt-4.1-mini
NEXT_PUBLIC_APP_NAME=CSAI320 Chat Starter
```

Rules:
- Do not commit real keys.
- Students copy .env.example to .env.local.
- CI should not require a real provider call if tests are mocked.

### Week 1 GitHub Classroom Release Checklist
Before publishing the assignment:
1. Confirm the template repo installs with npm ci.
2. Confirm npm run dev starts successfully.
3. Confirm npm run lint, npm run typecheck, and npm run test:integration all pass.
4. Confirm .env.example is complete but contains no secrets.
5. Confirm docs/assignment.md matches the student-facing Week 1 lesson.
6. Confirm the Classroom invitation link creates private student copies correctly.

### Week 1 docs/assignment.md Requirements
The assignment handout inside the repo should include:
- the problem scenario
- what learners will build this week
- required setup steps
- exact commands to run locally
- expected submission artifacts
- reminder to use GitHub Copilot carefully and verify outputs
- troubleshooting section for common startup failures

### Week 1 README.md Requirements
The repo README should include:
- project purpose in plain language
- setup steps
- local run commands
- test commands
- environment variable explanation
- brief architecture note:
  browser -> Next.js route -> model provider -> route response -> UI

### Week 1 Integration Test Scope
Week 1 tests should validate the basics only.

Required checks:
- the home page renders without crashing
- the chat input and send button are visible
- the chat API route returns the expected response shape
- the UI displays a returned assistant response
- empty input is blocked or handled gracefully

Avoid testing:
- actual provider latency
- complex streaming behavior
- model quality judgments
- visual polish beyond basic presence and usability

### Week 1 Testing Strategy
Use mocked model responses for deterministic CI.

Suggested split:
- chat-api.test.ts: validates request/response behavior for app/api/chat/route.ts
- chat-ui.test.ts: validates that the learner can submit a message and see assistant output

Suggested mock response:
```json
{
  "message": "Hello. I can help you get started.",
  "role": "assistant"
}
```

### Week 1 CI Requirements
The Week 1 ci.yml should run:
1. npm ci
2. npm run lint
3. npm run typecheck
4. npm run test:integration

Week 1 CI should fail with clear messages if:
- the chat form cannot render
- the API route shape is incorrect
- the assistant response is not displayed
- the code does not type-check

### Week 1 Suggested package.json Scripts
```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "eslint .",
    "typecheck": "tsc --noEmit",
    "test:integration": "vitest run"
  }
}
```

### Week 1 Submission Evidence
Require learners to submit:
- pushed repository with passing CI
- working chat demo
- short AI usage log using docs/ai-usage-log-template.md

Suggested AI usage log prompts:
- What did GitHub Copilot help you write?
- What did you change after reviewing it?
- What did you test manually?
- What do you now understand better than before?

### Week 1 Rubric Mapping
Map Week 1 grading mainly to:
- CC3: basic model integration
- CC19: basic chat UI behavior
- CLO4 practice: responsible AI-assisted development habits

Suggested grading split for the week:
- 40% working chat flow
- 25% correct request/response wiring
- 20% local and CI test success
- 15% AI usage reflection quality

### Week 1 Instructor Validation Checklist
- Can the learner run the app locally?
- Can the learner explain the flow of one chat message?
- Does the UI successfully display an assistant response?
- Did the learner verify AI-generated code rather than pasting blindly?
- Is the repository clean of exposed secrets?

### Week 1 Known Failure Modes to Plan For
- missing OPENAI_API_KEY in local environment
- form submits but does not update UI state
- route handler returns unexpected JSON shape
- test suite accidentally depends on live provider calls
- learner confuses GitHub Copilot suggestions with required final architecture
