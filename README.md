
Repositório central de infraestrutura usando GitOps + Crossplane.

## Fluxo
1. Dev cria recurso via Backstage
2. Backstage abre PR neste repositório
3. PR aprovado
4. ArgoCD aplica manifests
5. Crossplane cria recurso na Cloud

## Convenções
- Um recurso = um arquivo
- Separação por ambiente
- Ownership por pasta