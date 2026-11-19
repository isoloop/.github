<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="mark-dark.svg">
    <img src="mark.svg" alt="" width="120">
  </picture>
</p>

<h1 align="center">Isoloop</h1>

<h3 align="center">Event-loop isolation for JavaScript apps</h3>

<p align="center">
  <a href="https://www.npmjs.com/org/isoloop"><img alt="npm: @isoloop" src="https://img.shields.io/badge/npm-%40isoloop-2f57cc?style=for-the-badge&logo=npm&logoColor=white"></a>
  <a href="https://github.com/isoloop/isoloop/blob/main/LICENSE"><img alt="MIT licence" src="https://img.shields.io/github/license/isoloop/isoloop?style=for-the-badge&color=6e46c2"></a>
  <img alt="Status: pre-release" src="https://img.shields.io/badge/status-pre--release-555?style=for-the-badge">
</p>

<p align="center">
  <a href="https://isoloop.dev">Website</a> •
  <a href="https://isoloop.dev/features/">Features</a> •
  <a href="https://isoloop.dev/how-it-works/">How it works</a> •
  <a href="https://isoloop.dev/examples/">Examples</a>
</p>

Isoloop is an open-source TypeScript library that brings an Erlang/OTP-style
kernel to your app. Each part of it (a React or Preact UI tree, plain DOM, or a
headless background task) runs as an *isolate*, on its own worker or in a shared
pool, under a supervisor. When one blocks or crashes, the rest of the app keeps
running, and the supervisor restarts it.

- **A message bus, not shared state.** Isolates talk over typed topics,
  validated with Standard Schema, each through its own channel. An isolate
  publishes and subscribes only to the topics it is granted.
- **Restart and catch up.** A restarted isolate rebuilds its state by replaying
  its topics from the records the bus keeps. Persistent topics go to a durable
  log, so they survive a reload.
- **Placement is a switch.** The same code runs one isolate per worker or many
  per pool. An experimental balancer moves isolates between pools by measured
  load.
- **Built for agents.** Typed tools on your contracts, a dev MCP server, a live
  inspection feed, and WebMCP support (experimental).

- [**isoloop**](https://github.com/isoloop/isoloop): the library, `@isoloop/*` on npm (prereleases under `next`)
- [**web**](https://github.com/isoloop/web): [isoloop.dev](https://isoloop.dev), the examples and the design system
