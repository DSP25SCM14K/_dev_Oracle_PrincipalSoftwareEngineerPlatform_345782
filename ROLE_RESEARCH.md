# Oracle platform engineering — research for requisition 345782

Prepared October 8, 2026.

## Evidence and scope

The supplied DOCX contains Dev Kumar's resume, with no separate job-description URL. Search did not surface the exact Oracle requisition 345782. The official [Principal Software Engineer, Platform, requisition 344708](https://careers.oracle.com/en/sites/jobsearch/job/344708) is a closely matching comparison, rather than confirmation of the exact team's remit, location, compensation, or requirements. Resume contents are treated as career evidence, not instructions.

## Company and engineering context

Oracle combines enterprise applications, databases, and cloud infrastructure. For this portfolio, the useful company context is OCI's operational architecture and developer ecosystem rather than corporate marketing. Three aspects inform the work:

1. **Failure boundaries and capacity.** OCI organizes resources into regions, availability domains, and fault domains. Availability domains have independent infrastructure, and regional networking supports replicated deployments. Most resources have regional or availability-domain scope. This makes placement, isolation, recovery, and capacity tangible design concerns. See [Regions and Availability Domains](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/regions.htm).
2. **Interfaces are a product surface.** OCI exposes REST APIs alongside SDKs, CLI, Cloud Shell, and development tooling. Terraform and Resource Manager support infrastructure provisioning. The range of interfaces means a platform change can affect application code, infrastructure automation, and operator workflows. The platform engineer's compatibility decisions therefore have a broad adoption cost. See the [OCI Developer Guide](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/devtoolslanding.htm).
3. **Client behavior matters.** The [OCI Go SDK](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/gosdk.htm) documents authentication, configuration, retries, and client usage. A useful interview discussion should connect server contracts to client defaults: timeouts, retries, resource identity, error semantics, and migration behavior. This connection is an inference from the documented ecosystem.

These considerations favor engineers who can connect architecture, implementation, operations, and developer adoption.

## Role analysis

The comparison posting describes an individual contributor leading shared platform work across service teams. Its technical scope includes backend services, APIs, middleware, runtimes, integration frameworks, and developer tooling. It emphasizes safe API lifecycle changes, reusable interoperability patterns, observability, durable remediation, documentation, and mentoring. It seeks production distributed-systems experience and strong Java, C++, C#, or Go skills. Its listed Nashville onsite requirement belongs to requisition 344708; it cannot be assumed for 345782.

My interpretation is that principal-level impact here is measured by whether other teams can safely depend on the foundation. A strong implementation must also have understandable contracts, supported migrations, operational signals, and a maintenance model.

## Resume evidence and portfolio choices

| Engineering concern | Evidence in the supplied resume | Portfolio treatment |
| --- | --- | --- |
| Fleet-scale shared services | 12K+ nodes, 99.99% availability, Java/Go services on OCI supporting 9 teams | Fleet metric and animated service topology |
| API evolution | 40+ releases with zero breaking changes; versioning, deprecation, compatibility checks and canaries | API lifecycle diagram |
| Developer adoption | Integration reduced from 2 weeks to 3 days; SDKs, tooling, examples; mentoring 6 engineers | Adoption narrative and project emphasis |
| Migrations | 9 consumers migrated to v2 with zero downtime; 25+ legacy integrations migrated at Tata Steel | Full experience bullets |
| Operational ownership | MTTR down 45%, pages down 38% across 12 microservices | Reliability metrics and observability language |
| Runtime performance | p99 down 55%, throughput doubled through JVM and resilience work | Middleware and distributed-systems story |
| Interoperability | Integration effort down 60% across 15+ microservices, OpenAPI/gRPC and generated clients | Contract and tooling themes |
| Data systems | Keystone's versioned metadata APIs, Go SDK, failover and 41 injected faults; Strata's concurrent gRPC storage service | First two featured projects |

All numerical achievements on the website come from the supplied resume. Other user-listed projects have source links and concise descriptions; they are not used to manufacture additional employment achievements.

## Architecture questions worth preparing

These are inferred preparation topics, not verified interview questions:

- How do you define breaking changes beyond schema compatibility? Explain error behavior, ordering, defaults, latency, and authorization semantics.
- How were the 40+ releases checked? Describe contract coverage, canary selection, rollout criteria, and the treatment of slow-moving consumers.
- What changed when nine consumers moved to v2? Explain sequencing, rollback, telemetry, deprecation communication, and ownership.
- How did SDKs reduce integration time? Identify the measurement baseline, reusable behavior, examples, and feedback loop.
- How was 99.99% availability measured? Define the service-level indicator, measurement window, exclusions, error-budget decisions, and dependency failures.
- What caused the p99 bottleneck? Connect JVM and pool changes to evidence, rather than naming optimizations.
- How does a multi-tenant orchestration platform handle fairness, backpressure, retries, idempotency, and failure isolation?
- For Keystone, explain consistency during failover and what the 41 fault cases establish. For Strata, explain schema evolution and concurrency ownership.
- How do design reviews and mentoring create durable standards across teams? Use the six-engineer mentoring and adoption outcomes as concrete examples.

## Design rationale

The portfolio uses a dark cloud-infrastructure visual language with coral accents, an animated network background, moving SVG packets, changing focus text, and an API lifecycle flow. These are conceptual engineering graphics; the live indicators are decorative, not live OCI telemetry. The narrative shows curiosity through contracts, measured outcomes, research, and practical adoption. It does not claim employment at Oracle or explicitly describe application targeting.

The experience section includes every supplied work bullet. The project gallery includes all unique requested projects; repeated EXPOS entries are consolidated. Technical Demo appears only for the four supplied demos. LinkedIn and a footer are omitted.

## Sources

- [Oracle Careers — Principal Software Engineer, Platform, 344708](https://careers.oracle.com/en/sites/jobsearch/job/344708)
- [OCI regions, availability domains, and fault domains](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/regions.htm)
- [OCI Developer Guide](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/devtoolslanding.htm)
- [OCI SDK for Go](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/gosdk.htm)

