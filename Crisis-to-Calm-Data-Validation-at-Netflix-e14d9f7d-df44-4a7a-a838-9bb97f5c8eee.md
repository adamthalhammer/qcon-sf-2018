# Crisis to Calm: Data Validation at Netflix

- Data circuit breakers (invariants)
    - integrity checks
    - duplicate detection
    - object counts
    - semantic checks
    - need knobs to fine-tune and exclude
    - take business value into account
- Data canaries
    - test services with old vs new data
- Staggered data rollouts
    - roll new data out to a single region first
    - requires an architecture that allows for data to be out of sync between regions
- Data rollbacks
    - Ability to traverse data history
    - Visibility: data diff UI
    - Versioned data changes