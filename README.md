# Weather-Robust-and-Explainable-Object-Detection-for-Autonomous-Driving

📄 Overview
Autonomous driving relies heavily on robust perception, yet state-of-the-art object detectors (like YOLOv8) frequently fail under adverse weather conditions (heavy rain, fog, nighttime). Furthermore, existing solutions often function as "black boxes," lacking the transparency required for safety-critical deployment.
This project introduces a Unified Weather-Robust XAI Framework. Unlike traditional approaches that treat robustness and explainability separately, our architecture jointly optimizes three critical dimensions:
  - Adverse Weather Adaptation: using curriculum-based learning.
  - Uncertainty Quantification: measuring both data noise (Aleatoric) and model ignorance (Epistemic).
  - Real-Time Explainability: embedding class-conditioned saliency maps directly into the inference loop.

🚀 Key Features
  - Curriculum-Based Adaptation: A progressive training strategy that adapts the model from clear weather to synthetic augmentations, and finally to real-world complex datasets (DAWN, ACDC, CADC).
  - Dual-Uncertainty Estimation: Fuses Aleatoric and Epistemic uncertainty into a unified "Risk Score," allowing the vehicle to distinguish between confident detections and ambiguous hazards.
  - Embedded XAI: Generates real-time Grad-CAM visualizations during inference to justify every detection, ensuring the model focuses on relevant vehicle features (chassis/wheels) rather than background noise.
  - Weather-Aware Preprocessing: Includes illumination correction, de-raining, and contrast normalization.

📊 Performance
  - Accuracy: Achieved 74.2% mAP under severe weather conditions (Rain/Fog).
  - Improvement: Outperformed baseline detectors by over 12%.
  - Real-Time: Operates at 29 FPS on NVIDIA Jetson AGX Xavier, maintaining low latency (33ms) suitable for deployment.

🛠️ Architecture
The system consists of three integrated modules:
  1. Weather-Aware Preprocessing Module (MW) : Standardizes degraded inputs.
  2. Uncertainty-Aware Detection Module (MU) : Predicts bounding boxes + risk scores.
  3. Explainability Generation Module (ME): Produces spatial explanation maps.
     
📚 Datasets Used
  - DAWN: Diverse Adverse Weather Dataset.
  - ACDC: Adverse Conditions Dataset with Correspondences.
  - CADC: Canadian Adverse Driving Conditions.
