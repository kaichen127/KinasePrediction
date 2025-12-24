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
➡️ [Download `model_state.pth`](https://mailmissouri-my.sharepoint.com/my?CT=1762894034365&OR=OWA%2DNT%2DMail&CID=ed7bf1d7%2D2196%2D46ef%2D6414%2D603daa7c905a&e=5%3A116f7edc372e494a824884deaa68b405&sharingv2=true&fromShare=true&at=9&id=%2Fpersonal%2Fdc57y%5Fumsystem%5Fedu%2FDocuments%2FKinase%20model%20checkpoint&FolderCTID=0x012000FD8061A658A93B4BB7BAE70D3A6E59D5)

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
