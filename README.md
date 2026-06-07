# Verify Merge

Repositorio de validacao do Release Guardian.

Este repositorio contem Pull Requests reais para simular uma release homologada e uma branch de producao divergente.

## Cenario

- Producao: `main`
- Release: `release/25.4`
- PRs entregues na release: calculo de ferias, decimo terceiro e fechamento mensal.
- Apenas parte desses PRs deve chegar em producao, permitindo validar relatorios de pendencias.

## Relatorios esperados

Os relatorios em `reports/` documentam quais PRs estao na release e se chegaram em producao.

## Pull Requests reais

- PR #1: `Feature: calculo de ferias`, mergeado em `release/25.4` e promovido para `main` pelo PR #4.
- PR #2: `Feature: decimo terceiro`, mergeado em `release/25.4` e pendente em `main`.
- PR #3: `Feature: fechamento mensal`, mergeado em `release/25.4` e pendente em `main`.
- PR #4: promocao parcial para producao, usado para validar divergencia entre release e `main`.

## Como validar

Use o auditor apontando para este repositorio:

```powershell
npm run audit -- --repo . --base 9c1777d --release release/25.4 --production main
```

Resultado esperado:

- Total PRs: 3
- Em producao: 1
- Pendentes: 2
