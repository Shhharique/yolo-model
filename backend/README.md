# Backend README
# Backend


## Setup
python -m venv .venv 
.venv\Scripts\activate
pip install -r requirements.txt


# Put your weights somewhere and export paths
export VEG_MODEL_PATH=/abs/path/to/veg/best.pt
export SOIL_MODEL_PATH=/abs/path/to/soil/best.pt


# Run
uvicorn main:app --host 0.0.0.0 --reload --port 8000 