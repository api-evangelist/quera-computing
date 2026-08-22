# QuEra Computing (quera-computing)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
