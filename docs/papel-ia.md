# Papel da IA

## Objetivo

A IA deve apoiar a operacao, nao substituir medicoes, regras contratuais ou validacoes regulatórias. No MVP, ela deve funcionar como camada de analise e assistencia para administradores.

## Casos de uso

| Caso | Beneficio |
| --- | --- |
| Previsao de demanda | Estimar horarios com maior uso e evitar sobrecarga operacional. |
| Deteccao de anomalias | Sinalizar sessoes muito longas, kWh fora do padrao ou dados incompletos. |
| Explicacao de cobranca | Gerar resumo claro para administrador ou usuario. |
| Classificacao de incidentes | Organizar relatos de erro, falha no carregador ou interrupcao. |
| Recomendacao operacional | Sugerir manutencao, expansao de potencia ou mudanca de regra. |

## Entradas de dados

- historico de sessoes;
- potencia do carregador;
- horario de inicio e fim;
- kWh consumido;
- tipo de usuario;
- local e unidade;
- eventos de erro;
- tarifa vigente;
- clima e calendario, em fase futura.

## Saidas esperadas

- alertas de consumo fora do padrao;
- previsao simples por dia da semana e horario;
- resumo mensal de operacao;
- justificativa de cobranca em linguagem natural;
- lista de dados faltantes para fechar rateio.

## Limites

- IA nao deve alterar valores financeiros sem aprovacao humana.
- IA nao deve inventar leitura de medidor.
- IA nao deve emitir parecer regulatorio definitivo.
- IA nao deve expor dados pessoais sem controle de permissao.

## MVP recomendado

1. Criar regras deterministicas para anomalias basicas.
2. Gerar resumo textual do fechamento mensal.
3. Criar assistente para explicar uma sessao de recarga.
4. Evoluir para previsao estatistica quando houver historico suficiente.

## Exemplos de alertas

- Sessao sem leitura final.
- kWh igual a zero com tempo conectado maior que 30 minutos.
- Consumo acima de 2 desvios do padrao do usuario.
- Carregador com muitas sessoes interrompidas na semana.
- Diferenca entre soma das sessoes e medidor geral acima da tolerancia.
