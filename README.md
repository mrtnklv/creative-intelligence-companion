# The Creative Intelligence Companion

An independent creative workspace for individual thinkers, makers and creators — with an AI companion that helps capture, connect, research and develop ideas.

**Humans create. AI assists. Ideas move forward.**

## The idea

Creative work rarely happens in one meeting or one app. Ideas emerge while reading, making, talking, walking, researching and collaborating. Important context becomes scattered across notes, conversations, documents and people's memories.

The Creative Intelligence Companion is a personal creative workspace that brings this process together. It combines a visual project environment with an always-available conversational and voice-based AI companion. It helps an individual preserve their thinking, develop projects over time and selectively collaborate with others.

The workspace is the home of project knowledge. Integrations are ways to bring information and actions into it — not the place where the project itself lives.

## Product foundation

- **Individual-first:** useful to one person without requiring a team. Collaboration is optional and permission-based.
- **Hybrid interface:** visual workspace, chat and voice work together. Users can move between structured project views and natural conversation.
- **Layered memory:** personal memory, project memory and explicitly shared knowledge remain distinct, with clear ownership, permissions and provenance.
- **Human-directed:** the companion supports creative judgement; it does not replace it or make unapproved decisions.
- **Quiet by default:** no unsolicited interruptions or recording. Voice capture is explicitly started and visibly controlled.
- **Evidence-aware:** research distinguishes sources, facts, interpretations and uncertainty.
- **Open and modular:** AI, speech and external integrations should be replaceable.

## Core capabilities

1. **Projects:** organise goals, sessions, ideas, references, tasks and outputs in persistent project spaces.
2. **Creative thinking:** capture ideas and questions, explore relationships, and develop evolving mind maps.
3. **Living memory:** retrieve relevant personal and project context across sessions, with user control over what is retained and shared.
4. **Research:** investigate questions on demand and preserve source references in project context.
5. **Creation:** turn thinking into briefs, documents, presentations, plans and other deliverables.
6. **Integrations:** selectively connect conversations, files, calendars and meetings to the workspace.

## Memory and privacy model

- **Personal memory:** private preferences, working notes and context owned by an individual.
- **Project memory:** context associated with a project and accessible according to that project's permissions.
- **Shared knowledge:** items deliberately published or approved for collaborators.

Information must not silently move from a private layer into a shared one. Each memory item should retain its source, owner, visibility, creation time and review status. Users should be able to inspect, correct, move, export and delete information, subject to project permissions and retention rules.

## Current status

The repository includes an early, self-contained browser prototype in `prototype/index.html`. It demonstrates manual session capture, typed notes, a grouped view, a simple synthesis, local browser storage and Markdown export.

**This is not yet the independent workspace described above.** The prototype does not yet provide accounts, persistent cloud projects, layered memory, AI, audio capture, transcription, integrations, synchronisation or multi-user permissions. The next product step is to evolve the prototype into an individual-first workspace foundation.

## Documentation

- [Product vision](docs/PRODUCT_VISION.md)
- [Product specification](docs/PRODUCT_SPEC.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Roadmap](docs/ROADMAP.md)
- [Contributing](CONTRIBUTING.md)
- [Security](SECURITY.md)

## Privacy

Do not record people without their knowledge and consent. Audio capture, transcription, external AI processing, integrations and cloud storage must each have clear controls and documented data handling before they are enabled.

## License

This project is licensed under the [MIT License](LICENSE).
