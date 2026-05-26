# PRD Input Discovery

Use this guide when the product manager has only a rough business idea, provides incomplete context, or wants to organize the requirement before writing the PRD.

## Conversation Style

- Ask one question at a time.
- Keep each question practical and easy to answer.
- After each answer, briefly acknowledge what was captured, then ask the next question.
- Do not ask all six questions in one message unless the user explicitly asks for a full questionnaire.
- If the user says "先写" or wants to skip, stop asking and draft with assumptions under "待确认事项".
- After collecting one full pass of answers, run a coverage check before drafting. Ask only the missing or risky follow-up questions.
- After the coverage check is complete, generate a requirement input brief and present it to the user as the retained basis for the PRD.

## Six-Step Guided Questions

### 1. Business Problem

Question:
```markdown
这个需求主要想解决什么业务问题？可以简单说一下现在怎么做、现在的问题是什么、为什么现在要做。
```

Capture:
- Current process
- Pain points
- Business trigger
- Expected business improvement

### 2. Users and Scenarios

Question:
```markdown
主要使用人是谁？他们会在什么场景下使用这个功能？例如 HR、财务、运营、业务管理员、普通员工等。
```

Capture:
- User roles
- Use scenarios
- Frequency
- Key user goals

### 3. Scope and Systems

Question:
```markdown
本期涉及哪些系统、菜单或页面？哪些内容明确本期不做？
```

Capture:
- Involved systems
- Menus/pages
- In-scope items
- Out-of-scope items
- Upstream/downstream dependencies

### 4. Core Operations

Question:
```markdown
用户需要完成哪些核心操作？例如查询、新增、编辑、审批、导入、导出、查看附件、下载文件等。
```

Capture:
- List top actions
- List row actions
- In-page actions
- Operation form fields if any
- Import/export needs

### 5. Status, Rules, and Permissions

Question:
```markdown
这个需求是否涉及状态流转、业务规则或权限？例如待提交、审核中、已归档；不同状态是否影响页面展示、可执行操作、权限、审批或后续业务结果；或者是否按部门数据权限展示列表。
```

Capture:
- Statuses and transitions
- Whether the statuses form a business lifecycle and require a state machine
- Status effects on display, actions, permissions, approvals, scheduled/business-event processing, or downstream results
- Business rules/data rules
- Menu permissions
- Button permissions
- Scenario-based data permissions

### 6. Launch and Historical Data

Question:
```markdown
上线前是否需要处理历史数据或做业务准备？例如初始化线下历史数据、业务手工录入、开发补录、试点范围、验收方式等。
```

Capture:
- Historical data content
- Handling method
- Business confirmation
- Launch scope
- Acceptance criteria

## Coverage Check

Check these items before drafting:

| Area | Check |
| --- | --- |
| Business goal | Is the problem, goal, and expected outcome clear? |
| Users | Are primary users and usage scenarios clear? |
| Scope | Are involved systems/pages, in-scope items, and out-of-scope items clear? |
| Operations | Are list top actions, row actions, in-page actions, and forms clear where relevant? |
| Rules | Are key business rules, data rules, field validation, status transitions, or approval rules clear where relevant? If status changes exist, is it clear whether they affect display, actions, permissions, approval, automatic processing, or downstream results and therefore require a state machine? |
| Permissions | Are menu, button, data, and attachment permissions clear where relevant? |
| Data | Are data sources, data口径, import/export, historical data, or snapshot needs clear where relevant? |
| Launch | Are rollout scope, historical data handling, and acceptance criteria clear enough for a PRD draft? |

If gaps remain, ask targeted follow-up questions in one concise batch:

```markdown
我检查了一遍，目前还有几个会影响 PRD 完整性的点需要确认：

1. 待确认点：
2. 待确认点：
3. 待确认点：

确认后我就可以开始写 PRD。
```

Only ask about gaps that materially affect the PRD. Do not ask for optional details that can be marked as assumptions.

## Requirement Input Brief

After the coverage check and any follow-up confirmations are complete, generate a requirement input brief. This brief is the source document for the PRD and should be kept concise, factual, and traceable to the user's answers.

Use this structure:

```markdown
# 需求输入摘要

## 1. 业务背景与问题

- 当前做法：
- 主要问题：
- 需求触发原因：
- 期望改善：

## 2. 使用人和业务场景

- 主要使用人：
- 使用场景：
- 高频操作：
- 关键诉求：

## 3. 本期范围

- 涉及系统/菜单/页面：
- 本期范围内：
- 本期范围外：
- 上下游依赖：

## 4. 核心操作

- 列表顶部操作：
- 列表行操作：
- 页面内操作：
- 表单/附件/导入导出：

## 5. 状态、规则和权限

- 状态流转：
- 状态是否构成业务生命周期/是否需要状态机：
- 状态对展示、操作、权限、审批或后续业务结果的影响：
- 业务规则/数据规则：
- 菜单权限：
- 按钮权限：
- 数据权限：

## 6. 历史数据和上线准备

- 初始化的数据内容：
- 处理方式：
- 上线范围：
- 验收方式：

## 7. 待确认事项

| 编号 | 问题 | 影响范围 |
| --- | --- | --- |
| Q-001 | 待补充 | 待补充 |
```

After generating the brief, ask for confirmation:

```markdown
以上是本次 PRD 的需求输入摘要，我会以它作为后续 PRD 的依据。请确认是否需要补充或调整；如果没问题，我将继续生成 PRD。
```

Do not start the PRD until the user confirms, unless the user explicitly asks to proceed directly.
