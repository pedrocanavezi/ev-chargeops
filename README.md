# EV ChargeOps

Projeto de referencia para planejar uma operacao de recarga de veiculos eletricos em condominios, frotas, estacionamentos ou pontos comerciais.

O repositorio organiza uma proposta inicial de produto, arquitetura, regras de negocio, dados de exemplo e plano de desenvolvimento para a Sprint 02. A ideia e deixar uma base simples para edicao, validacao tecnica e evolucao para um MVP.

## Objetivo

Criar uma plataforma que ajude operadores de recarga a:

- Registrar pontos de recarga e carregadores.
- Controlar sessoes de recarga por usuario, veiculo e unidade consumidora.
- Calcular rateio de energia por kWh, tempo, taxa operacional e regras do local.
- Gerar relatorios para cobranca interna ou repasse financeiro.
- Apoiar operacao com IA para analise de consumo, previsao de demanda e deteccao de anomalias.

## Estrutura

```text
assets/
  arquitetura-placeholder.txt      Diagrama textual em Mermaid
  data/exemplos-sessoes.csv        Dados ficticios de sessoes de recarga
docs/
  arquitetura.md                   Desenho funcional e tecnico da solucao
  base-regulatoria.md              Pontos regulatórios para validar
  fontes.md                        Fontes usadas e referencias de pesquisa
  modelo-rateio.md                 Regras de rateio e exemplos de calculo
  papel-ia.md                      Como IA entra no produto
  pesquisa-mercado.md              Contexto de mercado e personas
sprint-02/
  plano-desenvolvimento.md         Plano pratico da Sprint 02
```

## Como usar este material

1. Comece pelo plano em `sprint-02/plano-desenvolvimento.md`.
2. Ajuste as premissas de negocio em `docs/modelo-rateio.md`.
3. Revise os riscos regulatórios em `docs/base-regulatoria.md`.
4. Troque os dados ficticios em `assets/data/exemplos-sessoes.csv` por dados reais ou simulados mais proximos do seu cenario.
5. Use `docs/arquitetura.md` como base para desenhar telas, API e banco de dados.

## Escopo do MVP

O MVP deve provar tres coisas:

- O operador consegue cadastrar carregadores e sessoes de recarga.
- O sistema calcula consumo e valor a ratear de forma transparente.
- O usuario ou administrador consegue auditar a cobranca por sessao.

## Observacao

Este material nao substitui parecer juridico, regulatorio, contábil ou projeto eletrico assinado por profissional habilitado. A documentacao aponta referencias e decisoes pendentes para validacao.
