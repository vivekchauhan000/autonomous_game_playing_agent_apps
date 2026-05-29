# 🎮 Autonomous Game Playing Agent Apps

<div align="center">

![Banner](https://img.shields.io/badge/Autonomous-Game_Playing_Agent-e11d48?style=for-the-badge&logo=gamepad&logoColor=white)

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![AI Powered](https://img.shields.io/badge/AI-Powered-ff6b35?style=for-the-badge&logo=openai&logoColor=white)]()
[![Reinforcement Learning](https://img.shields.io/badge/Reinforcement-Learning-7c3aed?style=for-the-badge&logo=buffer&logoColor=white)]()
[![LLM Agent](https://img.shields.io/badge/LLM-Agent-0ea5e9?style=for-the-badge&logo=robot&logoColor=white)]()
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)]()

---

### 🕹️ AI agents that autonomously perceive, reason, and play games — powered by LLMs, Reinforcement Learning & Computer Vision

[📋 Overview](#-overview) • [✨ Features](#-features) • [🏗️ Architecture](#%EF%B8%8F-architecture) • [🎯 Supported Games](#-supported-games) • [🚀 Getting Started](#-getting-started) • [📁 Project Structure](#-project-structure) • [🤝 Connect](#-connect-with-me)

</div>

---

## 📋 Overview

**Autonomous Game Playing Agent Apps** is a comprehensive AI framework where intelligent agents learn to **perceive game environments, reason about strategies, and take optimal actions** — all without human intervention.

This project combines the power of **Large Language Models (LLMs)** for high-level reasoning, **Reinforcement Learning (RL)** for adaptive learning, and **Computer Vision** for screen-based game understanding. The result? Agents that can play, improve, and even *master* games autonomously.

Whether you're exploring AI game theory, building RL baselines, or just want to watch an AI beat your favorite game — this is your toolkit.

> 💡 *Give the agent a game. Watch it learn. Watch it win.*

---

## ✨ Features

| Feature | Description |
|---|---|
| 🧠 **LLM-Powered Reasoning** | Uses large language models for strategic decision-making & planning |
| 🎮 **Multi-Game Support** | Works across text-based, grid-based, and screen-based games |
| 👁️ **Vision-Based Perception** | Computer vision pipeline to understand game screens in real time |
| 🔁 **Reinforcement Learning** | PPO, DQN, A3C agents for self-improvement through experience |
| 📈 **Live Training Dashboard** | Real-time metrics — reward curves, win rates, episode stats |
| 🧪 **Experiment Tracking** | Logs every run with hyperparameters for reproducibility |
| 🤖 **Agent Memory** | Short & long-term memory for context-aware multi-step gameplay |
| 🌐 **REST API** | Deploy agents as services and query them via API |
| 🏆 **Leaderboard** | Track agent performance across games and versions |

---

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│                        GAME ENVIRONMENT                          │
│          (Text / Grid / Browser / Emulator / Custom)             │
└────────────────────────┬─────────────────────────────────────────┘
                         │  Observation (State)
                         ▼
┌──────────────────────────────────────────────────────────────────┐
│                     PERCEPTION LAYER                             │
│   ┌─────────────────┐          ┌──────────────────────────┐      │
│   │  Screen Capture │          │   Text / State Parser    │      │
│   │  + CV Pipeline  │          │   (JSON / ASCII / API)   │      │
│   └────────┬────────┘          └────────────┬─────────────┘      │
└────────────┼───────────────────────────────┼────────────────────┘
             └────────────────┬──────────────┘
                              ▼
┌──────────────────────────────────────────────────────────────────┐
│                      AGENT BRAIN                                 │
│                                                                  │
│   ┌──────────────────┐     ┌──────────────────────────────┐      │
│   │   LLM Reasoner   │◄───►│  Reinforcement Learning Core │      │
│   │  (Strategy +     │     │  (PPO / DQN / A3C)           │      │
│   │   Planning)      │     └──────────────────────────────┘      │
│   └──────────────────┘                                           │
│                                                                  │
│   ┌──────────────────┐     ┌──────────────────────────────┐      │
│   │   Agent Memory   │     │   Reward Shaping Engine      │      │
│   │  (Short + Long)  │     │   (Custom reward functions)  │      │
│   └──────────────────┘     └──────────────────────────────┘      │
└────────────────────────────────┬─────────────────────────────────┘
                                 │  Action
                                 ▼
┌──────────────────────────────────────────────────────────────────┐
│                       ACTION EXECUTOR                            │
│     Keyboard / Mouse Simulation  |  API Call  |  Game Command    │
└────────────────────────────────────────────────────────────────-─┘
                                 │
                                 ▼
┌──────────────────────────────────────────────────────────────────┐
│                    MONITORING & LOGGING                          │
│       Live Dashboard  |  Reward Curves  |  Episode Replays       │
└──────────────────────────────────────────────────────────────────┘
```

---

## 🎯 Supported Games

| Game Type | Examples | Agent Type |
|---|---|---|
| 🔤 **Text Adventure** | Zork, TextWorld, Custom | LLM Agent |
| 🟦 **Grid / Puzzle** | Snake, Minesweeper, Sokoban | RL (DQN/PPO) |
| 🃏 **Card / Board** | Blackjack, Chess (simplified) | MCTS + LLM |
| 🖥️ **Screen-Based** | Atari Games, Browser Games | Vision + RL |
| 🏟️ **Custom Env** | Any OpenAI Gym compatible env | Pluggable Agent |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- pip / conda
- API keys (OpenAI / Anthropic)
- Optional: CUDA GPU for faster RL training

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/vivekchauhan000/autonomous_game_playing_agent_apps.git

# 2. Navigate into the project
cd autonomous_game_playing_agent_apps

# 3. Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Set up environment variables
cp .env.example .env
# Edit .env with your API keys
```

### Running an Agent

```bash
# Run LLM agent on a text game
python main.py --agent llm --game textworld --episodes 10

# Train RL agent on Snake
python main.py --agent dqn --game snake --train --episodes 1000

# Run vision agent on Atari
python main.py --agent vision_rl --game atari_breakout --render

# Launch the live training dashboard
python dashboard.py
# Open http://localhost:8050 in browser
```

### Sample Output

```
═══════════════════════════════════════════════
  🎮 Game: Snake  |  Agent: DQN  |  Episode: 47
═══════════════════════════════════════════════
  Score       : 1,840
  High Score  : 2,310
  Epsilon     : 0.21
  Avg Reward  : 127.4
  Win Rate    : 68.3%
  Status      : TRAINING ⚡
═══════════════════════════════════════════════
```

---

## 📁 Project Structure

```
autonomous_game_playing_agent_apps/
│
├── 📂 agents/
│   ├── llm_agent.py              # LLM-powered reasoning agent
│   ├── dqn_agent.py              # Deep Q-Network agent
│   ├── ppo_agent.py              # Proximal Policy Optimization agent
│   ├── vision_agent.py           # Screen-based vision agent
│   └── memory.py                 # Short & long-term agent memory
│
├── 📂 environments/
│   ├── text_game_env.py          # Text adventure environment wrapper
│   ├── grid_env.py               # Grid-based game environment
│   ├── browser_env.py            # Browser game environment (Selenium)
│   └── atari_env.py              # Atari game environment (Gym)
│
├── 📂 perception/
│   ├── screen_capture.py         # Real-time screen capture
│   ├── cv_pipeline.py            # Computer vision processing
│   └── state_parser.py           # Text/JSON state parser
│
├── 📂 training/
│   ├── trainer.py                # RL training loop
│   ├── reward_shaping.py         # Custom reward function builder
│   └── experiment_tracker.py     # MLflow / W&B integration
│
├── 📂 api/
│   ├── server.py                 # FastAPI server
│   └── routes.py                 # API endpoints
│
├── 📂 dashboard/
│   └── app.py                    # Plotly Dash live training dashboard
│
├── 📂 models/
│   └── schemas.py                # Data models & configs
│
├── 📂 utils/
│   ├── logger.py                 # Logging & replay saving
│   └── config.py                 # Config loader
│
├── 📂 tests/
│   └── test_agents.py            # Unit & integration tests
│
├── .env.example                  # Environment variable template
├── requirements.txt              # Python dependencies
├── main.py                       # CLI entry point
└── README.md                     # You are here!
```

---

## 🛠️ Tech Stack

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![OpenAI Gym](https://img.shields.io/badge/OpenAI_Gym-412991?style=flat-square&logo=openai&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=chainlink&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)

</div>

---

## 🤝 Connect with Me

<div align="center">

I'm always open to collaborating on exciting AI/ML projects!

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Vivek_Chaudhary-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/vivek-chaudhary-438a5524a)
[![GitHub](https://img.shields.io/badge/GitHub-vivekchauhan000-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/vivekchauhan000)

</div>

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

Made with ❤️ by [Vivek Chaudhary](https://github.com/vivekchauhan000)

⭐ *If you found this useful, please consider giving it a star!* ⭐

</div>
