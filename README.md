# Multi-Agent Reinforcement Learning HW2 - Actor-Critic

**Home Assignment (Grade 98, M.Sc. Data Science, HIT). Deep multi-agent actor-critic methods with the MARL textbook codebase: training Independent A2C (IA2C) on Level-Based Foraging, tuning its entropy regularisation, and comparing independent and centralised critics on the Robotic Warehouse.**

## Headline Results
- **IA2C learns to cooperate:** on Foraging-8x8-3p-2f the mean return rises from 0.24 to the environment's maximum of 1.0 (all food collected) at 751K steps, with most later evaluations above 0.9.
- **No clear winner in the entropy search:** coefficients 0.001, 0.01 and 0.1 all learn (peaks 1.00, 0.95, 1.00), and the ranking flips between criteria — a single seed cannot separate them.
- **Centralised critics buy stability:** on rware-tiny-4ag, MAPPO beats IPPO in both mean return (11.0 vs. 9.8) and consistency across seeds, while IA2C scores highest on average (16.3) but one of its three seeds collapses to 0.

## Key Features
- **Deep MARL with the Book Codebase:** IA2C trained for 1M steps, with returns, policy entropy and actor and critic losses analysed from the logged metrics.
- **Hyperparameter Search:** three entropy-regularisation coefficients compared under the same seed.
- **Independent vs. Centralised Critics:** IA2C, IPPO, MAA2C and MAPPO compared over three seeds on the course's prepared training data.
- **Rollout Video:** the trained IA2C agents in the warehouse, rendered from the final checkpoint.

## Repository Structure
- `Multi_Agent_Reinforcement_Learning_HW2.ipynb`: Full solution notebook — training, analysis, comparisons and the embedded rollout video (explanations in Hebrew).
- `hw2_lbf_ia2c.csv`: Metrics of the main IA2C run on Level-Based Foraging.
- `hw2_lbf_entropy_search.csv`: Metrics of the three entropy-coefficient runs.
- `hw2_rware_comparison.csv`: Metrics of IA2C, IPPO, MAA2C and MAPPO on the warehouse task, three seeds each.
- `HW2_rware_ia2c_eval.mp4`: Rollout video of the trained IA2C agents in the warehouse.
- `Assignment_2.pdf`: Original assignment instructions.

## Source
The assignment is the Wednesday exercise, *Actor-Critic Algorithms in Level-Based Foraging*, from [marl-book-exercises](https://github.com/marl-book/marl-book-exercises) — designed for the Barcelona Summer School 2024 on Multi-Agent Reinforcement Learning and based on the textbook *Multi-Agent Reinforcement Learning: Foundations and Modern Approaches*. Training uses the book's codebase.
