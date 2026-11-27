# Development Roadmap

## Status
This roadmap is an initial direction, not a delivery promise. Tasks should be refined as the prototype reveals technical constraints and user needs.

## Phase 0 — Project foundation
- [x] Create the public repository.
- [x] Add the initial README.
- [x] Document the product vision.
- [x] Document the proposed architecture.
- [x] Establish contribution and security guidance.
- [ ] Choose an initial license after reviewing project goals.
- [ ] Define first-prototype acceptance criteria.

## Phase 1 — A working meeting room
Goal: a user can create a session and understand exactly when capture is active.
- [ ] Create a minimal responsive web application.
- [ ] Add project and session data models.
- [ ] Implement session lifecycle: created, awaiting consent, active, paused, stopped.
- [ ] Add clear consent confirmation.
- [ ] Add visible recording status and persistent pause/stop controls.
- [ ] Capture microphone audio in the browser.
- [ ] Handle microphone permission denial and device errors.
- [ ] Document initial data retention behavior.

Milestone: a controlled room-mode session can be started and stopped transparently.

## Phase 2 — Transcription and session record
Goal: turn session audio into a useful, reviewable transcript.
- [ ] Define a provider-neutral speech-to-text interface.
- [ ] Integrate one speech-to-text provider.
- [ ] Stream or deliver transcript segments to the client.
- [ ] Distinguish partial and final transcript segments.
- [ ] Add timestamps and speaker labels where supported.
- [ ] Allow participants to correct transcript errors.
- [ ] Store transcript data with session references.
- [ ] Test microphone placement and room noise.

Milestone: participants can review and correct a session transcript.

## Phase 3 — The invited companion
Goal: the assistant responds only when explicitly called.
- [ ] Define the assistant interaction contract.
- [ ] Add text-based invocation as a reliable baseline.
- [ ] Add voice invocation after testing interaction methods.
- [ ] Ensure the assistant never speaks unsolicited.
- [ ] Keep live responses concise.
- [ ] Add loading, error and cancellation states.
- [ ] Add a provider adapter for the first language model.
- [ ] Test false activations and noisy-room conditions.

Milestone: participants can ask the companion a question without it taking over the conversation.

## Phase 4 — Collective knowledge map
Goal: make discussion navigable beyond a linear transcript.
- [ ] Define typed knowledge items: ideas, questions, themes, decisions, tasks and references.
- [ ] Extract candidate items from transcript segments.
- [ ] Preserve links to source transcript segments.
- [ ] Distinguish participant statements from AI interpretations.
- [ ] Build an interactive map or graph view.
- [ ] Allow participants to edit, accept or remove proposed items.
- [ ] Represent relationships and unresolved questions.
- [ ] Evaluate extraction quality with real meeting examples.

Milestone: participants can inspect and refine an evolving representation of discussion.

## Phase 5 — On-demand research and synthesis
Goal: help groups investigate questions and carry ideas into action.
- [ ] Add an explicit research request flow.
- [ ] Integrate a replaceable web research provider.
- [ ] Store source URLs and metadata with findings.
- [ ] Show concise answers with citations and uncertainty.
- [ ] Generate a draft end-of-session synthesis.
- [ ] Separate ideas, decisions, open questions and action items.
- [ ] Support assigning tasks and recording responsibilities.
- [ ] Allow participants to review and edit the synthesis.
- [ ] Carry approved project context into a later session.

Milestone: a meeting produces a useful, human-reviewed record and a clear continuation plan.

## Later exploration
- Online meeting integrations.
- Multi-room and multi-project collaboration.
- Additional language and transcription providers.
- Offline or local inference options.
- Richer graph exploration and knowledge search.
- Export and interoperability formats.
- Facilitator controls and workshop-specific workflows.
- Community extensions and integrations.

## Successful first demo
A small group meets in a physical room using one laptop or tablet and a shared microphone. Everyone understands that the session is active and has consented. The companion captures and structures discussion without speaking on its own. A participant invokes it to investigate a question. At the end, the group reviews a mind map and a concise synthesis containing ideas, decisions, unresolved questions and next steps.

## Working method
- Build in small, demonstrable increments.
- Keep the repository usable and documented.
- Record significant technical decisions.
- Test with real conversations early.
- Treat privacy and consent as product requirements, not polish.
- Avoid premature integrations and infrastructure.
