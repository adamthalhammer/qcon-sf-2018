# Architecture without an end state

> how to design systems that evolve over time in the face of technological and business change

- What is architecture
    1. Structure of a system
    2. Components and their relationships
    3. Mechanisms for cross-cutting concerns

- Purpose of software architecture
    1. Choose and create desirable system-wide-properties
    2. Make trade-offs with deliberation and understanding
    3. Allow orderly construction of a system of systems
    4. Divide responsibilities among team members
    5. Provide a common vocabulary
    6. Manage cost
- Value curve: when do we start seeing benefits?
    - Design for early returns
    - Don't compromise the payback period
    - Build systems that support themselves (pyramids vs arches)
- Fundamentals of architecture

    Diagrams as a tool to **communicate** and **make decisions**

    - Context
        - Users
            - customers
            - customer service
            - finance staff
            - sales
        - Other systems
            - Email
            - Payments
            - Currency
    - Interfaces
        - ID
        - name
        - initiation (inbound/outbound)
        - synchronicity
        - frequency
        - payload size
        - transport
        - framing (format)
        - encoding
        - semantics
- Architecture qualities: prioritise!
    - Qualities observed at runtime (rather than non-functional requirements):
        - Performance
        - Security
        - Availability
        - Usability
    - Non-runtime qualities
        - Scalability
        - Modifiability
        - Portability
        - Integrability
        - Reusability
        - Testability

- Architecturally significant requirements: Architecture Killers
    - Languages, currencies, timezones
    - Compliance & reporting
    - Disconnected operation
    - Active/active
    - Intelligence
    - Customer service needs
    - Human overrides
    - Interface with physical objects that move
    - Toxic, hazardous, radioactive, or remote environments

- Constraints
    - Law, e.g. GDPR
    - Industry regulations, e.g. PCI/DSS
- Decomposing the system
    - Goals

        Must:

        - terminate every external interface at a component
        - deliver the features

        Should:

        - 
    - Maxims
        - Use both static and dynamic structures
            - Can this be a library?
            - Does this need to be a service?
        - Extract common mechanisms
        - What knowledge must be shared across this boundary?
    - Evaluation
        - Anthropomorphise the components in the architecture
        - Pass a token around to simulate a request
        - Score it like golf
    - Views you can use
        - C4 - context, containers, components, ~~classes~~
        - Data flow diagram
            - data store → process → data store
            - processes must always be triggered by control flow
- When and how much
    - Time: Build time vs change time vs lifespan
    - Ongoing work
        - Interface table
        - architecture quality scenarios
        - internal boundaries, dispute resolution
        - information architecture
        - evaluations of the architecture
        - verification of the implementations
    - [Set-based concurrent engineering](https://sloanreview.mit.edu/article/toyotas-principles-of-setbased-concurrent-engineering/)
        - Series of incremental decisions
        - More models, prototypes, proofs of concept
        - Slow progression from rough design to detailed design
        - Avoid premature commitment
        - Desire to avoid backtracking on commitments
        - Last responsible moment
    - **Minimum marketable features** pull **architecture elements**
    - Sequencing based on [estimates](https://www.amazon.com/How-Measure-Anything-Intangibles-Business-ebook/dp/B00INUYS2U): weighted shortest job first
    - [Principles of product development flow](https://www.amazon.com/Principles-Product-Development-Flow-Generation/dp/1935401009)
- YAGNI does not apply across microservice boundaries
    1. Collective code ownership
    2. Merciless refactoring
    3. 
- Communication
    1. Communicate
    2. Capture information
    3. Aid our memory
    4. Share our thinking with the future
    - Use the right views to serve different viewpoints
- Orthogonality
    - Separation of concerns
        - cross-cutting vs isolated: pick your fights
        - Dimensions to work with
            - Modules
            - Components
            - Processes
            - Hosts
            - Services
            - Geographies
    - High cohesion
    - Low coupling
    - Decision hiding
- Explore the problem through solutions
    1. State the problem
    2. Find an approach
    3. Test a solution
    4. Find gaps
    5. Repeat
- Localise decisions
    - Don't let entity types proliferate through systems, keep them local
    - Use common interfaces
    - Use common representations/data formats
    - Activation set vs failure domain
- Reducing the surface area of change
    - Augment upstream
        - Combine sources
        - Add human judgement
        - Apply ML models
    - Contextualise downstream
        - Applying policies or restrictions
- Information Architecture: reality ≠ representation
    - Identifiers
        - Make the context explicit
        - Integrate via data instead of code
        - URLs vs naked ids
    - Splitting nouns

        SKU strictly as an identifier

- API Design
    - Principles
        - Design API from the perspective of the caller
        - Offer what the caller wants to achieve
        - Avoid
            - internal state names
            - coded fields
            - composite fields
            - conversations
    - Breaking changes
        - prefer adding a new interface
        - prefer adding new request types
        - avoid mapping domain classes onto the wire
    - Hexagonal architecture
        - separate domain objects from persistence, message format, etc

    - Consumer driven contract tests
        - test only the behaviour needed by one consumer
        - offer those tests to the interface provider
    - Open vs closed world

- Q&A
    - Tools
        - [https://github.com/cognitect-labs/vase](https://github.com/cognitect-labs/vase)
        - [https://github.com/cognitect-labs/requestinator](https://github.com/cognitect-labs/requestinator)
        - [https://docs.pact.io](https://docs.pact.io/)