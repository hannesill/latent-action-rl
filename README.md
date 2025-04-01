# Learning Latent Action Spaces in Deep RL

This repository contains the code and experiments for my “Learning Latent Action Spaces in Deep RL” research project. This work focuses on investigating whether operating in a lower-dimensional latent action space can simplify the learning process and improve exploration efficiency in reinforcement learning (RL). The project further explores using a complexity metric—Policy-Optimal Information Capacity (POIC)—to optimize a projector that maps latent actions to the original action space.

The research report can be viewed [here](https://h9ll.notion.site/Learning-Latent-Action-Spaces-in-Deep-RL-76d9acedfeee47959e579aa4cf1fbd52?pvs=74).

## 1. Overview

### 1.1. Motivation
Traditional RL methods efficiently handle large state spaces by learning state representations. This project extends that idea to the action space by learning latent action representations, hypothesizing that a lower-dimensional action space may simplify exploration and learning, especially in sample-inefficient on-policy methods.

### 1.2. Key Contributions
* Implementation of latent action space configurations in a deep RL setting.
* Re-implementation and analysis of the POIC metric to evaluate task complexity.
* Extensive experimental comparison across multiple environments (Walker2d, Ant, HalfCheetah, Humanoid) using CleanRL’s PPO.
* An investigation into projector optimization via random weight sampling based on POIC scores.
* Results & Findings:
 
The experiments yielded mixed results—some environments showed benefits from latent action spaces while others did not. The variability in POIC scores and their impact on performance highlights both the promise and challenges of this approach.

### 1.3. Repository Structure

TODO

## 2. Getting Started

### 2.1. Installation
#### a) Clone the repository:

```bash
git clone https://github.com/hannesill/latent-rl.git
cd latent-rl
```

#### b) Install dependencies:

Prerequisites
* Python 3.8+
* Required libraries: TODO
(See requirements.txt for the full list.)

```bash
pip install -r requirements.txt
```


### 2.2. Running the Experiments

#### a) Baseline & Latent Action Experiments:
The experiments are implemented using CleanRL’s PPO. You can run the experiments for each environment by executing:

```bash
python experiments/run_experiment.py --env Walker2d --config baseline
python experiments/run_experiment.py --env Walker2d --config latent
```

#### b) POIC Evaluation & Projector Optimization:
To evaluate the POIC metric and run projector optimization tests, execute:

```bash
python experiments/poic_evaluation.py --env Ant --samples 50
```

For detailed usage instructions and parameter configurations, please refer to the documentation.

## 3. Results

Detailed results, including plots of episodic returns and video comparisons, can be found in the docs/ directory. Highlights include:
	•	Walker2d & Ant: Comparison videos demonstrating performance differences.
	•	HalfCheetah & Humanoid: Charts illustrating the episodic return trends over 6 million global steps.
	•	POIC Analysis: Graphs comparing reimplemented POIC scores against the original paper’s results.

## 4. Discussion & Future Work

The project demonstrates that while latent action spaces can affect learning dynamics, their effectiveness varies significantly across environments. Future work should focus on:
	•	Refining the precision of the POIC reimplementation.
	•	Integrating projector optimization more tightly with policy training.
	•	Running experiments with larger computational budgets to reduce variance.
	•	Extending the approach to additional environments and RL algorithms.

## 5. License

This project is licensed under the MIT License. See the LICENSE file for details.

## 6. Acknowledgments

Special thanks to Oliver Hausdörfer for supervision and to the TUM Practical Course on Deep Reinforcement Learning for inspiring this work.
