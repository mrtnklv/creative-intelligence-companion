# Development Roadmap

## Status

The project has moved from documentation into its first interactive prototype. This roadmap is an evolving plan, not a delivery promise.

## Phase 0 — Project foundation
- [x] Create the public repository.
- [x] Add the initial README.
- [x] Document the product vision.
- [x] Document the proposed architecture.
- [x] Establish contribution and security guidance.
- [x] Choose and add the MIT license.
- [x] Define first-prototype acceptance criteria.

## Phase 1 — A working meeting-room prototype
Goal: demonstrate a clear session lifecycle and a useful structure for manually captured thoughts.
- [x] Create a minimal responsive web prototype.
- [x] Add a manual session lifecycle: start, pause, resume and end.
- [x] Add a clear pre-session confirmation.
- [x] Add visible session status and persistent pause/stop controls.
- [x] Capture ideas, questions, decisions, next steps and references.
- [x] Show a basic grouped view of the session's thinking.
- [x] Generate a simple live synthesis from captured items.
- [x] Save notes locally in the browser.
- [x] Export session notes as Markdown.
- [ ] Test the prototype with a real creative conversation and collect feedback.
- [ ] Refine the interaction based on that test.

Milestone: a group can use one device to manually capture and review the structure of a creative session.

## Phase 2 — A reliable meeting record
Goal: add audio capture and transcription only after the session and consent model is designed and tested.
- [ ] Define a participant-facing consent flow for every session.
- [ ] Document data retention and deletion behavior.
- [ ] Implement browser microphone permission handling and visible capture state.
- [ ] Define a provider-neutral speech-to-text interface.
- [ ] Integrate one speech-to-text provider.
- [ ] Display transcript segments with timestamps.
- [ ] Allow participants to correct transcript errors.
- [ ] Evaluate transcription accuracy in real rooms.

Milestone: participants can review and correct a consent-based session transcript.

## Phase 3 — The invited companion
Goal: the assistant responds only when explicitly called.
- [ ] Define the assistant interaction contract.
- [ ] Add text-based invocation as a reliable baseline.
- [ ] Add a provider adapter for the first language model.
- [ ] Ensure the assistant never responds unsolicited.
- [ ] Add concise responses, loading, error and cancellation states.
- [ ] Add voice invocation only after testing interaction methods.

Milestone: participants can ask the companion a question without it taking over the conversation.

## Phase 4 — Collective knowledge map
Goal: make discussion navigable beyond a linear transcript.
- [ ] Define typed knowledge items and relationships.
- [ ] Extract candidate items from transcript segments.
- [ ] Preserve links to source transcript segments.
- [ ] Distinguish participant statements from AI interpretations.
- [ ] Build an interactive graph view.
- [ ] Allow participants to edit, accept or remove proposed items.
- [ ] Represent relationships and unresolved questions.

Milestone: participants can inspect and refine an evolving representation of discussion.

## Phase 5 — On-demand research and continuity
Goal: help groups investigate questions and carry ideas into action.
- [ ] Add an explicit research request flow.
- [ ] Integrate a replaceable web research provider.
- [ ] Show concise answers with inspectable sources and uncertainty.
- [ ] Generate a draft end-of-session synthesis.
- [ ] Support assigning tasks and recording responsibilities.
- [ ] Carry approved project context into a later session.
- [ ] Evaluate multi-user collaboration and online meeting integrations.

Milestone: a meeting produces a useful, human-reviewed record and a clear continuation plan.

## Working method
- Build in small, demonstrable increments.
- Keep the repository usable and documented.
- Record significant technical decisions.
- Test with real conversations early.
- Treat privacy and consent as product requirements, not polish.
- Avoid premature integrations and infrastructure.
