# UX Direction — Hybrid Creative Workspace

## Design decision

The Creative Intelligence Companion uses a hybrid interface: a structured digital notebook and an open visual studio are two complementary views of the same project knowledge.

The visual studio is the product's distinctive creative surface. The notebook provides structure, precision and reliable navigation. Neither view owns a separate copy of the content.

## Experience principles

1. **One project, multiple views.** A note created in notebook view can appear as a card on the studio canvas. Editing it in either place updates the same underlying item.
2. **Structure without rigidity.** Users can organise work into projects and typed items without being forced into a predefined methodology.
3. **Visual thinking is first-class.** Connections, spatial arrangement, clusters and open questions are meaningful parts of the work, not decorative diagrams.
4. **The companion is contextual.** It understands the selected project, item or canvas selection and makes its active context visible.
5. **The user remains in control.** AI-generated cards, links, summaries and edits are proposals until accepted.
6. **Private by default.** Visual placement does not change an item's visibility or memory layer.
7. **Progressive complexity.** A new user can capture a thought immediately; advanced mapping and project structures can emerge gradually.

## Primary application shell

### Persistent navigation
- Workspace home.
- Projects.
- Quick capture / inbox.
- Search.
- Memory and privacy controls.
- Settings and integrations.

### Project header
- Project title and intention.
- Current view selector: Overview, Notebook, Studio, Activity.
- Project search.
- Companion context indicator.
- Project sharing and permissions, when collaboration is enabled.

### Main content area
The main content changes according to the selected view while preserving the same project identity and data.

### Companion panel
A collapsible side panel available throughout the workspace. It supports:
- Ask: questions about the selected project or item.
- Explore: brainstorm, challenge assumptions and find connections.
- Research: investigate a question and return sources.
- Create: draft a brief, outline, presentation or plan.
- Organise: propose tags, links, summaries or task extraction.

The panel should show its context (for example, current project, selected items and memory layer). Users can change context before sending a request.

## The four primary project views

### 1. Overview
A calm project landing page with:
- Project intention and status.
- Recent activity.
- Pinned ideas and open questions.
- Next actions.
- Recent artifacts and research.
- A clear entry point to continue with the companion.

### 2. Notebook
A structured, searchable view for:
- Notes and ideas.
- Questions.
- References and research findings.
- Decisions and tasks.
- Documents and artifacts.

The notebook should support fast capture, filtering, editing and predictable navigation. It is the reliable source-oriented view.

### 3. Studio
An open canvas for:
- Idea cards and notes.
- Images and reference cards.
- Questions and hypotheses.
- Clusters and thematic groups.
- Explicit relationships and directional links.
- AI-proposed connections, visibly distinguished from user-created ones.

Users can move, group, connect and annotate items. Canvas position is presentation/layout metadata; it must not alter the underlying content or visibility permissions.

### 4. Activity
A chronological history of project changes:
- Items created or edited.
- Research performed.
- AI proposals accepted or rejected.
- Decisions confirmed.
- Artifacts generated.
- Sharing and permission changes.

Activity helps the user understand how the project evolved and where information came from.

## Quick capture

Capture must be available from anywhere in the workspace. Initial methods:
- Text entry.
- Pasted material or links.
- File upload.
- Voice note as a later increment.

A capture can enter an inbox when the project is unknown. The user can assign it to a project later. The system may suggest a destination but must not silently move it.

## Companion interaction patterns

- **Ask:** answer using authorised project context.
- **Explore:** facilitate divergent thinking and offer alternative perspectives.
- **Research:** retrieve and cite external evidence.
- **Create:** produce editable drafts from selected context.
- **Organise:** suggest structure, links and next steps.

The companion should not speak or make unsolicited changes. Generated content should be previewed and reviewed before it becomes durable project knowledge.

## Visual language

The interface should feel like a thoughtful creative studio rather than a corporate task-management dashboard:
- Calm, spacious and focused.
- Clear typography and restrained visual hierarchy.
- Canvas space reserved for thinking, not dense widgets.
- Cards that are legible and easy to rearrange.
- Subtle distinction between user-authored, imported and AI-proposed content.
- Accessible contrast, keyboard navigation and responsive layouts.

Avoid visual effects that compete with the content. The workspace should support long periods of focused work.

## Responsive behavior

Desktop is the primary environment for complex canvas work. Tablet should support notebook use and moderate canvas interaction. Mobile should prioritise quick capture, reading, search and companion conversations; a full canvas editor is not required for the first release.

## First UX prototype acceptance criteria

- A user can create a project and understand its purpose.
- A user can add an idea in a few seconds.
- The same idea is visible in both Notebook and Studio views.
- The user can create a relationship between two items.
- The companion can be opened without leaving the current project.
- The companion visibly indicates which project and selected items are in context.
- A user can distinguish personal/private content from project content.
- An AI-proposed connection or edit is visibly a proposal and requires approval.
- The interface remains useful without an AI provider connected.

## Out of scope for the first UX prototype

- Real-time multi-user canvas collaboration.
- Infinite canvas performance at very large scale.
- Audio recording and live transcription.
- WhatsApp group participation.
- Autonomous background agents.
- Complex project-management workflows.

## Key design test

Give a person an unfinished idea and ask them to develop it over several sessions. Observe whether they can capture it quickly, find it later, explore connections visually, ask the companion for help and turn the result into a useful artifact without losing ownership of their thinking.
