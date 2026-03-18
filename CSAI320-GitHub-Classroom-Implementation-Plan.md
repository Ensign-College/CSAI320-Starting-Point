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
- Week 3: tool-calling contract and API fallback behavior tests
- Week 4: retrieval pipeline and grounding checks
- Week 5: agent orchestration state-transition tests
- Week 6: deployment readiness and validation tests
- Week 7: end-to-end acceptance tests

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
