# Literature Survey

Oracle-D reviews sixteen recent research works (2021–2025) spanning social-media disaster classification, multimodal deep learning, weather-based flood prediction, and satellite-based flood mapping using Sentinel-1 SAR and Sentinel-2 optical imagery.

| # | Paper (Author, Year) | Method Used | Dataset | Result / Accuracy | Limitation / Gap |
|---|---|---|---|---|---|
| 1 | An ML-Based Approach to Leveraging Social Media for Disaster Type Classification (2025) | ML classifiers on multi-region Twitter data | Multi-region Twitter disaster dataset | Accuracy varies by region | Universal models overlook linguistic/cultural nuances across regions |
| 2 | Deep Learning Benchmarks for Social Media Image Classification for Disaster Response | CNN + Knowledge Distillation (teacher-student GAN) | Custom relabeled disaster image datasets | Not specified | Limited labeled image resources for training robust deep models |
| 3 | Khattar & Quadri, CAMM: Cross-Attention Multimodal Classification of Disaster Tweets (2022) | Cross-attention multimodal (text+image) | Twitter (Typhoon Hagupit) | 87.60% accuracy | Fails when only text or only image available |
| 4 | Koshy & Elango, Multimodal Tweet Classification using Transformer-Based Bidirectional Attention (2023) | Transformer bidirectional attention | Disaster tweet corpus | Not specified | Single social platform (Twitter) dependency |
| 5 | Kumbam & Vejre, FloodLense: ChatGPT-Based Real-Time Flood Detection (2024) | LLM (ChatGPT)-based framework | Real-time flood text/image data | Not specified | Relies on closed-source LLM, cost/latency for real-time use |
| 6 | Review of Deep Learning for Disaster Management in Social Media, EPJ (2024) | AdaBoost, GradBoost, RF, SVM | Nepal Earthquake 2015 (FIRE 2016, SMERP 2017) | 82.4% accuracy | Earthquake-specific only; traditional ML plateaus vs deep learning |
| 7 | AI to Identify Emergency Messages during Hurricane Harvey (2023) | Binary ML classification | Hurricane Harvey Twitter dataset | Binary classification only | No multi-category urgency classification |
| 8 | Haq et al., Enhancing Disaster Response with NLP, ETASR (2024) | Fine-tuned DistilBERT | Disaster tweet dataset | High predictive accuracy (English) | No Hinglish/regional-language handling |
| 9 | Disaster Assessment from Social Media using Multimodal Deep Learning (2024) | Cross-modal + self-attention fusion | Multiple benchmark disaster datasets | Not specified | Prior work mostly unimodal; fusion adds compute overhead |
| 10 | Social Media Data Analysis Framework for Disaster Response (2022) | SVM, Bernoulli/Multinomial NB, BERT | Earthquake + flood benchmark datasets | SVM 0.83/0.79 precision | Handcrafted feature models underperform transformers |
| 11 | Flood Prediction using ML, IJRASET (2023) | Rainfall-based prediction model | Rainfall data for Indian districts | Not specified | Many regions lack access to early-warning systems |
| 12 | Assessing Flood Vulnerability using ML, Geoscience Letters (2025) | ML on LULC + climate data | CMIP6 + IMD precipitation data | Not specified | Limited to specific coastal areas, not full regions |
| 13 | Konapala, Kumar & Ahmad, Exploring Sentinel-1 and Sentinel-2 Diversity for Flood Inundation Mapping (2021) | Deep learning fusion of SAR + multispectral bands | Sen1Floods11 (446 hand-labeled images, 11 flood events) | Fusion outperforms single-sensor models | Optical fails under cloud cover; SAR alone has speckle noise |
| 14 | Flood Mapping through Sentinel-1, Sentinel-2 Imagery and U-Net (2025) | U-Net on SAR + optical imagery | Tabasco, Mexico flood region | Accuracy improves with more data | Not validated on Indian conditions |
| 15 | Mapping Global Floods with 10 Years of Satellite Radar Data, Nature Comms (2025) | Deep learning flood detection on Sentinel-1 SAR only | 10 years of global Sentinel-1 SAR data | Consistent mapping through cloud cover | SAR-only; no optical fusion |
| 16 | Wieland et al., S1S2-Water: Global Dataset for Water Body Segmentation (2023) | Semantic segmentation dataset + benchmark models | Global Sentinel-1 + Sentinel-2 paired imagery | Establishes benchmark | General water-body focus, not disaster-response optimized |

## Identified Research Gaps

1. **Ground-truth verification gap** — social media and weather-based systems never visually confirm actual flood extent against satellite data.
2. **All-weather detection gap** — optical satellites (Sentinel-2) fail under cloud cover, exactly when floods/cyclones occur.
3. **Regional-language gap** — almost no research handles Hindi/Hinglish disaster content.
4. **Detection-to-action gap** — research stops at classification/mapping accuracy, rarely reaches an actionable dashboard.

Oracle-D addresses all four gaps by fusing SOCMINT (multilingual NLP), Sentinel-1/2 satellite verification, and a real-time first-responder dashboard into one pipeline.
