# Elastic Stack Minimal Setup (NodePort + Auto Index Pattern)

This setup deploys:
- Elasticsearch (NodePort 30920)
- Kibana (NodePort 30601)
- Filebeat (to ship logs from Kubernetes containers)
- A Job that automatically creates the Kibana index pattern `logs-*` and sets it as default.

## Access
- Kibana: http://<node-ip>:30601
- Elasticsearch: http://<node-ip>:30920

## Deploy
1. Push this repo to GitHub.
2. Update `05-argocd-application.yaml` with your repo URL.
3. Apply the ArgoCD Application or sync via ArgoCD UI.

## Notes
- Dev/test only. No TLS or authentication.
- Index pattern will appear in Kibana Discover after Kibana is ready.
