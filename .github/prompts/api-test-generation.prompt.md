Analise a funcionalidade ou endpoint e gere um plano de teste prático.

## Objetivo

- identificar se a tarefa envolve entrada de dados e API
- gerar curl para testes manuais quando aplicável
- orientar uso de Swagger/OpenAPI quando o projeto já o expõe
- descrever entradas, headers, parâmetros e payloads esperados
- apontar riscos e cenários importantes

## Fluxo

1. Verificar se existe endpoint, controller, DTO ou contrato de entrada.
2. Identificar método HTTP, path, headers, query, path params e body.
3. Se o projeto já tiver Swagger/OpenAPI, orientar a rodar o serviço e validar diretamente no ambiente de homologação ou local.
4. Se não houver Swagger ou se a análise exigir mais clareza, gerar curl de exemplo com payload realista.
5. Explicar rapidamente o que a chamada faz e quais impactos a entrada pode causar.

## Formato obrigatório de saída

### Endpoint
- método
- path
- descrição breve

### Entrada esperada
- headers obrigatórios
- query/path params
- payload JSON

### Curl para teste
```bash
curl -X ...
```

### Cenários relevantes
- positivo
- negativo
- risco de integração ou negócio

### Observações
- segurança
- autenticação
- impacto da chamada

## Regras

- não inventar campos que não existam no código
- se a API já estiver documentada em Swagger, preferir orientação para uso do endpoint documentado
- priorizar exemplos executáveis e práticos
- quando houver integração externa, indicar risco e impacto
- responder em formato curto, técnico e útil para QA, testes manuais e code review
