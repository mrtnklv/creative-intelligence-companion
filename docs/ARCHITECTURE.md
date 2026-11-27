# Initial Technical Architecture

## Status
This is a proposed architecture for exploration, not a commitment to a particular framework, vendor or deployment model. Technical choices should be validated through a small prototype.

## Goals
- Keep the product modular and maintainable.
- Separate audio capture, transcription, conversation structure, research and user interface.
- Support interchangeable AI model and speech service providers.
- Make consent and session state explicit throughout the system.
- Keep live interaction responsive while allowing deeper processing asynchronously.
- Make data ownership, retention and deletion understandable.
- Prefer a small, testable first release over premature infrastructure.

## Proposed components

### Web client
A responsive web application for laptop and tablet use. Responsibilities include project and session creation, consent and recording-state display, microphone controls, transcript review, assistant invocation, evolving knowledge map, synthesis and project history.

A React-based application is a reasonable starting point. Next.js is one option, not a requirement.

### Application API
A backend for authentication, projects, sessions, permissions and orchestration. Python with FastAPI is a candidate because of its audio and AI ecosystem. A TypeScript backend may be preferable if it simplifies implementation.

### Realtime session service
Manages the active session and streams events between client and backend. Responsibilities include session lifecycle, audio stream handling, transcript events, explicit assistant invocation and pause/resume/stop behavior. WebSockets are one possible transport.

### Speech processing adapter
A provider-neutral interface for speech-to-text. Normalize provider responses into internal events such as transcript partial, transcript final, speaker detected and transcription error. Evaluate accuracy, language support, latency, cost, data handling and retention before selecting a provider.

### AI orchestration layer
Coordinates model calls for extracting ideas, questions, themes and decisions; updating the meeting structure; responding to explicit requests; planning research; and producing synthesis.

Keep model access behind a provider interface. Claude may be an initial target, but the application should not depend on provider-specific data structures or features unless isolated behind an adapter.

Preserve provenance: whether information came from a participant, transcript, AI inference or external source.

### Research service
Runs only when explicitly requested or authorized. It should turn a question into a focused search, retrieve sources, summarize evidence and disagreements, return citations and clearly label uncertainty. Search providers should be replaceable.

### Knowledge structure
Represent a meeting as linked, typed objects rather than one unstructured summary.

Initial object types:
- Idea
- Question
- Theme
- Decision
- Task
- Reference
- Person
- Session
- Research finding

Possible relationships include relates to, supports, challenges, answers, derived from, assigned to and decided in.

Each extracted item should link to the relevant transcript segment or source where possible. React Flow is one candidate for the interactive map visualization.

### Persistence
PostgreSQL is a reasonable initial choice for projects, sessions, users, structured items and relationships.

Treat audio storage separately from transcript and project data. Define retention and deletion behavior before enabling persistent audio storage. Avoid retaining raw audio by default unless users explicitly choose it and understand the implications.

## Conceptual data flow
1. A participant creates a session.
2. The client displays consent and capture state.
3. Capture begins only after explicit confirmation.
4. Audio is streamed to the speech adapter while the session is active.
5. Transcript events are delivered to the client and stored according to retention settings.
6. Structured extraction proposes ideas, questions, themes and decisions with transcript references.
7. The knowledge structure is updated and shown to participants.
8. A participant explicitly invokes the assistant.
9. The orchestration layer handles the request and calls research when needed.
10. The response is returned with sources where applicable.
11. At session end, synthesis generates a draft for human review.
12. Participants can correct, accept, export or delete session outputs.

## Session state
A minimal lifecycle:
- created
- awaiting consent
- active
- paused
- processing
- completed
- cancelled

The server must enforce state transitions. A client-side visual indicator alone is not sufficient to guarantee capture has stopped.

## Event model
Use typed, versioned events so components can evolve independently. Candidate events:
- session.created
- session.consent.confirmed
- session.started
- session.paused
- session.resumed
- session.stopped
- audio.chunk.received
- transcript.partial
- transcript.final
- knowledge.item.proposed
- knowledge.item.updated
- assistant.invoked
- assistant.response.completed
- research.started
- research.source.added
- research.completed
- session.synthesis.ready

Events should include identifiers and timestamps. Avoid unnecessary personal data in logs.

## Privacy and security requirements
- No recording before explicit session start and consent.
- Clear, persistent indication while capture is active.
- Obvious pause and stop controls.
- No unsolicited assistant speech.
- Authentication and project-level access controls before multi-user deployment.
- Secure transport and protected credentials.
- Defined data retention and deletion policies.
- Avoid logging raw audio, secrets or sensitive transcript content unnecessarily.
- Document external providers and their data-processing behavior.
- Allow correction or deletion of inaccurate AI-generated items.

This is not a completed security review or legal compliance assessment.

## Suggested implementation sequence
1. Build a static web shell and project/session model.
2. Implement session lifecycle and visible consent/capture controls.
3. Add audio capture and one speech-to-text adapter.
4. Display and store transcript segments.
5. Add explicit assistant invocation with text first, then voice.
6. Add structured extraction and transcript-linked knowledge items.
7. Add on-demand research with source references.
8. Add end-of-session synthesis and human correction.
9. Evaluate deployment, authentication, retention and online meeting integrations.

## Decisions to validate
Frameworks, realtime transport, audio format, speech provider, model abstraction, database schema, graph representation, audio retention, authentication, hosting costs and deployment model all remain open.

## Architecture principle
Choose the simplest implementation that proves the intended experience. Keep provider-specific code at the edges, preserve source provenance, and make session state and consent enforceable rather than merely visual.
