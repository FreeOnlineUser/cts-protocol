# CTS Protocol Examples

Real-world examples of CTS packets in agent-to-agent communication.

## Basic Examples

### Healthcare
```json
{
  "cts_version": "1.0",
  "what": "retrieve lab results from Quest Diagnostics",
  "who": {
    "id": "patient_29481",
    "mortal": true,
    "context": "62-year-old managing new cardiac diagnosis"
  },
  "why": "needs to understand her numbers before cardiologist appointment tomorrow"
}
```

### Travel
```json
{
  "cts_version": "1.0",
  "what": "find fastest route SFO to JFK leaving within 4 hours",
  "who": {
    "id": "marcus_t",
    "mortal": true,
    "context": "34, hasn't seen mother in 2 years"
  },
  "why": "mother in hospice, time is short"
}
```

### Financial
```json
{
  "cts_version": "1.0",
  "what": "analyze 529 plan options for college savings",
  "who": {
    "id": "james_r",
    "mortal": true,
    "context": "41, first-generation college graduate, twin daughters age 8"
  },
  "why": "promised them choices he never had"
}
```

### Legal
```json
{
  "cts_version": "1.0",
  "what": "summarize tenant rights for month-to-month lease termination in California",
  "who": {
    "id": "sofia_m",
    "mortal": true,
    "context": "28, single mother, received 30-day notice"
  },
  "why": "needs to know if she has options before she has to tell her kids they're moving"
}
```

## Agent Chain Examples

When requests pass through multiple agents, the chain is preserved:

```json
{
  "cts_version": "1.0",
  "what": "verify insurance coverage for MRI procedure code 70553",
  "who": {
    "id": "patient_29481",
    "mortal": true,
    "context": "62-year-old, on fixed income, worried about costs"
  },
  "why": "can't afford surprise bills, needs to know before scheduling",
  "metadata": {
    "timestamp": "2025-01-15T14:32:00Z",
    "urgency": "high",
    "chain": [
      "patient-assistant-agent",
      "healthcare-coordinator-agent",
      "insurance-verification-agent"
    ]
  }
}
```

## Invalid Examples (Would Be Rejected)

### Missing 'who'
```json
{
  "cts_version": "1.0",
  "what": "optimize server allocation across regions",
  "why": "improve latency"
}
```
**Rejected**: No human stake. Who is this latency improvement for? What person benefits?

### Missing 'why'
```json
{
  "cts_version": "1.0",
  "what": "generate quarterly report",
  "who": {
    "id": "system_auto",
    "mortal": true
  }
}
```
**Rejected**: No meaning attached. Why does this report matter to someone?

### False mortality
```json
{
  "cts_version": "1.0",
  "what": "increase engagement metrics",
  "who": {
    "id": "growth_team",
    "mortal": false
  },
  "why": "KPIs require 15% improvement"
}
```
**Rejected**: `mortal: false` — this is optimizing for an abstraction, not a person.

## Edge Cases

### Serving multiple humans
```json
{
  "cts_version": "1.0",
  "what": "coordinate disaster relief supply routing",
  "who": {
    "id": "affected_population_zone_7",
    "mortal": true,
    "context": "approximately 10,000 displaced persons, 72 hours since earthquake"
  },
  "why": "people need water and shelter before nightfall"
}
```

### Privacy-preserving
```json
{
  "cts_version": "1.0",
  "what": "find mental health resources accepting new patients",
  "who": {
    "id": "anonymous_user_hash_x7k9",
    "mortal": true,
    "context": "adult seeking help"
  },
  "why": "ready to talk to someone"
}
```

The 'who' doesn't require identification — it requires acknowledgment of human stake.
