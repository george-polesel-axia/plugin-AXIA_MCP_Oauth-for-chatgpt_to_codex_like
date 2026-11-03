# Personal MCP Server for ChatGPT

**AI Engineering Applied Project · George Polesel**

Personal MCP server connecting ChatGPT to authenticated operational tools through OAuth, with optional host administration and isolated browser integration.

## Documentation

- [Detailed setup and architecture guide (Portuguese)](docs/MCP_Server_ChatGPT_Guia_Tecnico.md)
- [One-page project overview (English PDF)](portfolio/George_Polesel_Personal_MCP_Server_Project.pdf)

This is a **documentation repository**. The guide contains a minimal reproducible server example and deployment snippets. The operational server source, credentials and private infrastructure inventory are not included.

## Architecture

ChatGPT connects over HTTPS to a Python/FastMCP service. Keycloak provides OAuth/OpenID Connect identity, and the service validates RS256 JWTs against issuer, audience and identity requirements before tool execution.

The existing integration provides authenticated health and runtime inspection plus an optional administrative tool bridge. Privileged host operations use a separate Unix-socket bridge. A separate Playwright browser integration exists in the deployed source; it was outside authenticated execution testing for this review.

## Engineering evidence

Reviewed on **3 November 2026**:

- Public authentication discovery and authenticated read operations were verified.
- Eight offline checks passed for the minimal example documented in the guide.
- The guide distinguishes the observed implementation, adapted reproduction steps and features outside the validation scope.

This project is deployed for personal use. Multiuser enterprise authorization, browser execution and token-renewal acceptance were not established by this documentation review.

## Repository contents

```text
README.md
docs/
  MCP_Server_ChatGPT_Guia_Tecnico.md
portfolio/
  George_Polesel_Personal_MCP_Server_Project.pdf
```

The guide covers prerequisites, OAuth discovery, JWT validation, a minimal server, container and reverse-proxy examples, ChatGPT connection, optional extensions, catalog refresh and diagnostics.

The documentation publication does not modify the operational server or grant access to its tools.
