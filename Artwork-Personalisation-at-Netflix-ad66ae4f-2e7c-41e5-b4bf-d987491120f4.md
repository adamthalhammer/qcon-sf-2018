# Artwork Personalisation at Netflix

Challenges: Attribution, Change Effects, Clickbait

Collaborative Filtering? Not possible, since users can only play based on artwork chosen by Netflix

**Multi-armed bandit** artwork optimisation

- Environment: Netflix homepage
- Learner: Artwork selector
- Action: Display image
- Reward: positive engagement

Good outcome: watching and enjoying the content

Bad outcome: no engagement *or* abandoning/not enjoying the content

Metric: take fraction

Goal: Minimise cumulative regret

Don't be ε-greedy: unbounded regret

Upper Confidence Bound: need to update frequently

Thompson Sampling: continues to explore based on randomness (Chappelle & Li, 2011)

## Personalisation: Contextual Bandits

Like supervised learning, but the feedback is in the form of a reward rather than a label.