# Oracle-D

**O**ptical **R**adar **A**nalysis for **C**risis **L**ocation and **E**mergency **R**esponse

B.Tech Major Project — Department of CSE (AI & ML), JSS Academy of Technical Education, Noida (AKTU)

Multilingual social media intelligence, all-weather satellite integration, and a real-time first-responder dashboard for disaster detection and response coordination in the Indian context.

## Team

| Name | Roll No. |
|---|---|
| Adarsh Kumar Pandey | 2300911530006 |
| Khushi Kumari | 2300911530068 |
| Avanish Kumar Singh | 2300911530035 |

**Guide:** Ms. Pooja Deswal, Department of CSE (AI & ML)

## Problem Statement

Disaster response in India is delayed by fragmented detection methods — social monitoring, satellite imagery, and weather data are each used in isolation, with no unified system to verify and act on disaster events in real time, especially in regional languages and under poor weather conditions.

## System Overview

Oracle-D is built on three integrated modules:

1. **SOCMINT (Multilingual Social Media Intelligence)** — NLP classifier detecting disaster-related content in Hindi, Hinglish, and English.
2. **All-Weather Satellite Integration** — Fusion of Sentinel-1 SAR (Optical Radar) and Sentinel-2 optical imagery for flood mapping under any weather condition.
3. **First-Responder Dashboard** — Real-time GIS dashboard combining both signals into a unified risk score with alerts and actionable tasks.

## Current Progress

- [x] Literature survey completed (16 papers reviewed) — research gap identified
- [x] Synopsis presentation and documentation submitted to guide
- [x] Satellite module: U-Net training/prediction pipeline set up (Sentinel-1 SAR flood segmentation, Sen1Floods11 India subset)
- [ ] Basic FastAPI backend + React frontend skeleton running locally
- [ ] Sentinel-2 optical fusion (currently SAR-only)
- [ ] SOCMINT NLP module (Hindi/Hinglish disaster classifier) — not started
- [ ] Fusion layer combining SOCMINT + satellite + risk score
- [ ] Dashboard integration with live map view
- [ ] Testing & evaluation against benchmark literature

## Tech Stack

- **Language & Core:** Python, Pandas, NumPy
- **NLP / SOCMINT:** Hugging Face Transformers (IndicBERT / DistilBERT), scikit-learn
- **Satellite Processing:** PyTorch (U-Net), rasterio, Google Earth Engine, Sentinel Hub
- **Datasets:** Sen1Floods11 (India subset), disaster tweet corpora, data.gov.in
- **Backend:** FastAPI
- **Frontend:** React (may migrate to Streamlit — TBD)
- **Deployment:** GitHub, (Streamlit Cloud / TBD)

## Project Structure

```
├── src/                # Satellite module: U-Net training & prediction scripts
├── backend/             # FastAPI backend
├── frontend/             # React frontend (dashboard)
├── dataset/              # Local dataset folder (gitignored — see Setup)
├── outputs/              # Model checkpoints & predictions (gitignored)
└── README.md
```

## Setup

### Prerequisites
- Python 3.11
- Node.js (LTS)
- Git

### Installation

```bash
git clone https://github.com/YOUR_USERNAME/Oracle-D.git
cd Oracle-D

python -m venv .venv
.\.venv\Scripts\activate        # Windows
pip install -r requirements.txt
```

### Dataset

This project uses the India subset of the [Sen1Floods11](https://github.com/cloudtostreet/Sen1Floods11) dataset (Sentinel-1 SAR imagery with hand-labeled flood masks). Due to size, it is not included in this repository — download instructions are in `docs/dataset_setup.md`.

### Running the satellite module

```bash
# Train
python src/train.py --epochs 25 --patch-size 256 --patches-per-image 24 --batch-size 8

# Predict on a single image
python src/predict.py --checkpoint outputs/checkpoints/best_unet.pt --input <path_to_image> --output <path_to_output>
```

### Running the website

```bash
# Terminal 1 — backend
.\run_backend.ps1

# Terminal 2 — frontend
cd frontend && npm install && npm run dev
```

## Roadmap

| Phase | Task | Status |
|---|---|---|
| 1 | Dataset collection & literature survey | Done |
| 2 | Satellite fusion module (SAR) | In progress |
| 3 | SOCMINT NLP classifier | Not started |
| 4 | Risk fusion layer | Not started |
| 5 | Dashboard integration | Not started |
| 6 | Testing & documentation | Not started |

## References

Full literature survey with all reviewed papers is available in `docs/literature_survey.md`.

---
*This is an active academic project under development. Last updated: 19/09/2026.*
