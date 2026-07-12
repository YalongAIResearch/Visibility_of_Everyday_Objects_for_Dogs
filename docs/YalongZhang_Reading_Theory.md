# Week 2 Reading and Theory Assignment

## Student Name
YourName

## Project Title
Visibility of Everyday Objects for Dogs: A Computer-Vision-Based Study Using Simulated Dichromatic Vision

## Assigned Anchor Paper
Color Vision in the Dog  
Neitz, J., Geist, T., & Jacobs, G. H.  
Visual Neuroscience, 1989.

## 1. Paper Summary
The 1989 paper by Neitz et al. investigates canine color vision through behavioral discrimination experiments on three domestic dogs. Using increment-threshold spectral sensitivity measurements and direct color-matching tests, the authors determined that dogs possess two classes of cone photopigments with peak sensitivities around 429 nm (short-wavelength, blue-sensitive) and 555 nm (longer-wavelength). This results in dichromatic color vision, allowing dogs to distinguish blue-yellow differences effectively while struggling with red-green distinctions—similar to human deuteranopia (red-green color blindness). The study refutes simplistic claims that dogs see no color and provides quantitative evidence of their limited but functional color perception.

## 2. Why This Paper Is Related to My Project
This paper supplies the biological foundation for simulating dog-like vision in a computer-vision system. My project uses image processing to approximate dichromatic perception and quantify object visibility (via brightness and color contrast) against backgrounds. Understanding the two-cone system directly informs the color transformation step in my prototype, enabling realistic simulation rather than crude grayscale conversion. It grounds the project in empirical science while allowing measurable, reproducible computer-vision outputs.

## 3. System Input, Method, and Output in the Paper
- **Input**: Controlled visual stimuli (lights of specific wavelengths) presented to dogs in behavioral tasks.
- **Method**: Behavioral discrimination experiments combined with spectral sensitivity measurements and color-matching tests to characterize cone photopigments.
- **Output**: Confirmation of dichromatic vision with specific spectral peaks and predictions about color discrimination abilities (strong blue-yellow, weak red-green).

## 4. Fundamental Theory Behind My Project
Dogs have dichromatic color vision and see a more limited color range than humans. They are mainly sensitive to blue-yellow differences, while red-green differences are harder for them to distinguish. My project applies this by implementing a simulated dog-like dichromatic vision pipeline. It processes everyday object images to estimate visual salience through brightness contrast and transformed color differences, producing observable metrics of object visibility rather than claiming exact replication of canine perception. This provides an approximate computer-vision simulation of dog-like dichromatic color perception.

## 5. Equations or Metrics I Can Use
I will use at least these two (with plans for more):

**1. Brightness / Luminance Approximation**  
For an RGB image:  
\[ \text{Brightness} = 0.299R + 0.587G + 0.114B \]  
This weights channels to approximate perceived luminance, crucial for simulating dog vision where brightness cues dominate in low-color-discrimination scenarios. Applied per-pixel or per-ROI.

**2. Brightness Contrast**  
\[ \text{Brightness Contrast} = |\text{Average Object Brightness} - \text{Average Background Brightness}| \]  
Measures how distinguishable an object is from its background in the simulated view. Higher values indicate better visibility.

**Additional (Visibility Score - Beginner-friendly version):**  
\[ \text{Visibility Score} = \text{Brightness Contrast} + \text{Color Difference} \]  
(or weighted: \( 0.5 \times \text{Brightness Contrast} + 0.5 \times \text{Color Difference} \)). Color Difference uses Euclidean distance in transformed (dichromatic-simulated) channels.

## 6. How These Equations Connect to My Prototype
These metrics operationalize the theory: after applying a dichromatic color transformation (matrix-based simulation of the two-cone system), I select object/background ROIs, compute brightness and color differences, derive a visibility score, log to CSV, and plot comparisons (e.g., blue/yellow vs. red/green objects). This directly supports the pipeline: Object image → dog-like color simulation → ROI selection → visibility score → CSV → bar chart. It enables testing hypotheses about color/background effects and generates the required graphs for evaluation.

## 7. One Limitation of the Paper or Method
The behavioral experiments were conducted on a small sample (three dogs) under controlled lab conditions, which may not fully capture natural variability in real-world lighting, motion, or individual differences across breeds. The simulation in my project is an approximation and cannot perfectly replicate a living dog's visual processing, attention, or higher-level cognition.

## 8. One Question I Still Have
How do factors like motion blur or varying illumination levels (beyond static images) further modulate object visibility in dichromatic vision, and how could video-based extensions of the simulation account for them?

## Required Final Section Table

| Required Item | Your Response |
| ----------------------------------------- | ------------- |
| My selected project | Project 6 — Visibility of Everyday Objects for Dogs |
| My assigned paper | Color Vision in the Dog (Neitz et al., 1989) |
| Main input in the paper | Controlled spectral light stimuli for behavioral tests |
| Main method in the paper | Increment-threshold spectral sensitivity and color-matching behavioral experiments |
| Main output in the paper | Evidence of dichromatic vision with specific cone peaks (~429nm and ~555nm) |
| Fundamental theory behind my project | Dogs have dichromatic color vision... (as explained in section 4) |
| Two equations or metrics I will use | Brightness approximation; Brightness Contrast (plus Visibility Score) |
| How the equations connect to my prototype | Enable ROI-based salience calculation after dichromatic transform, feeding CSV logging and graphing |
| One limitation of the method | Small sample size and lab conditions; simulation is approximate |
| One question I still have | Impact of motion/illumination on visibility in dynamic scenarios |
