# Vision

The goal of this project is to create a hyper-modern, performant, and minimalist JavaScript Solid server. While drawing inspiration from Node Solid Server (NSS), this new implementation will address its shortcomings and prioritize scalability, modularity, and developer usability.

## Key Objectives

- **Performance First:** Capable of handling enterprise-scale loads, targeting thousands to millions of users.
- **Minimalist Design:** Remove unused and experimental features; focus on what matters most.
- **Modularity:** Clear separation of identity, authentication, storage, and onboarding.
- **Developer Friendly:** Clean, well-documented, and extensible codebase that adheres to the Solid specification.
- **Modern Tooling:** Leverage async/await, native modules, fast HTTP servers like Fastify, and cutting-edge JavaScript runtimes.
- **HTTP Simplicity:** Prioritize simple HTTP/1.1 compatibility for maximum interoperability.
- **Frontend Agnostic:** Work with any frontend or application layer via standardized APIs.
- **Testable and CI Ready:** Fully integrated with Solid test suites and modern CI/CD pipelines.

---

# ARCHITECTURE

## Overview
The architecture is inspired by NSS but modernized and streamlined. Each subsystem is designed to operate independently and follow the single-responsibility principle.

### Components

- **HTTP Layer**
  - Fastify server
  - Routing and middleware based on HTTP verbs and Solid operations
  - Blazingly fast, with benchmarks from the start

- **Identity Provider (IDP)**
  - Handles Pod based WebIDs
  - Handles external WebIDs
  - Minimal by default, extendable via plugins

- **Authenticaion Module (AUthn)**
  - Handles WebID-based authentication, including WebID-TLS
  - OIDC-compliant with modular Authentication
  - Single sign-on including WebID-TLS

- **Authorization Module (Authz)**
  - Supports Web Access Control (WAC)
  - Token-based permissions model
  - Modular Authorization system

- **Storage Engine**
  - Modular backend adapters (e.g. file system, S3, memory)
  - POD-level quota management (optional)
  - Interoperable with existing Cloud

- **Account and Onboarding**
  - API-first registration
  - Public, private, invite modes
  - Extensible account templates

### Deployment Model
- Works as a single binary or serverless function
- Container-friendly (Docker, Deno, etc.)
- CLI for local dev setup and testing

### Separation of Concerns
- Each subsystem lives in its own module/package
- Clear boundaries between IDP and storage
- Frontend-independent API endpoints

### Compatibility
- Solid-compliant, LWS Compliant
- API parity with NSS where applicable
- API parity with CSS where applicable

