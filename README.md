# Boolean Neural Networks for Edge AI

Implementation of **Boolean Neural Networks**, **Perceptrons**, **Multi-Layer Perceptrons (MLPs)**, and **Genetic Algorithms** for hardware-oriented Edge AI.

This repository contains the research implementation developed during my **Summer Research Internship (May–June 2026)** at the **Indian Institute of Technology (IIT) Jammu**, under the supervision of **Prof. Soma Dhavala**.

The project explores how Boolean logic can be represented using neural network architectures and investigates evolutionary optimization techniques for hardware-efficient AI systems. The implementation covers perceptrons, MLPs, genetic algorithms, and Boolean neural networks, with future work focused on FPGA-based deployment for Edge AI applications.

---

| **Institution** | Indian Institute of Technology Jammu |
|-----------------|--------------------------------------|
| **Internship** | Summer Research Internship (May–June 2026) |
| **Supervisor** | Prof. Soma Dhavala |
| **Research Area** | Edge AI • Boolean Neural Networks • Genetic Algorithms • Hardware Acceleration |
| **Status** | Research Implementation Complete • FPGA Extension in Progress |

---

# Project Overview

Boolean logic forms the foundation of digital hardware, while neural networks form the foundation of modern Artificial Intelligence.

This project investigates the intersection of these two fields by implementing Boolean logic using neural network architectures and optimizing them using Genetic Algorithms. The long-term objective is to develop hardware-efficient neural models that can be deployed on FPGA-based Edge AI platforms.

The repository demonstrates the theoretical foundations, practical implementations, and experimental evaluation of Boolean Neural Networks through a series of progressively complex models.

---

# Project Workflow

```text
Boolean Logic
        │
        ▼
Threshold Logic Units (TLUs)
        │
        ▼
Single-Layer Perceptrons
        │
        ▼
Multi-Layer Perceptrons (MLPs)
        │
        ▼
Continuous XOR Classification
        │
        ▼
Genetic Algorithm Optimization
        │
        ▼
Boolean Neural Networks
        │
        ▼
FPGA Deployment (Future Work)
```

---

# Technical Components

## Neural Logic

- Threshold Logic Units (TLUs)
- Single-Layer Perceptrons
- Boolean Logic Gates
- Decision Boundary Analysis

## Neural Networks

- XOR using Multi-Layer Perceptrons
- Continuous XOR Classification
- Improved MLP Architectures
- Training Behaviour Analysis

## Machine Learning Frameworks

- Scikit-learn Implementation
- PyTorch Implementation
- Performance Comparison

## Evolutionary Computing

- Genetic Algorithms
- TorchGA
- Continuous Genetic Algorithms
- Discrete Genetic Algorithms
- Custom Crossover Operators
- Custom Mutation Operators

## Boolean Neural Networks

- Boolean MLP Design
- XOR Optimization
- Gate-Level Analysis
- Logic Gate Discovery

---

# Repository Structure

```text
Boolean-Neural-Networks-Edge-AI/

│── README.md
│── LICENSE
│── requirements.txt

├── notebooks/
│   ├── 01_perceptron_logic.ipynb
│   ├── 02_boolean_gates.ipynb
│   ├── 03_xor_mlp.ipynb
│   ├── 04_sklearn_vs_pytorch.ipynb
│   ├── 05_genetic_algorithm.ipynb
│   └── 06_boolean_mlp.ipynb

├── src/

├── images/

├── report/

└── hardware/
    └── (Future FPGA Implementation)
```

---

# Technologies Used

| Category | Technology |
|-----------|------------|
| Programming Language | Python |
| Numerical Computing | NumPy |
| Data Visualization | Matplotlib |
| Machine Learning | Scikit-learn |
| Deep Learning | PyTorch |
| Evolutionary Computing | PyGAD, TorchGA |
| Development Environment | Google Colab |

---

# Key Experiments

- Implementation of Boolean Logic Gates using Threshold Logic Units
- XOR Realization using Multi-Layer Perceptrons
- Decision Boundary Visualization
- Continuous XOR Classification
- Scikit-learn vs PyTorch Performance Comparison
- Genetic Algorithm Optimization of Neural Networks
- Boolean MLP Implementation
- Gate-Level Analysis of Learned Neural Architectures

---

# Experimental Results

| Experiment | Accuracy |
|------------|---------:|
| PyTorch Perceptron | **78.0%** |
| Improved Scikit-learn MLP | **97.5%** |
| Improved PyTorch MLP | **99.5%** |
| Genetic Algorithm XOR | **100%** |
| Boolean MLP XOR | **100%** |

---

# Roadmap

- [x] Threshold Logic Units
- [x] Boolean Logic Gates
- [x] XOR using Perceptrons
- [x] XOR using Multi-Layer Perceptrons
- [x] Continuous XOR Classification
- [x] Scikit-learn vs PyTorch Comparison
- [x] Genetic Algorithm Optimization
- [x] Boolean Neural Networks
- [ ] FPGA Implementation
- [ ] Verilog Design
- [ ] Hardware Synthesis
- [ ] Resource Utilization Analysis
- [ ] Latency & Power Benchmarking
- [ ] Edge AI Hardware Deployment

---

# Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/Boolean-Neural-Networks-Edge-AI.git
```

Navigate to the project directory:

```bash
cd Boolean-Neural-Networks-Edge-AI
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

# Future Extensions

The next stage of this work focuses on deploying Boolean Neural Networks onto FPGA hardware for efficient Edge AI inference.

Planned extensions include:

- FPGA implementation
- Verilog realization
- Hardware synthesis
- Resource utilization analysis
- Latency benchmarking
- Power consumption analysis
- Real-time Edge AI inference

---

# Research Internship

**Department of Computer Science and Engineering**

**Indian Institute of Technology Jammu**

**Duration:** May 2026 – June 2026

**Research Areas**

- Edge AI
- Neural Networks
- Boolean Neural Networks
- Genetic Algorithms
- Hardware Acceleration

---

# Acknowledgements

I sincerely thank **Prof. Soma Dhavala** for his guidance and mentorship throughout my Summer Research Internship at IIT Jammu.

This repository contains the implementation developed as part of the internship under his supervision. The organization of the repository, documentation, and future FPGA extension are maintained as part of my personal academic and professional portfolio.

---

# License

This project is licensed under the **MIT License**.
