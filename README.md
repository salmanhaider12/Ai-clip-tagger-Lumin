🎮 SmartClip AI Tagger – Lumin Prototype
This is a prototype for Lumin demonstrating how AI can automatically tag key frames from gameplay clips using OpenAI’s CLIP model.

Features
Upload real gameplay clip frames (screenshots from Lumin)

Automatically selects most important frame using scene-difference detection

Zero-shot tagging with CLIP model

Custom tags: clutch, headshot, fail, comedy, highlight

Output: most relevant tags + confidence scores

Technologies
Python (Google Colab / Streamlit)

OpenAI CLIP (ViT-B/32)

PyTorch

PIL

OpenCV

Matplotlib

 How It Works
Upload multiple frames from a gameplay clip (e.g. extracted from a video).

The model automatically selects the most dynamic or high-change frame using frame difference detection.

CLIP generates visual embeddings and compares them to your tag labels.

Outputs the most relevant tag + score.

🧩 How We Select the Right Frame:
In large video clips (millions of frames), it’s inefficient to tag every frame.
Instead, we apply a two-stage filtering process:

Down-sampling: Extract 1 frame per second or based on scene boundary detection.

Key Frame Selection: From the sample, we use frame-to-frame difference or motion peaks to choose the most meaningful frame (high action or scene shift).

This approach ensures we always tag the most contextually relevant moment, not just a random still.
