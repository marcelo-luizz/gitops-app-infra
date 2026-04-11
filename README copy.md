# gitops-app-infra

Repositório de infraestrutura de aplicação gerenciado via GitOps (ArgoCD + Crossplane).

## Escopo

Recursos efêmeros e específicos de aplicações, provisionados via self-service:
- **Storage**: GCS Buckets
- **Messaging**: PubSub Topics + Subscriptions
- **IAM**: Service Accounts de aplicações
- **Compute**: Cloud Functions, Cloud Run (futuro)

## Estrutura

```
├── argocd/
│   ├── projects/app-infra.yaml
│   └── applicationsets/app-environments.yaml
└── environments/
    ├── integration/teams/<team>/<category>/
    ├── pre-prod/teams/<team>/<category>/
    └── prod/teams/<team>/<category>/
```

## Como solicitar um recurso

1. Acesse o **Backstage** → Templates → Escolha o recurso desejado
2. Preencha o formulário (nome, team, environment)
3. O Backstage cria um PR automaticamente neste repositório
4. Após aprovação + merge, o ArgoCD provisiona via Crossplane

## Os Claims usam XRDs definidos no gitops-core-infra

O developer escreve um `BucketClaim` (simples), e a Composition (definida pelo Platform Team) garante encryption, labels, lifecycle, etc.

## CODEOWNERS

- Times de produto podem aprovar PRs em `integration/`
- PRs em `prod/` requerem aprovação do Platform Team
