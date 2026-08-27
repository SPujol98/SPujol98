# Sergio Pujol

**AI Engineer · Python · LLMs · RAG · C**

Engineer transitioning into AI — building LLM pipelines, RAG systems, and algorithm-heavy tools with Python and C. Currently completing 42 Barcelona's Common Core.

Open to roles in AI Engineering and Data Science.

<p align="center">
  <a href="https://www.linkedin.com/in/sergiopserrano/">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:sergiopujol.98@gmail.com">
    <img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" />
  </a>
</p>

---

## 📂 Selected Projects

**[RAG against the machine](https://github.com/SPujol98/rag-against-the-machine)** — Repository-Scale Hybrid Retrieval

Answers natural-language questions about the vLLM codebase (1900+ files), fully local — no training, no external APIs. 83% recall@5 on docs, 69% on code.

- **BM25 from scratch** — Robertson-style scoring over a hand-built inverted index, no `bm25s` or `rank-bm25`
- **Identifier-aware tokenization** — camelCase/snake_case decomposition on top of stemming; moved code recall@5 from 48% to 65% on its own
- **Hybrid ranking** — BM25 and `all-MiniLM-L6-v2` cosine scores min-max normalized and blended at `alpha=0.85`, tuned empirically against the eval sets
- **Recall@k evaluation suite** — a 200-question benchmark that drove every retrieval decision, plus a CLI and a FastAPI layer over the same pipeline

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=flat&logo=huggingface&logoColor=black)
![BM25](https://img.shields.io/badge/BM25-000000?style=flat)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

---

**[Call Me Maybe](https://github.com/SPujol98/call-me-maybe)** — LLM Constrained Decoding

A constrained decoding pipeline that forces a 0.6B LLM to generate 100% valid JSON function calls by intercepting token selection at every step. No retries, no post-processing — invalid output is structurally impossible by construction.

- **FSM in lockstep with generation** — a finite-state machine tracks the JSON structure token by token and masks every illegal token to `-inf` before sampling; validity is enforced at the sampler, not repaired afterwards
- **Single-token fast path** — when exactly one token is legal, the forward pass is skipped entirely, cutting model calls by ~60-75% on structural tokens
- **BPE-aware string handling** — precomputed token sets handle multi-character tokens (a single token encoding `."` breaks naive character matching), eliminating quote-hallucination failures

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=flat&logo=huggingface&logoColor=black)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

---

**[Pac-Man 42](https://github.com/SPujol98/pac-man)** — Arcade Game Engine & Ghost AI

The 1980 arcade classic rebuilt in Python/Pygame: procedurally generated mazes, four ghosts with distinct hunting personalities, persistent highscores, and a neon/CRT restyle. The whole simulation runs as plain Python with zero rendering dependencies, kept honest by a strict MVC split.

- **Hybrid grid/pixel movement** — entities decide on a discrete grid but render interpolated in continuous space, with buffered input and clamped delta time for frame-rate-independent, tunnel-proof physics
- **Ghost AI as an OCP hierarchy** — an abstract `Ghost` FSM (chase/scatter/frightened/eaten) on a shared wave timer, with Blinky, Pinky, Inky, and Clyde each defining their personality in one overridden method
- **Zero-crash engineering** — a self-healing Pydantic config (invalid keys are clamped, never fatal) and anti-tampering highscore persistence that survives hand-edited or corrupted files without a single traceback
- **Parallel two-person architecture** — model and view built simultaneously against a fixed entity contract, so the simulation and the UI/menus/data layers never touched each other's code

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pygame](https://img.shields.io/badge/Pygame-00B140?style=flat&logo=python&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white)
![mypy-strict](https://img.shields.io/badge/mypy-strict-2B5B84?style=flat)

---

**[Fly-in](https://github.com/SPujol98/fly-in)** — Multi-Drone Routing Simulator

Routes a fleet of drones through a constrained graph using a modified Dijkstra that handles zone capacities, restricted airspace, and priority lanes simultaneously. Visualized live with Pygame.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pygame](https://img.shields.io/badge/Pygame-00B140?style=flat&logo=python&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white)

---

**[Codexion](https://github.com/SPujol98/codexion)** — Concurrency Simulation

A programmer's take on the Dining Philosophers problem in C. Deadlock-free by design through global lock ordering, starvation-free through a per-resource min-heap with FIFO and EDF scheduling policies.

![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![POSIX](https://img.shields.io/badge/POSIX_Threads-FCC624?style=flat&logo=linux&logoColor=black)
![Valgrind](https://img.shields.io/badge/Valgrind_Helgrind-303284?style=flat)

---

**[A-Maze-ing](https://github.com/SPujol98/a-maze-ing)** — Maze Generator & Solver

Generates configurable mazes via recursive backtracking, solves them with BFS, and renders everything in an interactive terminal UI with live color themes. Core logic packaged as a reusable Python library — stdlib only, zero runtime dependencies.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Zero-deps](https://img.shields.io/badge/stdlib_only-3776AB?style=flat)

---

## ⚙️ Tech Stack

<div align="center">

<h3>Languages</h3>

<img src="https://iconic-api.onrender.com/dark/python" width="58" alt="Python" title="Python" />
&nbsp;&nbsp;
<img src="https://iconic-api.onrender.com/dark/c" width="58" alt="C" title="C" />
&nbsp;&nbsp;
<img src="https://iconic-api.onrender.com/dark/postgresql" width="58" alt="SQL" title="SQL" />
&nbsp;&nbsp;
<img src="https://iconic-api.onrender.com/dark/bash" width="58" alt="Bash" title="Bash" />

<h3>AI / ML</h3>

<img src="https://img.shields.io/badge/LLMs-FFD21E?style=flat&logo=huggingface&logoColor=black" />
<img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white" />
<img src="https://img.shields.io/badge/Transformers-FFD21E?style=flat&logo=huggingface&logoColor=black" />
<img src="https://img.shields.io/badge/RAG-4B0082?style=flat" />
<img src="https://img.shields.io/badge/BM25-000000?style=flat" />
<br/>
<img src="https://img.shields.io/badge/Constrained_Decoding-4B0082?style=flat" />
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white" />
<img src="https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white" />
<img src="https://img.shields.io/badge/Pydantic-E92063?style=flat&logo=pydantic&logoColor=white" />
<img src="https://img.shields.io/badge/Pytest-0A9EDC?style=flat&logo=pytest&logoColor=white" />

<h3>Tools</h3>

<img src="https://iconic-api.onrender.com/dark/git" width="58" alt="Git" title="Git" />
&nbsp;&nbsp;
<img src="https://iconic-api.onrender.com/dark/linux" width="58" alt="Linux" title="Linux" />
&nbsp;&nbsp;
<img src="https://iconic-api.onrender.com/dark/pytest" width="58" alt="Pytest" title="Pytest" />
&nbsp;&nbsp;
<img src="https://iconic-api.onrender.com/dark/vim" width="58" alt="Vim" title="Vim" />
&nbsp;&nbsp;
<img src="https://iconic-api.onrender.com/dark/vscode" width="58" alt="VS Code" title="VS Code" />

</div>
