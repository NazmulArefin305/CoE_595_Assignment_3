# Object Detection and Distance Estimation through Reflective and Glassy Surfaces

This project investigates the robustness of object detection and distance estimation when objects are viewed through **reflective and glassy surfaces**, a known challenge for depth cameras. Using the **Intel RealSense D455** and a custom YOLOv11-based pipeline, we evaluated how transparent, frosted, and unobstructed environments affect depth accuracy.

## Objectives

* Assess depth estimation reliability behind reflective and glassy surfaces.
* Build a real-time system for object detection and distance measurement.
* Quantify errors across scenarios to understand limitations of depth sensing.

## Methodology

1. **Hardware & Calibration** – Intel RealSense D455 stereo depth camera with RGB-depth alignment.
2. **Data Collection** – 10 objects across 3 scenarios (reflective, transparent, no glass), multiple distances/locations.
3. **Annotation** – Manual labeling via Roboflow, exported in YOLO format.
4. **Model Training** – YOLOv11-small trained on custom dataset (10 classes, 60 epochs, Colab GPU).
5. **Distance Estimation** – Extracted median depth values from bounding box regions; stored results in structured CSVs.
6. **Evaluation** – Compared against ground-truth distances, computed Mean Absolute Error (MAE), and analyzed per-scenario performance.

## Results

* **YOLOv11 Model Performance:**

  * Precision: 0.986
  * Recall: 0.993
  * mAP\@0.5: 0.990
  * mAP\@0.5:0.95: 0.795
* **Scenario Findings:**

  * **No Glass (Unobstructed):** Highly stable, errors < 2 cm.
  * **Transparent Glass:** Moderate degradation, errors \~2–6 cm.
  * **Frosted Glass:** Severe degradation, errors up to 8–10 cm.

## Key Insights

* Frosted glass introduces the greatest error variance.
* Transparent glass maintains moderate stability.
* Unobstructed conditions yield optimal results.
* Real-time detection and distance estimation is feasible and efficient with YOLO + RealSense.

## Resources

* 📂 **Code:** [GitHub Repository](https://github.com/NazmulArefin305/CoE_595_Assignment_3.git)
* 📂 **Dataset:** [Download Here](https://kfupmedusa-my.sharepoint.com/:f:/g/personal/g202416760_kfupm_edu_sa/Emr3aJcLAUxIptZeJvgNv3QBJARIc466GfZE7OWctzXVbg?e=B4uHR2)

Do you want me to also create a **shorter one-paragraph abstract-style version** (for the very top of the README), or keep only this detailed summary?
