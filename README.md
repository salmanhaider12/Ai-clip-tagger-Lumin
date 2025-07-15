# 🎮 SmartClip AI Tagger – Lumin Prototype

This is a prototype built for **Lumin** that demonstrates how an AI-powered system can automatically **tag key frames from gaming clips** using OpenAI’s CLIP model.

---

## Features

- Upload **real gameplay clip frames** (screenshots from the Lumin app)
- Automatically selects the **most important frame** using scene-difference detection
- **Zero-shot tagging** with CLIP model (ViT-B/32)
- Uses custom tags: `clutch`, `headshot`, `fail`, `comedy`, `highlight`
- Outputs the **most relevant tag + confidence scores**

---

## Technologies Used

- Python (Google Colab / Streamlit)
- OpenAI CLIP `ViT-B/32`
- PyTorch
- PIL
- OpenCV
- Matplotlib

---

## How It Works

1. Upload multiple frames from a gameplay clip (e.g. extracted from a video or screen-recorded from Lumin).
2. The model automatically selects the **most dynamic or high-change frame** using simple frame difference analysis.
3. The selected frame is passed into the CLIP model to generate visual embeddings.
4. The model then compares these embeddings with predefined text labels using cosine similarity.
5. The **top tag(s)** are returned along with **confidence scores**.

---

## How We Select the Right Frame

In large video clips (millions of frames), it’s **computationally expensive** to analyze every frame.

To solve this, we apply a **two-stage filtering strategy**:

### 1. Down-Sampling  
We reduce the number of frames by sampling **1 frame per second** or detecting scene changes using histogram differences or other visual cues.

### 2. Key Frame Selection  
From the sampled frames, we apply:
- **Frame-to-frame difference detection** to find the moment of maximum change (i.e., high action or transition).
- Alternatively, we can use **optical flow** or **saliency** techniques to locate frames with peak visual or emotional impact.

This method ensures we extract the **most contextually relevant and meaningful moment** in the clip — not just a random still.



