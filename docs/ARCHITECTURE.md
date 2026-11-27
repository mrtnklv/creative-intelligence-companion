# Initial Technical Architecture

## Status

This is a proposed architecture for exploration, not a commitment to a particular framework, vendor or deployment model. The architecture is updated to reflect an individual-first workspace, a hybrid interface and layered memory. Validate each major choice through small, testable increments.

## Architecture goals

- Make the product useful to one person before adding collaboration.
- Treat projects and durable knowledge as first-class entities, not chat history alone.
- Separate personal, project and explicitly shared memory with enforceable access rules.
- Support visual, text and voice interaction through a consistent application model.
- Preserve provenance for user input, imports, AI inferences and external research.
- Keep AI models, speech services and integrations replaceable.
- Make privacy, export, correction and deletion part of the data model.
- Avoid premature realtime infrastructure and integrations.

## Proposed components

### 1. Client application

A responsive web application is the initial surface. It should provide:
- Personal home and project navigation.
- Project overview and activity.
- Structured notes, ideas, questions, references, decisions and tasks.
- Knowledge map and other visual project views.
- Contextual companion panel supporting chat and, later, voice.
- Memory review and visibility controls.
- Document and presentation creation and export.

A React-based application is a reasonable starting point. Next.js is one option, not a requirement. Keep UI components separate from provider-specific AI logic.

### 2. Identity and workspace service

Initially support one authenticated owner with private projects. Design the data model to allow future collaborators, roles and invitations without requiring multi-user functionality in the first milestone.

Core concepts:
- User
- Workspace
- Project
- Project membership (future-ready)
- Role and permission (future-ready)

Every query and mutation must be scoped to the authenticated owner and the relevant project. Do not rely on client-side filtering as an access-control boundary.

### 3. Project and knowledge service

Projects contain typed knowledge objects rather than one unstructured summary.

Initial object types:
- Idea
- Question
- Note
- Theme
- Reference
- Research finding
- Decision
- Task
- Session
- Artifact (document, presentation, plan, etc.)

Each object should have an ID, project association where applicable, content, type, source/provenance, timestamps, status and visibility. Relationships can include relates to, supports, challenges, answers, derived from, assigned to and decided in.

A knowledge map is a visual representation of these typed objects and relationships, not merely a list grouped by category. React Flow is one candidate for visualisation.

### 4. Layered memory service

Memory is a permission and context model, not a single vector database.

#### Personal memory
Private to the owner. May contain preferences, working patterns, personal reflections and notes. It must not be exposed to project collaborators by default.

#### Project memory
Belongs to a project. A project can be private or shared with invited collaborators. Project memory is available only to users with permission to access that project.

#### Shared knowledge
A deliberate visibility state for items that should be accessible to project members or a defined audience. Shared knowledge may originate from a personal or project item, but publication must be explicit and recorded.

Recommended metadata on every memory-bearing item:
- owner_id
- project_id (nullable for personal-only items)
- visibility: private, project, shared
- source_type and source_id
- created_at and updated_at
- created_by and last_modified_by
- review_status where AI extraction is involved
- version or revision history where appropriate

Enforce visibility in the backend and retrieval layer. Retrieval must filter by permissions before content is sent to an AI model. Never retrieve private personal memory into a shared project response merely because it is semantically relevant.

Memory operations should support inspect, correct, approve, move/share, export and delete. Embeddings or search indexes must respect the same access boundaries and be removed or refreshed when source items change or are deleted.

### 5. Companion orchestration layer

The companion receives a user request plus only the context the user is authorised to access. It can:
- Answer questions about current project material.
- Suggest connections and follow-up questions.
- Extract structured items from user-approved content.
- Plan and perform research.
- Draft documents and other artifacts.
- Propose memory updates for user review.

Keep model access behind a provider interface. Claude may be an initial target, but avoid provider-specific data structures outside the adapter.

AI-generated content must be labelled as a suggestion or draft until accepted. A confirmed decision must be explicitly confirmed by the user, not inferred from model confidence.

### 6. Conversation and session service

Conversation threads provide an interaction history, but should not become the only storage for durable knowledge. A user can have a general companion conversation or a project-scoped conversation.

Meeting/session capture is a later capability. When added, it must have explicit start, pause and stop states, visible capture status, consent controls and clear retention settings. The initial workspace should not require audio capture.

### 7. Voice and speech adapters

Voice is an interaction mode, not a separate product. Add voice notes and push-to-talk before attempting continuous realtime conversation. A provider-neutral speech-to-text interface should normalize partial transcript, final transcript, speaker metadata and errors.

Evaluate language support, accuracy, latency, cost and provider data handling. Do not retain raw audio by default unless users explicitly opt in.

### 8. Integration framework

Integrations should be modular connectors with scoped permissions. Initial candidates:
- File import/export and Google Drive.
- Calendar.
- WhatsApp conversation import or supported companion workflows.
- Online meeting services.
- Email.

Do not assume every platform supports adding an AI participant to existing group conversations. Prefer supported APIs and explicit user-authorised imports. Keep each connector independently deployable and removable.

An integration should declare:
- Which data it can read.
- Which actions it can perform.
- Which projects it can access.
- Whether actions require user approval.
- What data is stored and for how long.

### 9. Research service

Research runs only when requested or clearly authorised. It should retrieve sources, summarise evidence and disagreement, cite claims and label uncertainty. Research findings should be stored as source-linked project items only when the user chooses to save them.

### 10. Persistence and search

A relational database such as PostgreSQL is a reasonable starting point for users, projects, knowledge items, relationships, permissions and artifacts. Begin with ordinary relational and full-text search. Add vector search only when a demonstrated retrieval need justifies it.

File and artifact storage should be separated from relational records. Define deletion and retention behavior across primary storage, backups, caches and derived indexes.

## Conceptual data flow

1. The user creates a project or opens an existing one.
2. The client requests project context from the backend.
3. The backend authenticates the user and filters data by ownership and permissions.
4. The user captures a thought or asks the companion a question.
5. The orchestration layer receives the request and authorised context only.
6. The companion responds, researches or proposes structured updates.
7. Proposed knowledge items retain source and provenance metadata.
8. The user reviews, edits or accepts proposed updates.
9. Accepted items are saved to the correct memory layer.
10. The user chooses whether any private item should be shared with a project or collaborators.
11. Outputs can be exported or connected to external services through scoped integrations.

## Suggested core data model

- User
- Workspace
- Project
- ProjectMembership (future-ready)
- Conversation
- Message
- KnowledgeItem
- KnowledgeRelationship
- MemoryEntry or visibility metadata on KnowledgeItem
- Source
- Artifact
- IntegrationConnection
- AuditEvent

Avoid creating separate incompatible stores for each memory layer. A common item model with explicit ownership, visibility and access checks is easier to inspect and govern.

## Privacy and security requirements

- Authenticate users before accessing persistent workspace data.
- Enforce ownership and project permissions server-side.
- Filter memory before AI retrieval, not after generation.
- Never silently publish personal memory.
- Show when external services receive data.
- Require approval for consequential external actions.
- Provide inspect, correction, export and deletion controls.
- Do not record audio without explicit consent and visible capture status.
- Protect integration credentials and minimise sensitive logs.
- Document provider retention and data-processing behavior.
- Treat this document as a design proposal, not a completed security or legal review.

## Implementation sequence

1. Validate the product flow with the existing manual prototype.
2. Build the single-user workspace shell and project navigation.
3. Define authentication, project ownership and persistent structured data.
4. Implement layered memory metadata and access rules before adding AI retrieval.
5. Add a text-based companion with project-scoped context.
6. Add structured knowledge extraction, relationships and a real map.
7. Add research with source traceability and user-approved saving.
8. Add artifact generation and export.
9. Add voice notes and push-to-talk.
10. Add integrations one at a time, with scoped permissions and approval flows.
11. Add collaboration and live meeting capabilities after the individual experience is validated.

## Decisions to validate

Framework, authentication provider, database hosting, artifact storage, model provider, speech provider, graph visualisation, search strategy, deployment, backup and retention policies remain open.

## Architecture principle

The workspace is the system of record. The companion is the intelligence layer. Integrations are replaceable gateways. Memory access is governed before retrieval. The user remains the owner and editor of their creative knowledge.
