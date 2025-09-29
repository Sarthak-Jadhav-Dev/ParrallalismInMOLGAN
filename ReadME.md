
---
<h1 align="center">
   &nbsp; 🚀 Implementing MOLGAN: Hybrid Quantum GAN for Molecule Generation &nbsp;
</h1>

<p align="center">
  A cutting-edge exploration into the world of molecular design using a Hybrid Quantum Generative Adversarial Network (HQ-Cycle-MolGAN). This project combines the power of quantum computing with classical machine learning to synthesize novel molecular structures, pushing the boundaries of chemical discovery!
</p>

---

## 🌟 Quick Glance & Project Status

[![GitHub last commit](https://img.shields.io/github/last-commit/your-username/ImplementingMOLGAN?style=for-the-badge&color=8A2BE2&label=Last%20Update%20%F0%9F%9B%A0)](https://github.com/your-username/ImplementingMOLGAN/commits/main)

[![Python Version](https://img.shields.io/badge/Python-3.9%2B-blueviolet?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![PyTorch Version](https://img.shields.io/badge/PyTorch-1.12%2B-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![PennyLane Version](https://img.shields.io/badge/PennyLane-0.29%2B-FF69B4?style=for-the-badge&logo=pennylane&logoColor=white)](https://pennylane.ai/)
[![Colab Compatible](https://img.shields.io/badge/Google_Colab-Yes-F9AB00?style=for-the-badge&logo=google-colab&logoColor=white)](https://colab.research.google.com/)

<br>

## 🌈 Project Highlights

*   ⚛️ **Quantum-Classical Hybrid GAN:** Leveraging PennyLane for quantum layers within a PyTorch GAN architecture.
*   🧪 **Molecule Generation:** Synthesizing molecular graphs from the QM9 dataset.
*   🔄 **Cycle-Consistency Loss:** Enhancing stability and reconstruction accuracy with a novel HQ-Cycle-MolGAN.
*   🏆 **Reward-Driven Optimization:** Guiding generation towards desired molecular properties (using a synthetic reward for now!).
*   📊 **WGAN-GP Training:** Stable and robust adversarial training with Gradient Penalty.
*   🖼️ **RDKit-Free Visualization:** Innovative graph and embedding visualizations without RDKit, ensuring broader compatibility.



---

## 📖 Notebook Explanations - Your Learning Path!

Dive deep into the insights and decisions behind this project. Each link provides a detailed timestamped explanation of the notebook's evolution.

*   [**Explanation of Notebook (14/09/2025, 12:21 pm)**](Link_To_First_Explanation_Doc) 🚀 - *Initial setup & foundational concepts.*
*   [**Explanation of Notebook (16/09/2025, 4:51 pm)**](Link_To_Second_Explanation_Doc) 💡 - *Deep dive into GAN training & quantum layers.*
*   [**Explanation of Notebook (17/09/2025, 3:51 pm)**](Link_To_Third_Explanation_Doc) ✨ - *Cycle-consistency, rewards, and advanced features.*

## 📘 Project Guides - Your Companion

Whether you're starting fresh or finalizing your understanding, these guides will navigate you through the project's journey.

*   [**Initial Guide**](Link_To_Initial_Guide_Doc) - *Getting started, environment setup, and basic understanding.*
*   [**Final Guide**](Link_To_Final_Guide_Doc) - *Comprehensive overview, advanced concepts, and deployment insights.*

---

## 🎨 Architecture & Implementation Journey

This project unfolds in two meticulously structured parts within the main notebook, guiding you from environment setup to a fully functional HQ-Cycle-MolGAN.

### Part 1: 🛠️ Testing Dependencies and Environment (Cells: 1-8)



This critical phase ensures your computational playground is perfectly set up for quantum and classical molecular generation.

*   <img src="https://media.giphy.com/media/l4hLDD1Q87Rj9yP4Q/giphy.gif" width="20" height="20"> **Dependency Installation:** `PyTorch`, `PyTorch Geometric`, and `PennyLane` are the core libraries, installed with care.
*   <img src="https://media.giphy.com/media/l4hLDD1Q87Rj9yP4Q/giphy.gif" width="20" height="20"> **Colab CUDA Fixes:** Tackling and resolving common compatibility issues with Colab's CUDA wheels for seamless GPU acceleration.
*   <img src="https://media.giphy.com/media/l4hLDD1Q87Rj9yP4Q/giphy.gif" width="20" height="20"> **RDKit Woes & Workarounds:** Encountered `RDKit` installation challenges due to Colab's Python upgrades (3.11/3.12) and environment conflicts. A fallback solution using `!pip install rdkit` was found for stability, but the project ensures full functionality *even without* RDKit for visualization.
*   <img src="https://media.giphy.com/media/l4hLDD1Q87Rj9yP4Q/giphy.gif" width="20" height="20"> **QM9 Dataset Loading:** The renowned QM9 dataset for molecular graphs is loaded and prepared for training.
*   <img src="https://media.giphy.com/media/l4hLDD1Q87Rj9yP4Q/giphy.gif" width="20" height="20"> **PennyLane Circuit Test:** Verifying the proper functioning of PennyLane quantum circuits, the heart of our quantum generator.

---

### Part 2: 🎯 Executing the System (Training & Testing) (Cells: 1, 2, 9-12)



This section is where the magic happens! We build, train, and evaluate our sophisticated Hybrid Quantum Cycle GAN for molecular generation.

#### ✅ Phase 1: Environment Setup & GPU Verification
*   **Status:** <img src="https://img.shields.io/badge/COMPLETED-4CAF50?style=for-the-badge&logo=checkmarx&logoColor=white"/>
*   **Description:** All dependencies installed, and GPU presence successfully verified. Ready for action!

#### ✅ Phase 2: Dataset Loading
*   **Status:** <img src="https://img.shields.io/badge/COMPLETED-4CAF50?style=for-the-badge&logo=checkmarx&logoColor=white"/>
*   **Description:** The QM9 dataset is loaded, and raw molecular data is transformed into graph vectors (adjacency matrices + atom features) suitable for neural network processing.

#### ✅ Phase 3: Generator + Cycle (Quantum Layer)
*   **Status:** <img src="https://img.shields.io/badge/COMPLETED-4CAF50?style=for-the-badge&logo=checkmarx&logoColor=white"/>
*   **Description:**
    *   **Quantum Generator:** Implemented a unique **Hybrid Quantum Generator** utilizing `PennyLane` with an 8-qubit variational quantum circuit at its core. This layer introduces quantum entanglement and superposition effects, potentially allowing for the exploration of a richer molecular latent space.
    *   **Cycle Network:** A crucial classical network that attempts to reconstruct the initial noise vector from a generated molecule. This serves as a vital sanity check, ensuring proper gradient flow through the complex generator and facilitating the upcoming cycle-consistency loss.

#### ✅ Phase 4: WGAN-GP Training
*   **Status:** <img src="https://img.shields.io/badge/COMPLETED-4CAF50?style=for-the-badge&logo=checkmarx&logoColor=white"/>
*   **Description:**
    *   **Model Definition:** Defined the `Generator` (our quantum-classical hybrid) and the `Critic` (a classical MLP).
    *   **Adversarial Training:** Implemented the **Wasserstein GAN with Gradient Penalty (WGAN-GP)**. This variant is chosen for its enhanced training stability and ability to avoid mode collapse, crucial for generating diverse molecular structures.
    *   **Training:** The models are trained on the prepared QM9 molecular graphs, with the generator learning to produce realistic molecules and the critic learning to distinguish real from fake.

#### ✅ Phase 5: HQ-Cycle-GAN
*   **Status:** <img src="https://img.shields.io/badge/COMPLETED-4CAF50?style=for-the-badge&logo=checkmarx&logoColor=white"/>
*   **Description:**
    *   **Cycle Consistency Loss:** Integrated a novel `Cycle Consistency Loss` (inspired by CycleGANs) into the GAN framework. This loss ensures that a generated molecule, when passed through the cycle network, can reconstruct the original noise input. Similarly, a real molecule passed through a *reverse* process should reconstruct its latent representation. This bidirectional mapping (`noise ↔ molecule ↔ noise`) significantly stabilizes training and improves the quality and interpretability of generated samples.
    *   **Upgrade:** The model is upgraded to `HQ-Cycle-MolGAN`, a robust hybrid quantum architecture.

#### ✅ Phase 6: Reward Integration (Synthetic, no RDKit)
*   **Status:** <img src="https://img.shields.io/badge/COMPLETED-4CAF50?style=for-the-badge&logo=checkmarx&logoColor=white"/>
*   **Description:**
    *   **Reward Signal:** Introduced a synthetic `reward signal` based on the graph variance of generated molecules. This simple yet effective reward guides the generator towards producing molecules with a wider range of structural diversity.
    *   **Final Objective:** The ultimate objective function for the `HQ-Cycle-MolGAN` now combines three powerful loss components:
        1.  **Adversarial Loss (GAN):** To generate realistic molecules.
        2.  **Cycle Loss (Consistency):** To ensure stable and reversible mapping.
        3.  **Reward Loss (Property Optimization):** To steer generation towards desirable (or diverse, in this case) properties.

---

## 🖼️ Visualization Without RDKit - Creative Solutions!

Given the persistent `RDKit` installation challenges within the Google Colab environment (due to Python version conflicts and package management intricacies), innovative alternative visualization methods were employed to inspect and understand the generated molecules.

*   **Graph Visualization (NetworkX + Matplotlib):**
    *   **Method:** Generated molecular vectors are converted into `NetworkX` graph objects.
    *   **Details:**
        *   **Nodes:** Represent atoms (Carbon, Oxygen, Nitrogen, Fluorine, Hydrogen) and are visualized with distinct colors/sizes.
        *   **Edges:** Represent chemical bonds (single, double, triple, aromatic) and are drawn with appropriate line styles or colors.
    *   **Purpose:** Allows for intuitive inspection of the generated molecular structure.
    *   **Example:** `visualize_graph(fake_vec)` # Draws a generated molecule as a graph

*   **Heatmaps:**
    *   **Method:** Visualization of the raw tensor data.
    *   **Details:**
        *   **Adjacency Tensor Slices:** Show the connectivity patterns.
        *   **Atom Features:** Display the one-hot encoded atomic properties.
    *   **Purpose:** Provides a low-level, detailed view of the neural network's output.

*   **Graph Embeddings (PCA/t-SNE):**
    *   **Method:** Real and generated molecule graphs are embedded into a lower-dimensional space.
    *   **Details:** Using dimensionality reduction techniques like `PCA` or `t-SNE`.
    *   **Purpose:** To visually compare the distribution of real vs. generated molecules, assessing the generator's ability to cover the data manifold.

<p align="center">
 
  <br>
  <em>(Conceptual GIF: Imagine beautiful NetworkX graphs of molecules appearing!)</em>
</p>

---

## ✅ Achievements - What We've Built!

We've successfully navigated complex quantum-classical integrations and challenging environment setups to build a powerful molecular generation system.

*   <img src="https://img.shields.io/badge/ACHIEVED-blue?style=for-the-badge&logo=pennylane&logoColor=white&color=9400D3"/> Environment setup for `PyTorch`, `PennyLane`, and `PyTorch Geometric` is robust.
*   <img src="https://img.shields.io/badge/ACHIEVED-blue?style=for-the-badge&logo=pytorch&logoColor=white&color=9400D3"/> `QM9` dataset loaded and preprocessed for graph neural networks.
*   <img src="https://img.shields.io/badge/ACHIEVED-blue?style=for-the-badge&logo=github&logoColor=white&color=9400D3"/> Implemented a cutting-edge **Hybrid Quantum Generator** and a `Cycle Network`.
*   <img src="https://img.shields.io/badge/ACHIEVED-blue?style=for-the-badge&logo=github&logoColor=white&color=9400D3"/> Trained a stable **Hybrid Quantum WGAN-GP** for molecular generation.
*   <img src="https://img.shields.io/badge/ACHIEVED-blue?style=for-the-badge&logo=github&logoColor=white&color=9400D3"/> Enhanced the model with **Cycle Consistency Loss** transforming it into `HQ-Cycle-MolGAN`.
*   <img src="https://img.shields.io/badge/ACHIEVED-blue?style=for-the-badge&logo=github&logoColor=white&color=9400D3"/> Successfully integrated a **synthetic Reward signal** (Phase-6) for property optimization.
*   <img src="https://img.shields.io/badge/ACHIEVED-blue?style=for-the-badge&logo=github&logoColor=white&color=9400D3"/> Developed and deployed robust **visualization methods without RDKit**.

---

## 🔜 Next Steps - The Road Ahead!

The journey doesn't end here! We have exciting plans to further enhance `ImplementingMOLGAN`.

*   ⚡ **CUDA Parallel Programming:** Integrate parallel processing with CUDA to significantly optimize training speeds for larger datasets and more complex models.
*   🧪 **Real Chemical Property Rewards:** Implement actual chemical property rewards (e.g., QED, LogP, Synthetic Accessibility - SA score) using `RDKit` once compatibility issues are fully resolved or via alternative libraries. This will enable generation of molecules with truly *desired* properties.
*   ✨ **Improved Molecule Decoding & Visualization:** Enhance the decoding process from graph tensors back into chemically meaningful structures and refine visualization tools for clearer and more interactive molecular representations.

---

## 📂 Repository Structure - Navigate with Ease!

```
ImplementingMOLGAN/
├── ImplementingMOLGAN.ipynb   # ✨ Main Jupyter Notebook with all code & explanations
├── data/                      # 📊 Directory for QM9 dataset files
├── models/                    # 💾 Saved trained Generator and Critic models
└── README.md                  # 📄 This glorious documentation!
```

---

## ▶️ How to Run - Get Started!

Embark on your MOLGAN adventure with these simple steps:

1.  **Open the Notebook:** Navigate to the `ImplementingMOLGAN.ipynb` file in this repository and open it directly in [Google Colab](https://colab.research.google.com/github/your-username/ImplementingMOLGAN/blob/main/ImplementingMOLGAN.ipynb).
    *   <p align="center">
          <a href="https://colab.research.google.com/github/your-username/ImplementingMOLGAN/blob/main/ImplementingMOLGAN.ipynb">
            <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
          </a>
        </p>
2.  **Run Part 1:** Execute all cells in the "Testing Dependencies and Environment" section (Cells 1-8).
    *   **⚠️ Heads Up:** If you encounter `pip` installation wheels hanging (especially for `RDKit`), don't panic! Rerun the provided fallback installation code within the notebook – it usually resolves the issue.
3.  **Run Part 2:** Proceed to execute all cells in the "Executing the System (Training & Testing)" section (Cells 1, 2, 9-12).
4.  **For Visualization:** Ensure `networkx` and `matplotlib` are installed (they are part of the initial dependency setup) to view the generated molecule graphs.

---

<p align="center">
  
</p>
<h3 align="center">
  Thank you for exploring ImplementingMOLGAN!
  <br>
  We hope this README sparks your curiosity and inspires further innovations in quantum-enhanced molecular design!
</h3>
<p align="center">
  ✨ Happy Generating! ✨
</p>

---
**Note to the user:**
*   Remember to replace `your-username` with your actual GitHub username in the badge links and the Colab link.
*   Replace `Link_To_First_Explanation_Doc`, `Link_To_Second_Explanation_Doc`, `Link_To_Third_Explanation_Doc`, `Link_To_Initial_Guide_Doc`, and `Link_To_Final_Guide_Doc` with the actual URLs to your detailed notebook explanations and guides. These could be markdown files, Google Docs, Notion pages, etc.
*   The GIFs are conceptual placeholders. GitHub Markdown doesn't support direct animated text or CSS animations. The "animation" is achieved through descriptive text, liberal use of emojis, and the inclusion of relevant (and ideally project-specific) GIFs to break up text and add visual interest. You can find free GIFs on platforms like Giphy or create your own.
*   The "animated badges" are implemented using `shields.io` which offers a wide range of colorful and informative badges. While they aren't *animated* in the GIF sense, they are dynamic and update.
