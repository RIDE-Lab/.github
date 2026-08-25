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

Active incubation lines remain anonymous while their repositories and papers
are private. RIDE Lab publishes a project name, owner, repository link, and
evidence summary only after the project reaches its explicit release gate.

## Decision Domains

- **Workflow and SLO:** DAG scheduling, admission, deadlines, fairness, and
  capacity allocation.
- **Routing and placement:** backend, replica, cache-holder, model, and
  continuation placement.
- **State and KV:** reuse prediction, materialization, recomputation, tiering,
  recovery, and lifecycle control.
- **Quality and economics:** quality bounds, token budgets, service risk, cost,
  and safe fallback.

## Evidence Contract

Every research line must connect observable state to an action, correctness
oracle, matched comparison, and stopping condition. Smoke tests, simulations,
replays, projected profiles, and dry runs are labeled as such and are never
reported as real online effects. Negative results close mechanisms, not
automatically the underlying systems question.

## Incubation and Graduation

Projects may begin in private incubation, move to
[IntelliStream](https://github.com/intellistream) for a second incubation
stage, and graduate to the organization that best matches their mature
technical ownership. Public pages do not expose private incubation locations,
project identities, or repository links before release.

Graduation requires a stable abstraction, named maintainers, reproducible
evaluation, evidence-bounded claims, documentation, tests, licensing, and a
sustainable release path.

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
