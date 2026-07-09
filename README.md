# Hi, I'm Jack

I build machine-learning systems: reinforcement learning for games, and lately AI-safety experiments. Current obsession: teaching a transformer to play Magic: The Gathering.

## Projects

### [XMage RL Player](https://github.com/jackmaiorino/mage)

A reinforcement-learning agent that plays full games of Magic through the real XMage engine. No simplified environment. Transformer policy trained with PPO, self-play with an adaptive curriculum, and population-based training across a pool of Pauper decks, scaled out on a Slurm HPC cluster (one GPU head node feeding 640 parallel game runners on CPU satellites). The long-run benchmark: teaching it to reliably execute a multi-step combo line, a hard credit-assignment problem.

Two years in and counting. The [repo README](https://github.com/jackmaiorino/mage#readme) has the architecture, progress history, and how to run it.

### [Selvarath Debate](https://github.com/jackmaiorino/selvarath-debate)

Testing when debate-as-oversight breaks: an honest and a dishonest LLM debater argue before a weaker judge that can spend a limited budget of oracle verification calls — and the pilot found that a few oracle calls made the judge *worse* than none. Funded by a [Manifund grant](https://manifund.org/projects/testing-failure-modes-of-debate-style-ai-control-schemes-tewkbpvy1s); pilot write-up on [LessWrong](https://www.lesswrong.com/posts/2a3vce7WooJ4XkDqw/limited-verification-can-hurt-debate-oversight). My side of the collaboration: the pilot re-analysis, a code audit that caught two data-corrupting bugs in the oracle channel, and the fixed re-judge harness now running the validation experiments.

### [Dota Science](https://github.com/jackmaiorino/Dota-Science)

A data-science walkthrough predicting Dota 2 match outcomes from OpenDota API data — exploratory analysis, regression, and a Random Forest classifier reaching 85.7% accuracy. [Read it live](https://jackmaiorino.github.io/Dota-Science/).
