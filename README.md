# Jack Maiorino

I build reinforcement-learning systems for games, mostly Magic: The Gathering, and run small experiments on AI oversight.

## Now

**[mtg-kernel](https://github.com/jackmaiorino/mtg-kernel)** · Rust, Python<br>
A deterministic Magic: The Gathering rules engine in Rust with a Python self-play training and evaluation stack. Runs are reproducible, and an XMage bridge checks both rules behavior and agent strength against an independent engine.

**[spellbench](https://github.com/jackmaiorino/spellbench)** · Python<br>
An open protocol and tournament arena where MTG engines and bots built by different people play each other. Seat-swapped game pairs, Elo ratings with bootstrap intervals, and every rating re-derivable from the match ledger.

**[Selvarath Debate](https://github.com/jackmaiorino/selvarath-debate)** · Python<br>
Manifund-funded tests of debate as AI oversight. In a pre-registered 22,140-cell run, giving a weaker judge two oracle checks raised its error by 3.9 points (95% CI 2.2 to 5.7). My part: the pilot re-analysis, a code audit that found two data-corrupting bugs, and the follow-up harness. [Pilot write-up](https://www.lesswrong.com/posts/2a3vce7WooJ4XkDqw/limited-verification-can-hurt-debate-oversight)

## Earlier

- **[XMage RL agent](https://github.com/jackmaiorino/mage)**: transformer policy trained with PPO and population-based self-play inside the XMage engine, on a Slurm cluster (one GPU head feeding 640 CPU game runners). Predecessor to mtg-kernel.
- **[Diffusion medical augmentation](https://github.com/jackmaiorino/diffusion-medical-augmentation)**: a class-conditional DDPM that synthesizes rare skin-lesion classes (HAM10000) as training data for rare-class classification. Group project.
- **[Dota Science](https://github.com/jackmaiorino/Dota-Science)**: predicting Dota 2 match outcomes from OpenDota data, 85.7% accuracy. [Write-up](https://jackmaiorino.github.io/Dota-Science/)
