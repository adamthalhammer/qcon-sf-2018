# Netflix Play API

Why we built and Evolutionary Architecture

- 3 Principles
    1. Identity: Why does your service exist? How does it support our mission?
        - Simple, singular identity for all services
    2. Consequential decisions (vs inconsequential decisions)
        - Appropriate coupling: Binary vs operational vs language vs protocol
        - Blocking vs non-blocking IO: 🙄 🐘
        - Data architecture: materialised view of data required by the service
    3. Evolvability
        - Fitness functions to guide future evolution of the service