# Base Regulatoria

## Pontos principais

A operacao de recarga de veiculos eletricos no Brasil deve considerar regras de energia eletrica, seguranca das instalacoes, normas tecnicas, relacao de consumo e regras internas do local de instalacao.

## ANEEL

A ANEEL informa que aprovou em 2018 a primeira regulamentacao nacional sobre recarga de veiculos eletricos, originalmente pela Resolucao Normativa 819/2018. A propria ANEEL informa que a Resolucao Normativa 1000/2021 consolidou regras anteriores, incluindo conteudos sobre recarga de veiculos eletricos.

Ponto relevante para o projeto: a REN 1000/2021 permite recarga de veiculos eletricos de terceiros na unidade consumidora onde esta a estacao, inclusive com exploracao comercial a precos livremente negociados, conforme texto disponibilizado pela ANEEL.

## Inmetro e normas tecnicas

Segundo pagina de perguntas frequentes do Inmetro, carregadores de veiculos eletricos sao abrangidos pela serie IEC 61851, internalizada no Brasil como ABNT NBR IEC 61851. A mesma pagina informa que, no momento consultado, nao havia regulamentacao do Inmetro nem exigencia de certificacao pelo Inmetro para sistemas de carregamento condutivo de veiculos eletricos.

Mesmo sem certificacao obrigatoria especifica, o projeto deve tratar seguranca eletrica como requisito central:

- instalacao dimensionada por profissional habilitado;
- protecao eletrica adequada;
- aterramento;
- identificacao do circuito;
- compatibilidade de potencia contratada;
- manutencao preventiva;
- registro de incidentes.

## Geracao distribuida

Se o local usar energia solar, autoconsumo, credito de energia ou outro arranjo de geracao distribuida, o modelo deve considerar a Lei 14.300/2022, que institui o marco legal da microgeracao e minigeracao distribuida, o Sistema de Compensacao de Energia Eletrica e o Programa de Energia Renovavel Social.

Para o MVP, a recomendacao e separar:

- custo de energia medido na conta ou tarifa configurada;
- credito de geracao distribuida, se houver;
- taxa operacional da infraestrutura de recarga;
- regra interna de rateio aprovada pelo local.

## Cuidados juridicos e operacionais

- Evitar prometer conformidade automatica sem validacao de especialista.
- Guardar historico de tarifas, leituras e regras usadas em cada cobranca.
- Deixar claro se a cobranca e comercial, reembolso, rateio condominial ou taxa interna.
- Validar regras de privacidade para dados de usuario, veiculo, placa e consumo.
- Validar normas de seguranca e responsabilidade por dano eletrico.

## Itens para validar antes de operar

| Tema | Pergunta |
| --- | --- |
| Energia | A carga instalada e a demanda contratada suportam os carregadores? |
| Cobranca | O modelo e venda comercial, reembolso, taxa condominial ou outro? |
| Medicao | O medidor usado para rateio e confiavel e auditavel? |
| Seguranca | A instalacao foi projetada e assinada por responsavel tecnico? |
| Dados pessoais | Ha base legal e aviso de privacidade para coletar dados de uso? |
| Tributacao | Ha emissao de nota, recibo, boleto condominial ou repasse interno? |
