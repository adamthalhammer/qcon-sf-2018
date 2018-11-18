# Human-centric ML infrastructure at Netflix

Observation: technical problems transform into human problems over time

Let data scientists focus on building models, feature engineering etc

The ML infrastructure supports building and deploying models

Netflix uses ML to optimise all aspects of the business, not only the core product

- **Stack**
    - ML Libraries
    - Notebooks: Nteract (vs Jupyter)
    - Job Scheduler: Meson (vs Airflow)
    - Compute Resources: Titus (vs Kubernetes)
    - Query Engine: Spark, Presto
    - Data Lake: S3
- **Problems**
    - With this stack, taking a model from inception to production took 4 months
    - 60% of the code was about infrastructure
    - Monitoring?
    - Debugging?
    - Backfill?
    - Performance?
- **Metaflow**
    - Uses decorators to
        - create a DAG
        - assign compute resources
        - create HTTP endpoints for inference
    - Persists intermediate results by default
    - Provides direct access to data from S3
    - Code, data, and models are versioned by default
    - Single CLI command to deploy a model to the production scheduler
    - No universal dashboards, instead empower data scientists to create UIs using jupyter notebooks

Diverse problems → diverse people → diverse models