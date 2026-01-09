# Skateboard Trick Recognition through an AI-based Approach

> **[Click here to read the full thesis](thesis_kris.pdf)**

> **[Click here to go to the project files](https://github.com/Krissal1234/Bsc_Thesis_Project)**
---

## Project Overview
 This research explores an AI-based approach to automate the identification of skateboard tricks from video data.  The primary goal is to enhance viewer engagement on digital platforms and live-streamed events by providing real-time trick classification through digital overlays.

 This project was submitted in partial fulfilment of the requirements for the degree of **Bachelor of Science in Information Technology (Honours)** at **L-Università ta' Malta** in June 2024.

---

## Technical Architecture
 The study evaluates four Deep Learning architectures that combine Convolutional Neural Networks (CNNs) for spatial feature extraction with Recurrent Neural Networks (RNNs) for temporal sequence modelling.

<div align="center">
  <table border="0">
    <tr>
      <td align="center">
        <img width="428" height="500" alt="Screenshot from 2026-01-10 00-14-43" src="https://github.com/user-attachments/assets/b8f854e4-6b64-4ec8-a2db-64153676e388" />
        <br /><i>Figure: Data flow pipeline from raw video to trick classification.</i>
      </td>
    </tr>
  </table>
</div>



###  Evaluated Architectures:
* **VGG16-LSTM / VGG16-BiLSTM**
* **ResNet50-LSTM / ResNet50-BiLSTM**

---

## Methodology & Preprocessing
 To address the challenges of limited data and complex human movement, the research implemented three key preprocessing strategies:

1.   **Optical Flow Extraction**: Farneback’s algorithm was used to extract frames with the most significant motion, ensuring the model focuses on the actual trick execution rather than static backgrounds.
2.   **Data Augmentation**: Techniques such as rotation, scaling, and brightness manipulation were applied to artificially expand the dataset by 200%, resulting in a **7.75% improvement** in model accuracy.
3.   **PCA (Principal Component Analysis)**: Dimensionality reduction was utilised to remove redundant data components, significantly reducing training costs while improving generalizability.

<div align="center"> <img width="624" height="199" alt="Optical Flow Representation" src="https://github.com/user-attachments/assets/32874808-8a2a-4b97-9de5-40a8686b419e" /> <br /><i>Figure: Representation of Optical Flow used for intelligent frame extraction.</i> </div>

---


## Key Results
 The results confirm that Deep Learning models can effectively classify complex sport manoeuvres from video data.
 
<div align="center"> 
  
| Model | Highest Accuracy achieved |
| :--- | :--- |
| **VGG16-BiLSTM** |  **88%**  |
| VGG16-LSTM |  86%  |
| ResNet50-BiLSTM |  86%  |
| ResNet50-LSTM |  80%  |
  
</div>

### Findings:
*  **Model Performance**: Bidirectional LSTM (BiLSTM) variants consistently outperformed standard LSTMs by capturing temporal patterns from both past and future contexts.
*  **Ruggedness**: Despite a Ryzen 5 3600 CPU-only training environment, the implementation of PCA allowed for highly efficient hyperparameter tuning.
*  **Class Observations**: The models showed exceptional performance in identifying **Pop-Shuvits** (100% accuracy in BiLSTM variants) but faced minor challenges differentiating between **Ollies** and **Kickflips** due to shared visual characteristics in the initial "pop" phase.

---

## Acknowledgements
*  **Supervisor**: Dr. Joseph Bonello.
*  **Data Contribution**: Hanxiao Chen (Author of SkateboardAI).
