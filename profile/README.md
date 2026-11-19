# Isoloop

Event-loop isolation for JavaScript apps.

Isoloop brings an Erlang/OTP-style kernel to your app. Each part of it (a React
or Preact UI tree, plain DOM, or a headless background task) runs as an
*isolate*, on its own worker or in a shared pool, under a supervisor. When one
blocks or crashes, the rest of the app keeps running, and the supervisor
restarts it.

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

[Features](https://isoloop.dev/features/) · [How it works](https://isoloop.dev/how-it-works/) · [Examples](https://isoloop.dev/examples/)
