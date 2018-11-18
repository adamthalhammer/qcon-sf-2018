# Deep Representation

- Building a semantic image search engine
    - image → image
    - text <> image
    - text → text
- Computer vision
    - **C**onvolutional **N**eural **N**etworks: feature extraction + classification
- Natural Language Processing

- Approaches
    - End-to-end models (CNN + RNN): powerful, but hard to debug
    - Pairwise similarity model
        - Scales to large datasets
        - Slow to train
        - Does not work for text
        - Needs good examples
    - Embeddings: proximity search
        - Scalable
        - Fast
        - Can leverage pre-trained models

        Improvements:

        - Object detection first
        - Re-weighting
    - Joint model:

        [https://github.com/hundredblocks/semantic-search](https://github.com/hundredblocks/semantic-search)

- Next steps
    - incorporate user feedback (e.g. clicks)
    - leverage domain specific aspects
    - [https://blog.insightdatascience.com/the-unreasonable-effectiveness-of-deep-learning-representations-4ce83fc663cf](https://blog.insightdatascience.com/the-unreasonable-effectiveness-of-deep-learning-representations-4ce83fc663cf)