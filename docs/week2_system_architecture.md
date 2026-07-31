# YourName System Architecture and Prototype Design (Week 2)

## Part A — Project Information
| Item | Student Response |
| -------------------------- | ---------------- |
| Student Name | YourName |
| Date | July 2026 |
| Project Number | Project 6 |
| Project Title | Visibility of Everyday Objects for Dogs: A Computer-Vision-Based Study Using Simulated Dichromatic Vision |
| Main Research Problem | Everyday objects vary in visibility to dogs due to their dichromatic vision; humans often misjudge which toys or items stand out, leading to suboptimal choices in pet products and training aids. |
| Research Question | How do object color, brightness, and background affect the visual salience of everyday objects under simulated dog-like dichromatic vision? |
| Target User or Application | Pet owners, toy designers, and animal behavior researchers seeking data-driven insights into canine visual perception. |
| Main Input Data | Everyday object + background images (static RGB). |
| Main Output Result | Visibility scores, ranked objects, comparison graphs, and CSV logs. |

## Part B — System Input and Output
| Question | Student Response |
| ----------------------------------------------------------- | ---------------- |
| What data does your system collect? | RGB images of objects on varied backgrounds. |
| What tool or device collects the data? | Uploaded images or Colab webcam capture (static photos). |
| What does your system analyze? | Simulated dichromatic transformation + ROI brightness/color contrast. |
| What result does your system produce? | Numeric visibility scores and labels (e.g., High/Medium/Low salience). |
| What data file will be saved? | `visibility_scores.csv` |
| What graph or screenshot will prove that the system worked? | Bar chart comparing visibility scores across colors/backgrounds; before/after simulation images. |

## Part C — System Architecture Diagram
```mermaid
flowchart LR
    A[Everyday Object Images<br/>(Uploaded or Webcam)] --> B[Image Collection & Resize]
    B --> C[Preprocessing<br/>(OpenCV resize, normalization)]
    C --> D[Dog-Like Dichromatic Vision Simulation<br/>(Color transformation matrix)]
    D --> E[Manual Object/Background ROI Selection]
    E --> F[Brightness & Color Contrast Analysis]
    F --> G[Visibility Score Calculation]
    G --> H[Result Display<br/>(Simulated images + scores)]
    G --> I[CSV Data Logging<br/>(Pandas)]
    I --> J[Evaluation<br/>(Matplotlib Bar/Scatter Graphs)]
```
