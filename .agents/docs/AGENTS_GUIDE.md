# Online Test Management System SaaS Docs v1.0
## Antigravity `.agents` Execution & Architecture Guide

> **System Name:** Online Test Management System SaaS (v1.0)  
> **Repository:** `my-saas`  
> **Agent Engine:** Antigravity Customization Framework (`.agents/`)

---

## 1. System Overview & Core Modules

The **Online Test Management System SaaS (v1.0)** is designed for educational institutions, universities, and coding bootcamps to construct, deliver, proctor, and automatically grade online assessments at scale.

### Key SaaS Modules:
1. **Multi-Tenant Workspaces (`workspace_id` scoping):** Isolated environments for schools, departments, and enterprise clients.
2. **Teacher Assessment Studio:** Drag-and-drop exam builder, question bank (multiple-choice, coding sandbox, essays), automated test cases, and time limits.
3. **Student Examination Portal:** Secure, cheating-resistant exam runner featuring live timer sync, auto-saving drafts, and tab-switch detection.
4. **Automated Evaluation Engine:** Instant grading for objective & code questions, rubric-based manual grading for essays, and performance analytics.
5. **Monetization & Billing Portal:** Tiered subscription plans (Free, Pro Instructor, Enterprise Institution) managed via Stripe.

---

## 2. `.agents` Studio Infrastructure

All 12 AI agent personas, 24 skills, 9 guardrail rules, and 10 templates in `.agents/` are configured to build this SaaS system deterministically.

```text
e:\OnlineTestPlatform\my-saas\.agents\
├── agents/                       <-- 12 Agent Personas
│   ├── product-director.md       # Product vision, idea validation, scope governance
│   ├── technical-director.md     # System architecture, ADRs, engineering standards
│   ├── producer.md               # Phase tracking, lifecycle routing, scope checks
│   ├── product-manager.md        # PRD authoring, user stories, acceptance criteria
│   ├── ux-designer.md             # Wireframes, user flows, Tailwind/shadcn UI specs
│   ├── frontend-engineer.md      # Next.js App Router, React components, client state
│   ├── backend-engineer.md       # API routes, Server Actions, grading engine logic
│   ├── database-engineer.md      # Supabase Postgres schema, migrations, RLS policies
│   ├── billing-engineer.md       # Stripe integration, subscription portal, webhooks
│   ├── qa-engineer.md            # Vitest unit tests, Playwright E2E test suites
│   ├── security-engineer.md      # OWASP audits, STRIDE threat models, anti-cheat security
│   └── devops-engineer.md        # Vercel deployment, CI/CD pipelines, env key security
│
├── skills/                       <-- 24 User-Invocable Skills
│   ├── start/                    # Stage detection & route recommendation
│   ├── validate-idea/            # Market validation & PROCEED/PIVOT/KILL verdict
│   ├── write-prd/                # Full PRD generation
│   ├── map-flows/                # User journey & screen list mapping
│   ├── design-ui/                # UI design system & component spec
│   ├── setup-stack/              # Next.js + Supabase + Stripe scaffolding
│   ├── design-architecture/      # System architecture & ADRs
│   ├── architecture-diagram/     # Dark-mode HTML/SVG architecture visualizer
│   ├── design-schema/            # Postgres schema & tenant RLS policy generator
│   ├── build-feature/            # Feature implementation engine
│   ├── code-review/              # Codebase quality & security audit
│   ├── design-pricing/           # Stripe pricing tier designer
│   ├── setup-billing/            # Stripe checkout & webhook portal setup
│   ├── qa-plan/                  # QA strategy & test plan authoring
│   ├── test-setup/               # Vitest + Playwright test stack setup
│   ├── write-tests/              # Authoring unit & E2E tests
│   ├── security-audit/           # OWASP vulnerability report
│   ├── threat-model/             # STRIDE multi-tenant threat modeling
│   ├── compliance-check/         # GDPR & SOC 2-lite readiness check
│   ├── setup-deploy/             # Vercel & CI/CD deployment setup
│   ├── launch-checklist/         # Pre-launch security & infrastructure gate
│   ├── studio-status/            # Phase progress report
│   ├── scope-check/              # PRD scope boundary check
│   └── help/                     # Complete skill directory reference
│
├── rules/                        <-- 9 Path-Scoped Guardrails
│   ├── conventions.md            # Authoring standards for agents & skills
│   ├── app.md                    # Next.js App Router rules
│   ├── auth.md                   # Supabase Auth standards
│   ├── billing.md                # Stripe webhook signature verification
│   ├── data.md                   # Multi-tenant Row Level Security (RLS)
│   ├── env.md                    # Zero server secret leaks
│   ├── security.md               # OWASP input validation rules
│   ├── specs.md                  # Specification document conventions
│   └── tests.md                  # Deterministic testing rules
│
└── templates/                    <-- 10 Document Skeletons
    ├── prd.md                    # Product Requirements Document
    ├── idea-validation.md        # Idea Canvas
    ├── data-model.md             # Postgres Schema & RLS Template
    ├── adr.md                    # Architecture Decision Record
    ├── pricing.md                # Monetization plan
    ├── qa-plan.md                # Test strategy template
    ├── threat-model.md           # Threat matrix template
    ├── security-audit.md         # Vulnerability report template
    ├── compliance.md             # GDPR/SOC 2 readiness check
    └── launch-checklist.md       # Pre-launch gate checklist
```

---

## 3. End-to-End Building Lifecycle (v1.0 Implementation)

### Phase 1: Product & UX Discovery

```bash
# 1. Validate the Online Test Management SaaS concept
Run /validate-idea for Online Test Management System SaaS v1.0 — a platform for universities to host timed, cheating-resistant coding and quiz exams.

# 2. Write the MVP PRD
Run /write-prd --review lean focusing on Teacher Exam Builder, Student Exam Portal, Automated Grading, and Multi-tenant Workspaces.

# 3. Map user journeys and UI components
Run /map-flows
Run /design-ui for exam timer, question builder, and live code runner UI.
```

### Phase 2: Architecture & Database Schema

```bash
# 1. Define technical architecture & dark-themed SVG visualization
Run /design-architecture for Next.js App Router, Supabase Postgres, and Stripe.
Run /architecture-diagram

# 2. Design multi-tenant Postgres schema with RLS
Run /design-schema --review full for tables: workspaces, members, exams, questions, submissions, and grades.
```

### Phase 3: Incremental Feature Engineering

```bash
# 1. Build Teacher Exam Builder
Run /build-feature "Teacher Exam Creation Form with question ordering, time limits, and passing score settings" --review lean

# 2. Build Student Exam Portal & Instant Grading
Run /build-feature "Student Exam Interface with live countdown timer, auto-save draft submissions, and instant evaluation engine" --review lean

# 3. Code review against security rules
Run /code-review
```

### Phase 4: Monetization & Billing

```bash
# 1. Design pricing strategy
Run /design-pricing with Free Tier (50 submissions/mo), Pro ($49/mo), and Enterprise ($299/mo).

# 2. Integrate Stripe Checkout & Webhooks
Run /setup-billing --review full
```

### Phase 5: Hardening & Testing

```bash
# 1. Test strategy & test authoring
Run /qa-plan
Run /test-setup
Run /write-tests for grading calculation and multi-tenant RLS isolation.

# 2. Security audit & threat modeling
Run /threat-model on public exam links
Run /security-audit
```

### Phase 6: Production Infrastructure & Launch

```bash
# 1. Configure Vercel & Environment Keys
Run /setup-deploy

# 2. Final Launch Gate Sign-off
Run /launch-checklist
```

---

## 4. Agent Role Quick Reference

| Persona File | Agent Role | Command Prompt Example |
| :--- | :--- | :--- |
| `product-director.md` | Product Strategy & Gates | `Ask product-director: Validate our v1.0 MVP scope.` |
| `technical-director.md` | System Architecture | `Ask technical-director: Review WebSockets vs SSE for exam timer.` |
| `producer.md` | Studio Orchestration | `Run /studio-status to show remaining v1.0 tasks.` |
| `product-manager.md` | Requirements & Stories | `Ask product-manager: Write acceptance criteria for student retakes.` |
| `ux-designer.md` | UI / UX Design | `Ask ux-designer: Design the dark-mode layout for student exam runner.` |
| `frontend-engineer.md` | Next.js & React UI | `Ask frontend-engineer: Build the exam timer component.` |
| `backend-engineer.md` | API & Grading Logic | `Ask backend-engineer: Implement auto-grading evaluation handler.` |
| `database-engineer.md` | Postgres & RLS | `Ask database-engineer: Write Supabase RLS for exam_submissions.` |
| `billing-engineer.md` | Stripe Integration | `Ask billing-engineer: Verify Stripe webhook signature handling.` |
| `qa-engineer.md` | Test Engineering | `Ask qa-engineer: Write Vitest unit tests for grade calculations.` |
| `security-engineer.md` | Security & Anti-Cheat | `Ask security-engineer: Audit student exam links for IDOR.` |
| `devops-engineer.md` | Vercel Deployment | `Ask devops-engineer: Configure Vercel production environment variables.` |
