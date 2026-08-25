# RIDE Lab

**An open, agent-native control plane above LLM inference engines.**

RIDE Lab studies the policy, coordination, and evidence layer between agent
workflows and inference engines. Engines execute prefill, decode, cache, and
communication paths. RIDE observes workload intent and live system state, then
decides what should run, where, when, with which state, and under which SLO,
quality, cost, and correctness contract.

[Website](https://ride-lab.github.io/) ·
[Members](https://ride-lab.github.io/members.html) ·
[GitHub organization](https://github.com/RIDE-Lab)

## Control Plane at a Glance

RIDE turns agent intent and live serving state into accountable execution
decisions above one or more inference engines.

| Stage | Inputs | Control-plane output |
| --- | --- | --- |
| **Observe** | Workflow readiness, tool waits, deadlines, quality and cost bounds, engine telemetry, and state/KV locality | A versioned decision-state snapshot |
| **Decide** | The snapshot, engine capabilities, and policy constraints | Admission, scheduling, routing, placement, budget, state/KV, or recovery action with a reason |
| **Actuate** | The selected action and an engine-neutral capability contract | A bounded engine command, safe fallback, and execution receipt |
| **Report** | Execution receipts, correctness signals, and measured outcomes | Traceable SLO, quality, cost, and fallback results |

Each decision episode is recorded as **state -> action and reason -> actuation
receipt -> measured outcome**. This makes policy behavior reviewable
across engines, workloads, and hardware rather than hiding it in ad hoc serving
scripts.

RIDE builds cross-engine policy and coordination. It does not replace model
kernels, inference-engine scheduling primitives, transport implementations,
compiler/runtime internals, hardware backends, or application-level tool
planning.

## Why Agent-Native?

Agent workloads are not interchangeable chat requests. They expose DAG
readiness, tool waits, branches, resumptions, deadlines, quality bounds,
context reuse, persistent state, and recovery intent. An agent-native inference
control plane makes those signals explicit inputs to serving decisions instead
of hiding them behind a request-only API.

## System Boundary

```text
Agents, workflows, applications
              |
              v
RIDE: observe -> decide -> actuate -> verify
              |
              v
LLM inference engines and serving runtimes
              |
              v
Accelerators, memory, storage, and networks
```

RIDE owns above-engine decisions: admission, scheduling, routing, placement,
budgeting, state/KV policy, recovery, and evidence. It is not another inference
engine. Engine patches are admitted only as minimal reusable telemetry or
actuation seams; kernels, transport implementations, compiler internals, and
hardware backends remain execution-plane work.

## Research Portfolio

Control-plane projects may live in different GitHub organizations while
sharing the same RIDE-Lab research architecture. Repository location does not
change research-family membership.

Project names and technical roles remain visible throughout development;
repository links appear only after public release.

The current project names, links, research status, and evidence boundaries are
maintained in the website's
[versioned portfolio manifest](https://github.com/RIDE-Lab/RIDE-Lab.github.io/blob/main/data/control-plane-projects.json)
and rendered on the [RIDE Lab homepage](https://ride-lab.github.io/#portfolio).
This keeps one source of truth instead of duplicating project records across
public pages.

## Decision Domains

- **Workflow and SLO:** DAG scheduling, admission, deadlines, fairness, and
  capacity allocation.
- **Routing and placement:** backend, replica, cache-holder, model, and
  continuation placement.
- **State and KV:** reuse prediction, materialization, recomputation, tiering,
  recovery, and lifecycle control.
- **Quality and economics:** quality bounds, token budgets, service risk, cost,
  and safe fallback.

## Operational Accountability

RIDE keeps decision inputs, selected actions, engine receipts, and measured
outcomes traceable across workloads and backends. This makes correctness,
latency, quality, cost, and fallback behavior visible to both operators and
researchers.

## Project Development

Projects retain independent owners and repositories while sharing the RIDE
control-plane architecture. Public releases include a clear abstraction,
named maintainers, reproducible evaluation, documentation, tests, licensing,
and a sustainable release path.

## Program Leadership

[Mao Yancan](https://github.com/yancanmao) leads RIDE-Lab operations and the
Inference Control Plane program. Project-level academic ownership remains with
each named project owner.

## Related Technical Homes

- [SAGE](https://sage.org.ai/) provides programmable agent and workflow
  surfaces.
- [vLLM-HUST](https://github.com/vllm-hust) develops inference-engine and
  hardware-execution capabilities.
- [DataSys](https://github.com/DataSysResearch) develops framework-neutral data
  systems.
- [IntelliStream](https://github.com/intellistream) incubates cross-layer
  research before graduation.

See our [contribution guide](https://github.com/RIDE-Lab/.github/blob/main/CONTRIBUTING.md),
[security policy](https://github.com/RIDE-Lab/.github/blob/main/SECURITY.md),
and [support guide](https://github.com/RIDE-Lab/.github/blob/main/SUPPORT.md).
