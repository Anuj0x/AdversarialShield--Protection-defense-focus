# Modern Adversarial Attacks Framework

[![Creator](https://img.shields.io/badge/Creator-Anuj0x-9cf)](https://github.com/Anuj0x)

A cutting-edge, production-ready framework for adversarial machine learning research and robust AI development. Built with modern PyTorch 2.x, featuring unified APIs, type safety, and extensible architecture for comprehensive adversarial attack and defense evaluation.

**Created by [Anuj0x](https://github.com/Anuj0x)** - Expert in Programming & Scripting Languages, Deep Learning & State-of-the-Art AI Models, Generative Models & Autoencoders, Advanced Attention Mechanisms & Model Optimization, Multimodal Fusion & Cross-Attention Architectures, Reinforcement Learning & Neural Architecture Search, AI Hardware Acceleration & MLOps, Computer Vision & Image Processing, Data Management & Vector Databases, Agentic LLMs & Prompt Engineering, Forecasting & Time Series Models, Optimization & Algorithmic Techniques, Blockchain & Decentralized Applications, DevOps, Cloud & Cybersecurity, Quantum AI & Circuit Design, Web Development Frameworks.

## 🚀 Core Features

- **🔧 Unified API**: Single, consistent interface across all attack and defense implementations
- **📝 Type Safety**: Complete type annotations for enhanced developer experience and reliability
- **⚡ Modern PyTorch**: Leverages PyTorch 2.x features including compilation, mixed precision, and optimized training loops
- **⚙️ Hydra Configuration**: Declarative experiment management with YAML-based configuration override
- **🔌 Plugin Architecture**: Abstract base classes enable seamless integration of custom attacks and defenses
- **📊 Research-Grade Evaluation**: Comprehensive metrics including success rates, robustness scores, and detection precision
- **🏭 Production Ready**: Clean code architecture, proper error handling, and logging for real-world deployment

## 📦 Installation

```bash
pip install -r requirements.txt
```

## 🏃 Quick Start

### Basic Usage

```python
from modern_attacks import SimpleCNN, FGSMAttack, AttackConfig
import torch

# Load your model
model = SimpleCNN()
model.load_state_dict(torch.load('model.pth'))
model.eval()

# Create attack
config = AttackConfig(epsilon=0.1)
attack = FGSMAttack(model, config)

# Generate adversarial examples
inputs, targets = next(iter(test_loader))
adv_inputs = attack.generate(inputs, targets)
```

### Configuration-Based Experiments

```bash
# Run default experiment
python main.py

# Customize experiment
python main.py experiment.name=my_attack_test training.epochs=20 attacks.0.epsilon=0.2

# Run with specific attacks only
python main.py attacks='[{name: fgsm, epsilon: 0.1}]'
```

## 🏗️ Architecture

### Core Components

- **`modern_attacks.py`**: Unified attack implementations
  - FGSM, Vanilla Gradient, L-BFGS attacks
  - Attack evaluation and metrics
  - Modern CNN architectures

- **`modern_defenses.py`**: Defense mechanisms
  - Adversarial training
  - Knowledge distillation
  - Binary thresholding
  - Ensemble methods

- **`main.py`**: Experiment orchestration with Hydra config

### Supported Attacks

| Attack | Description | Parameters |
|--------|-------------|------------|
| FGSM | Fast Gradient Sign Method | `epsilon`, `random_start`, `alpha` |
| Vanilla | Gradient descent on noise | `epsilon`, `alpha`, `num_iterations` |
| L-BFGS | Box-constrained optimization | `epsilon`, `num_iterations` |

### Supported Defenses

| Defense | Description | Key Features |
|---------|-------------|--------------|
| Adversarial Training | Train with adversarial examples | Robust model training |
| Knowledge Distillation | Compress teacher knowledge | Smaller, robust models |
| Binary Thresholding | Activation pattern analysis | Real-time detection |
| Ensemble | Multiple model consensus | Improved robustness |

## 📊 Configuration

The framework uses Hydra for configuration management. Key configuration sections:

```yaml
experiment:
  name: "my_experiment"
  seed: 42

model:
  architecture: "simple_cnn"  # or "distilled_cnn"

attacks:
  - name: "fgsm"
    epsilon: 0.1
  - name: "vanilla"
    epsilon: 0.1
    alpha: 0.01

defenses:
  - name: "adversarial_training"
    epsilon: 0.1
```

## 🔬 Research Features

### Modern PyTorch Patterns
- Proper device handling
- Mixed precision support (when available)
- Gradient accumulation
- Model compilation (torch.compile)

### Evaluation Metrics
- Attack success rate
- Robust accuracy
- Detection precision/recall
- Confidence scores

### Extensibility
- Abstract base classes for custom attacks/defenses
- Factory pattern for easy registration
- Modular configuration

## 📈 Results

The framework automatically saves results in JSON format with detailed metrics:

```json
{
  "experiment": "modern_adversarial_attacks",
  "attacks": {
    "fgsm": {
      "success_rate": 0.85,
      "original_accuracy": 0.98,
      "total_samples": 1000
    }
  },
  "defenses": {
    "adversarial_training": {
      "clean_accuracy": 0.95,
      "adversarial_accuracy": 0.78,
      "detection_rate": 0.92
    }
  }
}
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Add tests for new functionality
4. Ensure type hints and documentation
5. Submit a pull request

## 📝 Citation

```bibtex
@software{modern_adversarial_attacks,
  title = {Modern Adversarial Attacks Framework},
  author = {Anuj0x},
  year = {2024},
  url = {https://github.com/Anuj0x/modern-adversarial-attacks}
}
```
