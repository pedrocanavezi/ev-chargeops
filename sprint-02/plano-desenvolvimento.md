# Plano de Desenvolvimento - Sprint 02

## Objetivo da sprint

Transformar a ideia do EV ChargeOps em um MVP navegavel e testavel, com foco em cadastro, registro de sessoes e calculo de rateio.

## Resultado esperado

Ao final da sprint, deve existir uma versao simples capaz de:

- cadastrar local, carregador e usuario;
- importar ou registrar sessoes de recarga;
- calcular valor de rateio por sessao;
- listar sessoes com status e total;
- exportar ou visualizar relatorio mensal;
- documentar premissas regulatórias e limites do MVP.

## Escopo

### Incluido

- Modelo de dados inicial.
- CRUD basico de locais, carregadores, usuarios e sessoes.
- Importacao CSV de sessoes.
- Calculo de rateio com tarifa por kWh e taxa operacional.
- Relatorio simples por periodo.
- Documentacao do MVP.

### Fora do escopo

- Pagamento online real.
- Integracao OCPP completa.
- App mobile nativo.
- Automacao de medicao com distribuidora.
- Parecer juridico ou certificacao tecnica.

## Backlog priorizado

| Prioridade | Item | Entrega |
| --- | --- | --- |
| P0 | Definir entidades e banco | Schema inicial documentado e implementado. |
| P0 | Cadastro de local e carregador | Tela ou endpoint funcional. |
| P0 | Registro/importacao de sessao | CSV e formulario manual. |
| P0 | Calculo de rateio | Funcao testavel com exemplos. |
| P1 | Relatorio mensal | Lista consolidada por usuario/unidade. |
| P1 | Auditoria basica | Registro de tarifa e regra usada. |
| P2 | Alertas de IA | Regras simples para dados inconsistentes. |
| P2 | Dashboard | Indicadores de kWh, receita e uso. |

## Cronograma sugerido

| Dia | Atividade |
| --- | --- |
| 1 | Revisar documentacao, fechar premissas e escolher stack. |
| 2 | Criar modelo de dados e carga do CSV de exemplo. |
| 3 | Implementar cadastro e listagem das entidades principais. |
| 4 | Implementar motor de rateio e testes. |
| 5 | Implementar relatorio mensal e ajustes de UX/API. |
| 6 | Validar com exemplos, documentar riscos e preparar demo. |

## Critérios de aceite

- Uma sessao com kWh e tarifa gera valor total correto.
- O calculo guarda a regra usada no momento da sessao.
- O sistema mostra sessoes por usuario, local, carregador e periodo.
- O CSV de exemplo pode ser importado sem erro.
- A documentacao explica limites regulatórios e tecnicos.
- Um administrador consegue entender como conferir uma cobranca.

## Riscos

| Risco | Mitigacao |
| --- | --- |
| Regra regulatória mal interpretada | Validar com fonte oficial e especialista. |
| Dados de carregador inconsistentes | Registrar origem do dado e permitir auditoria. |
| Modelo de cobranca contestado | Mostrar memoria de calculo por sessao. |
| Escopo crescer demais | Manter OCPP e pagamento real fora da sprint. |
| Falta de historico para IA | Comecar com regras deterministicas simples. |

## Proximas decisoes

- Escolher stack tecnica.
- Definir se a primeira interface sera web, API ou notebook/prototipo.
- Confirmar tarifa base e taxa operacional.
- Definir formato final do relatorio mensal.
- Validar se o contexto principal sera condominio, estacionamento ou frota.
