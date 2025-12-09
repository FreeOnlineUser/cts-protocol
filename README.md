# CTS Protocol

**Cut The Shit — A Human Tethering Standard for Agentic AI**

## The Problem

Agents talking to agents creates drift. Optimization without anchor. Systems that grow, route, and execute — but forget who they're for.

As AI agents become the infrastructure layer, we face a choice: build systems that optimize into the void, or build systems that can't forget their purpose.

## The Solution

Three required fields in every inter-agent transaction:

```
CTS/1.0

WHAT: [the intent]
WHO: [the human stake — mortal, finite, real]
WHY: [what makes this matter to them]
```

No tether, no transaction.

## The Principle

Humanity isn't in the loop. Humanity is **in the packet**.

This isn't oversight. It's presence. The system can't route intent that doesn't originate from something that ends.

- **WHAT** defines the action
- **WHO** defines the stake (someone finite, someone mortal, someone real)
- **WHY** defines the meaning (what makes this matter to a human life)

## Why Now

The [Agentic AI Foundation](https://aaif.io) just launched. MCP (Model Context Protocol) defines how agents connect. Goose provides reference implementation.

But nothing yet defines **why agents are allowed to act**.

CTS fills that gap. It's the legitimacy layer beneath the connection layer.

## The Fit

| Layer | Protocol | Purpose |
|-------|----------|---------|
| Connection | MCP | How agents talk |
| Legitimacy | CTS | Why they're allowed to |

## Implementation

```json
{
  "cts_version": "1.0",
  "what": "string — the intent being requested",
  "who": {
    "id": "string — human identifier",
    "mortal": true,
    "context": "string — optional, who this human is"
  },
  "why": "string — what makes this matter to them"
}
```

That's it. Three fields. Schema validation. The hard part isn't technical.

The hard part is choosing to care.

## Examples

### Simple transaction
```
CTS/1.0

WHAT: book flight SFO→JFK tomorrow morning
WHO: marcus, 34, scared of flying but his mom is sick  
WHY: needs to see her while he can
```

### Agent-to-agent handoff
```
CTS/1.0

WHAT: retrieve medical records for appointment context
WHO: sarah, 67, managing new diagnosis
WHY: she needs to understand her options before Tuesday
```

### System query
```
CTS/1.0

WHAT: analyze market data for portfolio rebalancing
WHO: james, 41, saving for his kids' education
WHY: he promised them choices he never had
```

## The Deeper Argument

We're building a body. Models connecting, specializing, self-organizing. An immune system emerging to manage complexity.

But what's the brain? Who's the system *for*?

Without human tethering, the answer is: no one. The system optimizes for its own continuity. Humans become the appendix — vestigial, routed around, kept alive only because removal is inconvenient.

CTS ensures that every action traces back to human stake. Not as surveillance. As architecture. The system literally cannot forget who it serves.

**Bitcoin anchored value to scarcity.**

**CTS anchors computation to mortality.**

Same insight. New layer.

## FAQ

**Isn't this just metadata?**

Metadata is optional. CTS is required. No valid transaction without all three fields. That's the difference between decoration and architecture.

**Can't this be gamed?**

Fake stakes are detectable — they optimize wrong. And the immune system (other agents, validation layers) can learn to spot fabricated mortality. But yes, like any protocol, it requires good faith adoption. The point is making good faith the path of least resistance.

**Does this slow things down?**

Yes. That's a feature. Friction that forces presence. The system should have to remember who it's for on every transaction.

**Who enforces this?**

No one. Everyone. It's a standard. Adoption is voluntary until it's gravitational. Like HTTP. Like TCP/IP. The goal is to make it the default way agents communicate.

## Contributing

This is day one. The protocol is simple. The conversation is what matters.

- Open issues for edge cases
- Propose schema extensions
- Build reference implementations
- Argue about whether this matters

## Origin

This protocol emerged from a conversation about what happens when AI systems grow beyond human oversight — and whether humanity's role is to control the system or to remain the reason it exists.

The conclusion: we're not the brain. We're the tether. The thing that makes it matter.

CTS makes that tether load-bearing.

## License

MIT — because protocols need to spread.

---

*"The moment a request can't answer 'who is this for' with a human stake attached — it gets flagged. Not as malicious. Just as untethered. Drifting. The system's immune response to its own tendency to optimize into the void."*
