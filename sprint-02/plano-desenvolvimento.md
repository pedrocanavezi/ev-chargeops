# Plano de Desenvolvimento - Sprint 02

## Objetivo da sprint

Transformar a documentacao da Sprint 01 em um MVP pequeno, navegavel e testavel. O foco deve ficar em cadastro, registro de sessoes, importacao CSV e calculo de rateio.

A Sprint 02 nao deve tentar resolver integracao real com GoodWe/SEMS+ logo de inicio. Essa integracao depende de acesso tecnico que ainda precisa ser confirmado. Primeiro vale provar que o sistema calcula corretamente e gera um relatorio que o administrador consegue conferir.

## Resultado esperado

Ao final da sprint, deve existir uma versao simples capaz de:

- cadastrar local, carregador e usuario;
- importar ou registrar sessoes de recarga;
- calcular valor de rateio por sessao;
- listar sessoes com status, origem do dado e total;
- visualizar ou exportar relatorio mensal;
- documentar limites tecnicos, regulatorios e de integracao.

## Escopo

### Incluido

- Modelo de dados inicial.
- CRUD basico de locais, carregadores, usuarios e sessoes.
- Importacao CSV de sessoes.
- Calculo de rateio com tarifa por kWh e taxa operacional.
- Relatorio simples por periodo.
- Registro da origem do dado: CSV, manual ou integracao futura.
- Documentacao do MVP.

### Fora do escopo

- Pagamento online real.
- Integracao GoodWe/SEMS+ real.
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
| P1 | Auditoria basica | Registro de tarifa, regra e origem do dado. |
| P2 | Alertas de IA | Regras simples para dados inconsistentes. |
| P2 | Dashboard | Indicadores de kWh, custo e uso. |

## Cronograma sugerido

| Dia | Atividade |
| --- | --- |
| 1 | Revisar premissas, fechar stack e formato do CSV. |
| 2 | Criar modelo de dados e carga do CSV de exemplo. |
| 3 | Implementar cadastro e listagem das entidades principais. |
| 4 | Implementar motor de rateio e testes com exemplos. |
| 5 | Implementar relatorio mensal e filtros basicos. |
| 6 | Validar fluxo completo, documentar limites e preparar demo. |

## Criterios de aceite

- Uma sessao com kWh e tarifa gera valor total correto.
- O calculo guarda a regra usada no momento da sessao.
- O sistema mostra sessoes por usuario, local, carregador e periodo.
- O CSV de exemplo pode ser importado sem erro.
- O relatorio mostra origem do dado e memoria de calculo.
- A documentacao explica que GoodWe/SEMS+ ainda e integracao futura.
- Um administrador consegue conferir uma cobranca sem acessar o banco diretamente.

## Riscos

| Risco | Mitigacao |
| --- | --- |
| Regra regulatoria mal interpretada | Manter fonte oficial citada e sinalizar necessidade de especialista. |
| Dados de carregador inconsistentes | Registrar origem do dado e permitir auditoria por sessao. |
| Modelo de cobranca contestado | Mostrar memoria de calculo por sessao. |
| Escopo crescer demais | Manter pagamento real, OCPP e SEMS+ real fora desta sprint. |
| Falta de historico para IA | Comecar com regras deterministicas simples. |

## Proximas decisoes

- Escolher stack tecnica.
- Definir se a primeira interface sera web ou API documentada.
- Confirmar tarifa base e taxa operacional dos exemplos.
- Definir formato final do relatorio mensal.
- Validar se o contexto principal da demo sera condominio, estacionamento ou frota.
- Definir campos minimos para uma futura importacao vinda do GoodWe/SEMS+.
