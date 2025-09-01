# 📑 Glossário do Event Log (DataJud → Process Mining)

## Campos essenciais

- **case_id**  
  Identificador único do processo no DataJud (campo `_id`).  
  Exemplo: `TST_1689_SUP_45226_01552001520135170141`

- **activity**  
  Nome do movimento processual registrado no processo.  
  Exemplo: `Recebimento`, `Remessa`, `Conclusão`

- **time:timestamp**  
  Data e hora do movimento em formato ISO 8601 UTC.  
  Exemplo: `2016-05-02T21:17:04.000Z`

---

## Atributos do evento (nível de movimento)

- **movimentos.codigo**  
  Código numérico do movimento, conforme tabela do CNJ.  
  Exemplo: `981` (Recebimento), `123` (Remessa)

- **movimentos.complementosTabelados**  
  Complementos do movimento (motivo, tipo etc.).  
  Flatten no formato `chave=valor|...`  
  Exemplo: `nome=outros motivos|descricao=motivo_da_remessa|codigo=18|valor=40`

- **movimentos.orgaoJulgador.codigoOrgao**  
  Código do órgão julgador vinculado ao movimento (quando disponível).

- **movimentos.orgaoJulgador.nomeOrgao**  
  Nome do órgão julgador vinculado ao movimento.  
  Exemplo: `GAB. DO MINISTRO WALMIR OLIVEIRA DA COSTA`

---

## Atributos do caso (repetidos em cada linha)

- **numeroProcesso**  
  Número único do processo no padrão CNJ.  
  Exemplo: `01552001520135170141`

- **tribunal**  
  Tribunal responsável pelo processo.  
  Exemplo: `TST`

- **grau**  
  Grau de jurisdição.  
  Exemplo: `SUP` (Superior)

- **nivelSigilo**  
  Grau de sigilo do processo (`0 = público`).

- **classe.codigo**  
  Código da classe processual.  
  Exemplo: `1689`

- **classe.nome**  
  Nome da classe processual.  
  Exemplo: `Embargos de Declaração Cível`

- **formato.codigo**  
  Código do formato do processo (`1 = Eletrônico`, `2 = Físico`).

- **formato.nome**  
  Nome do formato do processo.  
  Exemplo: `Eletrônico`

- **sistema.codigo**  
  Código do sistema de origem do processo.

- **sistema.nome**  
  Nome do sistema de origem.  
  Exemplo: `Outros`

- **orgaoJulgador.codigo**  
  Código do órgão julgador principal do processo.

- **orgaoJulgador.nome**  
  Nome do órgão julgador principal do processo.  
  Exemplo: `GAB. DO MINISTRO WALMIR OLIVEIRA DA COSTA`

- **orgaoJulgador.codigoMunicipioIBGE**  
  Código IBGE do município do órgão julgador.  
  Exemplo: `5300108` (Brasília/DF)

- **assunto_principal**  
  Primeiro assunto classificado no processo.  
  Exemplo: `Penhora / Depósito/ Avaliação`

- **dataAjuizamento**  
  Data/hora do ajuizamento (entrada inicial do processo).  
  Exemplo: `2016-05-02T21:17:04.000Z`

- **dataHoraUltimaAtualizacao**  
  Data/hora da última atualização do processo no DataJud.  
  Exemplo: `2023-07-29T02:13:48.350Z`

- **@timestamp**  
  Data/hora em que o processo foi indexado no DataJud.  
  Exemplo: `2023-10-02T04:54:23.521Z`
