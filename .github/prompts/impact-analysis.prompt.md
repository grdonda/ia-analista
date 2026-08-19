Analise o impacto da alteração solicitada e determine o que precisa ser realizado, onde será aplicado e quais riscos podem aparecer.

## Objetivo

- identificar classes, DTOs, serviços, controllers e integrações afetados
- listar configurações e contratos impactados
- apontar dependências e regras de negócio envolvidas
- avaliar impacto em fluxos existentes
- indicar se a alteração pode afetar PF/PJ, validações e integrações externas

## Regras

- responder sempre em tabela
- usar o formato com arquivo afetado, descrição breve e prioridade
- classificar a prioridade em:
  - imediata
  - grave
  - urgente
  - alta
  - normal
  - baixa
  - melhoria
- evitar quebra de compatibilidade
- indicar riscos reais, não hipotéticos
- sugerir testes e validações quando a mudança exigir

## Formato obrigatório de saída

### Contexto da alteração
- o que precisa ser realizado
- onde será aplicado
- qual fluxo ou regra será afetado

### Impacto
| Arquivo afetado | Descrição rápida | Prioridade |
|---|---|---|

### Riscos e compatibilidade
- dependências e integrações impactadas
- risco de regressão
- efeitos em PF/PJ ou regras de negócio sensíveis
- validações necessárias

### Testes recomendados
- testes existentes que podem ser afetados
- testes que devem ser criados ou melhorados

Se houver endpoint ou entrada de dados, perguntar se deseja curl de teste manual ou OpenAPI/Swagger JSON para uso em Bruno/IDE.