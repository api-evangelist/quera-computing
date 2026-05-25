# QuEra Computing (quera-computing)

QuEra Computing is a Boston-based neutral-atom quantum computing company (founded 2018) that operates Aquila, a 256-qubit Analog Hamiltonian Simulation QPU available publicly through Amazon Braket, and Gemini-class, a 260-qubit gate-model neutral-atom system used for fault-tolerant logical-qubit research with Harvard and MIT. QuEra has no native public REST API; developers submit programs to Aquila through the AWS Braket task API using QuEra's Bloqade SDKs (bloqade-analog for Python hardware submission, Bloqade.jl for Julia emulation, bloqade-circuit for gate-model programs), built on the Kirin compiler IR. Additional open-source tools include tsim (QEC circuit sampling), bloqade-shuttle, bloqade-lanes, and bloqade-decoders for the Dynamic Qubit Array compilation stack.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/quera-computing/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- Quantum Computing, Neutral Atom, Analog Hamiltonian Simulation, AWS Braket, Aquila, Gemini, Fault Tolerance, Quantum Error Correction, Bloqade, Hardware

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Hardware

| System | Type | Qubits | Access | Notes |
|---|---|---|---|---|
| Aquila | Analog Hamiltonian Simulation (neutral atom) | 256 | AWS Braket (us-east-1) | ARN `arn:aws:braket:us-east-1::device/qpu/quera/Aquila`, $0.30/task + $0.01/shot |
| Gemini-class | Gate-model (neutral atom, DQA shuttling) | 260 (Rb-87) | Pilot/Premium engagement | 1Q 99.9% / 2Q 99.2% reported fidelity; magic-state distillation demonstrated |

## APIs

### QuEra Aquila on AWS Braket
QuEra's flagship 256-qubit neutral-atom Analog Hamiltonian Simulation QPU. Programs are submitted through Amazon Braket, not a QuEra-owned endpoint.

**Human URL:** [https://www.quera.com/aquila](https://www.quera.com/aquila)

- [Aquila product page](https://www.quera.com/aquila)
- [AWS Braket device documentation](https://docs.aws.amazon.com/braket/latest/developerguide/braket-devices.html)
- [QuEra Braket Examples](https://github.com/QuEraComputing/QuEra-braket-examples)
- [quera-ahs-utils (helper Python package)](https://github.com/QuEraComputing/quera-ahs-utils)

### QuEra Gemini Neutral-Atom Quantum Computer
Gate-model neutral-atom system with Dynamic Qubit Array (DQA) shuttling, all-to-all connectivity, and reported fidelities of 99.9% (1Q global), 99.2% (2Q). Access is via pilot collaboration rather than a self-service API.

**Human URL:** [https://www.quera.com/gemini](https://www.quera.com/gemini)

### Bloqade Analog Python SDK
`pip install bloqade-analog` — hardware-first Python SDK for writing AHS programs and submitting them to Aquila on AWS Braket via `.braket.aquila().run_async()`.

**Human URL:** [https://bloqade.quera.com/](https://bloqade.quera.com/)

- [GitHub](https://github.com/QuEraComputing/bloqade-analog)
- [PyPI: bloqade-analog](https://pypi.org/project/bloqade-analog/)
- [Examples](https://github.com/QuEraComputing/bloqade-analog-examples)

### Bloqade Circuit Python SDK
Gate-model eDSL component of the Bloqade family. Built on Bloqade Core (Apache-2.0) and integrates with the Kirin compiler IR. Targets gate-model neutral-atom hardware like Gemini.

**Human URL:** [https://github.com/QuEraComputing/bloqade-circuit](https://github.com/QuEraComputing/bloqade-circuit)

### Bloqade.jl Julia SDK
Emulation-first Julia package for analog quantum simulation on neutral-atom architectures. CPU and GPU backends.

**Human URL:** [https://github.com/QuEraComputing/Bloqade.jl](https://github.com/QuEraComputing/Bloqade.jl)

### Kirin Kernel IR Infrastructure
Python compiler framework providing the typed intermediate representation that underpins Bloqade Core and Bloqade Circuit. Pluggable dialects, analyses, and rewrites.

**Human URL:** [https://github.com/QuEraComputing/kirin](https://github.com/QuEraComputing/kirin)

### tsim Universal QEC Simulator
Fast universal ZX stabilizer-rank quantum circuit sampler for quantum error correction research. Released April 2026.

**Human URL:** [https://github.com/QuEraComputing/tsim](https://github.com/QuEraComputing/tsim)

### Bloqade Shuttle / Lanes / Decoders
Compilation surface for QuEra's Dynamic Qubit Array hardware model — explicit atom-movement simulation (Shuttle), fixed-lane shuttle compilation (Lanes), and open-source QEC decoder integration (Decoders).

- [bloqade-shuttle](https://github.com/QuEraComputing/bloqade-shuttle)
- [bloqade-lanes](https://github.com/QuEraComputing/bloqade-lanes)
- [bloqade-decoders](https://github.com/QuEraComputing/bloqade-decoders)

## Common Properties

- [Portal](https://www.quera.com/)
- [Bloqade Documentation](https://bloqade.quera.com/)
- [GitHub Organization](https://github.com/QuEraComputing)
- [LinkedIn](https://www.linkedin.com/company/quera-computing-inc)
- [AWS Braket Pricing](https://aws.amazon.com/braket/pricing/) (includes Aquila per-task / per-shot rates)
- [QuEra Braket Examples (Getting Started)](https://github.com/QuEraComputing/QuEra-braket-examples)
- [Contact](https://www.quera.com/contact)
- [News](https://www.quera.com/news)

## Notes on Tier

QuEra is profiled as **Tier-3**: there is no QuEra-operated REST API, no QuEra-published OpenAPI spec, and no QuEra cloud authentication surface of its own. Programmatic access to Aquila is mediated by the AWS Braket task API, and the developer experience is delivered through QuEra's open-source SDKs (Bloqade family on Python and Julia, plus the Kirin compiler IR). Gemini-class access is gated behind pilot engagements and is not self-service.

## Maintainer

- Kin Lane / API Evangelist — [apievangelist.com](https://apievangelist.com)
