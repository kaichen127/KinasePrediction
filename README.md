# Kinase–Substrate Site Prediction
This is an official implementation of **Predicting Kinase-Specific Phosphorylation Sites with
Pretrained Protein Language Models** [link](https://www.biorxiv.org/content/10.1101/2025.03.12.642740v2.abstract).

| Project | Description | Usage |
|----------|-------------|-------|
| [Docker](./Docker) | Run the pretrained model entirely inside a Docker container. | Plug-and-play inference without local dependencies. |
| [Inference](./inference) | Run inference directly via Python (`inference.py`) and a config file. | For developers who want more control or integration. |

The method outputs **per-residue predictions** (binary binding masks) and **positive residue indices** for each substrate sequence. Probabilities for each predicted residue can be enabled in inference script.

---

## Model Overview
The model is a **transformer-based encoder–decoder** architecture that:
- Encodes a **substrate protein sequence** and a **kinase protein sequence** using a pretrained **ESMC backbone**.
- Applies a **Transformer decoder with cross-attention** to predict residue-level interaction sites.

---

## Pretrained Checkpoint
Download the pretrained model weights here:  
➡️ [Download `model_state.pth`](https://mailmissouri-my.sharepoint.com/my?id=%2Fpersonal%2Fdc57y%5Fumsystem%5Fedu%2FDocuments%2FKinase%20model%20checkpoint&ga=1)



After downloading, place it in:
```bash
# For Docker:
./Docker/model_state.pth

# For Python inference:
./inference/model_state.pth

```

## 📜 Citation

If you use this code or the pretrained models, please cite the following paper:

```bibtex
@article{pourmirzaei2025predicting,
  title={Predicting Kinase-Specific Phosphorylation Sites with Pretrained Protein Language Models},
  author={Pourmirzaei, Mahdi and Esmaili, Farzaneh and Chen, Kai and Pourmirzaei, Mohammadreza and Rezaei, Mohsen and Wang, Duolin and Xu, Dong},
  journal={bioRxiv},
  pages={2025--03},
  year={2025},
  publisher={Cold Spring Harbor Laboratory}
}

```
