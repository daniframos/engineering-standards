# Engineering Standards

Este repositório reúne diretrizes de engenharia para orientar agentes e contribuidores na criação, revisão e manutenção de projetos. O conteúdo atual está organizado como guias Markdown independentes, cada um voltado a um contexto de uso específico.

## O que há no projeto

- `global.md`: regras gerais de estilo, arquitetura, testes, commits e instruções para agentes.
- `react.md`: orientações para projetos frontend com React, incluindo componentes, TypeScript, estado, APIs, UX e testes.
- `spring.md`: padrões para aplicações Java com Spring Boot, cobrindo camadas, REST, validação, persistência, configuração e testes.
- `quarkus.md`: diretrizes para projetos Quarkus, com foco em Panache, OpenAPI, logs, transações, persistência e testes.
- `dotnet.md`: recomendações para soluções .NET, incluindo estrutura, comandos, estilo, testes, commits e segurança de configuração.

Todos os arquivos seguem a mesma estrutura base:

1. organização do projeto;
2. comandos de build, teste e desenvolvimento;
3. estilo de código e convenções de nomenclatura;
4. diretrizes de teste;
5. commits e pull requests;
6. instruções específicas para agentes.

## Como usar

Use `global.md` como guia padrão para qualquer projeto. Quando o trabalho envolver uma tecnologia específica, combine as regras globais com o arquivo correspondente:

- React: `global.md` + `react.md`
- Spring Boot: `global.md` + `spring.md`
- Quarkus: `global.md` + `quarkus.md`
- .NET: `global.md` + `dotnet.md`

As regras específicas complementam as regras globais. Quando houver conflito, siga primeiro as instruções explícitas do projeto em que o agente está trabalhando.

## Contribuindo

Mantenha os guias curtos, objetivos e acionáveis. Ao adicionar um novo guia, use a mesma estrutura dos arquivos existentes e escreva o conteúdo em inglês, salvo quando o objetivo do arquivo for documentação para leitores em português.

Use commits no padrão Conventional Commits, por exemplo:

```text
docs: add python agent guidelines
docs: update react testing guidance
```
