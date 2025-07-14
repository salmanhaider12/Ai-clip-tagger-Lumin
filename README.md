# AI Clip Tagger for Lumin 🎮

This is a prototype built as part of the Lumin Internship AI Take-Home Task. It demonstrates an AI-powered system that automatically tags frames from gaming clips using OpenAI’s CLIP model.

##  Features

- Upload a gaming image frame
- Zero-shot tagging with CLIP model
- Custom tags: `clutch`, `headshot`, `fail`, `comedy`, `highlight`
- Output: most relevant tag + confidence scores

## Technologies

- Python (Google Colab)
- OpenAI CLIP (`ViT-B/32`)
- PyTorch
- PIL
- matplotlib

## How It Works

1. Upload a game frame (screenshot)
2. CLIP model embeds the image + text labels
3. Similarity is computed to pick the best matching tag
4. Output shows top tag with probability scores
