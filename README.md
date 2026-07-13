# Visibility of Everyday Objects for Dogs: A Computer-Vision-Based Study Using Simulated Dichromatic Vision

## Research Problem
Everyday objects vary in visibility to dogs due to their dichromatic vision. Humans often misjudge which toys, tools, or items stand out in a dog's environment, leading to suboptimal choices in pet products, training aids, and enrichment activities. This project uses computer vision to simulate dog-like dichromatic color perception and quantify object salience through measurable contrast metrics.

## Research Question
How do object color, brightness, and background affect the visual salience of everyday objects under simulated dog-like dichromatic vision?

## System Overview
The system follows this pipeline:  
**Object image → Dog-like dichromatic simulation (color transformation) → ROI selection → Brightness & color contrast analysis → Visibility score calculation → CSV logging → Comparison graphs.**

It produces guaranteed results: processed images, `visibility_scores.csv`, and visual graphs for analysis. The first prototype uses static images in Google Colab with OpenCV, NumPy, Pandas, and Matplotlib. No actual dog testing is involved — this is an approximate simulation grounded in the 1989 Neitz et al. study.

## Main Prototype Functions
(See full details in `docs/YourName_System_Architecture.md` and the function table.)

- F1: Load and display images  
- F2: Apply dichromatic vision simulation  
- F3: Select object/background ROIs  
- F4: Calculate brightness contrast and visibility scores  
- F5: Save results to CSV  
- F6: Generate comparison graphs  

## Tools and Technologies
- **Core**: Python (Google Colab), OpenCV, NumPy, Pandas, Matplotlib  
- **Simulation**: Custom color transformation matrix approximating canine dichromatic vision (two-cone system: ~429nm blue, ~555nm yellow-green)  
- **Data**: Static images in `data/sample_data/`  
- **Output**: CSV logs and graphs in `results/`  

## Week 2 Progress
- Completed anchor paper reading and theory connection (`docs/YourName_Week2_Reading_Theory.md`)  
- Full system architecture diagram and prototype function table (`docs/YourName_System_Architecture.md`)  
- Guaranteed result plan with CSV + graphs  
- Research question and boundaries clearly defined  

## Current Challenges
- Fine-tuning the dichromatic transformation matrix for realistic but simple results  
- Consistent manual ROI selection (can be semi-automated later)  
- Expanding dataset while keeping prototype lightweight  

## Next Step (Week 3)
Implement the full prototype in Colab, test with 12+ images (4 colors × 3 backgrounds), validate scores against expected patterns (blue/yellow higher visibility), and prepare experimental variables for data collection.

