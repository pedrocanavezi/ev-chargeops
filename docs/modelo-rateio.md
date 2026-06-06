# Modelo de Rateio

## Objetivo

O modelo de rateio calcula quanto cada usuario deve pagar por uma sessao de recarga. Ele deve ser simples, auditavel e facil de explicar.

## Formula base

```text
valor_energia = kwh_consumido * tarifa_kwh
valor_taxa = taxa_fixa_sessao + (valor_energia * percentual_operacional)
valor_total = valor_energia + valor_taxa - desconto
```

## Campos necessarios

| Campo | Exemplo | Observacao |
| --- | --- | --- |
| kwh_consumido | 18.4 | Deve vir do carregador, medidor ou leitura validada. |
| tarifa_kwh | 0.92 | Valor configurado por local e vigencia. |
| taxa_fixa_sessao | 2.00 | Opcional, cobre custo operacional minimo. |
| percentual_operacional | 12% | Opcional, cobre manutencao e infraestrutura. |
| desconto | 0.00 | Opcional, usado para campanhas ou ajustes. |

## Exemplo

```text
kwh_consumido = 18.4
tarifa_kwh = R$ 0.92
taxa_fixa_sessao = R$ 2.00
percentual_operacional = 12%
desconto = R$ 0.00

valor_energia = 18.4 * 0.92 = R$ 16.93
valor_taxa = 2.00 + (16.93 * 0.12) = R$ 4.03
valor_total = 16.93 + 4.03 = R$ 20.96
```

## Variacoes de regra

| Cenario | Regra sugerida |
| --- | --- |
| Condominio residencial | Rateio por kWh, com demonstrativo mensal por unidade. |
| Estacionamento comercial | Preco por kWh + taxa por sessao ou por tempo. |
| Frota corporativa | Centro de custo por veiculo, motorista ou departamento. |
| Carregador gratuito | Registrar kWh e custo interno, sem cobranca ao usuario. |
| Horario de ponta | Tarifa por faixa horaria, se houver medicao confiavel. |

## Requisitos de auditoria

- Registrar tarifa usada em cada sessao.
- Guardar leitura inicial e final quando disponivel.
- Guardar origem do dado: carregador, CSV, medidor externo ou lancamento manual.
- Registrar usuario que alterou ou aprovou ajuste.
- Permitir recalculo simulado sem apagar o calculo original.

## Regras pendentes

- Definir se havera arredondamento por sessao ou apenas no fechamento mensal.
- Definir tratamento para sessoes interrompidas.
- Definir tolerancia para diferenca entre medidor do carregador e medidor geral.
- Definir valor minimo por sessao.
- Definir politica para isencao, cortesia ou erro operacional.
