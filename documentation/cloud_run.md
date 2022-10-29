# building and submiting to GCR

this did not work:
gcloud buildx build --platform linux/amd64 --tag gcr.io/united-impact-363519/youtube_stats_app:v1.0.0 --project="united-impact-363519"

# build image locally, push to GCR, deploy to cloud run
docker buildx build --platform linux/amd64 -t gcr.io/united-impact-363519/youtube_stats_app:v1.0.0 .

docker push gcr.io/united-impact-363519/youtube_stats_app:v1.0.0

gcloud run deploy --image gcr.io/united-impact-363519/youtube_stats_app:v1.0.0 --platform managed  --project=united-impact-363519 --allow-unauthenticated

