# 🍜 Central Vietnamese Food Recognition with Fine-Tuned CLIP

[![Hugging Face Spaces](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Live%20Demo-blue)](LINK_HUGGING_FACE_CỦA_BẠN)
[![Python](https://img.shields.io/badge/Python-3.9%2B-green)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-orange)](https://pytorch.org/)

Fine-tuning OpenAI's CLIP (Contrastive Language-Image Pre-training) model on a custom dataset of Central Vietnamese cuisine, featuring an interactive Gradio web demo for real-time classification.

---

## 📌 Overview
Pre-trained Vision-Language Models (VLMs) like CLIP often struggle with fine-grained regional dishes due to cultural and visual domain gaps (e.g., distinguishing *Bún Bò Huế*, *Mì Quảng*, and *Cao Lầu*). This project adapts CLIP (`ViT-B/32` or `ViT-B/16`) to accurately classify Central Vietnamese dishes using contrastive fine-tuning and custom text prompts.

## 🚀 Live Demo
Try out the model directly in your browser via Hugging Face Spaces:  
👉 **[Interactive Gradio App](LINK_HUGGING_FACE_CỦA_BẠN)**

*(Gợi ý: Hãy chụp màn hình giao diện Gradio khi đang nhận diện thành công 1 món ăn, upload lên repo và chèn link ảnh vào dòng dưới đây)*
![Demo Screenshot](assets/demo_screenshot.png)

## 📊 Dataset & Methodology
* **Dataset:** Custom-curated dataset consisting of **[Tổng số ảnh, vd: 1,500]** images across **[Số lượng món, vd: 10]** signature Central Vietnamese dishes (e.g., *Bún Bò Huế, Mì Quảng, Bánh Xèo, Bánh Bèo, Cao Lầu,...*).
* **Data Split:** 80% Training / 10% Validation / 10% Testing.
* **Base Model:** OpenAI CLIP (`[Tên backbone bạn dùng, vd: ViT-B/32]`).
* **Training Setup:** Fine-tuned with Cross-Entropy / Contrastive Loss using AdamW optimizer (`lr=[tốc độ học, vd: 1e-5]`, `batch_size=[vd: 32]`, `epochs=[vd: 15]`).

## 📈 Evaluation Results
Fine-tuning significantly improved classification accuracy compared to the zero-shot baseline:

| Model Configuration | Top-1 Accuracy | Top-3 Accuracy |
| :--- | :---: | :---: |
| Zero-Shot CLIP (Baseline) | `[vd: 42.5%]` | `[vd: 68.0%]` |
| **Fine-Tuned CLIP (Ours)** | **`[vd: 89.2%]`** | **`[vd: 97.5%]`** |

## 🛠️ Installation & Local Usage

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/](https://github.com/)[USERNAME_CỦA_BẠN]/clip-finetuned-vietnamese-food-detection.git
   cd clip-finetuned-vietnamese-food-detection
