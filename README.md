# Jack Maiorino

I build machine-learning systems: reinforcement learning for games, and more recently AI-safety experiments.

## Projects

### [XMage RL Player](https://github.com/jackmaiorino/mage)

A reinforcement-learning agent that plays full games of Magic: The Gathering through the XMage engine rather than a simplified environment. Transformer policy trained with PPO, self-play with an adaptive curriculum, and population-based training across a pool of Pauper decks, scaled out on a Slurm HPC cluster (one GPU head node feeding 640 parallel game runners on CPU satellites). The long-run benchmark is reliably executing a multi-step combo line, a hard credit-assignment problem. In progress since mid-2024; the [repo README](https://github.com/jackmaiorino/mage#readme) covers the architecture, progress history, and how to run it.

### [Selvarath Debate](https://github.com/jackmaiorino/selvarath-debate)

Testing failure modes of debate-style AI oversight: an honest and a dishonest LLM debater argue before a weaker judge that can spend a limited budget of oracle verification calls. The pilot found that a small oracle budget made the judge perform worse than none at all. Funded by a [Manifund grant](https://manifund.org/projects/testing-failure-modes-of-debate-style-ai-control-schemes-tewkbpvy1s); pilot write-up on [LessWrong](https://www.lesswrong.com/posts/2a3vce7WooJ4XkDqw/limited-verification-can-hurt-debate-oversight). My contributions: the pilot re-analysis, a code audit that found two data-corrupting bugs in the oracle channel, and the re-judge harness now running the validation experiments.

### [Dota Science](https://github.com/jackmaiorino/Dota-Science)

Predicting Dota 2 match outcomes from OpenDota API data: exploratory analysis, regression, and a Random Forest classifier reaching 85.7% accuracy. [Live write-up](https://jackmaiorino.github.io/Dota-Science/).
