# Fator Momentum no Ibovespa

Trabalho de programação sobre Factor Investing. O programa escolhe as 10 ações do Ibovespa (carteira vigente em março de 2024) com maior momentum 12-1, usando só dados até 27/03/2024. Depois simula a compra de R$ 100.000 em 28/03/2024, com pesos iguais, e mantém até 01/07/2026 (buy and hold). O resultado é comparado com o Ibovespa e o CDI.

**Momentum 12-1:** retorno de 12 meses atrás até 1 mês atrás (de 22/03/2023 a 27/02/2024). O último mês fica de fora porque, no curto prazo, as ações tendem a devolver parte do movimento.

## Como rodar

```bash
python3 -m venv .venv
.venv/bin/pip install pandas numpy matplotlib
.venv/bin/python momentum.py
```

No VS Code, também dá para abrir `momentum.py` e rodar célula por célula (**Run Cell**).

Os gráficos e as tabelas são salvos em `resultados/`.

## Arquivos

| Arquivo | O que é |
|---|---|
| `momentum.py` | **O programa.** Momentum, filtros, ranking, carteira, indicadores e gráficos |
| `dados/` | Dados prontos: universo, preços ajustados, volume, CDI e Ibovespa |
| `resultados/` | Gráficos e tabelas gerados pelo programa |

## De onde vêm os dados

Os dados são os mesmos do trabalho de Baixa Volatilidade do grupo, para que todos os fatores usem a mesma base:
https://github.com/gabrielmeloboaventura/Baixa_Volatilidade_Ibovespa

- **Composição do Ibovespa vigente em março de 2024:** B3.
- **Fechamento e volume financeiro:** arquivo oficial de cotações da B3 (COTAHIST).
- **Proventos e desdobramentos:** brapi e Yahoo Finance, conferidos com a Fundamentus e a B3.
- **CDI:** Banco Central, série SGS 12.
- **Ibovespa:** B3.

Eventos tratados que afetam esta carteira: a incorporação da BRF (BRFS3) pela Marfrig em 22/09/2025 (0,8521 ação da Marfrig por ação da BRF) e a bonificação da Cyrela (CYRE3) em ações CYRE4 em 02/01/2026. A coleta e as correções estão na pasta `preparacao_dados` do repositório acima.
