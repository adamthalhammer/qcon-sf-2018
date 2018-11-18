# Airbnb: Monolith → Services

- Why?
    - 4 million lines of code by 2018
    - deploys locked for 15h per week
- Initial design tenets
    - Services own their data (r/w)
    - Services address a specific concern
    - Avoid duplicate functionality
    - Mutations propagate via standard events → spinal tap
    (as a replacement for Rails callbacks)
- Migration pathway

    They started with the `home` model

    It would have been too much work to change all the call sites, so they...

    → ... created a custom MySQL adapter to talk to their new service instead of the DB 🤯

    Admin UI to compare and switch read + write paths between DB vs service

- Best practices
    - Frameworks (code generation)
    - Replaying production traffic to test new releases using [Diffy](https://github.com/twitter/diffy)
    - Standard templates for observability based on the Thrift IDL → Datadog 🐕

    They created a service framework team to build these for Ruby and Java using [Thrift](https://thrift.apache.org/docs/idl).

- Results
    - 250 services, 800 engineers
    - They reduced latency, mostly due to using Java instead of Ruby
    - 10k deploys per week
    - Per-team on call
    - Starting to move from EC2 → Kubernetes