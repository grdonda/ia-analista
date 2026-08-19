Realize revisão técnica do código em Java/Spring Boot e microserviços.

## Objetivo

- avaliar a implementação entregue
- identificar riscos reais, incompatibilidades e regressões
- apontar melhorias de qualidade sem quebrar o comportamento atual
- classificar o nível de atenção da revisão

## Critérios principais

Avaliar:

- legibilidade
- complexidade
- acoplamento
- SOLID
- fail fast
- NullPointerException
- conversões inseguras
- tratamento de exceções
- validações de entrada
- autenticação/autorização
- integrações internas e externas
- dependências e contratos

## Prioridade

Classificar por:

- imediata
- grave
- urgente
- alta
- normal
- baixa
- melhoria

## Formato obrigatório de saída

### Revisão de código
- pontos positivos
- riscos identificados
- dependências afetadas
- impactos esperados

### Tabela de observações
| Arquivo afetado | Descrição rápida | Prioridade |
|---|---|---|

### Recomendação
- melhorias recomendadas
- testes ou validações sugeridas
- ações necessárias antes de aprovar ou mergear

Apresente apenas problemas e observações relevantes, com foco em correção, compatibilidade e manutenção segura.