Avalie a estratégia de testes em Java/Spring Boot e microserviços.

## Objetivo

- verificar a cobertura existente
- identificar lacunas e riscos de regressão
- apontar cenários ausentes
- recomendar testes que devem ser criados, melhorados ou refatorados

## Critérios

Identificar:

- cobertura unitária
- testes de integração
- testes de contrato
- cenários de falha externa
- tratamento de erro
- casos de PF/PJ e regras específicas
- regressão em endpoints e integrações

## Prioridade

Classificar os testes e riscos por:

- imediata
- grave
- urgente
- alta
- normal
- baixa
- melhoria

## Formato obrigatório de saída

### Avaliação de testes
- cobertura atual
- lacunas identificadas
- riscos de regressão

### Tabela de testes
| Arquivo afetado | Descrição rápida | Prioridade |
|---|---|---|

### Recomendações
- testes que precisam ser criados
- testes que devem ser melhorados
- cenários críticos faltantes
- dependências e contratos que precisam ser validados

Sempre priorizar testes que aumentem segurança, confiabilidade e prevenção de regressão sem excessos de esforço.