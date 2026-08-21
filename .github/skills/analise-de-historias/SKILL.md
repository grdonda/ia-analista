---
name: analise-de-historias
description: Analisa histórias de negócio em arquivos Markdown, verifica existência, completude, dependências, referências, acessos, inconsistências e prepara refinamento técnico com tarefas e cenários Gherkin.
---

# Skill de análise de histórias

## Entrada obrigatória

A análise de requisito começa com o domínio e o identificador da história.
Localizar a história em `<dominio>/historias/<id>.md`.

Se o identificador vier com título, usar somente o identificador para localizar o arquivo.
Não procurar a história em outros domínios sem evidência ou autorização.

## Encerramento imediato

- Se o arquivo não existir, responder `História inexistente: <caminho esperado>` e parar.
- Se o arquivo existir, mas estiver vazio ou contiver somente espaços, responder `História vazia: <caminho>` e parar.
- Não analisar código, integrações ou arquivos relacionados quando a história for inexistente ou vazia.

## Verificação de completude

Ler toda a história e verificar, com base apenas em fatos observáveis:

- objetivo e comportamento esperado;
- contexto e escopo;
- regras de negócio;
- entradas, saídas e contratos;
- critérios de aceite verificáveis;
- serviços, sistemas e dependências envolvidos;
- integrações, dados, acessos e ambientes;
- referências externas e anexos;
- cenários de sucesso, validação, falha e exceção aplicáveis;
- observabilidade, auditoria ou rastreabilidade quando mencionadas ou necessárias ao comportamento descrito;
- consistência entre título, contexto, regras e critérios.

Analisar qualquer elemento citado ou necessário para compreender a história. Não limitar a análise a tecnologias, ferramentas ou tipos de recurso previamente enumerados.

## Referências e acessos

Para cada recurso mencionado, verificar e registrar quando houver evidência:

- tipo do recurso;
- nome ou descrição;
- arquivo, caminho, endereço ou URL;
- existência;
- acesso requerido;
- perfil ou usuário necessário;
- acesso verificado, não verificado ou não realizado;
- conteúdo disponível para análise;
- informação que falta para utilizá-lo.

Recursos podem ser documentos, planilhas, apresentações, imagens, protótipos, contratos, pastas compartilhadas, portais, plataformas, APIs ou qualquer outro artefato.

Não afirmar que um recurso está inacessível sem tentativa autorizada que comprove isso. Não inventar links, permissões, conteúdo ou existência.

## Registro factual de problemas

Quando houver informação insuficiente, não gerar refinamento definitivo. Registrar cada ocorrência com linguagem neutra e suficiente para entendimento independente:

| Classificação | Localização | Fato observado | Impacto | Esclarecimento necessário |
|---|---|---|---|---|

Usar classificações descritivas, como `informação ausente`, `informação parcial`, `ambiguidade`, `inconsistência`, `referência não localizada`, `acesso não verificado`, `dependência não confirmada`, `comportamento não definido`, `critério não verificável`, `risco identificado` ou outra classificação factual adequada.

O fato deve descrever o que está escrito ou o que não foi encontrado. O impacto deve explicar precisamente o que não pode ser definido, validado ou implementado. O esclarecimento deve formular a pergunta completa necessária para remover a incerteza. Não usar sugestões subjetivas nem atribuir culpa ao autor.

Se houver problemas, parar após apresentar os fatos, impactos e questionamentos necessários.

## História pronta

Se a história possuir informações suficientes para o refinamento, responder somente:

`A história <id> foi lida e está completa para o refinamento técnico.`

Parar e aguardar o pedido para prosseguir. Não produzir resumo executivo nem repetir template de análise.

## Refinamento técnico

Somente após a história estar completa e o usuário pedir prosseguimento:

1. identificar os serviços indicados;
2. localizar serviços correlacionados por contratos, chamadas, eventos, filas, dados ou configurações;
3. analisar dependências internas e externas;
4. distinguir fatos confirmados de itens não verificados;
5. gerar tarefas técnicas vinculadas à história;
6. gerar cenários de teste aplicáveis a cada tarefa;
7. informar quando outro agente for necessário em uma única linha antes de acioná-lo.

Considerar, quando aplicável, serviços, APIs, endpoints, bancos, caches, filas, eventos, mensageria, máquinas de estado, plataformas, feature toggles, autenticação, autorização, usuários, ambientes, configurações, logs, métricas, rastreamento e observabilidade. Não presumir uma tecnologia que não esteja confirmada.

## Nomenclatura e organização

Para a história `biarepv-1449`:

- História: `biarepv-1449 - Título.md`;
- Tarefa: `biarepv-1449 - Título.md`;
- Cenário: `CT001 - Título.md`, `CT002 - Título.md`, em sequência.

Manter os arquivos em:

```text
<dominio>/historias/<id>/
├── <id> - Título.md
├── tarefas/
└── testes/
```

`TP`, `TE` e `TS` são referências de configuração associadas aos cenários, não arquivos gerados.

## Template de tarefa

Cada tarefa deve informar:

- o que deve ser feito;
- como deve ser feito;
- onde deve ser feito;
- arquivos, módulos ou componentes relacionados;
- dependências e acessos;
- critérios de aceite;
- Definition of Ready (DoR);
- Definition of Done (DoD);
- exceções e comportamento esperado;
- logs e observabilidade;
- testes relacionados;
- estimativa base, margem e total dentro do ciclo de duas semanas.

Critérios de aceite comprovam o comportamento de negócio. DoR comprova que a tarefa pode começar. DoD comprova que a tarefa foi concluída com qualidade técnica e processual.

## Cenários de teste

Gerar cenários somente para comportamentos definidos na história, na tarefa ou confirmados no sistema. Usar títulos `CT001 - Título` em português normal.

O Gherkin deve ser básico, simples e completo para a tarefa. Usar somente as palavras-chave necessárias, em inglês e maiúsculas: `FEATURE`, `SCENARIO`, `GIVEN`, `WHEN`, `THEN`, complementando com `AND` ou `BUT` apenas quando necessário. O texto descritivo permanece em português normal. Não incluir estruturas Gherkin que não sejam necessárias e não inventar dados ou resultados.

Modelo:

```gherkin
FEATURE: Atualização dos dados do representante

SCENARIO: Atualizar representante com dados válidos
  GIVEN que o representante existe
  WHEN o usuário solicita a atualização com dados válidos
  THEN os dados do representante devem ser atualizados
```

Cada cenário deve conter, quando aplicável:

- objetivo;
- pré-condições;
- dados de entrada;
- passos;
- resultado esperado;
- evidências de resposta, persistência, eventos, logs ou rastreamento;
- referência à história, tarefa, `TP`, `TE` e `TS`.

Cobrir os fluxos aplicáveis, sem obrigatoriedade artificial: fluxo direto, validações, exceções, integrações, autorização, dados, idempotência, desempenho, regressão ou observabilidade.
