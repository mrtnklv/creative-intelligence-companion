# Security Policy

## Project status
This is an early-stage project and is not yet suitable for handling sensitive or confidential meetings in production. Security controls and operational procedures are still being designed.

## Reporting a vulnerability
Please do not publish exploitable vulnerability details in a public issue.

Until a dedicated private reporting process is established, contact the repository owner through GitHub's private contact options. Include:
- A clear description of the affected component.
- Steps to reproduce the issue.
- Potential impact.
- Any suggested mitigation.

Please allow time for investigation before publicly disclosing a vulnerability.

## Current security priorities
- Explicit consent before audio capture.
- Clear indication whenever capture is active.
- Reliable pause and stop controls enforced by the application.
- Secure handling of authentication credentials and provider API keys.
- Access controls for projects and sessions before multi-user release.
- Encryption in transit and appropriate protection at rest.
- Minimal collection and retention of audio and transcript data.
- Safe handling of external research content and links.
- Separation of participant statements and AI-generated interpretations.
- Clear deletion behavior for sessions and associated data.

## Data and recordings
Do not use this prototype to record people without their knowledge and consent. Do not commit audio, transcripts, API keys, access tokens or other private information to the repository.

Before a public production release, the project needs documented retention defaults, deletion workflows, provider data-handling disclosures and a security review.

## Supported versions
No production version is currently designated as security-supported. This policy will be updated as releases and deployment practices mature.
