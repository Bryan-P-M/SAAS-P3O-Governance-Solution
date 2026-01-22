# Helm Project Brief

## Project Overview

|Item                 |Detail                                                                                                                                                                   |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|**Project name**     |Helm                                                                                                                                                                     |
|**Tagline**          |Governance control for organisational change                                                                                                                             |
|**Vision**           |Portfolio/programme governance tool that connects to an organisation's operational stack to provide oversight, assurance, and action-driven management of change delivery|
|**Phase 1 goal**     |Live landing page explaining the product                                                                                                                                 |
|**Target completion**|2–3 weeks (learning pace)                                                                                                                                                |
|**Tools**            |VS Code, Git, GitHub, Claude Code                                                                                                                                        |

-----

## Core Capabilities (Full Solution)

### 1. Centralised RAID Log

|Element         |Function                                                               |
|----------------|-----------------------------------------------------------------------|
|**Risks**       |Identify, assess, mitigate, escalate across portfolio/programme/project|
|**Assumptions** |Track and validate; flag when invalidated                              |
|**Issues**      |Log, assign, track to resolution                                       |
|**Dependencies**|Map internal/external dependencies; flag blockers                      |

**Key features:**

- Single indexed repository across all tiers (portfolio → programme → project)
- Inheritance and escalation pathways between levels
- Ownership assignment and accountability tracking
- Status dashboards and ageing reports
- Search and filtering by programme, owner, status, category

-----

### 2. Governance Meeting Integration

|Capability                     |Detail                                                              |
|-------------------------------|--------------------------------------------------------------------|
|**Meeting recording ingestion**|Connect to Teams/Zoom recordings                                    |
|**Transcription & indexing**   |Searchable transcripts linked to governance tier                    |
|**Action extraction**          |AI-assisted identification of decisions and actions from recordings |
|**Action tracking**            |Assigned actions flow into central tracker with owners and due dates|
|**Audit trail**                |Link actions/decisions back to source recording and timestamp       |

**Governance tiers supported:**

- Portfolio board / investment committee
- Programme board
- Project board
- Working groups / workstream leads

-----

### 3. Action-Driven Management

|Feature                 |Purpose                                            |
|------------------------|---------------------------------------------------|
|**Action register**     |Central log of all actions across governance levels|
|**Owner accountability**|Clear assignment, notifications, escalation        |
|**Progress tracking**   |Status updates, completion evidence                |
|**Overdue alerts**      |Automated nudges and escalation triggers           |
|**Reporting**           |Action completion rates, ageing, bottlenecks       |

-----

### 4. P3O Alignment

Helm's design will conform to **P3O (Portfolio, Programme and Project Offices)** guidance from AXELOS. Key principles embedded:

|P3O Principle        |Helm Implementation                                                      |
|---------------------|-------------------------------------------------------------------------|
|**Tiered governance**|Supports portfolio, programme, project levels with appropriate separation|
|**Scalability**      |Configurable for single programme or enterprise-wide deployment          |
|**Assurance**        |Built-in health checks, stage gate support, exception reporting          |
|**Information hub**  |Single source of truth for RAID, actions, decisions                      |
|**Tailoring**        |Governance structures configurable to organisation context               |
|**Enablement**       |Supports P3O functions: delivery support, COE, embedded PMO              |

**Reference frameworks:**

- P3O (Portfolio, Programme and Project Offices)
- MSP (Managing Successful Programmes)
- MoP (Management of Portfolios)
- PRINCE2
- PRINCE2 Agile
- MoR (Management of Risk)

-----

### 5. RACI Matrix & Accountability Dashboard

|Element                   |Function                                                                          |
|--------------------------|----------------------------------------------------------------------------------|
|**RACI definitions**      |Responsible, Accountable, Consulted, Informed assignments per deliverable/decision|
|**Cascade logic**         |Portfolio-level RACIs inherited and refined at programme/project level            |
|**Action log integration**|Actions auto-tagged with RACI roles; accountability visible in action register    |
|**Dashboard views**       |Filter by role, person, tier; identify gaps and overloads                         |
|**Conflict detection**    |Flag missing Accountables, multiple Accountables, orphaned responsibilities       |

**Key features:**

- Define RACI at portfolio level; programmes/projects inherit and extend
- Link RACI to governance decisions, deliverables, and RAID items
- "My accountabilities" view per user across all tiers
- Workload heatmaps to spot over-assignment

-----

### 6. Cascaded OKRs, KPIs & Earned Value Management

|Element               |Function                                                                       |
|----------------------|-------------------------------------------------------------------------------|
|**Strategic OKRs**    |Portfolio-level objectives and key results                                     |
|**KPI cascade**       |OKRs decompose into programme KPIs → project KPIs                              |
|**Traceability**      |Every project KPI traces back to strategic objective                           |
|**EVM integration**   |Earned Value metrics (PV, EV, AC, SPI, CPI) at project level, aggregated upward|
|**Variance reporting**|Automatic flag when KPIs/EVM thresholds breached                               |

**Key features:**

- Define strategic OKRs at portfolio level
- Map programme objectives to portfolio OKRs
- Map project deliverables/milestones to programme KPIs
- EVM calculated per project; rolled up to programme/portfolio health scores
- Traffic light dashboards with drill-down to root cause

**EVM metrics supported:**

|Metric       |Description                                   |
|-------------|----------------------------------------------|
|**PV**       |Planned Value                                 |
|**EV**       |Earned Value                                  |
|**AC**       |Actual Cost                                   |
|**SV / SPI** |Schedule Variance / Schedule Performance Index|
|**CV / CPI** |Cost Variance / Cost Performance Index        |
|**EAC / ETC**|Estimate at Completion / Estimate to Complete |
|**TCPI**     |To-Complete Performance Index                 |

-----

### 7. Critical Path Tracking

|Element                  |Function                                                      |
|-------------------------|--------------------------------------------------------------|
|**Project critical path**|Identify longest dependency chain per project                 |
|**Programme aggregation**|Roll up project critical paths to programme-level view        |
|**Portfolio view**       |Cross-programme dependencies and portfolio-level critical path|
|**Dependency mapping**   |Internal and external dependencies visualised                 |
|**Impact analysis**      |Model "what if" scenarios for slippage                        |

**Key features:**

- Auto-calculate critical path from task dependencies
- Highlight tasks with zero float
- Programme dashboard shows which projects are on critical path
- Portfolio dashboard shows cross-programme dependencies
- Alerts when critical path tasks slip or are at risk
- Integration with Planner/Project for task-level data

-----

## Future Integration Landscape

|System                               |Integration purpose                                   |
|-------------------------------------|------------------------------------------------------|
|**MS Teams**                         |Meeting recordings, notifications, approvals          |
|**Planner / Project**                |Task sync, workstream visibility, critical path data  |
|**SharePoint**                       |Document governance, artefact storage                 |
|**Outlook**                          |Calendar integration, email alerts                    |
|**Power BI / Data warehouse**        |Reporting, status aggregation, EVM dashboards         |
|**Azure AD / Entra**                 |SSO, user provisioning, org structure, RACI population|
|**Jira / ADO**                       |Delivery team integration                             |
|**Zoom**                             |Alternative meeting recording source                  |
|**Azure Cognitive Services / OpenAI**|Transcription, action extraction                      |

-----

## Phase 1 File Structure

```
helm/
├── .git/
├── .gitignore
├── README.md
├── index.html
├── css/
│   └── styles.css
├── images/
└── docs/
    ├── project-brief.md
    ├── objectives.md
    ├── planning-log.md
    └── capability-model.md
```

-----

## Phase 1 Task Breakdown

### Stage 1: Environment Setup

|#  |Task                                                         |Acceptance Criteria           |
|---|-------------------------------------------------------------|------------------------------|
|1.1|Create project folder `helm`                                 |Folder exists locally         |
|1.2|Initialise Git                                               |`.git/` folder present        |
|1.3|Create `.gitignore`                                          |Ignores OS files, editor files|
|1.4|Create `README.md` with project name and one-line description|File committed                |
|1.5|Create folder structure (`css/`, `images/`, `docs/`)         |Folders exist                 |
|1.6|First commit                                                 |`git log` shows initial commit|

**Claude Code prompt:**

> "Help me set up a new project folder called helm with Git initialised, a sensible .gitignore for a static website, a basic README, and folders for css, images, and docs."

-----

### Stage 2: Planning Foundations (Brainstorming)

|#  |Task                                                                                                         |Acceptance Criteria               |
|---|-------------------------------------------------------------------------------------------------------------|----------------------------------|
|2.1|Define project objectives                                                                                    |Documented in `docs/objectives.md`|
|2.2|Define target users and pain points                                                                          |Included in objectives doc        |
|2.3|Document core capabilities (RAID, meeting integration, actions, RACI, OKRs/EVM, critical path, P3O alignment)|`docs/capability-model.md` created|
|2.4|Draft Phase 1 deliverables and success criteria                                                              |Clear, measurable outcomes        |
|2.5|Identify assumptions and constraints                                                                         |Documented                        |
|2.6|Outline future phases at high level                                                                          |Roadmap sketch                    |
|2.7|Review and stress-test the plan                                                                              |No obvious gaps                   |
|2.8|Commit planning docs                                                                                         |Clean commit                      |

**Outputs:**

- `docs/objectives.md` — Objectives, users, pain points, success criteria
- `docs/capability-model.md` — Core capabilities, P3O alignment, integration landscape
- `docs/planning-log.md` — Brainstorming decisions and rationale

**Claude Code prompt:**

> "Act as a brainstorming agent. Help me iterate on the objectives and deliverables for Helm—a P3O-aligned governance tool for portfolio, programme and project managers. Core capabilities include: (1) centralised RAID log across all governance tiers, (2) integration with meeting recordings for action extraction and tracking, (3) action-driven management dashboards, (4) cascading RACI matrix with accountability dashboards, (5) strategic OKR to KPI cascade with Earned Value Management, and (6) portfolio-to-project critical path tracking. The design should align with P3O, MSP, MoP, PRINCE2, PRINCE2 Agile, and MoR frameworks. Challenge my assumptions, identify gaps, and help me refine until the planning foundations are robust."

**Quality checklist before proceeding:**

```
[ ] Objectives are specific and measurable
[ ] Target users clearly defined (portfolio, programme, project roles)
[ ] Pain points articulated from user perspective
[ ] Core capabilities documented and aligned to P3O
[ ] Phase 1 deliverables scoped realistically
[ ] Success criteria are testable
[ ] Assumptions documented
[ ] Constraints acknowledged
[ ] Future phases sketched
[ ] Planning rationale captured
```

-----

### Stage 3: Landing Page Content

|#  |Task                                       |Acceptance Criteria     |
|---|-------------------------------------------|------------------------|
|3.1|Draft landing page copy                    |Markdown file in `docs/`|
|3.2|Create `index.html` with semantic structure|Valid HTML              |
|3.3|Add content to HTML                        |Page displays in browser|
|3.4|Commit progress                            |Clean commit            |

**Suggested page sections:**

1. **Hero** – Headline + value prop
1. **Problem** – Why governance over change portfolios is hard
1. **Solution** – What Helm does
1. **Features** – Centralised RAID, meeting-to-action, RACI accountability, OKR/KPI/EVM tracking, critical path visibility
1. **P3O alignment** – Built on best practice frameworks
1. **Integrations** – Connects to MS Teams, SharePoint, Planner, etc.
1. **CTA** – "Request early access"
1. **Footer**

**Claude Code prompt:**

> "Using the objectives and capability model from docs/, help me draft landing page copy for Helm. Emphasise: centralised RAID log, governance meeting integration with action extraction, cascading RACI accountability, OKR-to-KPI traceability with EVM, critical path tracking across the portfolio, and P3O alignment. Then create a semantic HTML structure for the single-page site."

-----

### Stage 4: Styling

|#  |Task                   |Acceptance Criteria              |
|---|-----------------------|---------------------------------|
|4.1|Create `css/styles.css`|File exists, linked in HTML      |
|4.2|Apply base styles      |Page is readable and professional|
|4.3|Make layout responsive |Works on mobile                  |
|4.4|Commit progress        |Clean commit                     |

**Claude Code prompt:**

> "Help me create a clean, professional CSS stylesheet for my Helm landing page. Use a modern sans-serif font, a colour palette suitable for a B2B governance/enterprise product, and make it responsive."

-----

### Stage 5: GitHub & Deployment

|#  |Task                           |Acceptance Criteria         |
|---|-------------------------------|----------------------------|
|5.1|Create GitHub repository `helm`|Repo exists on GitHub       |
|5.2|Connect local repo to remote   |`git remote -v` shows origin|
|5.3|Push code                      |Code visible on GitHub      |
|5.4|Enable GitHub Pages            |Live URL works              |
|5.5|Update README with live URL    |Pushed                      |

**Claude Code prompt:**

> "Walk me through connecting my local helm repo to a new GitHub repository and pushing the code. Then help me enable GitHub Pages so the site is live."

-----

### Stage 6: Review & Iterate

|#  |Task                                  |Acceptance Criteria|
|---|--------------------------------------|-------------------|
|6.1|Review live site on desktop and mobile|No obvious issues  |
|6.2|Fix any issues                        |Changes committed  |
|6.3|Write a short reflection in `docs/`   |File exists        |
|6.4|Final commit and push                 |Repo up to date    |

-----

## Checklist Summary

```
[ ] Project folder and Git initialised
[ ] .gitignore, README, folder structure in place
[ ] Planning foundations complete (objectives.md, capability-model.md, planning-log.md)
[ ] Landing page copy drafted
[ ] index.html created with semantic structure
[ ] styles.css applied, page looks professional
[ ] Responsive on mobile
[ ] Pushed to GitHub
[ ] GitHub Pages enabled, site live
[ ] README updated with live URL
```

-----

## Next Actions

1. Open Claude Code
1. Run the Stage 1 prompt to scaffold the project
1. Spend proper time on Stage 2—get the capability model and objectives right
1. Proceed through remaining stages, committing as you go

-----

## Document History

|Version|Date      |Changes                                                                  |
|-------|----------|-------------------------------------------------------------------------|
|1.0    |2025-01-22|Initial project brief created                                            |
|1.1    |2025-01-22|Added RACI matrix, OKRs/KPIs/EVM, and critical path tracking capabilities|
