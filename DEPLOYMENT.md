# Déploiement Cloud Run

## Pré-requis
- Google Cloud SDK (`gcloud`) configuré
- API Cloud Run et Cloud Build activées

## Build & Déploiement
```bash
gcloud builds submit --tag gcr.io/<PROJECT_ID>/feednly-video-processor
gcloud run deploy feednly-video-processor \
  --image gcr.io/<PROJECT_ID>/feednly-video-processor \
  --platform managed \
  --region <REGION> \
  --allow-unauthenticated \
  --set-env-vars PORT=8080
```

## Endpoint santé
```bash
curl https://<SERVICE_URL>/
```
