# OpenShift AI Embedding Chat Application Demo

## Install OpenShift AI

1. Pipeline Operator
2. GPU Operator
3. Node Feature Operator
3-1. Node Feature Discovery NFD インスタンス作成
4. OpenShift AI Operator
4-1. Data Science Project作成
5. OpenShift GitOps Operator

## コンポーネントのデプロイ

### LLMサーバ、Vector DB、Object Storageのデプロイ

bootstrap/applicationsetディレクトリの`applicationset-bootstrap.yaml`を使ってデプロイします。

```
oc apply -f applicationset-bootstrap.yaml
```

### Chat アプリケーションのデプロイ

app/deploymentディレクトリの`application.yaml `を使ってデプロイします。
```
oc apply -f application.yaml
```

### 個別にデプロイ
個別にコンポーネントをデプロイする場合は、それぞれのディレクトリで
`
oc apply -k .
`
を実行

## Notebookの利用

OpenShift AI のワークベンチで Data Science Projectイメージを利用して、Notebookを実行します。

Embeddingしたデータの登録には、`Langchain-PgVector-ingest.ipynb`を利用します。
このノートブックはHuggingFaceからEmbeddingするための複数言語対応のモデルを取得するため、HuggingFaceのトークンを取得し　`!export HUGGINGFACEHUB_API_TOKEN="|REPLACE YOUR TOKEN|"` の部分に設定して実行します。
