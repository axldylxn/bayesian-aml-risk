# Bayesian AML Risk Classifier
### Investment-Linked Insurance Product Risk Assessment

## Overview
Risk evaluation methodology designed for a major insurance company launching a new investment-linked insurance product with no historical transaction data available.

With 11 risk variables and no prior data to train a traditional ML model, a Bayesian approach with expert-assigned probability weights was designed to classify each product configuration as Low, Medium, or High AML/CFT risk.

Built during an AML/CFT compliance consulting engagement at Grant Thornton Mexico.

## Key Results
- Base product configuration (conservative profile, national client, AML limits): **98% Low risk**
- High-risk configuration (foreign client, aggressive profile, cash payments, no limits): **72% High risk**
- Model correctly discriminates across the full risk spectrum

## Risk Variables
| Variable | Description |
|----------|-------------|
| INV_FONDO | Investment fund type |
| BENEF_TERCERO | Third-party beneficiary |
| PERFIL_INVERSION | Investment profile |
| RESIDENCIA | Client residency |
| PAGO_METODO | Payment method |
| MONEDA_APORT | Contribution currency |
| TIPO_CLIENTE | Client type |
| TRANSFER_TERCERO | Third-party transfers |
| LIQUIDEZ | Liquidity permissions |
| LIMITE_INVERSION | Investment limits |
| CLIENTE_PERFILADO | Client profiling status |

## Methodology
When no historical data exists, Bayesian methods with structured expert knowledge outperform rule-based systems by providing probability distributions rather than binary classifications.

1. Expert elicitation of risk weights per variable combination
2. Probability matrix construction (26 product configurations)
3. Bayesian lookup classifier implementation
4. Scenario comparison: base vs high-risk configurations

## Stack
- **Language:** Python 3.13
- **Libraries:** pandas, matplotlib, seaborn
- **Original model:** R (codigo_riesgobayesiano.txt)
- **Data:** tabla_componentes_probabilidad.xlsx (expert-assigned priors)

## Files
- notebooks/bayesian_risk_classifier.ipynb — Python implementation and visualization
- codigo_riesgobayesiano.txt — Original R implementation
- data/tabla_componentes_probabilidad.xlsx — Probability matrix (4 sheets)
- bayesian-aml-risk.pdf — Full methodology document
- bayesian-aml-risk.pptx — Executive presentation
