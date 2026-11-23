# Mental Health Score Predictor

Predicts a student's mental health score (0–10) from their social media usage, sleep, study and activity habits.

- **Backend:** FastAPI serving a scikit-learn Random Forest pipeline (`Mental_Health_Model.pkl`)
- **Frontend:** plain HTML/CSS/JS (`index.html`) that calls the API
- **Training:** `ML_Project.ipynb` on the *Student Social Media And Mental Health Impact* dataset

> Based on [tanishq-latent/Mental-Health-Score](https://github.com/tanishq-latent/Mental-Health-Score).

## Run locally

Requires Python 3.10+.

```bash
git clone https://github.com/adi542/<your-repo-name>.git
cd <your-repo-name>
python -m venv venv
# Windows:      venv\Scripts\activate
# Mac / Linux:  source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

The API runs at http://127.0.0.1:8000. You can try it at http://127.0.0.1:8000/docs.

To use the UI, keep the server running and open `index.html` in your browser.

## Example request

`POST /predict`

```json
{
  "age": 20,
  "gender": "Male",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Entertainment",
  "avg_daily_usage_hours": 5,
  "daily_unlocks": 80,
  "study_hours": 3,
  "physical_activity_hours": 1,
  "sleep_hours_per_night": 6,
  "stress_level": "High"
}
```

Response:

```json
{ "predicted_mental_health_score": 5.67 }
```

## Disclaimer

This is a learning project trained on a small survey dataset. It is not a medical or psychological assessment.
