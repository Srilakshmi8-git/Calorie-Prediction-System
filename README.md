# Calorie Prediction Backend

## Setup

1. Create and activate virtualenv:

```bash
python3 -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Place your .pth models in app/models/.

Place segmented images in app/static/segmented/.

Original images will be saved to app/static/original/ on upload.

Put your calorie_mapping.csv in app/.

Run backend server
bash
Copy
Edit
cd app
uvicorn main:app --reload 
API endpoint
POST /predict
Accepts multipart form data with key file for original image upload.

Returns JSON with:

json
Copy
Edit
{
  "original_image_url": "/static/original/<filename>",
  "segmented_image_url": "/static/segmented/<filename>.png",
  "predicted_class": "<class>",
  "calorie_count": <int or string>
}
http://127.0.0.1:8000/docs#/
