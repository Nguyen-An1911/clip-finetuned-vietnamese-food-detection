# Vietnamese Local Food Image Retrieval with CLIP

A text-to-image retrieval system for Vietnamese local foods, built using CLIP and multilingual text embeddings.

Search for Vietnamese dishes using natural-language queries and retrieve the most relevant food images based on image-text similarity.

## 🚀 Live Demo

Try the Vietnamese Local Food Image Retrieval system here:

**[Open Live Demo](https://dc2151f0c906e62499.gradio.live)**

The demo allows users to:
- Search Vietnamese local foods using natural-language queries.
- Choose the number of retrieved images (Top-K).
- View retrieved images with similarity scores.

**Note:** This is a temporary Gradio link hosted through Google Colab. The demo is available only while the Colab runtime and Gradio application are running.

---

## 1. Project Overview

Vietnam has a rich and diverse food culture, with many traditional dishes having different names, ingredients, and regional variations.

This project aims to build a semantic image retrieval system that allows users to search for Vietnamese local foods using text queries.

**Example queries:**
- "Bánh bột lọc Quảng Bình"
- "Phở bò"
- "Bánh mì Việt Nam"

The system converts text queries and food images into feature vectors in a shared embedding space, then ranks images according to cosine similarity.

## 2. Features

- Text-to-image retrieval using natural-language queries.
- Multilingual text encoding with M-CLIP.
- Image encoding using OpenCLIP.
- Fine-tuned models for Vietnamese local-food retrieval.
- Precomputed image embeddings for faster retrieval.
- Interactive Gradio web interface.
- Top-K image retrieval with similarity scores.

## 3. Model Architecture

The system consists of two encoders:

| Component | Model |
|---|---|
| Image Encoder | OpenCLIP ViT-B-16-plus-240 |
| Text Encoder | M-CLIP XLM-Roberta-Large-Vit-B-16Plus |

Both encoders produce embeddings in a compatible vector space.

The system calculates cosine similarity between the text query embedding and the precomputed image embeddings.

## 4. Dataset

The dataset contains images of Vietnamese local foods across 30 categories.

| Split | Number of Images |
|---|---:|
| Training | 17,591 |
| Validation | 2,515 |
| Testing | 5,040 |
| **Total** | **25,146** |

The dataset is organized into three splits:
- `Train`
- `Validate`
- `Test`

Each split contains folders corresponding to food categories.

**Note:** Add the dataset source and usage permissions here.

## 5. How It Works

1. Load a text query from the user.
2. Encode the query using the M-CLIP text encoder.
3. Load the precomputed image embeddings.
4. Calculate cosine similarity between the query and all image embeddings.
5. Rank images by similarity.
6. Display the Top-K most relevant images.

## 6. Project Structure

```text
Vietnamese-Local-Food-Retrieval/
│
├── notebooks/
│   ├── 01_Training.ipynb
│   └── 02_Gradio_Deployment.ipynb
│
├── app.py
├── requirements.txt
├── README.md
│
└── assets/
    └── demo.png
```

**Note:** Update this structure to match the actual repository.

## 7. Installation

Clone the repository:

```bash
git clone <YOUR_REPOSITORY_URL>
cd Vietnamese-Local-Food-Retrieval
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## 8. Run the Demo

Run the application locally:

```bash
python app.py
```

Open the local Gradio URL displayed in your terminal.

**Online Demo:** [Try the Vietnamese Local Food Retrieval Demo](https://dc2151f0c906e62499.gradio.live)

*Note: The online demo currently uses a temporary Gradio share link hosted through Google Colab. A permanent deployment using Hugging Face Spaces is planned.*

## 9. Evaluation

The retrieval system will be evaluated using:

- Precision@K
- Recall@K

Evaluation results will be added after testing the model.

## 10. Future Improvements

- Improve Vietnamese food captions with regional information.
- Expand the dataset with more local dishes.
- Improve retrieval performance through further fine-tuning.
- Evaluate retrieval performance across different query styles.
- Deploy a permanent version using Hugging Face Spaces.

## 11. Acknowledgements

This project uses:

- [OpenCLIP](https://github.com/mlfoundations/open_clip)
- [Multilingual-CLIP](https://github.com/FreddeFrallan/Multilingual-CLIP)
- [Gradio](https://www.gradio.app/)
