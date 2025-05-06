# 🖼️ Leonardo da Vinci Painting Embeddings with ResNet34

This project downloads images of Leonardo da Vinci's artworks, processes them through a pretrained **ResNet34** model, and extracts **512-dimensional embeddings** for each image.

---

## 📦 What This Project Does

1. **Download Images**  
   Uses `bing-image-downloader` to fetch up to 500 images of *Leonardo da Vinci artworks*.

2. **Clean Up and Flatten Files**  
   - Moves `.jpg` files from nested folders into a flat `paintings/` directory  
   - Renames images to prevent filename conflicts

3. **Generate Embeddings**  
   - Loads a pretrained `ResNet34` model from PyTorch  
   - Removes the classification head to use it as a feature extractor  
   - Transforms and embeds each image into a 512-dim vector

4. **Handle Corrupted Files**  
   - Skips unreadable images  
   - Deletes corrupted files from disk

5. **Save Embeddings**  
   - Embeddings are saved to a `.pickle` file for future use  
   - A validation check ensures all embeddings are saved correctly

---

## 🗂️ Output
- `paintings/`: Cleaned and renamed image files  
- `paintings_embeddings.pickle`: Dictionary mapping image paths to embeddings

---

## ✅ Dependencies
Make sure to install:
```bash
pip install bing-image-downloader torch torchvision pillow tqdm