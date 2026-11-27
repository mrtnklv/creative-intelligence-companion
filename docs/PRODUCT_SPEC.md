# Product Specification

## 1. Product summary

The Creative Intelligence Companion (CIC) is an independent creative workspace for individual creators, thinkers and researchers. It combines a visual project environment with a contextual AI companion available through text and voice.

Its purpose is to help a person capture, organise, connect, research and develop ideas over time. Collaboration and external integrations extend the workspace but are not prerequisites for its usefulness.

**Product principle:** Humans create. AI assists. Ideas move forward.

## 2. Product decisions

| Dimension | Decision |
|---|---|
| Primary user | Individual |
| Interface | Hybrid: visual workspace + chat + voice |
| Memory | Layered: personal + project + explicitly shared |
| Collaboration | Optional, project-scoped and permission-based |
| System of record | CIC workspace |
| AI behavior | Contextual, invited and human-directed |

## 3. Target user and primary job

### Primary user
An individual creator or knowledge worker developing one or more ongoing projects. Examples include artists, designers, architects, writers, independent researchers and multidisciplinary practitioners.

### Primary job
"Help me preserve and develop my thinking across time, connect relevant knowledge, investigate questions and turn ideas into meaningful outputs — without taking creative control away from me."

### Initial use cases
1. Capture a thought and attach it to a project.
2. Return to a project and recover its context.
3. Ask the companion to explain, challenge or connect ideas.
4. Research an open question and save sourced findings.
5. Turn accumulated material into a brief, plan or presentation.
6. Keep private reflections separate from material shared with collaborators.

## 4. Product information architecture

### Workspace home
A personal overview of active projects, recent activity, quick capture and companion entry point.

### Projects
Each project has:
- Name, description, intention and status.
- Project overview and activity history.
- Ideas, notes, questions and references.
- Knowledge map and relationships.
- Tasks and confirmed decisions.
- Research findings.
- Documents and other artifacts.
- Project memory and visibility controls.
- Optional collaborators and integrations.

### Companion
A persistent contextual interface that can:
- Answer questions using authorised workspace context.
- Help brainstorm, reflect and explore alternatives.
- Research when asked.
- Suggest structured updates and relationships.
- Draft artifacts.
- Explain what context it used.

### Capture
Fast entry for text, voice notes and imported material. Each capture can be assigned to a project later if the destination is not yet known.

### Memory review
A place to inspect remembered items, their source, owner, visibility, age and status; correct, approve, move/share, export or delete them.

## 5. Hybrid interaction model

### Visual
Projects, structured items, maps, timelines, tasks, sources and artifacts are navigable and editable.

### Conversational
The user can ask questions or give instructions in natural language. Conversation is an interface to the workspace, not the only place durable knowledge lives.

### Voice
Voice notes and push-to-talk are the first voice capabilities to consider. Continuous live audio is a later phase and requires explicit session controls and consent.

### Context
The user should always understand which project and memory layer the companion is using. Provide a way to inspect or change the context before consequential operations.

## 6. Layered memory and sharing rules

### Personal memory
Private to the individual. Examples: preferences, personal reflections, private notes, recurring interests and working habits.

### Project memory
Information associated with a project. Projects can be private or shared. Project membership determines who can access project memory.

### Shared knowledge
Items explicitly made available to collaborators or a defined audience. Sharing can be item-level or project-level according to the permission model.

### Non-negotiable rules
- Private memory is never included in a shared-project answer by default.
- Semantic similarity does not grant permission.
- AI-generated items remain proposals until reviewed or accepted.
- A project discussion does not automatically publish personal memory.
- Moving or copying an item between layers requires explicit user action.
- Every item retains provenance: who or what created it, where it came from and when it changed.
- Permission checks happen before retrieval and before sending context to an AI provider.
- Revoking access must also apply to search indexes, cached context and future retrieval.

### Memory item fields
At minimum: identifier, owner, project (optional), type, content, visibility, source, creator, created/updated timestamps, review status and revision history where appropriate.

## 7. Core functional requirements

### FR-01 Workspace and projects
A user can create, rename, archive and delete projects. Each project has a stable identity and persistent history.

### FR-02 Capture and organisation
A user can create, edit, tag, search and delete ideas, questions, notes, references, decisions and tasks.

### FR-03 Companion interaction
The companion accepts text requests in the context of the current workspace or selected project. It explains which context it used when relevant.

### FR-04 Layered memory
Users can inspect the source and visibility of memory items and control their retention and sharing.

### FR-05 Knowledge relationships
Users can connect items manually. AI may propose relationships but must label them as suggestions.

### FR-06 Research
Research is user-invoked, source-linked and clear about uncertainty. Users choose whether findings become project memory.

### FR-07 Creative outputs
Users can generate drafts of briefs, outlines, plans, research notes and presentations. Drafts remain editable and linked to source material.

### FR-08 Integrations
Connectors have scoped permissions, clear data-access descriptions and revocable authorisation. External actions with material consequences require user approval.

### FR-09 Voice and sessions
Voice capture is explicitly started, visibly active and easy to pause or stop. No passive recording.

### FR-10 Export and deletion
Users can export their data and delete items or projects. Deletion behavior for backups, derived indexes and connected services must be documented.

## 8. Non-functional requirements

- Privacy and permissions enforced server-side.
- Responsive interface for desktop and tablet; mobile-friendly capture.
- Data portability and understandable export formats.
- Provider-neutral model and speech adapters.
- Source provenance for imported, generated and researched content.
- Recoverable errors and clear status for long-running tasks.
- Accessibility for keyboard and assistive-technology use.
- Avoid storing raw audio unless explicitly enabled.
- Secure handling of credentials and integration tokens.

## 9. MVP scope

The first meaningful MVP is a single-user persistent workspace:
1. Workspace home and project creation.
2. Structured project items.
3. Basic search and project history.
4. Layered memory metadata and visibility controls.
5. Text-based companion with project-scoped context.
6. Review and approval of proposed updates.
7. Basic export.

Not required for this MVP: WhatsApp group bot, real-time meeting transcription, autonomous background agents, multi-user collaboration, advanced graph analytics or multiple integrations.

## 10. Success criteria

Validate through observed use rather than vanity metrics:
- A user can create a project and capture an idea in under a minute.
- The user can return later and find relevant project context.
- The companion answers from the selected project without exposing private memory.
- Users can identify whether an item is personal, project-only or shared.
- AI-generated content is distinguishable from user-authored content.
- A user can correct, export or delete stored information.
- The workspace is useful without connecting an external service.

## 11. Open questions

- Which project views are essential for the first release?
- Should quick capture default to an inbox or require a project?
- What memory retention controls should be offered by default?
- How should personal preferences be distinguished from project-specific context?
- Which artifact formats are most valuable initially?
- Which AI provider and hosting model best balance quality, privacy and cost?
- What is the minimum useful mobile experience?

## 12. Product guardrail

The companion should increase the user's ability to think and create, not increase dependence on the AI. The user owns the workspace, controls memory and sharing, and makes the creative decisions.
