# The Creative Intelligence Companion

An open-source, voice-first companion for creative meetings and collaborative research.

**Humans create. AI assists. Ideas move forward.**

## The idea

Creative conversations generate ideas, questions and decisions that are easy to lose. This project explores a quiet, on-demand AI companion that helps groups preserve their thinking, investigate questions when asked, and turn conversations into useful next steps.

## Core principles

- **Quiet by default:** the companion does not interrupt or initiate conversation.
- **Explicitly invited:** it responds when a participant addresses it.
- **Consent-led:** recording and transcription happen only in a clearly started session with participant consent.
- **Evidence-aware:** research answers should be concise and include sources.
- **Human-directed:** the tool supports group thinking; it does not make decisions for people.
- **Open and modular:** the project aims to support interchangeable AI and speech services.

## Current status

The repository now includes the first interactive browser prototype in `prototype/index.html`.

The prototype supports:
- Starting, pausing, resuming and ending a manual note-taking session.
- Capturing ideas, questions, decisions, next steps and references.
- Viewing a simple grouped connection map and live session synthesis.
- Saving notes locally in the current browser.
- Exporting session notes as Markdown.

**Important limitations:** this is an early UX prototype. It does not access the microphone, record audio, transcribe speech, call an AI model, perform web research, synchronize across devices or support multiple participants. Do not treat its session-start confirmation as consent to audio recording; no audio is captured.

## Try the prototype

Open [the prototype source](prototype/index.html) and use GitHub's **Raw** view or download the file to run it locally in a modern browser. It is a self-contained HTML file and does not require a build step or external dependencies.

## Documentation

- [Product vision](docs/PRODUCT_VISION.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Roadmap](docs/ROADMAP.md)
- [Contributing](CONTRIBUTING.md)
- [Security](SECURITY.md)

## Privacy

The prototype stores manually entered notes in browser local storage on the device where it is used. It does not send those notes to a server. Clearing browser storage may remove them. Future audio capture, cloud storage and AI services will require separate, explicit privacy and retention decisions.

Do not record people without their knowledge and consent.

## License

This project is licensed under the [MIT License](LICENSE).
