# Development Roadmap

## Status

The project has an early manual session prototype. The product direction is now individual-first, hybrid and based on layered memory. This roadmap prioritises a useful personal workspace before voice capture, integrations or collaboration.

This is an evolving plan, not a delivery promise.

## Phase 0 — Project foundation
- [x] Create the public repository.
- [x] Add README and product vision.
- [x] Document an initial technical architecture.
- [x] Establish contribution and security guidance.
- [x] Choose and add the MIT license.
- [x] Define initial prototype acceptance criteria.
- [x] Establish individual-first, hybrid-interface and layered-memory direction.
- [x] Add a product specification.

## Phase 1 — Manual interaction prototype
Goal: test how a person captures and develops ideas in a simple session.
- [x] Create a minimal responsive browser prototype.
- [x] Add manual session lifecycle: start, pause, resume and end.
- [x] Capture ideas, questions, decisions, next steps and references.
- [x] Show a basic grouped view of captured thinking.
- [x] Generate a simple synthesis.
- [x] Save notes locally in the browser.
- [x] Export session notes as Markdown.
- [ ] Test with a real individual creative workflow.
- [ ] Refine the interaction based on feedback.

Milestone: a person can capture, review and export thoughts without AI or cloud infrastructure.

## Phase 2 — Personal workspace foundation
Goal: turn the prototype into a persistent, individual-first workspace.
- [ ] Define the first information architecture and navigation.
- [ ] Build workspace home and project creation.
- [ ] Add project overview and project-specific sections.
- [ ] Add authentication and secure personal ownership.
- [ ] Define the relational data model for projects and knowledge items.
- [ ] Implement persistent storage and project history.
- [ ] Support creating, editing, searching and deleting ideas, questions, notes, references, decisions and tasks.
- [ ] Add artifact/file attachment and export basics.
- [ ] Define backup, export and deletion expectations.

Milestone: one person can manage multiple ongoing creative projects in one persistent workspace.

## Phase 3 — Layered memory and permissions
Goal: make memory useful without compromising privacy.
- [ ] Define personal, project and shared visibility semantics.
- [ ] Add ownership and visibility metadata to memory-bearing items.
- [ ] Enforce access control in backend queries and mutations.
- [ ] Build a memory review interface showing source and visibility.
- [ ] Allow correction, approval, export and deletion.
- [ ] Add explicit user-controlled promotion of an item from private to project/shared visibility.
- [ ] Add audit history for sharing and permission changes.
- [ ] Test that private memory never appears in shared project retrieval.

Milestone: users can understand and control what the system remembers and who can see it.

## Phase 4 — The hybrid companion
Goal: make the companion useful inside the workspace, starting with text.
- [ ] Build a contextual chat/companion panel.
- [ ] Add a provider-neutral model adapter.
- [ ] Support project-scoped questions and answers.
- [ ] Retrieve only authorised context from the correct memory layer.
- [ ] Clearly label AI suggestions and drafts.
- [ ] Allow users to accept, edit or reject proposed knowledge updates.
- [ ] Preserve provenance for generated and user-authored content.
- [ ] Add voice notes or push-to-talk after text interaction is reliable.

Milestone: the companion can help a user think through a project without losing the distinction between user knowledge and AI suggestions.

## Phase 5 — Knowledge maps and research
Goal: help users connect ideas and investigate open questions.
- [ ] Define typed knowledge relationships.
- [ ] Build a navigable visual knowledge map.
- [ ] Connect map nodes to source notes, conversations and references.
- [ ] Suggest relationships while clearly marking them as AI proposals.
- [ ] Add on-demand research with source citations.
- [ ] Save selected findings into the appropriate memory layer.
- [ ] Generate project summaries and identify unanswered questions.

Milestone: a user can explore a project's evolving knowledge and investigate questions with traceable evidence.

## Phase 6 — Creative production
Goal: turn accumulated thinking into useful work.
- [ ] Generate editable project briefs and research notes.
- [ ] Generate presentation outlines and slide content.
- [ ] Create project plans, task lists and experiment proposals.
- [ ] Maintain links between outputs and source material.
- [ ] Add export formats and user review before finalising outputs.

Milestone: the workspace helps move from exploration to tangible deliverables.

## Phase 7 — Integrations and collaboration
Goal: connect the independent workspace to the tools people already use.
- [ ] Define connector permissions and approval model.
- [ ] Add file import and selected cloud-drive integration.
- [ ] Add calendar integration.
- [ ] Evaluate supported WhatsApp import/companion workflows.
- [ ] Evaluate online meeting integrations.
- [ ] Add project invitations and roles.
- [ ] Support deliberately shared knowledge across collaborators.
- [ ] Test revocation, access changes and removal of connected accounts.

Milestone: a user can bring selected external context into a project and collaborate without giving integrations unrestricted access.

## Phase 8 — Voice-first sessions and advanced assistance
Goal: support invited live participation once the core workspace and privacy model are proven.
- [ ] Design explicit session consent and participant controls.
- [ ] Define audio and transcript retention behavior.
- [ ] Add microphone capture with visible active state and reliable pause/stop.
- [ ] Add a replaceable speech-to-text adapter.
- [ ] Display and correct transcript segments.
- [ ] Add explicit voice invocation and concise responses.
- [ ] Generate source-linked session synthesis.
- [ ] Evaluate multi-participant attribution and real-room performance.

Milestone: the companion can participate in a consent-based session without interrupting or taking ownership of the conversation.

## Working method

- Build the smallest useful increment and test it with real creative work.
- Validate the single-user experience before expanding collaboration.
- Treat privacy and memory permissions as foundational architecture.
- Do not add integrations simply because they are technically possible.
- Keep AI outputs reviewable and source-linked.
- Record major technical decisions and keep the repository documentation current.
