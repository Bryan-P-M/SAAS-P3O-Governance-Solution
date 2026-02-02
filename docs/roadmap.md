# Roadmap

This document outlines the phased delivery plan for Helm, from landing page through to full capability. Each phase delivers user-facing value and builds toward the complete vision.

---

## Roadmap Overview

```
┌────────────────────────────────────────────────────────────────────────────────────────────┐
│                                      HELM ROADMAP                                         │
├────────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                            │
│  PHASE 1         MVP            PHASE 2         PHASE 3           PHASE 4        PHASE 5   │
│  ────────       ─────           ────────        ────────          ────────        ──────   │
│                                                                                            │
│  Landing    →   RAID +      →   Meeting     →   OKRs/KPIs   →   Critical     →   MCP       │
│  Page           Actions +       Integration     EVM             Path +           Integration│
│                 Dashboards      RACI                            Dependency       Hub        │
│                                                                  Mgmt                      │
│                                                                                            │
│  "What is      "I can see      "Actions       "I can track    "I can see     "Risks and    │
│   Helm?"        everything      captured       performance     dependencies   actions from  │
│                 in one place"   from meetings; against         across         Jira/ADO/MS  │
│                                 accountability strategy"       portfolio"     Project, etc.│
│                                 is clear"                                   flow in auto" │
│                                                                                            │
└────────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## Phase 1: Landing Page (Current)

| Attribute | Detail |
|-----------|--------|
| **Focus** | Marketing and validation |
| **Goal** | Live landing page that explains Helm's value proposition |
| **Success Criteria** | Page live; messaging resonates with target personas; early access signups |

### Deliverables

- [ ] Single-page marketing site
- [ ] Clear problem statement
- [ ] Capability overview
- [ ] Call-to-action (early access / waitlist)
- [ ] Responsive design

### User Outcome

> "I understand what Helm is and why it matters. I want to learn more."

### Learning Goals

- Static HTML/CSS fundamentals
- Git workflow
- GitHub Pages deployment

---

## MVP: Functional Product

| Attribute | Detail |
|-----------|--------|
| **Focus** | Core value delivery |
| **Goal** | Usable product that solves the primary pain points |
| **Success Criteria** | See `docs/success-criteria.md` — pilot adoption, time saved, willingness to pay |

### Capabilities

| Capability | Scope | Persona Value |
|------------|-------|---------------|
| **Centralised RAID Log** | Create, view, update RAID items; tier assignment (portfolio/programme/project); ownership; status; search/filter | PMO Lead: "Everything in one place" |
| **Action Management** | Create actions; assign owners; due dates; status tracking; link to RAID items; overdue highlighting | Programme Manager: "Actions don't get lost" |
| **Basic Dashboards** | Portfolio summary; programme summary; RAID counts; action status; overdue items | Portfolio Director: "Real-time visibility" |
| **User Management** | Azure AD SSO; basic roles (Admin, Portfolio, Programme, Project) | All: "Secure, appropriate access" |

### Technical Foundation

| Component | Implementation |
|-----------|----------------|
| Frontend | React / Next.js application |
| Backend | Node.js API |
| Database | PostgreSQL (managed) |
| Authentication | Azure AD / MSAL |
| Hosting | Azure App Service |

### User Outcome

> "I can see all RAID items and actions in one place. I don't spend days consolidating spreadsheets. Nothing falls through the cracks."

### Learning Goals

- React/Next.js development
- API design and implementation
- Database design
- Azure AD integration
- Cloud deployment

---

## Phase 2: Meeting Integration + RACI

| Attribute | Detail |
|-----------|--------|
| **Focus** | Governance automation and accountability |
| **Goal** | Capture actions from meetings automatically; make accountability explicit |
| **Prerequisites** | MVP complete; assumption T4 validated (AI action extraction) |

### Capabilities

| Capability | Scope | Persona Value |
|------------|-------|---------------|
| **Meeting Integration** | Connect to Teams recordings; transcription; AI-assisted action extraction; link actions to meetings | PMO Lead: "Actions captured without manual notes" |
| **RACI Matrix** | Define RACI at programme level; link to actions/deliverables; "my accountabilities" view | Programme Manager: "Clear who's responsible" |
| **Accountability Dashboard** | Filter by role/person; workload visibility; conflict detection (missing Accountable) | Portfolio Director: "No accountability gaps" |
| **Enhanced Notifications** | Email alerts for assigned actions; overdue reminders; escalation notifications | All: "I know what needs my attention" |

### Technical Additions

| Component | Implementation |
|-----------|----------------|
| Meeting API | Microsoft Graph API for Teams recordings |
| Transcription | Azure Cognitive Services or OpenAI Whisper |
| Action Extraction | LLM-based extraction (GPT-4 or similar) |
| Notifications | Email service (SendGrid or similar) |

### Dependency: Assumption T4 Validation

Before committing to Phase 2, validate:
- Can we access Teams recordings via API?
- Does AI action extraction work reliably?
- What's the cost per meeting processed?

**If T4 fails:** Phase 2 becomes "manual meeting action capture with RACI" — still valuable, but less differentiated.

### User Outcome

> "Actions from governance meetings are automatically captured and tracked. Everyone knows who's responsible for what. No more 'I thought you were handling that.'"

### Learning Goals

- Microsoft Graph API
- AI/LLM integration
- Transcription services
- Complex data relationships (RACI)

---

## Phase 3: OKRs, KPIs & EVM

| Attribute | Detail |
|-----------|--------|
| **Focus** | Strategic alignment and performance measurement |
| **Goal** | Connect project delivery to strategic objectives; enable evidence-based intervention |
| **Prerequisites** | Phase 2 complete; sufficient data in system for meaningful metrics |

### Capabilities

| Capability | Scope | Persona Value |
|------------|-------|---------------|
| **OKR Definition** | Portfolio-level objectives and key results; cascade to programme OKRs | Portfolio Director: "Strategy is visible" |
| **KPI Tracking** | Programme and project KPIs; manual entry initially; link to OKRs | Programme Manager: "I can show contribution to strategy" |
| **Basic EVM** | Planned Value, Earned Value, Actual Cost at project level; SPI/CPI calculation | PMO Lead: "Cost/schedule variance visible" |
| **Performance Dashboards** | Traffic light status; variance reporting; trend analysis | Steering Board Chair: "Evidence for decisions" |
| **Benefits Tracking** | Expected vs realised benefits; link to business case | Programme Sponsor: "Is this still worth it?" |

### Technical Additions

| Component | Implementation |
|-----------|----------------|
| EVM Calculations | Backend calculation engine |
| Time-series data | Historical tracking for trends |
| Charting | Data visualisation library |
| Import capability | Excel/CSV import for baseline data |

### EVM Metrics Implemented

| Metric | Description | Phase 3 Scope |
|--------|-------------|---------------|
| PV | Planned Value | ✓ Manual entry |
| EV | Earned Value | ✓ Manual entry |
| AC | Actual Cost | ✓ Manual entry |
| SV / SPI | Schedule Variance / Index | ✓ Calculated |
| CV / CPI | Cost Variance / Index | ✓ Calculated |
| EAC | Estimate at Completion | ✓ Calculated |
| ETC | Estimate to Complete | ✓ Calculated |

### User Outcome

> "I can see how project work contributes to strategic objectives. I have cost and schedule performance data to support intervention decisions. Benefits realisation is tracked."

### Learning Goals

- EVM calculation logic
- Data visualisation
- Time-series data handling
- Excel import/export

---

## Phase 4: Critical Path + Dependency Management

| Attribute | Detail |
|-----------|--------|
| **Focus** | Dependency management and ecosystem integration |
| **Goal** | Visualise critical path across portfolio; connect to delivery tools |
| **Prerequisites** | Phase 3 complete; integration demand validated with customers |

### Capabilities

| Capability | Scope | Persona Value |
|------------|-------|---------------|
| **Dependency Mapping** | Cross-project and cross-programme dependencies; visual dependency graph | Programme Manager: "I can see what's connected" |
| **Critical Path Analysis** | Identify critical path per project; aggregate to programme/portfolio | Portfolio Director: "I know what's really critical" |
| **What-If Scenarios** | Model impact of slippage; forecast ripple effects | Steering Board Chair: "Evidence-based decisions" |
| **Advanced EVM** | Automated EV calculation from integrated schedule data; TCPI | PMO Lead: "EVM without manual entry" |

### Technical Additions

| Component | Implementation |
|-----------|----------------|
| Graph algorithms | Critical path calculation |
| Visualisation | Network diagrams, Gantt-style views |

### User Outcome

> "I can see dependencies across the entire portfolio. When something slips, I know the ripple effects immediately. Schedule data flows from delivery tools without manual re-entry."

### Learning Goals

- Graph algorithms (critical path)
- Complex integrations
- Data synchronisation patterns
- Advanced visualisation

---

## Phase 5: MCP Integration Hub — Connect to Customer Tooling

| Attribute    | Detail                                                                                                                                             |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| **Focus**    | Enterprise integration via Model Context Protocol (MCP) standard                                                                                   |
| **Goal**     | Position Helm as governance aggregation layer on top of customers' existing delivery tools                                                        |
| **Prerequisites** | Phase 3+ complete; at least one paying customer requesting integration                                                              |
| **Strategic rationale** | MCP is open standard (Anthropic, Microsoft, Atlassian). One adapter pattern works across all conforming tools vs bespoke REST connectors |

### The Integration Thesis
Most organisations use Jira, Azure DevOps, Planner, Confluence, SharePoint, or some combination. They won't abandon those tools. **Helm is the governance layer** (RAID, OKRs, KPIs, EVM, critical path). Customer tools are the delivery layer. MCP bridges the two with bi-directional sync.

### Available MCP Servers (Validated Feb 2026)

| Ecosystem    | MCP Server (Type)             | Tools/Scope                                               |
|--------------|-------------------------------|-----------------------------------------------------------|
| Microsoft    | Azure DevOps (official, public preview)   | Work items CRUD, sprints, boards, builds, test plans, wikis, WIQL, teams/projects |
|              | SharePoint (community)        | Document access via Graph API, lists, sites                 |
|              | Microsoft Planner (community, read-only) | Tasks, plans, buckets, assignments                        |
|              | Microsoft 365 Agents Toolkit (official)   | Broader M365 surface                                      |
|              | Microsoft Dataverse (official)            | NL queries, CRUD on business data                         |
| Atlassian    | Atlassian Rovo (official, GA)             | Jira+Confluence+Compass, OAuth 2.1, Cloud only, create/update/search |
|              | mcp-atlassian (community sooperset)       | Jira+Confluence, Cloud & Server/DC, JQL/CQL, CRUD, transitions, SLA |

### Capabilities

#### 5A. MCP Adapter Layer (Foundation)

| Feature                         | Description                                                        | Priority |
|----------------------------------|--------------------------------------------------------------------|----------|
| Connector Configuration UI       | Per-tenant setup, select provider, credentials, test, project map  | MUST     |
| MCP Client Runtime               | Server-side MCP client connecting to customer servers               | MUST     |
| Connection Health Monitoring     | Dashboard showing sync status, last sync, errors per connector      | MUST     |
| Multi-tenant Isolation           | Each customer's connections isolated, credentials encrypted         | MUST     |
| Transport Support                | Both stdio and HTTP/SSE for remote/Atlassian-type connectors        | SHOULD   |

#### 5B. RAID Mapping Engine

| Feature                         | Description                                                        | Priority |
|----------------------------------|--------------------------------------------------------------------|----------|
| Source-to-RAID Taxonomy Mapping  | Configurable rules (e.g., 'Jira Bug → Helm Issue')                 | MUST     |
| Field Mapping                    | Map source fields to Helm fields (priority, owner, dates, etc.)    | MUST     |
| Bi-directional Sync              | Read from source into Helm, optionally write back                   | SHOULD   |
| Conflict Resolution              | Configurable strategy for bi-directional updates                    | SHOULD   |
| Sync Scheduling                  | Real-time webhook, polling, or manual trigger                       | MUST     |
| Audit Trail                      | Sync operation log                                                 | MUST     |

#### 5C. Provider-Specific Integration Mapping

| Source Data                      | Helm Mapping                              | MCP Tools Used                 |
|-----------------------------------|-------------------------------------------|-------------------------------|
| Azure DevOps Work Items (Bug, Issue)         | RAID Issues                      | get_work_items, run_wiql_query          |
| Azure DevOps Work Items (Risk tag)           | RAID Risks                       | run_wiql_query with filter             |
| Azure DevOps Work Items (Task, Story)        | Actions                          | get_work_items, list_sprint_backlog     |
| Azure DevOps Sprint/Iteration data           | Programme timeline               | list_iterations                         |
| Azure DevOps Board columns                   | Status mapping                   | list_board_columns                       |
| Azure DevOps Build status                    | Project health indicators        | list_builds                              |
| Azure DevOps Wiki pages                      | Decision records/meeting notes   | get_wiki_page                            |
| Azure DevOps Team structure                  | Org hierarchy                    | list_teams, list_projects                |
| Jira Issues (Bug, Incident)                   | RAID Issues                      | jira_search (JQL), jira_get_issue        |
| Jira Issues (Risk type/label)                 | RAID Risks                       | jira_search (filtered), jira_get_issue   |
| Jira Issues (Task, Story, Action)             | Actions                          | jira_search, jira_get_issue              |
| Jira Issue transitions                        | Status sync                      | jira_transition_issue                    |
| Jira SLA metrics                              | KPI data                         | jira_get_issue_sla                       |
| Jira Epics/Projects                           | Programme/project hierarchy      | jira_search                              |
| Confluence Meeting notes pages                | Meeting records                  | confluence_search, confluence_get_page   |
| Confluence Decision log pages                 | RAID Decisions                   | confluence_search, confluence_get_page   |
| Confluence Project documentation              | Knowledge base links             | confluence_search                        |
| Planner Tasks                                 | Actions                          | planner                                 |
| Planner Plans/Buckets                         | Project/workstream structure     | planner                                 |
| Planner Assignments                           | Action ownership                 | planner                                 |
| Planner Progress/dates                        | Action status, due dates         | planner                                 |
| SharePoint Document libraries                 | Evidence/attachment links        | sharepoint                              |
| SharePoint Lists                              | Custom data sources              | sharepoint                              |
| SharePoint Business case docs                 | Benefits tracking evidence       | sharepoint                              |

#### 5D. Integration Dashboard

| Feature               | Description                                                             | Priority |
|-----------------------|-------------------------------------------------------------------------|----------|
| Connector Overview    | Visual grid with health/status (RAG)                                     | MUST     |
| Sync Activity Feed    | Real-time log of items synced/created/updated/conflicted                 | SHOULD   |
| Data Flow Visualisation| Sankey diagram showing item flow from sources to Helm categories         | NICE     |
| Coverage Report       | Gap analysis of unmapped source items                                    | SHOULD   |
| Cost Tracking         | MCP API call counts and cost per connector per month                     | SHOULD   |

### Technical Additions

| Component              | Implementation                            |
|-----------------------|--------------------------------------------|
| MCP Client            | @modelcontextprotocol/sdk (TypeScript)     |
| Transport             | stdio for self-hosted; HTTP/SSE for remote |
| Credential Storage    | Encrypted per-tenant vault                 |
| Sync Engine           | Background job queue (BullMQ or similar)   |
| Mapping Config        | JSON schema per connector, in database, UI |
| Webhook Receiver      | Optional inbound webhooks for real-time    |

### Competitive Positioning

| Alternative                | Weakness vs Helm MCP Hub                          |
|---------------------------|----------------------------------------------------|
| MS Project for the Web     | Microsoft-only, proprietary                        |
| Jira Portfolio (Roadmaps)  | Atlassian-only, limited integration                |
| Smartsheet                 | Custom connectors, expensive                       |
| Planview                   | Enterprise pricing, slow integrations              |
| Monday.com                 | Basic integrations, no P3O governance              |

### User Outcome

> "I connected my team's Jira in 10 minutes. All our risks and issues now flow into Helm automatically. The PMO can see everything across Azure DevOps AND Jira teams in one governance view — without anyone changing how they work."

### Learning Goals

- MCP protocol (client implementation)
- Background job queues
- Multi-tenant credential management
- Data mapping and transformation patterns
- Webhook architecture

---

## Beyond Phase 4: Future Vision

Capabilities to consider for future phases, based on market feedback:

| Capability | Description | Consideration |
|------------|-------------|---------------|
| **Resource Management** | Capacity planning; allocation across portfolio | High value, high complexity |
| **Financial Integration** | Connect to finance systems for actual costs | Depends on customer need |
| **Advanced AI** | Predictive risk identification; automated insights | Emerging capability |
| **Multi-org / Enterprise** | Parent-child organisations; consolidated views | For large enterprise market |
| **Audit & Compliance** | Automated compliance checking; audit reports | Public sector / regulated industries |
| **Mobile App** | Native iOS/Android apps | If demand justifies |
| **API Platform** | Public API for custom integrations | For technical customers |
| **Workflow Automation** | Custom workflows; approval chains | Enterprise requirement |

---

## Timeline Considerations

### AI-Assisted Development Impact

With AI coding assistance (Claude Code), the constraint shifts from "how long to write code" to "how long to make decisions and learn."

| Phase   | Primary Constraint                                 | Realistic Duration |
|---------|-----------------------------------------------------|-------------------|
| Phase 1 | Decision-making, learning HTML/CSS                 | 1-2 weeks         |
| MVP     | Learning React, API design, database; decisions on UX | 4-8 weeks         |
| Phase 2 | AI integration complexity; RACI design decisions   | 4-6 weeks         |
| Phase 3 | EVM domain knowledge; dashboard design             | 4-6 weeks         |
| Phase 4 | Integration complexity; graph algorithms           | 6-8 weeks         |
| Phase 5 | Multi-tool integration, mapping, sync, MCP learning| 6-10 weeks        |

**Note:** Durations are indicative. Actual time depends on:
- Hours per week available for development
- Learning curve for new technologies
- Customer feedback requiring iteration
- Unforeseen technical challenges

### Decision Gates

| Gate            | Decision                   | Criteria                       |
|-----------------|---------------------------|-------------------------------|
| **Post-Phase 1**| Proceed to MVP?           | Messaging validated; early access interest |
| **Post-MVP**    | Proceed to Phase 2?       | Pilot success; assumption T4 validated     |
| **Post-Phase 2**| Proceed to Phase 3?       | Paying customers; demand for OKR/EVM      |
| **Post-Phase 3**| Proceed to Phase 4?       | Integration demand validated; resources    |
| **Post-Phase 4**| Proceed to Phase 5?       | Customer MCP demand; partner integration  |

---

## Roadmap Principles

1. **Ship incrementally** — Each phase delivers usable value; don't wait for perfection
2. **Validate before building** — Test assumptions before committing development effort
3. **Listen to customers** — Roadmap should adapt based on real user feedback
4. **Manage scope** — Say no to features that don't serve MVP/current phase goals
5. **Build foundations well** — Technical shortcuts in MVP create debt in later phases

---

## Roadmap Summary Table

| Phase    | Capabilities                  | User Outcome                                         | Key Learning                      |
|----------|------------------------------|------------------------------------------------------|-----------------------------------|
| **Phase 1** | Landing page               | "I understand what Helm is"                          | HTML/CSS, Git                     |
| **MVP**     | RAID, Actions, Dashboards  | "Everything in one place"                            | React, Node, PostgreSQL, Azure    |
| **Phase 2** | Meetings, RACI, Notifications | "Accountability is clear"                           | Graph API, AI/LLM                 |
| **Phase 3** | OKRs, KPIs, EVM, Benefits  | "Performance against strategy"                       | EVM, visualisation                |
| **Phase 4** | Critical Path, Dependency Mgmt | "Dependencies visible"                              | Graph algorithms, integrations    |
| **Phase 5** | MCP Integration Hub        | "Risks/actions from customer tools flow in automatically" | MCP, adapters, mapping, multi-tenant |

---

## Document History

| Date       | Changes                                 |
|------------|-----------------------------------------|
| 2026-01-26 | Initial version created                 |
| 2026-02-02 | Added Phase 5: MCP Integration Hub, timeline/summary/gates updated |

---

*This roadmap is a living document. It should be reviewed and updated after each phase based on learnings and customer feedback.*
