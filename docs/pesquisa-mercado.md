# Pesquisa de Mercado

## Problema observado

O uso de carregadores compartilhados ainda tem uma parte pouco visivel: o fechamento operacional. Instalar o carregador resolve so uma parte do desafio. Depois disso, alguem precisa controlar quem usou, quanto consumiu, quanto deve pagar e se a infraestrutura esta funcionando bem.

Nos cenarios analisados, a dor aparece principalmente quando a recarga deixa de ser uso individual e passa a envolver varias pessoas ou unidades. Em condominio, por exemplo, uma cobranca mal explicada vira conflito. Em estacionamento, vira perda de controle comercial. Em frota, vira dificuldade para separar custo por veiculo ou motorista.

## Personas

| Persona | Dor principal | O que precisa |
| --- | --- | --- |
| Sindico ou administradora | Evitar discussao no rateio de energia. | Demonstrativo por unidade, usuario e periodo. |
| Operador de estacionamento | Cobrar recarga sem perder controle das sessoes. | Preco configuravel e relatorio confiavel. |
| Gestor de frota | Separar custo por veiculo, motorista ou area. | Centro de custo, auditoria e exportacao. |
| Motorista | Entender o valor cobrado. | Historico de sessoes e memoria de calculo simples. |
| Instalador ou integrador | Entregar algo alem da instalacao fisica. | Base de dados, regra de cobranca e suporte operacional. |

## Concorrentes e alternativas

| Alternativa | Ponto forte | Limite percebido |
| --- | --- | --- |
| Plataforma do fabricante do carregador | Tende a integrar melhor com o hardware da marca. | Pode prender a operacao a um ecossistema especifico. |
| Planilha manual | Comeca rapido e custa pouco. | Depende de digitacao, tem pouca auditoria e escala mal. |
| Administradora condominial | Ja participa da cobranca mensal. | Normalmente nao trata telemetria de recarga com detalhe. |
| Software de gestao de energia | Pode ser forte em medicao e indicadores. | Nem sempre cobre identificacao de motorista e rateio por sessao. |

## Recorte do EV ChargeOps

O projeto faz sentido se resolver primeiro o basico: registrar sessoes, calcular valor e explicar o resultado. Nao adianta comecar pela automacao completa se o modelo de cobranca ainda nao esta claro.

Diferenciais que podem ser testados no MVP:

- rateio por kWh com memoria de calculo;
- importacao CSV para nao depender de integracao real logo no inicio;
- cadastro de local, carregador, usuario e veiculo;
- relatorio mensal por unidade, usuario ou carregador;
- alertas simples para dados incompletos ou fora do padrao.

## Hipoteses de validacao

1. Administradores valorizam mais previsibilidade de cobranca do que automacao total no primeiro momento.
2. O MVP pode comecar com CSV se o fluxo de rateio for bem explicado.
3. Relatorio claro reduz contestacao mais do que um dashboard cheio de graficos.
4. A maior dor inicial e fechar o mes sem depender de ajuste manual.
5. IA gera mais valor no comeco como apoio de analise, nao como decisor financeiro.

## Metricas de sucesso

- tempo para fechar o rateio mensal;
- quantidade de sessoes com dado incompleto;
- quantidade de ajustes manuais por periodo;
- diferenca entre kWh medido e kWh rateado;
- numero de contestacoes de usuarios;
- uso dos carregadores por periodo;
- custo recuperado ou receita por local.
