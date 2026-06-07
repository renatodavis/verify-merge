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
