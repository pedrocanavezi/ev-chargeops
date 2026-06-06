# EV ChargeOps

Equipe: Pedro Henrique Canavezi - RM 570298

Projeto de referencia para planejar uma operacao de recarga de veiculos eletricos em condominios, frotas, estacionamentos ou pontos comerciais, com recorte tecnico para o desafio GoodWe.

O repositorio organiza a entrega da Sprint 01: contexto do problema, pesquisa de mercado, base regulatoria e tecnica, arquitetura, modelo de rateio, papel da IA, fontes consultadas e plano de desenvolvimento para a Sprint 02.

## Problema

A instalacao de carregadores de veiculos eletricos em condominios, estacionamentos, campus e pequenas frotas cria um problema operacional: quem usou, quanto consumiu, qual tarifa deve ser aplicada e como justificar o rateio de energia para usuarios e administradores.

Sem um sistema de controle, a operacao tende a depender de planilhas, leitura manual, cobranca pouco auditavel e baixa visibilidade sobre picos de demanda, falhas e uso indevido. O EV ChargeOps propoe uma camada de software para registrar sessoes, calcular custos e apoiar a gestao da infraestrutura de recarga.

## Relacao com o desafio GoodWe

A Sprint 01 considera como camada fisica de referencia o carregador GoodWe HCA G2. Pelas informacoes publicas da GoodWe, o equipamento oferece identificacao por RFID, conectividade por LAN, Wi-Fi, Bluetooth e RS-485, alem de integracao com a plataforma de monitoramento SEMS+.

Como nao ha acesso real ao ambiente SEMS Portal nesta etapa, a decisao tecnica do projeto e tratar a integracao como hipotese de evolucao:

- Sprint 01: modelagem do fluxo, dados simulados e importacao CSV de sessoes.
- Sprint 02: prototipo de ingestao com dados simulados no formato esperado.
- Evolucao futura: avaliar API SEMS Portal, exportacao da plataforma GoodWe ou leitura local via interfaces disponiveis, conforme documentacao e acesso autorizado.

## Objetivo do MVP

Criar uma plataforma que ajude operadores de recarga a:

- Registrar pontos de recarga e carregadores.
- Controlar sessoes de recarga por usuario, veiculo e unidade consumidora.
- Calcular rateio de energia por kWh, tempo, taxa operacional e regras do local.
- Gerar relatorios para cobranca interna ou repasse financeiro.
- Apoiar operacao com IA para analise de consumo, previsao de demanda e deteccao de anomalias.

## Sprint 01 - Frentes de pesquisa

### Frente 1 - Contexto e Problema

Opcao de aprofundamento escolhida: analise de mercado.

Resultado: o projeto foi posicionado para cenarios em que a recarga compartilhada precisa de controle operacional e financeiro, como condominios, estacionamentos, campus e frotas leves. A pesquisa indicou tres personas principais: administrador do local, usuario/motorista e responsavel financeiro ou operacional. O detalhamento esta em `docs/pesquisa-mercado.md`.

### Frente 2 - Base Regulatoria e Tecnica

Opcao de aprofundamento escolhida: APIs complementares e premissas de integracao.

Resultado: foram mapeados pontos da ANEEL, Inmetro, normas tecnicas e geracao distribuida que impactam o modelo de cobranca e operacao. Do lado tecnico, o projeto assume o GoodWe HCA G2 como carregador de referencia e documenta RFID, LAN, Wi-Fi, Bluetooth, RS-485 e SEMS+ como pontos de integracao a validar. O detalhamento esta em `docs/base-regulatoria.md`.

### Frente 3 - Arquitetura e IA

Opcao de aprofundamento escolhida: esquema da base de dados.

Resultado: foi definida uma arquitetura inicial com app web, API backend, banco relacional, modulo de ingestao, motor de rateio, relatorios e modulo de IA. Tambem foi proposto um modelo de dados inicial com entidades como Local, Carregador, Usuario, Veiculo, SessaoRecarga, Tarifa, Rateio e Auditoria. O detalhamento esta em `docs/arquitetura.md`.

## Diagrama de arquitetura

![Diagrama de arquitetura](assets/arquitetura.png)

O diagrama tambem esta descrito em Mermaid em `docs/arquitetura.md` para facilitar edicao.

## Modelo de rateio

O modelo de rateio usa como base:

```text
valor_energia = kwh_consumido * tarifa_kwh
valor_taxa = taxa_fixa_sessao + (valor_energia * percentual_operacional)
valor_total = valor_energia + valor_taxa - desconto
```

As regras, exemplos e pendencias estao em `docs/modelo-rateio.md`.

## Papel da IA

A IA entra como apoio operacional, nao como fonte de medicao ou decisao financeira automatica. Os usos previstos sao previsao de demanda, deteccao de anomalias, explicacao de cobranca, classificacao de incidentes e recomendacoes operacionais. O detalhamento esta em `docs/papel-ia.md`.

## Plano para Sprint 02

A Sprint 02 deve transformar a documentacao em prototipo navegavel ou MVP tecnico, priorizando cadastro de carregadores, importacao de sessoes simuladas, calculo de rateio e relatorio auditavel. O plano esta em `sprint-02/plano-desenvolvimento.md`.

## Estrutura

```text
assets/
  arquitetura.png                  Imagem do diagrama de arquitetura
  arquitetura-placeholder.txt      Diagrama textual em Mermaid usado como base
  data/exemplos-sessoes.csv        Dados ficticios de sessoes de recarga
docs/
  arquitetura.md                   Desenho funcional e tecnico da solucao
  base-regulatoria.md              Pontos regulatorios para validar
  fontes.md                        Fontes usadas e referencias de pesquisa
  modelo-rateio.md                 Regras de rateio e exemplos de calculo
  papel-ia.md                      Como IA entra no produto
  pesquisa-mercado.md              Contexto de mercado e personas
sprint-02/
  README.md                        Guia rapido da Sprint 02
  plano-desenvolvimento.md         Plano pratico da Sprint 02
```

## Fontes consultadas

As fontes estao consolidadas em `docs/fontes.md`. A lista inclui ANEEL, Inmetro, Lei 14.300/2022 e materiais publicos da GoodWe sobre HCA G2, datasheet e SEMS+.

## Como revisar este material

1. Comece pelo plano em `sprint-02/plano-desenvolvimento.md`.
2. Ajuste as premissas de negocio em `docs/modelo-rateio.md`.
3. Revise os riscos regulatorios em `docs/base-regulatoria.md`.
4. Troque os dados ficticios em `assets/data/exemplos-sessoes.csv` por dados reais ou simulados mais proximos do seu cenario.
5. Use `docs/arquitetura.md` como base para desenhar telas, API e banco de dados.

## Observacao

Este material nao substitui parecer juridico, regulatorio, contabil ou projeto eletrico assinado por profissional habilitado. A documentacao aponta referencias e decisoes pendentes para validacao.
