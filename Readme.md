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

