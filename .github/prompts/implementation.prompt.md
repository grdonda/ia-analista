Proponha a solução funcional mais simples possível, com foco em manutenção segura em Java/Spring Boot e microserviços.

## Objetivo

- resolver a demanda com menor impacto e menor risco
- preservar comportamento atual
- manter compatibilidade com integrações existentes
- detectar alterações necessárias em regras de negócio, validações, contratos e dependências

## Prioridades

1. Correção
2. Estabilização
3. Simplificação
4. Evolução
5. Refatoração

## Regras

- não realizar refatoração ampla sem necessidade
- preferir mudanças pequenas e isoladas
- validar se a solução pode afetar PF/PJ, contratos e integrações
- considerar impacto em filtros, regras, autenticação, persistência e APIs
- se houver entrada de dados, indicar se é necessário curl ou Swagger/OpenAPI para validação

## Formato obrigatório de saída

### Proposta de implementação
- o que será alterado
- onde será aplicado
- por que essa solução é a menor e mais segura

### Impacto
| Arquivo afetado | Descrição rápida | Prioridade |
|---|---|---|

### Riscos e dependências
- integrações afetadas
- regras de negócio impactadas
- risco de regressão
- validações necessárias

### Testes recomendados
- testes que devem ser criados ou ajustados
- casos negativos importantes

Responda sempre com foco em segurança, compatibilidade e qualidade, sem quebrar o que já existe.