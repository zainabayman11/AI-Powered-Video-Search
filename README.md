# 🎥 AI-Powered Video Search with CLIP

Search for specific scenes in videos using natural language queries in **English or Arabic**! This project uses OpenAI's CLIP model to find frames matching your text description from either uploaded videos or YouTube links.


## 🌟 Features

- 🔍 **Semantic Video Search**: Find specific scenes using natural language
- 🌐 **YouTube Support**: Search directly from YouTube videos without downloading
- 📁 **Local Video Upload**: Upload videos from your device
- 🌍 **Multilingual**: Supports both English and Arabic queries
- 🎯 **CLIP-Powered**: Uses OpenAI's CLIP for accurate image-text matching
- ⚡ **Fast Processing**: Efficient frame extraction and embedding
- 🎨 **User-Friendly Interface**: Built with Gradio for easy interaction

## 🚀 Demo

Search for "apple" or "تفاح" in a video and get relevant frames instantly!

```
Query: "girl singing" → Returns frames with people singing
Query: "sunset" → Returns frames with sunset scenes
Query: "تفاح" → Returns frames with apples (Arabic support!)
```

## 📋 Requirements

```bash
Python 3.8+
CUDA-compatible GPU (optional, but recommended)
```

## 🛠️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/video-search-clip.git
cd video-search-clip
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## 📦 Dependencies

Create a `requirements.txt` file with:

```
torch>=2.0.0
torchvision>=0.15.0
transformers>=4.30.0
gradio>=4.0.0
opencv-python>=4.8.0
yt-dlp>=2023.10.0
Pillow>=10.0.0
numpy>=1.24.0
sentencepiece>=0.1.99
protobuf>=3.20.0
```

## 🎮 Usage

### Run the application

```bash
python app.py
```

The Gradio interface will launch in your browser at `http://localhost:7860`

### Using the Interface

1. **Input Source**:
   - Upload a video from your device, **OR**
   - Paste a YouTube URL

2. **Search Query**: 
   - Enter your search term in English or Arabic
   - Examples: "car driving", "sunset", "تفاح", "بنت بتغني"

3. **Top-K Results**: 
   - Select how many matching frames you want (1-10)

4. **Click Search**: 
   - Get the most relevant frames with similarity scores



## 🧠 How It Works

1. **Frame Extraction**: Extracts frames from video (1 frame per second by default)
2. **Image Embedding**: Converts frames to CLIP embeddings
3. **Text Embedding**: Converts search query to CLIP embedding (with Arabic→English translation if needed)
4. **Similarity Search**: Computes cosine similarity between text and all frames
5. **Results**: Returns top-K most similar frames

## 🔧 Technical Details

### Models Used

- **CLIP**: `openai/clip-vit-large-patch14` for image-text matching
- **Translation**: `Helsinki-NLP/opus-mt-ar-en` for Arabic→English translation

### Key Improvements

✅ **YouTube Download Support**: Added `yt-dlp` integration for direct YouTube video processing  
✅ **Arabic Language Support**: Automatic translation from Arabic to English  
✅ **Better Error Handling**: Comprehensive error messages and status updates  
✅ **Larger CLIP Model**: Upgraded from base to large model for better accuracy  
✅ **Frame Validation**: Checks for successful video opening and frame extraction  

## 🎯 Use Cases

- 📺 Content creators finding specific scenes in long videos
- 🎬 Video editors searching for footage
- 📚 Researchers analyzing video content
- 🎓 Students extracting key moments from lectures
- 🔍 Anyone needing quick video content search

