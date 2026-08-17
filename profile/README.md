# RIDE Lab

RIDE Lab builds agent-native systems on vLLM-HUST. SAGE is the lab's flagship
open-source product for programming and orchestrating those systems.

Our research spans agent programming and orchestration, tool use, RAG, memory,
evaluation, application-level state, real workloads, and reproducible end-to-end
benchmarks. RIDE is the lab identity, not an additional runtime layer: products and
research projects call vLLM-HUST directly or through SAGE.

SAGE product website: [sage.org.ai](https://sage.org.ai/)

## System Boundary

```text
Sage Mate and other applications
              |
              v
        SAGE and research systems
              |
              v
          vLLM-HUST
```

RIDE repositories own caller-side agent systems, policies, workloads, and evaluations.
Model execution, KV-cache implementation, decode scheduling, kernels, compilation, and
hardware backends remain in [vLLM-HUST](https://github.com/vllm-hust).

## Ecosystem

- [IntelliStream](https://github.com/intellistream) incubates early research ideas across the ecosystem.
- **RIDE Lab** conducts agent-native systems research and turns mature results into open-source products.
- **SAGE** is RIDE Lab's flagship product for agent programming, RAG, workflow, evaluation, and service orchestration.
- [DataSys](https://github.com/DataSysResearch) provides framework-neutral stream, graph, vector, index, update, query, and benchmark infrastructure.
- [vLLM-HUST](https://github.com/vllm-hust) develops model execution, KV/cache scheduling, compilation, kernels, and hardware acceleration.

## Products

### SAGE

- [SAGE](https://github.com/RIDE-Lab/SAGE) - RIDE Lab's agent programming and orchestration product.
- [SAGE Docs](https://github.com/RIDE-Lab/SAGE-Docs) - product documentation and the source for [sage.org.ai](https://sage.org.ai/).
- [SAGE Agentic](https://github.com/RIDE-Lab/sage-agentic)
- [SAGE RAG](https://github.com/RIDE-Lab/sage-rag)
- [SAGE Eval](https://github.com/RIDE-Lab/sage-eval)
- [SAGE Studio](https://github.com/RIDE-Lab/sage-studio)
- [SAGE Tutorials](https://github.com/RIDE-Lab/sage-tutorials)

#### Product Modules and Integrations

- [SAGE Agent for VS Code](https://github.com/RIDE-Lab/sage-agent-vscode)
- [SAGE Agentic Tool Use](https://github.com/RIDE-Lab/sage-agentic-tooluse)
- [SAGE Examples](https://github.com/RIDE-Lab/sage-examples)
- [SAGE Finetune](https://github.com/RIDE-Lab/sage-finetune)
- [SAGE GitHub Manager](https://github.com/RIDE-Lab/sage-github-manager)
- [SAGE Intent Library](https://github.com/RIDE-Lab/sage-libs-intent)
- [SAGE Refiner](https://github.com/RIDE-Lab/sageRefiner)
- [SAGE PyPI](https://github.com/RIDE-Lab/sagepypi)
- [SAGE Wiki](https://github.com/RIDE-Lab/sage-wiki)

## Applications

- [Sage Mate](https://github.com/RIDE-Lab/sage-mate) - a continuously running agent application built with SAGE and backed by vLLM-HUST.

## Research Projects and Benchmarks

- [SAGE Benchmark](https://github.com/RIDE-Lab/sage-benchmark)
- [Agentic Tool-use Benchmark](https://github.com/RIDE-Lab/sage-agentic-tooluse-benchmark)
- [Agentic Tool-use SIAS](https://github.com/RIDE-Lab/sage-agentic-tooluse-sias)
- [RAG Benchmark](https://github.com/RIDE-Lab/sage-rag-benchmark)
- [Refiner Benchmark](https://github.com/RIDE-Lab/sage-refiner-benchmark)
- [Wiki-link Retrieval](https://github.com/RIDE-Lab/wiki-link-retrieval)
- [Neuromem Benchmark](https://github.com/RIDE-Lab/neuromem-bench)

### Achievements

- [Complete publication timeline](https://sage.org.ai/achievements/) - published
  work, public evidence, corresponding repositories, and explicitly labeled
  author-reported acceptances.
- [SAGE](https://openreview.net/forum?id=TXcFJdT7at) - ICML 2026
  dataflow-native framework for modular, controllable, and transparent
  LLM-augmented reasoning.
- [Neuromem](https://openreview.net/forum?id=mO7DgwFFVe) - ICML 2026
  benchmark and lifecycle decomposition for external memory in LLM systems.
- [FlowRAG](https://doi.org/10.1145/3774904.3792361) - WWW 2026 continual
  retriever adaptation for evolving corpora.
- [Demonstrating SAGE](https://sage.org.ai/achievements/) - ICPP 2026 demo
  acceptance reported by the authors; the public program or proceedings record
  is pending.

## Project Graduation

Projects graduate from IntelliStream when they have a clear public abstraction, named maintainers, reproducible evaluation, documentation, tests, licensing, and a sustainable release path.

RIDE Lab is not a data-engine or model-runtime umbrella. Framework-neutral data systems belong in DataSys, while model-runtime and hardware-execution projects belong in vLLM-HUST.

See our [contribution guide](https://github.com/RIDE-Lab/.github/blob/main/CONTRIBUTING.md), [security policy](https://github.com/RIDE-Lab/.github/blob/main/SECURITY.md), and [support guide](https://github.com/RIDE-Lab/.github/blob/main/SUPPORT.md).
