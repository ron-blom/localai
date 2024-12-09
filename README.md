https://github.com/go-skynet/helm-charts

helm repo add go-skynet https://go-skynet.github.io/helm-charts/
#helm install local-ai go-skynet/local-ai -f values.yaml

helm secrets upgrade --install local-ai ./local-ai -f values.yaml



curl http://192.168.110.13:8080/models/available
curl http://192.168.110.13:8080/models/apply -H "Content-Type: application/json" -d '{  "id": "model-gallery@bert-embeddings" }'

curl http://192.168.110.13:8080/v1/chat/completions -H "Content-Type: application/json" -d '{ "model": "gpt-4", "messages": [{"role": "user", "content": "How are you doing?", "temperature": 0.1}] }'    