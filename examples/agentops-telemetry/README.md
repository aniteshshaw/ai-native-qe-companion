# AgentOps Telemetry: Example Assets

Companion to the chapters *Workflow Hooks, the Nervous System*, *Measuring Adoption Without Fooling Yourself*, *Governing AI Quality Systems*, and *The AI-Native QE Platform*.

The printed book keeps the durable architecture: why an agent is an event stream, the lifecycle moments, correlation, de-duplication, the privacy boundary, metric definitions, the hook performance budget, failure behavior, schema evolution, and the scaling decisions. This folder holds the parts that are implementation rather than principle, and that change with the runtime and the tools.

## What is here

- `schema/agent-event.schema.json`: the privacy-safe event shape, as a schema.
- `schema/error-categories.yaml`: a governed, versioned list of error categories, so raw provider errors are never stored as they come.
- `schema/metric-dictionary.yaml`: one worked metric definition and the list of metrics that need an exact definition before they reach a dashboard.
- `fixtures/`: small, **synthetic, illustrative** event samples for testing a parser.
- `tests/README.md`: the scenarios to cover (correlation, privacy, parser, performance and failure), as checklists.

## What is deliberately not here

The full lifecycle hook scripts, the installer and uninstaller, the CSV parser implementation, the dashboard, runtime-specific hook and event names, exact product paths, and product screenshots are specific to one runtime and one organization. They belong in your own implementation, versioned and owned there. Everything in this folder is generic and illustrative; replace it with your own.

## A rule that does not move

Removing prompt text does not make telemetry anonymous, and a convenient installer must not become invisible instrumentation. Tell users what is collected, collect metadata and not content, and classify each hook's failure behavior before you ship it.
