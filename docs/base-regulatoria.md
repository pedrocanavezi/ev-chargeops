# Base Regulatoria

## Pontos principais

A operacao de recarga de veiculos eletricos no Brasil envolve energia eletrica, seguranca da instalacao, regra interna do local e relacao com o usuario que vai pagar ou reembolsar o consumo. Nesta Sprint 01, o objetivo foi mapear os pontos que afetam o MVP, nao fechar parecer juridico.

## ANEEL

A ANEEL informa que a primeira regulamentacao nacional sobre recarga de veiculos eletricos foi aprovada em 2018, pela Resolucao Normativa 819/2018. Depois, a Resolucao Normativa 1000/2021 consolidou regras anteriores, incluindo conteudos relacionados a recarga.

Para este projeto, o ponto mais importante e entender que a recarga de terceiros na unidade consumidora pode existir, inclusive com exploracao comercial a precos livremente negociados, conforme material da ANEEL. Mesmo assim, o modelo exato de cobranca precisa ser definido com cuidado: venda comercial, reembolso, taxa condominial ou rateio interno nao sao a mesma coisa na pratica.

## Inmetro e normas tecnicas

Na pagina de perguntas frequentes do Inmetro consultada, carregadores de veiculos eletricos aparecem relacionados a serie IEC 61851, internalizada no Brasil como ABNT NBR IEC 61851. A mesma fonte informa que, no momento consultado, nao havia regulamentacao do Inmetro nem exigencia de certificacao pelo Inmetro para sistemas de carregamento condutivo de veiculos eletricos.

Isso nao significa que a instalacao possa ser tratada de forma informal. Para o projeto, seguranca eletrica continua sendo requisito basico:

- instalacao dimensionada por profissional habilitado;
- protecao eletrica adequada;
- aterramento;
- identificacao do circuito;
- compatibilidade com carga instalada e demanda contratada;
- manutencao preventiva;
- registro de incidente ou falha.

## Geracao distribuida

Se o local usar energia solar, autoconsumo, credito de energia ou outro arranjo de geracao distribuida, o modelo deve considerar a Lei 14.300/2022. O sistema nao precisa resolver isso inteiro no MVP, mas precisa deixar os campos e regras separados para nao misturar coisas diferentes.

Na pratica, eu separaria:

- custo de energia pela tarifa configurada ou conta de energia;
- credito de geracao distribuida, se houver;
- taxa operacional da infraestrutura de recarga;
- regra interna aprovada pelo condominio, estacionamento ou frota.

## Cuidados juridicos e operacionais

- Nao prometer conformidade automatica sem validacao de especialista.
- Guardar historico de tarifa, leitura e regra usada em cada cobranca.
- Deixar claro se o valor cobrado e venda, reembolso, taxa condominial ou rateio.
- Tratar dados de usuario, veiculo, placa, RFID e consumo como informacoes sensiveis para a operacao.
- Validar normas de seguranca e responsabilidade por dano eletrico.

## Itens para validar antes de operar

| Tema | Pergunta |
| --- | --- |
| Energia | A carga instalada e a demanda contratada suportam os carregadores? |
| Cobranca | O modelo e venda comercial, reembolso, taxa condominial ou outro? |
| Medicao | O medidor usado para rateio e confiavel e auditavel? |
| Seguranca | A instalacao foi projetada e assinada por responsavel tecnico? |
| Dados pessoais | Ha base legal e aviso de privacidade para dados de uso, placa e RFID? |
| Tributacao | Havera nota, recibo, boleto condominial ou repasse interno? |

## Base tecnica GoodWe

Para a Sprint 01, o projeto usa o GoodWe HCA G2 como carregador de referencia. A documentacao publica da GoodWe indica RFID para acesso protegido, conectividade LAN, Wi-Fi, Bluetooth e RS-485, alem de integracao com SEMS+/SEMS Portal.

Premissas adotadas:

- RFID pode associar uma sessao a motorista, veiculo ou unidade.
- LAN e Wi-Fi podem servir para conectividade de rede se houver acesso autorizado.
- Bluetooth parece mais adequado para configuracao local ou operacao de curta distancia.
- RS-485 deve ser tratado como possibilidade tecnica, mas depende de documentacao e acesso ao equipamento.
- SEMS+/SEMS Portal fica como caminho de integracao futura, porque a Sprint 01 trabalha com CSV e dados simulados.

Pendencias:

- Confirmar se existe API publica, privada ou exportacao acessivel para sessoes do HCA G2.
- Confirmar campos disponiveis por sessao: inicio, fim, kWh, identificador RFID, status e erros.
- Validar politica de privacidade para dados coletados por RFID e telemetria.
- Validar se a leitura usada para cobranca tem precisao e rastreabilidade suficientes.
