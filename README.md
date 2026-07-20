# Mane Horizons

Small tools for people who are handing more and more of their work to agents.

Most of what goes wrong with an agent isn't the model. It's the configuration around it —
what the agent is allowed to assume, what it's allowed to call finished, what it never
bothered to look for. That's the thing I keep poking at here.

The distinction I keep coming back to is **gate vs. shape**. Prompting can shape behavior:
you nudge, and often it works. A gate doesn't care how the model feels about it. It checks
the ground truth and returns an exit code. Almost everything below is an attempt to move
something from the first column to the second.

I might be reading this wrong. But it's the version of the problem I can actually build against.

## Tools

| | What it does | Status |
|---|---|---|
| **[Cadence](https://github.com/manehorizons/cadence)** | DRAFT → BUILD → SETTLE verification loop with a refusal-to-settle primitive. An agent that writes the code, writes the tests, and runs the check can satisfy all three and still be wrong. Cadence is the part that won't sign off. | Released — MIT, [`@manehorizons/cadence-core`](https://www.npmjs.com/package/@manehorizons/cadence-core) |
| **Phenyx** | Behavior-aware codebase intelligence. Two planes: a deterministic symbol graph and a semantic concept graph, so a task doesn't need a full-repo scan to know its blast radius. | Testing |
| **Brainswarm** | Local-first multi-agent brainstorming cockpit. Everything stays on the machine. | Testing |
| **Déjà** | Reuse gate and oracle. LLMs reinvent your utilities constantly; asking them nicely not to (which I tried) doesn't hold. This one checks. | Testing |
| **[Necro](https://github.com/manehorizons/necro)** | Dead code forensics — confidence tiers and evidence chains rather than a verdict you have to take on faith. | Release — MIT, [`@manehorizons/necro`](https://www.npmjs.com/package/@manehorizons/necro) |

## A few things I've had to learn the hard way

- **Self-certification is the failure mode.** The agent
  genuinely believes it's done or maniputes the assertions so that it is and convinces the developer to push the changes.
- **Corpus before code.** Write the adversarial fixtures and run them against a real
  extractor before any implementation exists. Otherwise you build to the tests you imagined.

## Elsewhere

[manehorizons.com](https://manehorizons.com) · [thomas@manehorizons.com](mailto:thomas@manehorizons.com)

Everything here is a side project built around a day job. 
If something's useful to you, that's genuinely the best outcome. 
If something's wrong, I'd like to know.
