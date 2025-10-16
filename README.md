# QGNN-Lite

[![Python](https://img.shields.io/badge/python-3.9%2B-blue)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?logo=pytorch)](https://pytorch.org/)
[![PennyLane](https://img.shields.io/badge/PennyLane-quantum-green)](https://pennylane.ai/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**QGNN-Lite** is a minimal hybrid **Quantum–Graph Neural Network** prototype.  
It combines **classical GNN encoders** (GCN/GAT) with **quantum variational circuits** as heads for node classification tasks.  
The project is designed as an **educational demo** and a **portfolio-ready prototype** to explore how quantum machine learning can be applied to graph data.

---

## Features
- Graph encoder: GCN / GAT (via PyTorch Geometric).  
- Quantum head: Variational Quantum Circuit (VQC) with angle encoding.  
- Baseline: MLP head for fair comparison.  
- Supported datasets: Cora, KarateClub, MUTAG.  
- Experiments with different qubit numbers, depth, and shots.  
- Clear project structure, configs, and reproducible results.  

---

## Installation
```bash
git clone https://github.com/<yourname>/qgnn-lite.git
cd qgnn-lite
pip install -r requirements.txt
```

---

## Quickstart
Run training on Cora with a quantum head:
```bash
python qgnn/train.py --config configs/cora_qhead.yaml
```

Run with MLP baseline:
```bash
python qgnn/train.py --config configs/cora_mlp.yaml
```

---

## Results (demo)
| Model | Dataset | Accuracy | Notes |
|-------|---------|----------|-------|
| GCN + MLP | Cora | 81% | baseline |
| GCN + VQC (8 qubits, depth=2) | Cora | 79% | quantum head |
| GCN + VQC (16 qubits, depth=4) | Cora | 82% | slightly better |

*⚠️ Numbers are illustrative placeholders — fill after experiments.*

---

## Project structure
```
qgnn-lite/
  README.md
  requirements.txt
  configs/
  qgnn/
    data.py
    models/
      gnn.py
      qhead.py
      mhead.py
    train.py
    utils.py
  scripts/
  experiments/
  LICENSE
```

---

## Roadmap
- [ ] Add quantum-inspired attention mechanism  
- [ ] Add selective memory module (retrieval)  
- [ ] Implement long/short reasoning cycles  
- [ ] Try graph-level tasks (MUTAG, PROTEINS)  

---

## References
- [PennyLane documentation](https://pennylane.ai/)  
- [PyTorch Geometric](https://pytorch-geometric.readthedocs.io/)  
- Schuld, M., *Machine Learning with Quantum Computers* (Springer, 2021)  

---

## License
[MIT](LICENSE)
