---
name: write-prd
description: Create, refine, review, or template structured product requirement documents (PRDs) in Chinese for product managers. Use for 中文产品需求文档、PRD、需求说明书、功能需求、页面字段说明、筛选/列表/表单/导出设计、权限方案、状态流转、系统流程、业务规则、数据口径、接口同步、非功能性需求, or when drafting implementation-ready product requirements.
---

# Write PRD

## Core Workflow

1. Identify the PRD scenario first: report/display, form or operation, approval/workflow, lifecycle/status management, import/export, integration/synchronization, permission-only, or mixed.
2. If the user provides only a vague idea or asks to first organize the requirement, run the one-by-one guided discovery in `references/rules/input-discovery.md`, perform its coverage check, and generate a requirement input brief as the retained basis for the PRD before drafting.
3. Clarify blocking unknowns only when missing context changes scope or structure. Ask concise questions about scenario, users, data source, operation surface, approval/status needs, and delivery phase. If the user wants to proceed, make reasonable assumptions and list them under "待确认事项".
4. Use `references/templates/prd-template.md` as a menu, not a rigid checklist. Preserve the six major sections when useful, but include only relevant subsections.
5. Keep one source of truth for each requirement: scope defines in/out, page details define behavior, system/data rules define rules and validation, permissions define access, acceptance criteria define verification.
6. Produce Chinese PRDs by default. Preserve useful user-provided terminology when refining an existing PRD.

## Scenario-Module Mapping

| Scenario Type | Include | Omit or Restrict |
| --- | --- | --- |
| Report / Display | Background, target users, goals, scope, data sources, data calculation rules, filters, metrics/cards, table columns, refresh/export behavior, permissions, empty/error states, relevant non-functional requirements, acceptance criteria, open questions | Omit row actions, operation forms, approval flow, state machine, and system flow unless explicitly needed |
| Forms / Operations | Page entry, list actions if applicable, operation-specific form fields, validation rules, save/submit logic, success/failure feedback, empty/error states, acceptance criteria | Do not repeat filter fields as form fields |
| List With Row Actions | List top actions, row actions, status-to-action mapping, operation visibility, constraints, target status, permissions | Omit status-action mapping for read-only lists |
| Approval / Lifecycle | System flow, sequence diagram when helpful, state machine, transition rules, rollback, timeout, notifications, audit, acceptance criteria | Keep long rule details in tables, not overloaded diagram nodes |
| Integration / Sync | Upstream/downstream systems, triggers, frequency, field mapping, idempotency, retries, failure handling, reconciliation, logs, monitoring | Omit UI/page details unless a sync dashboard or manual operation exists |
| Permissions Only | Menu permissions, button permissions, scenario-based data permissions, permission exceptions, attachment or sensitive-data controls, audit logs, acceptance criteria | Omit unrelated business workflows, page forms, and role definitions when permissions are configured in a separate permission system |
| Mixed | Combine only the modules that materially apply | Avoid filling every template section by default |

Supplementary rules:
- Put business rules and calculation rules under "系统规则/数据规则" when they drive implementation.
- Omit a separate functional requirement list when scope and page details already cover the same capabilities, unless prioritization or delivery planning is needed.
- Include user analysis, business attachments, business flow, system scenarios, system flow, state machine, and functional requirement list only when they add decisions not already clear from scope.

## Output Specifications

- Start with document metadata when useful: version, owner, date, status, related links.
- Prefer numbered headings matching the template's six major sections, while omitting irrelevant subsections.
- Use tables for function lists, filters, table columns, form fields, permission matrices, status transition details, export fields, and open questions.
- Use Mermaid only for cross-system flows, approval/lifecycle flows, complex branching, or state machines. Read `references/rules/mermaid-diagrams.md` before drafting or revising diagrams.
- For page details, separate list top actions, list row actions, row status-action mapping, in-page actions, and operation form fields when they differ.
- Include non-functional requirements and acceptance criteria when they affect launch readiness, business compliance, data handling, user-visible performance, permission audit, historical data, or user acceptance. Avoid writing technical operation plans unless the user asks for a technical PRD.
- Prefer concrete nouns, measurable rules, trigger conditions, validation rules, permission rules, edge cases, and data rules. Avoid vague phrases such as "optimize experience".
- Add "待确认事项" when assumptions or unresolved business decisions remain.

## Resources Context

- Base template: `references/templates/prd-template.md`
- Input discovery: `references/rules/input-discovery.md`
- Diagram rules: `references/rules/mermaid-diagrams.md`
- Complex lifecycle example: `references/examples/lifecycle-management-prd.md`
