# 🌿 Vegetation & Soil Analysis Web App

An **AI-powered agricultural analysis system** that performs **vegetation segmentation** and **soil type detection** using YOLO models.  
Built with **FastAPI (backend)** and **React + Vite (frontend)**, this tool helps visualize vegetation coverage and soil health in a modern, interactive dashboard. 🌾

---

## ✨ Features

### 🪴 Vegetation Segmentation
- Detects vegetation areas using a YOLOv8 segmentation model.
- Generates:
  - Pure vegetation mask.
  - Overlay of mask on original image.
- Displays:
  - Vegetation coverage %  
  - Number of vegetation segments  
  - Processing time.

### 🏞️ Soil Detection
- Detects and classifies soil regions using YOLOv11 model.
- Draws bounding boxes with soil labels.
- Shows:
  - Count of detected regions  
  - Average confidence  
  - Breakdown by soil type.

### 💻 Modern Frontend
- Built with **React + Vite + Tailwind CSS**.
- Uses **ShadCN UI** components and **Lucide icons**.
- Two-tab interface:
  - Vegetation Segmentation
  - Soil Detection

---

## ⚙️ Tech Stack

| Layer | Technologies Used |
|--------|--------------------|
| **Frontend** | React, Vite, Tailwind CSS, ShadCN UI |
| **Backend** | FastAPI, Uvicorn, OpenCV, Pillow, NumPy, Ultralytics YOLO |
| **Language** | Python 3.10+, JavaScript (ESNext) |
| **Communication** | REST API with JSON + Base64 image responses |

---

## 🧩 Project Structure

veg-soil-app/
├── backend/
│ ├── main.py
| ├── Datasets/
| | ├──dataset.txt
| ├──Model_training/
| | ├──SoilDetectionModelTraining.ipynb
| | ├──VegetationSegmentationModelTraining.ipynb
│ ├── routers/
│ │ ├── vegetation.py
│ │ ├── soil.py
│ │ ├── health.py
│ ├── models/
│ ├── schemas/
│ ├── utils/
│ ├── requirements.txt
│ ├── .env.example
│ ├── best.pt # Vegetation model (not tracked)
│ ├── soil_best.pt # Soil model (not tracked)
│
├── frontend/
│ ├── src/
│ ├── components/
│ ├── package.json
│ ├── vite.config.js
│ └── .env.local.example
│
├── .gitignore
└── README.md



---

## ⚡ Getting Started

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/veg-soil-app.git
cd veg-soil-app

---

### 2️⃣ Setup the Backend

```bash

cd backend
python -m venv venv
venv\Scripts\activate   # (Windows)
# or
source venv/bin/activate  # (Mac/Linux)

pip install -r requirements.txt


Create a .env file:

VEG_MODEL_PATH=best.pt
SOIL_MODEL_PATH=soil_best.pt
CORS_ALLOW_ORIGINS=*


Run the FastAPI server:

uvicorn main:app --host 0.0.0.0 --port 8000

Backend runs at → http://localhost:8000


3️⃣ Setup the Frontend

cd ../frontend
npm install


Create .env.local:

VITE_FASTAPI_URL=http://localhost:8000


Start the frontend:

npm run dev

Frontend runs at → http://localhost:5173


| Endpoint              | Method | Description                        |
| --------------------- | ------ | ---------------------------------- |
| `/health`             | GET    | Check backend health               |
| `/predict/vegetation` | POST   | Run YOLOv8 vegetation segmentation |
| `/predict/soil`       | POST   | Run YOLOv11 soil detection         |



Example API Response
Vegetation Segmentation (/predict/vegetation)

{
  "width": 1024,
  "height": 1024,
  "mask_png_b64": "iVBORw0KGgoAAAANSUhEUgAA...",
  "overlay_png_b64": "iVBORw0KGgoAAAANSUhEUgAA...",
  "coverage_pct": 67.43,
  "segments": 5,
  "processingTime": 0.83
}


Soil Detection (/predict/soil)


{
  "width": 1024,
  "height": 1024,
  "boxes": [
    { "x1": 123, "y1": 145, "x2": 456, "y2": 312, "conf": 0.93, "label": "Alluvial Soil" }
  ],
  "annotated_png_b64": "iVBORw0KGgoAAAANSUhEUgAA..."
}



🪴 Dataset & Model Handling

Model weights (.pt files) and dataset files are not tracked in GitHub.

They are excluded by .gitignore:

__pycache__/
*.pt
*.pth
dataset/
data/


Keep them locally in:

backend/best.pt
backend/soil_best.pt
backend/dataset/

☁️ Deployment (Render / Railway)
🧠 Build Command
pip install -r requirements.txt

🚀 Start Command
uvicorn main:app --host 0.0.0.0 --port $PORT

🌍 Environment Variables
VEG_MODEL_PATH=best.pt
SOIL_MODEL_PATH=soil_best.pt
CORS_ALLOW_ORIGINS=*

🧠 Future Improvements

 Add multi-class vegetation segmentation.

 Include soil moisture prediction.

 Add authentication for private access.

 Deploy full stack on cloud (OCI / Render).

💚 Credits

Developed by Tejaswini Mohapatra
Guided & supported by Muhammad Sharique Raza

“Where data meets soil, insights grow.” 🌾

📜 License

This project is licensed under the MIT License.
You’re free to use, modify, and distribute it with attribution.