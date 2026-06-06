# Pesquisa de Mercado

## Problema

A expansao de veiculos eletricos cria demanda por infraestrutura de recarga em condominios, estacionamentos, empresas e frotas. O problema operacional nao e apenas instalar carregadores: tambem e medir consumo, cobrar corretamente, prestar contas e manter a infraestrutura confiavel.

## Personas

| Persona | Dor principal | O que precisa |
| --- | --- | --- |
| Sindico ou administradora | Evitar conflito no rateio de energia. | Demonstrativo claro por unidade e usuario. |
| Operador de estacionamento | Monetizar recarga sem perder controle operacional. | Preco configuravel e relatorio por periodo. |
| Gestor de frota | Controlar custo por veiculo e motorista. | Centro de custo, auditoria e exportacao. |
| Motorista | Entender quanto consumiu e quanto pagou. | Recibo simples e historico de sessoes. |
| Instalador ou integrador | Entregar solucao completa ao cliente. | Cadastro de locais, regras e suporte tecnico. |

## Concorrentes e alternativas

| Alternativa | Forca | Fraqueza |
| --- | --- | --- |
| Plataforma do fabricante do carregador | Integracao nativa com hardware. | Pode prender o cliente a uma marca. |
| Planilha manual | Rapida e barata. | Baixa auditoria, erro manual e dificil escalabilidade. |
| Administradora condominial | Ja tem relacionamento financeiro. | Nem sempre entende telemetria e medicao de recarga. |
| Software de gestao de energia | Forte em energia. | Pode nao cobrir experiencia do usuario de recarga. |

## Diferenciais possiveis

- Rateio transparente e auditavel.
- Importacao CSV para operar mesmo sem integracao completa.
- Suporte a diferentes modelos: condominio, estacionamento e frota.
- IA para alertas e explicacao de cobranca.
- Arquitetura aberta para integracao com OCPP no futuro.

## Hipoteses de validacao

1. Administradores pagariam por um sistema que reduz conflito de cobranca.
2. O MVP pode comecar sem integracao direta com carregadores.
3. Relatorios claros sao mais importantes que automacao completa na primeira fase.
4. A maior dor inicial e fechar a conta mensal com confiabilidade.
5. IA gera valor primeiro em explicacao e alertas, nao em decisao automatica.

## Metricas de sucesso

- tempo para fechar rateio mensal;
- numero de ajustes manuais por periodo;
- diferenca entre kWh total medido e kWh rateado;
- numero de contestacoes de usuarios;
- disponibilidade dos carregadores;
- receita ou recuperacao de custo por local.
