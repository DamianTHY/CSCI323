# 🚕 CSCI323 Group Project — Drive a Taxi (FT11)

This project implements and compares **four reinforcement learning algorithms** on the classic `Taxi-v3` environment from **OpenAI Gymnasium**:

- Monte Carlo (ε-soft)
- SARSA
- Q-Learning
- Value Iteration (baseline)

The study evaluates their performance in terms of **on-policy vs off-policy** and **model-free vs model-based** learning paradigms.

---

## 🧠 Project Overview

The goal is for the taxi agent to learn how to **pick up and drop off passengers** in the least number of steps possible.  
We compare algorithms by measuring:

- Average Return
- Average Steps per Episode
- Success Rate
- Convergence Stability
- Variance (Return Distribution)

Each algorithm is trained and evaluated under consistent hyperparameters and a custom **reward shaping wrapper** to encourage efficient driving behaviour.

---

## ⚙️ Environment Setup

 1. Clone Repository

git clone https://github.com/<your-username>/csci323-taxi-ft11.git
cd csci323-taxi-ft11


 2. Create and Activate Python Environment

python -m venv rl_env
source rl_env/bin/activate          # (Linux/macOS)
rl_env\Scripts\activate             # (Windows)

3. Install Dependencies
pip install -r requirements.txt

4. Verify Gymnasium and Matplotlib Versions

This project uses:

gymnasium>=0.29.1
matplotlib>=3.8.0
numpy>=1.26.0

| Package                            | Description          |
| ---------------------------------- | -------------------- |
|  gymnasium[toy_text]               | Taxi-v3 environment  |
|  numpy                             | Numerical operations |
|  matplotlib                        | Graph plotting       |
|  pickle                            | Policy serialization |
|  time ,  itertools ,  collections  | Training utilities   |




How to Reproduce Key Results
1. Run the Main Script
python csci323_groupproject_ft11.py

This will:
Train Monte Carlo, SARSA, Q-Learning, and Value Iteration agents.
Save learned policies (policy_mc.pkl, policy_sarsa.pkl, etc.)
Automatically plot training progress and evaluation figures.


2. Generate Key Figures


| Figure                                    | Description                                 |
| ----------------------------------------- | ------------------------------------------- |
|   Training Progress (per algorithm)       | Reward & ε vs Episode plots                 |
|   Return vs Episode / Steps vs Episode    | Evaluation performance                      |
|   On-policy vs Off-policy (Avg Return)    | Comparison of learning paradigms            |
|   Model-free vs Model-based (Bar Chart)   | Aggregated mean returns and steps           |
|   Variance & Heatmaps                     | Visualizes agent trajectories and stability |



All figures are saved automatically in the working directory


3. Reproduce Tables / Metrics

After training, a summary is printed:
Monte Carlo   | avg_return = +10.04 | avg_steps = 13.0 | success = 100.0 %
SARSA         | avg_return = +9.76  | avg_steps = 13.1 | success = 100.0 %
Q-Learning    | avg_return = +10.09 | avg_steps = 12.9 | success = 100.0 %
Value Iter.   | avg_return = +10.12 | avg_steps = 12.8 | success = 100.0 %


🧩 File Structure


├── csci323_groupproject_ft11.py   # Main training & evaluation script
├── policy_mc.pkl                  # Saved Monte Carlo policy
├── policy_sarsa.pkl               # Saved SARSA policy
├── policy_ql.pkl                  # Saved Q-Learning policy
├── policy_vi.pkl                  # Saved Value Iteration policy
├── fig_*.png                      # Auto-generated figures
├── requirements.txt               # Dependencies list
└── README.md                      # This file


To reproduce all results, simply run:
python csci323_groupproject_ft11.py
This will train, evaluate, and export every figure and metric automatically.
