# Projects

# Mage AI Reinforcement Learning

## Table of Contents
- [Summary](#summary)
- [Game Engine Updates](#game-engine-updates)
- [Key Components](#key-components)
  - [ComputerPlayerRL](#1-computerplayerrl)
  - [RLState](#2-rlstate)
  - [RLTrainer](#3-rltrainer)
  - [Model Versions & Evaluation History](#model-versions--evaluation-history)
- [Changelog](#changelog)

### **Summary**
This project began as a way for me to leverage my passion for Magic The Gathering(MTG) into learning about AI. It is an AI system for the Mage game client(a free open source MTG client), utilizing reinforcement learning (RL) techniques to make decisions. This was my first time working on an open source project, first time working with AI, and first time working with java at this scale. If you see something that you deem heinous to any of these practices, please let me know as this was a massive task to learn. At the time of writing this I have been working on the project for almost 14 months now with varried intensity when life allows.
### **Game Engine Updates**
Magic is an incredibly unforgiving game to code up due to the countless complex interactions. If you are unfamiliar with the game, I encourage you to just glance at the official rules here: [Magic: The Gathering Comprehensive Rules (2025)](https://media.wizards.com/2025/downloads/MagicCompRules%2020250207.pdf) to get a sense of the complexity. This meant that I ended up spending a lot of time improving the game runner itself to better legally mask the action space to my model. Any of my changes you see outside of the Mage.Player.AIRL dir are just game engine improvements. 

## Key Components

### 1 **ComputerPlayerRL**
An AI player class that extends the capabilities of a standard computer player by integrating reinforcement learning models. It uses the `RLModel` to make decisions during gameplay.

### 2 **RLState**
Represents the state of the game at any given time, including player stats, card features, and game actions. This class is essential for feeding data into the neural network for predictions.

### 3 **RLTrainer**
Manages the training process of the RLModel, coordinating multiple game simulations to refine the AI's strategies. It uses a multi-threaded approach to run numerous game instances in parallel, accelerating the learning process.

### Model Versions & Evaluation History

| Epochs | Version | Win Rate | Notes | Date |
|--------|---------|----------|-------|------|
| ~2000  | v1      | 29.17%   | Non-greedy selection. | 6/21/25 |
| ~2000  | v1.1    | 20.83%   | Changed so **pass** is always option 0. Aggressive long game penalty. Spell/action choice looks good, but spell targeting is awful (might be defaulting to targeting self). | 6/29/25 |
| ~2000  | v1.1    | 29.17%   | Changed targeting to use same logic as `ComputerPlayer7`, but did **not** retrain. | 7/11/25 |
| ~9k    | v1.2    | 43.75%   | Uses `ComputerPlayer7` targeting and retrained. | 7/12/25 |
| ~9k    | v1.2    | 41.67%   | Re-evaluation run. | 7/12/25 |
|        | v2.0    | 0.00%    | Full refactor of project. Benchmark overall win rate vs heuristic across pool: 0.000 (0/10) |  |
|        | v2.1    |          | Removed Tap for mana as solo action. |  |
|        | v2.2    |          | Added reward for playing lands and casting spells. |  |
| ~50k   | v2.3    | 50.47%   |  |  |
| ~150k  | v3.0    | 10-30%   | Added ability for RL spell and ability targetting. |  |

## Changelog

| Date    | Update | Blockers |
|---------|--------|----------|
| 2/8/26  | Began documenting large updates or changes as work on this project.<br><br>**Past 2 Months Summary:**<br>• Completely refactored the entire project, stripping complex text embeddings of cards and swapping for simple UUIDs<br>• Replaced all RL decisions with heuristic decisions except for "choose spell or ability or land"<br>• Choosing targets, declaring attackers, and declaring blockers were all heuristic in version 2.0<br>• Reached ~50% winrate in only 50k episodes (1-2 days of training)<br><br>**Key Issues Identified:**<br>• **For non-MTG players:** The heuristic targeting model was making poor decisions, stopping the RL model from learning the best choices<br>• **For MTG players:** For cards like Grab the Prize, the heuristic model had the options: Bolt, Fiery Temper, Fiery Temper. It was choosing Bolt despite having mana for the Fiery Temper madness. The model never learned the value of Grab the Prize as the heuristic model didn't perform the high value discards<br><br>At this point I deemed the model limited by its heuristic components and began implementing what I believed to be the next most important component: targeting. | Currently my biggest issue is compute. The model is very slowly learning due to the rareness of targeting decisions. At the time of this update, I'm at around 150k episodes, seeing highly volatile metrics fluctuating between 10% and 30% winrate. On manual inspection I am noticing slow understanding of targeting decisions which is good. Biggest issue is training on just my home PC. | 