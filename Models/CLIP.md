# CLIP: Contrastive Language–Image Pretraining

## Overview
CLIP (by OpenAI) is a groundbreaking model that learns visual concepts from natural language supervision. It aligns images and text in a shared latent space.

---

## Architecture
1. **Text Encoder:** Based on Transformer architecture.
2. **Image Encoder:** Based on ResNet or Vision Transformer (ViT).
3. **Contrastive Learning:** The objective is to minimize the distance between matched image-text pairs while maximizing the distance for mismatched pairs.

---

## Applications
1. Zero-shot image classification.
2. Image-to-text and text-to-image retrieval.
3. Visual question answering.

---

## Code Example
```python
from transformers import CLIPProcessor, CLIPModel

model = CLIPModel.from_pretrained("openai/clip-vit-base-patch32")
processor = CLIPProcessor.from_pretrained("openai/clip-vit-base-patch32")

inputs = processor(text=["A dog"], images=["dog_image.jpg"], return_tensors="pt")
outputs = model(**inputs)
