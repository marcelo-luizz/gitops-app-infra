# gitops-app-infra

Infraestrutura de aplicações provisionada via self-service.

## Como usar

1. Acesse o Backstage → Templates
2. Escolha o tipo de recurso (Bucket, PubSub, Service Account)
3. Preencha o formulário
4. O Backstage cria um PR neste repositório
5. Após merge, o recurso é provisionado automaticamente

## Recursos disponíveis

| Recurso | Claim Kind | Template Backstage |
|---------|------------|-------------------|
| GCS Bucket | `BucketClaim` | `app-infra-bucket` |
| PubSub Topic | `PubSubClaim` | `app-infra-pubsub` |
| Service Account | `ServiceAccountClaim` | `app-infra-service-account` |

## Contato

Platform Engineering — #platform-engineering no Slack
