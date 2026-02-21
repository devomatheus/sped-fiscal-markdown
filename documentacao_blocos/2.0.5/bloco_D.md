# Bloco D - Versão 2.0.5

**Data de Criação:** 2011-05-19  
**Páginas:** 76-108  
**Versão:** 2.0.5

---

--- Página 76 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 01 - Valor Válido: [C890]
Validação: não poderão existir dois ou mais registros para o conjunto DT_DOC, NR_SAT, CST_ICMS, CFOP e
ALIQ_ICMS.
Campo 02 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS,
constante do Artigo 5º do Convênio SN/70.
Campo 03 - Preenchimento: pelo fato do CF-e referir-se apenas a operações de saídas internas, deve ser preenchido com
CFOP iniciado por 5 (ex: 5102, 5405, etc.).
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme Ajuste
SINIEF 07/01 e iniciar com dígito “5”.
Campo 05 - Preenchimento: O valor deste campo deve corresponder ao somatório do Valor da Operação de todos os
registros informados no reg. C860, respeitando-se o agrupamento por DT_DOC, NR_SAT, CST_ICMS, CFOP e
ALIQ_ICMS.
Campo 06 - Preenchimento: O valor deste campo deve corresponder ao somatório do valor total da Base de Cálculo do
ICMS de todos os registros informados no reg. C860, respeitando-se o agrupamento por DT_DOC, NR_SAT, CST_ICMS,
CFOP e ALIQ_ICMS.
Campo 07 - Preenchimento: O valor deste campo deve corresponder ao somatório do Valor Total do ICMS de todos os
registros informados no reg. C860, respeitando-se o agrupamento por DT_DOC, NR_SAT, CST_ICMS, CFOP e
ALIQ_ICMS.
Campo 08 - Preenchimento: este campo só deve ser informado pelos contribuintes localizados em UF que determine em
sua legislação o seu preenchimento.
Validação: o código informado deve constar do registro 0460.
REGISTRO C990: ENCERRAMENTO DO BLOCO C
Este registro destina-se a identificar o encerramento do bloco C e informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Entr Saida
01 REG Texto fixo contendo "C990" C 004 - O O
02 QTD_LIN_C Quantidade total de linhas do Bloco C N - - O O
Observações: Registro obrigatório
Nível hierárquico - 1
Ocorrência – um por arquivo
Campo 01 - Valor Válido: [C990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco C é igual ao valor informado no campo QTD_LIN_C
(registro C990).
Validação do Registro: registro único e obrigatório para todos os informantes da EFD.
BLOCO D: DOCUMENTOS FISCAIS II - SERVIÇOS (ICMS).
Bloco de registros dos dados relativos à emissão ou ao recebimento de documentos fiscais que acobertam as
prestações de serviços de comunicação, transporte intermunicipal e interestadual.
REGISTRO D001: ABERTURA DO BLOCO D
Este registro deve ser gerado para abertura do Bloco D e indica se há informações sobre prestações ou
contratações de serviços de comunicação, transporte interestadual e intermunicipal, com o devido suporte do
correspondente documento fiscal.
Página 76 de 163

--- Página 77 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Nº Campo Descrição Tipo Tam Dec Entr
01 REG Texto fixo contendo "D001" C 004 - O
02 IND_MOV Indicador de movimento: C 001 - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência - um por arquivo
Campo 01 - Valor válido: [D001]
Campo 02 - Valores válidos: [0,1]
Preenchimento: quando houver aquisições ou prestações de serviços de comunicação, transporte interestadual e
intermunicipal, deve-se gerar esse bloco utilizando a opção 0. Quando não houver aquisições ou prestações de serviços de
comunicação, transporte interestadual e intermunicipal, deve-se gerar esse bloco com a opção 1.
Validação do Registro: registro obrigatório e único. Se o campo IND_MOV tiver valor igual a 1 (um), só devem ser
informados este registro de abertura e o registro D990, que é o registro de fechamento do Bloco D.
REGISTRO D100: NOTA FISCAL DE SERVIÇO DE TRANSPORTE (CÓDIGO 07) E
CONHECIMENTOS DE TRANSPORTE RODOVIÁRIO DE CARGAS (CÓDIGO 08),
CONHECIMENTOS DE TRANSPORTE DE CARGAS AVULSO (CÓDIGO 8B),
AQUAVIÁRIO DE CARGAS (CÓDIGO 09), AÉREO (CÓDIGO 10), FERROVIÁRIO DE
CARGAS (CÓDIGO 11) E MULTIMODAL DE CARGAS (CÓDIGO 26), NOTA FISCAL DE
TRANSPORTE FERROVIÁRIO DE CARGA ( CÓDIGO 27) E CONHECIMENTO DE
TRANSPORTE ELETRÔNICO – CT-e (CÓDIGO 57).
Este registro deve ser apresentado por todos os contribuintes adquirentes ou prestadores dos serviços que utilizem
os documentos previstos para este registro.
Validação do Registro: não podem ser informados dois ou mais registros com a combinação de mesmos valores dos
campos :
1. emissão de terceiros : IND_EMIT+NUM_DOC+COD_MOD+SER+SUB+COD_PART;
2. emissão própria: IND_EMIT+NUM_DOC+COD_MOD+SER+SUB.
Para cada documento emitido e portanto para cada registro D100, obrigatoriamente deve ser apresentado, pelo menos, um
registro D190, observadas as exceções abaixo relacionadas:
Exceção 1: Para documentos com código de situação (campo COD_SIT) cancelado (código “02”) ou cancelado
extemporâneo (código “03”), Conhecimento de Transporte Eletrônico (CT-e) denegado (código “04”) ou numeração
inutilizada (código “05”) preencher somente os campos REG, IND_OPER, IND_EMIT, COD_MOD, COD_SIT, SER,
SUB e NUM_DOC. Demais campos deverão ser apresentados com conteúdo VAZIO “||”. Não deverão ser informados
registros filhos. A partir de janeiro de 2011, no caso de CT-e de emissão própria com código de situação (campo
COD_SIT) cancelado (código “02”) e cancelado extemporâneo (código “03”) deverão ser informados os campos acima
citados incluindo ainda a chave do CT-e.
Exceção 2: Documentos de transporte complementares e documentos de transporte extemporâneos (campo COD_SIT
igual a “06” ou “07”): nesta situação, somente os campos REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD,
COD_SIT, SER, SUB, NUM_DOC e DT_DOC são obrigatórios. Os demais campos são facultativos (se forem
preenchidos, serão validados e aplicadas as regras de campos existentes). A apresentação do registro D190 é obrigatória,
devendo ser preenchidos todos os campos obrigatórios. Os demais campos e registros filhos do registro D100 serão
informados, se existirem.
Exceção 3: Documentos de transporte emitidos por regime especial ou norma específica (campo COD_SIT igual a “08”).
Para documentos fiscais emitidos com base em regime especial ou norma específica, (campo COD_SIT igual a “08”). Para
documentos fiscais emitidos com base em regime especial ou norma específica, deverão ser apresentados os registros D100
e D190, obrigatoriamente, e os demais registros “filhos”, se estes forem exigidos pela legislação fiscal. Nesta situação, no
registro D100, somente os campos REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT, SER, SUB,
NUM_DOC e DT_DOC são obrigatórios. Os demais campos são facultativos (se forem preenchidos serão validados e
aplicadas as regras de campos existentes).
Exceção 4: Conhecimento de Transporte Eletrônico - CT-e de emissão própria: neste caso, devem ser apresentados
somente os registros D100 e D190.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D100" C 004 - O O
Página 77 de 163

--- Página 78 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
02 IND_OPER Indicador do tipo de operação: C 001* - O O
0- Aquisição;
1- Prestação
03 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O O
0- Emissão própria;
1- Terceiros
04 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - O O
- do prestador de serviço, no caso de aquisição de
serviço;
- do tomador do serviço, no caso de prestação de
serviços.
05 COD_MOD Código do modelo do documento fiscal, conforme a C 002* - O O
Tabela 4.1.1
06 COD_SIT Código da situação do documento fiscal, conforme a N 002* - O O
Tabela 4.1.2
07 SER Série do documento fiscal C 004 - OC OC
08 SUB Subsérie do documento fiscal C 003 - OC OC
09 NUM_DOC Número do documento fiscal N 009 - O O
10 CHV_CTE Chave do Conhecimento de Transporte Eletrônico N 044* - OC OC
11 DT_DOC Data da emissão do documento fiscal N 008* - O O
12 DT_A_P Data da aquisição ou da prestação do serviço N 008* - O OC
13 TP_CT-e Tipo de Conhecimento de Transporte Eletrônico N 001* - OC OC
conforme definido no Manual de Integração do
CT-e
14 CHV_CTE_REF Chave do CT-e de referência cujos valores foram N 044* - OC OC
complementados (opção “1” do campo anterior) ou
cujo débito foi anulado(opção “2” do campo anterior).
15 VL_DOC Valor total do documento fiscal N - 02 O O
16 VL_DESC Valor total do desconto N - 02 OC OC
17 IND_FRT Indicador do tipo do frete: C 001* - O O
0- Por conta de terceiros;
1- Por conta do emitente;
2- Por conta do destinatário;
9- Sem cobrança de frete.
18 VL_SERV Valor total da prestação de serviço N - 02 O O
19 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 OC OC
20 VL_ICMS Valor do ICMS N - 02 OC OC
21 VL_NT Valor não-tributado N - 02 OC OC
22 COD_INF Código da informação complementar do documento C 006 - OC OC
fiscal (campo 02 do Registro 0450)
23 COD_CTA Código da conta analítica contábil debitada/creditada C - - OC OC
Observações:
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor válido: [D100]
Campo 02 - Valores válidos: [0,1]
Campo 03 - Valores válidos: [0, 1]
Preenchimento: informar o emitente do documento fiscal. Se o declarante for o prestador do serviço a emissão será
própria. Se o declarante for o adquirente, em regra, a emissão será de terceiros.
Validação: se este campo tiver valor igual a 1 (terceiros), então o campo IND_OPER deve ser igual a 0 (entradas). Se este
campo tiver valor igual a 0 (emissão própria), então o campo IND_OPER poderá ser igual a 0 (entradas) ou 1 (prestação).
Campo 04 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 05 - Valores válidos: [07, 08, 8B, 09, 10, 11, 26, 27 e 57]
Campo 06 - Valores válidos: [00, 01, 02, 03, 06, 07, 08]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3.
Página 78 de 163

--- Página 79 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 09 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 10 - Preenchimento: informar a chave do conhecimento de transporte eletrônico, para documentos de COD_MOD
igual a “57” de emissão própria. A chave do CT-e de emissão de terceiros não pode ser informada.
Validação: é conferido o dígito verificador (DV) da chave do CT-e. Este campo é de preenchimento obrigatório para
COD_MOD igual a “57”, quando o campo IND_EMIT for igual a “0”. Para escrituração de CT-e emitidos por terceiros
esse campo não pode ser informado.
Para confirmação inequívoca de que a chave do CT-e corresponde aos dados informados do documento, será comparado o
CNPJ existente na CHV_CTE com o campo CNPJ do registro 0000, que corresponde ao CNPJ do informante do arquivo.
Será verificada a consistência da informação do campo NUM_DOC e o número do documento contido na chave do CT-e.
Será também comparada a UF codificada na chave do CT-e com o campo UF informado no registro 0000.
Campo 11 - Preenchimento: informar a data de emissão do documento, no formato “ddmmaaaa”; excluindo-se quaisquer
caracteres de separação, tais como: “.”, “/”, “-”.
Validação: o valor informado deve ser menor ou igual ao valor do campo DT_FIN do registro 0000.
Campo 12 - Preenchimento: informar a data de aquisição ou prestação, conforme a operação, no formato “ddmmaaaa”,
excluindo-se quaisquer caracteres de separação, tais como: “.”, “/”, “-”.
Se operação de aquisição, este campo deve ser menor ou igual a DT_FIN do registro 0000. Para operações de aquisição de
serviço este valor deve ser maior ou igual à data de emissão (DT_DOC). Para operações de prestação de serviços, este
valor, se informado, deve ser maior ou igual à data de emissão (DT_DOC).
Campo 13 - Preenchimento: informar o tipo de CT-e quando o modelo do documento for “57”.
Campo 14 - Preenchimento: Não preencher, informar campo “vazio”.
Campo 17 – Valores válidos: [0, 1, 2, 9]
Preenchimento: usar o valor 0 (por conta de terceiros) para os casos em que o tomador é diferente do emitente e
destinatário (do documento fiscal que deu origem ao conhecimento de transporte).
Tem-se por tomador quem efetuou o contrato junto à transportadora, arcando com o valor do serviço. Somente a este deve
ser enviada a primeira via do conhecimento e só ele terá direito ao crédito.
Campo 18 – Preenchimento: o valor informado, em havendo, deve englobar pedágio e demais despesas.
Campo 19 - Validação: este valor deve corresponder ao resultado da diferença entre o campo VL_SERV e o VL_NT.
Campo 22 - Validação: o valor informado no campo deve existir no registro 0450.
Campo 23 - Preenchimento: deve ser a conta credora ou devedora principal, podendo ser informada a conta sintética
(nível acima da conta analítica).
REGISTRO D110: ITENS DO DOCUMENTO - NOTA FISCAL DE SERVIÇOS DE
TRANSPORTE (CÓDIGO 07)
Este registro deve ser apresentado para informar os itens das Notas Fiscais de Serviços de Transporte (Código 07)
fornecidas no registro D100.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D110" C 004 - Não O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - apresentar O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 VL_SERV Valor do serviço N - 02 O
05 VL_OUT Outros valores N - 02 OC
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor válido: [D110]
Página 79 de 163

--- Página 80 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 03 - Validação: o valor informado no campo deve existir no registro 0200.
Validação do Registro: não podem ser informados dois ou mais registros com o mesmo valor para o campo NUM_ITEM.
REGISTRO D120: COMPLEMENTO DA NOTA FISCAL DE SERVIÇOS DE TRANSPORTE
(CÓDIGO 07).
Este registro deve ser apresentado para informar o complemento das Notas Fiscais de Serviços de Transporte
(Código 07), com municípios de origem e destino do transporte.
Obs. Para operações que envolvem destinos ou origens em cidades fora do Brasil, os campos COD_MUN_ORIG
ou COD_MUN_DEST dos registros D120, D130, D140, D150, D160, D170 e D180 deverão ser preenchidos
com o código “9999999”.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D120" C 004 - Não O
02 COD_MUN_ORIG Código do município de origem do serviço, N 007* - apresentar O
conforme a tabela IBGE(Preencher com 9999999,
se Exterior)
03 COD_MUN_DEST Código do município de destino, conforme a N 007* - O
tabela IBGE(Preencher com 9999999, se Exterior)
04 VEIC_ID Placa de identificação do veículo C 007 - OC
05 UF_ID Sigla da UF da placa do veículo C 002 - OC
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor válido: [D120]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
REGISTRO D130: COMPLEMENTO DO CONHECIMENTO RODOVIÁRIO DE CARGAS
(CÓDIGO 08) E DO CONHECIMENTO RODOVIÁRIO DE CARGAS AVULSO (CÓDIGO
8B).
Este registro tem por objetivo informar o complemento do Conhecimento de Transporte Rodoviário de Cargas
(Código 08) e Conhecimento de Transporte de Cargas Avulso (Código 8B).
Obs. Para operações que envolvem destinos ou origens em cidades fora do Brasil, os campos
COD_MUN_ORIG ou COD_MUN_DEST dos registros D120, D130, D140, D150, D160, D170 e D180 deverão
ser preenchidos com o código “9999999”.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D130" C 004 - Não O
02 COD_PART_CONSG Código do participante (campo 02 do Registro C 060 - apresentar OC
0150):
- consignatário, se houver
03 COD_PART_RED Código do participante (campo 02 do Registro C 060 - OC
0150):
- redespachado, se houver
04 IND_FRT_RED Indicador do tipo do frete da operação de C 001* - O
redespacho:
0 – Sem redespacho;
1 - Por conta do emitente;
2 - Por conta do destinatário;
9 – Outros.
Página 80 de 163

--- Página 81 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
05 COD_MUN_ORIG Código do município de origem do serviço, N 007* - O
conforme a tabela IBGE(Preencher com 9999999,
se Exterior)
06 COD_MUN_DEST Código do município de destino, conforme a N 007* - O
tabela IBGE(Preencher com 9999999, se
Exterior)
07 VEIC_ID Placa de identificação do veículo C 007 - OC
08 VL_LIQ_FRT Valor líquido do frete N - 02 O
09 VL_SEC_CAT Soma de valores de Sec/Cat (serviços de N - 02 OC
coleta/custo adicional de transporte)
10 VL_DESP Soma de valores de despacho N - 02 OC
11 VL_PEDG Soma dos valores de pedágio N - 02 OC
12 VL_OUT Outros valores N - 02 OC
13 VL_FRT Valor total do frete N - 02 O
14 UF_ID Sigla da UF da placa do veículo C 002 - OC
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor válido: [D130]
Campo 02 - Preenchimento: preencher com a informação constante no corpo do Conhecimento de Transporte Rodoviário
de Cargas (CTRC) no campo consignatário.
Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 03 - Preenchimento: preencher com a informação constante no corpo do CTRC no campo redespacho.
Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 04 – Preenchimento: inclusive subcontratação, que é a contratação de outra transportadora para cumprir todo o
trecho do frete. Neste caso, para subcontratação, o valor deste campo pode ser qualquer um dos valores previstos.
No redespacho ou subcontratação, a subcontratada fornecerá na sua declaração o D100 correspondente ao D130 fornecido
pela empresa que contratou o redespacho ou subcontratou a prestação.
Valores válidos: [0, 1, 2, 9]
Campo 05 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 06 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 08 - Validação: o valor informado no campo deve ser maior que “0” (zero), se o campo IND_FRT do registro
D100 for diferente de 9 (Sem frete).
Campo 13 - Validação: o valor informado no campo deve ser maior que “0” (zero), se o campo IND_FRT do registro
D100 for diferente de 9 (Sem frete).
REGISTRO D140: COMPLEMENTO DO CONHECIMENTO AQUAVIÁRIO DE
CARGAS (CÓDIGO 09).
Este registro tem por objetivo informar o complemento do Conhecimento de Transporte Aquaviário de Cargas
(Código 09).
Obs. Para operações que envolvem destinos ou origens em cidades fora do Brasil, os campos COD_MUN_ORIG
ou COD_MUN_DEST dos registros D120, D130, D140, D150, D160, D170 e D180 deverão ser preenchidos com o
código “9999999”.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D140" C 004 - Não O
02 COD_PART_CONSG Código do participante (campo 02 do Registro C 060 - apresentar OC
0150):
- consignatário, se houver
03 COD_MUN_ORIG Código do município de origem do serviço, N 007* - O
conforme a tabela IBGE(Preencher com
9999999, se Exterior)
Página 81 de 163

--- Página 82 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
04 COD_MUN_DEST Código do município de destino, conforme a N 007* - O
tabela IBGE(Preencher com 9999999, se
Exterior)
05 IND_VEIC Indicador do tipo do veículo transportador: C 001* - O
0- Embarcação;
1- Empurrador/rebocador
06 VEIC_ID Identificação da embarcação (IRIM ou Registro C - - OC
CPP)
07 IND_NAV Indicador do tipo da navegação: C 001* - O
0- Interior;
1- Cabotagem
08 VIAGEM Número da viagem N - - OC
09 VL_FRT_LIQ Valor líquido do frete N - 02 O
10 VL_DESP_PORT Valor das despesas portuárias N - 02 OC
11 VL_DESP_CAR_DESC Valor das despesas com carga e descarga N - 02 OC
12 VL_OUT Outros valores N - 02 OC
13 VL_FRT_BRT Valor bruto do frete N - 02 O
14 VL_FRT_MM Valor adicional do frete para renovação da N - 02 OC
Marinha Mercante
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor válido: [D140]
Campo 02 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 04 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 05 - Valores válidos: [0, 1]
Campo 07 - Valores válidos: [0, 1]
REGISTRO D150: COMPLEMENTO DO CONHECIMENTO AÉREO (CÓDIGO 10).
Este registro tem por objetivo informar o complemento do Conhecimento de Transporte Aéreo de Cargas (Código
10).
Obs. Para operações que envolvem destinos ou origens em cidades fora do Brasil, os campos COD_MUN_ORIG
ou COD_MUN_DEST dos registros D120, D130, D140, D150, D160, D170 e D180 deverão ser preenchidos com o
código “9999999”.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D150" C 004 - Não O
02 COD_MUN_ORIG Código do município de origem do serviço, N 007* - apresentar O
conforme a tabela IBGE(Preencher com
9999999, se Exterior)
03 COD_MUN_DEST Código do município de destino, conforme a N 007* - O
tabela IBGE(Preencher com 9999999, se
Exterior)
04 VEIC_ID Identificação da aeronave (DAC) C - - OC
05 VIAGEM Número do vôo. N - - OC
06 IND_TFA Indicador do tipo de tarifa aplicada: C 001* - O
0- Exp.;
1- Enc.;
2- C.I.;
9- Outra
07 VL_PESO_TX Peso taxado N - 02 O
08 VL_TX_TERR Valor da taxa terrestre N - 02 OC
09 VL_TX_RED Valor da taxa de redespacho N - 02 OC
Página 82 de 163

--- Página 83 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
10 VL_OUT Outros valores N - 02 OC
11 VL_TX_ADV Valor da taxa "ad valorem" N - 02 OC
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor válido: [D150]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 06 - Valores válidos: [0, 1, 2, 9]
REGISTRO D160: CARGA TRANSPORTADA (CÓDIGO 08, 8B, 09, 10, 11, 26 e 27).
Neste registro devem ser apresentados dados sobre o transporte da carga, objeto dos conhecimentos de transporte
aqui especificados.
Obs. Para operações que envolvem destinos ou origens em cidades fora do Brasil, os campos COD_MUN_ORIG
ou COD_MUN_DEST dos registros D120, D130, D140, D150, D160, D170 e D180 deverão ser preenchidos com o
código “9999999”.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D160" C 004 - Não O
02 DESPACHO Identificação do número do despacho C - - apresentar OC
03 CNPJ_CPF_REM CNPJ ou CPF do remetente das mercadorias que N 014 - OC
constam na nota fiscal.
04 IE_REM Inscrição Estadual do remetente das mercadorias C 014 - OC
que constam na nota fiscal.
05 COD_MUN_ORI Código do Município de origem, conforme tabela N 007* - O
IBGE(Preencher com 9999999, se Exterior)
06 CNPJ_CPF_DEST CNPJ ou CPF do destinatário das mercadorias que N 014 - OC
constam na nota fiscal.
07 IE_DEST Inscrição Estadual do destinatário C 014 - OC
das mercadorias que constam na nota fiscal.
08 COD_MUN_DEST Código do Município de destino, conforme tabela N 007* - O
IBGE(Preencher com 9999999, se Exterior)
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor válido: [D160]
Campo 02 – Preenchimento: Informar o número do despacho quando se tratar de transporte ferroviário de cargas.
Campo 03 - Validação: se forem informados 14 caracteres, o campo será validado como CNPJ. Se forem informados 11
caracteres, o campo será validado como CPF.
Campo 04 - validação: a inscrição estadual será validada considerando-se a UF codificada nos dois primeiros caracteres
do campo COD_MUN_ORI. O preenchimento torna-se obrigatório se o Campo COD_MOD for ‘01’ ou ‘55’.
Campo 06 – Preenchimento: informar o CNPJ, com 14 dígitos, ou o CPF, com 11 dígitos, do destinatário.
Validação: se forem informados 14 caracteres, o campo será validado como CNPJ. Se forem informados 11 caracteres, o
campo será validado como CPF.
Campo 07 - Validação: a inscrição estadual será validada considerando-se a UF codificada nos dois primeiros caracteres
do campo COD_MUN_DEST
REGISTRO D161: LOCAL DA COLETA E ENTREGA (CÓDIGO 08, 8B, 09, 10, 11 e 26).
Este registro tem por objetivo informar o local de coleta e/ou entrega quando esse for diferente do endereço do
remetente e/ou destinatário.
Página 83 de 163

--- Página 84 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D161" C 004 - Não O
Indicador do tipo de transporte da carga apresentar O
coletada:
0-Rodoviário
1-Ferroviário
02 IND_CARGA 2-Rodo-Ferroviário N 001* -
3-Aquaviário
4-Dutoviário
5-Aéreo
9-Outros
03 CNPJ_CPF_COL Número do CNPJ ou CPF do local da coleta C 014 - OC
Inscrição Estadual do contribuinte do local de OC
04 IE_COL C 014 -
coleta
Código do Município do local de coleta, O
05 COD_MUN_COL conforme tabela IBGE(Preencher com N 007* -
9999999, se Exterior)
06 CNPJ_CPF_ENTG Número do CNPJ ou CPF do local da entrega C 014 - OC
Inscrição Estadual do contribuinte do local de OC
07 IE_ENTG C 014 -
entrega
Código do Município do local de entrega, O
08 COD_MUN_ENTG conforme tabela IBGE(Preencher com N 007* -
9999999, se Exterior)
Observações:
Nível hierárquico - 4
Ocorrência - 1:1
Campo 01 - Valor Válido: [D161]
Campo 02 - Valores Válidos: [0, 1, 2, 3, 4, 5, 9]
Campo 03 - Preenchimento: informar o número do CNPJ do contribuinte do local de coleta.
Validação: será conferido o dígito verificador (DV) do CNPJ informado.
Campo 04 - validação: a inscrição estadual será validada considerando-se a UF codificada nos dois primeiros caracteres
do campo COD_MUN_COL.
Campo 05 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 06 - Preenchimento: informar o número do CNPJ do contribuinte do local de entrega.
Validação: será conferido o dígito verificador (DV) do CNPJ informado.
Campo 07 - Validação: a inscrição estadual será validada considerando-se a UF codificada nos dois primeiros caracteres
do campo COD_MUN_ENTG.
Campo 08 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
REGISTRO D162: IDENTIFICAÇÃO DOS DOCUMENTOS FISCAIS (CÓDIGOS 08, 8B, 09,
10, 11, 26 E 27)
Neste registro devem ser apresentados dados dos documentos fiscais que acobertam a carga transportada, objeto
dos conhecimentos de transporte previstos no registro D160.
Não informar este registro caso o CFOP do conhecimento de transporte seja 5359 ou 6359.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D162" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, conforme a C 002* - apresentar OC
Tabela 4.1.1
03 SER Série do documento fiscal C 004 - OC
Página 84 de 163

--- Página 85 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
04 NUM_DOC Número do documento fiscal N 009 - O
05 DT_DOC Data da emissão do documento fiscal N 008* - OC
06 VL_DOC Valor total do documento fiscal N - 02 OC
07 VL_MERC Valor das mercadorias constantes no documento fiscal N - 02 OC
08 QTD_VOL Quantidade de volumes transportados N - - O
09 PESO_BRT Peso bruto dos volumes transportados (em Kg) N - 02 OC
10 PESO_LIQ Peso líquido dos volumes transportados (em Kg) N - 02 OC
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 – valor válido: [D162]
Campo 02 - Valores válidos: [01, 1B, 04 e 55]
Preenchimento: o valor informado deve constar na tabela 4.1.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008,
constante da subseção 6.4 deste guia. O “código” a ser informado não é exatamente o “modelo” do documento. Exemplo: o
código “01” deve ser utilizado para as notas fiscais modelo “01” ou “1A".
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Preenchimento: informar o período de validade das informações contidas neste registro, no formato
“ddmmaaaa”, excluindo-se quaisquer caracteres de separação, tais como: “.”, “/”, “-”.
Validação: o valor informado no campo deve ser menor ou igual ao campo DT_FIN do registro 0000.
Campo 07 - Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO D170: COMPLEMENTO DO CONHECIMENTO MULTIMODAL DE CARGAS
(CÓDIGO 26).
Este registro tem por objetivo informar o complemento do Conhecimento Multimodal de Cargas (Código 26).
Obs. Para operações que envolvem destinos ou origens em cidades fora do Brasil, os campos COD_MUN_ORIG
ou COD_MUN_DEST dos registros D120, D130, D140, D150, D160, D170 e D180 deverão ser preenchidos com o
código “9999999”.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D170" C 004 - Não O
02 COD_PART_CONSG Código do participante (campo 02 do Registro C 060 - apresentar OC
0150):
- consignatário, se houver
03 COD_PART_RED Código do participante (campo 02 do Registro C 060 - OC
0150):
- redespachante, se houver
04 COD_MUN_ORIG Código do município de origem do serviço, N 007* - O
conforme a tabela IBGE(Preencher com 9999999,
se Exterior)
05 COD_MUN_DEST Código do município de destino, conforme a N 007* - O
tabela IBGE(Preencher com 9999999, se
Exterior)
06 OTM Registro do operador de transporte multimodal C - - O
07 IND_NAT_FRT Indicador da natureza do frete: C 001* - O
0- Negociável;
1- Não negociável
08 VL_LIQ_FRT Valor líquido do frete N - 02 O
09 VL_GRIS Valor do gris (gerenciamento de risco) N - 02 OC
10 VL_PDG Somatório dos valores de pedágio N - 02 OC
11 VL_OUT Outros valores N - 02 OC
12 VL_FRT Valor total do frete N - 02 O
13 VEIC_ID Placa de identificação do veículo C 007 - OC
14 UF_ID Sigla da UF da placa do veículo C 002 - OC
Página 85 de 163

--- Página 86 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor Válido: [D170]
Campo 02 - Preenchimento: preencher com a informação constante no corpo do CTRC no campo consignatário.
Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 03 - Preenchimento: preencher com a informação constante no corpo do CTRC no campo de redespacho.
Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 04 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 05 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 06 - Preenchimento: número de registro do operador de transporte multimodal junto à ANTT. O valor é numérico
e possui 8 dígitos.
Campo 07 - Valores Válidos: [0, 1]
Preenchimento: o Complemento do Conhecimento Multimodal de Cargas pode ser negociado em instituição financeira,
em um processo semelhante ao desconto de duplicata bancária.
REGISTRO D180: MODAIS (CÓDIGO 26)
Este registro tem por objetivo identificar todos os transportadores e seus documentos fiscais emitidos durante o
transporte multimodal.
Obs. Para operações que envolvem destinos ou origens em cidades fora do Brasil, os campos COD_MUN_ORIG ou
COD_MUN_DEST dos registros D120, D130, D140, D150, D160, D170 e D180 deverão ser preenchidos com o código
“9999999”.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D180" C 004 - Não O
02 NUM_SEQ Número de ordem sequencial do modal N - - apresentar O
03 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O
0- Emissão própria;
1- Terceiros
04 CNPJ_CPF_EMIT CNPJ ou CPF do participante emitente do modal N 014 - O
05 UF_EMIT Sigla da unidade da federação do participante C 002* - O
emitente do modal
06 IE_EMIT Inscrição Estadual do participante emitente do C 014 - OC
modal
07 COD_MUN_ORIG Código do município de origem do serviço, N 007* - O
conforme a tabela IBGE(Preencher com 9999999,
se Exterior)
08 CNPJ_CPF_TOM CNPJ/CPF do participante tomador do serviço N 014 - O
09 UF_TOM Sigla da unidade da federação do participante C 002* - O
tomador do serviço
10 IE_TOM Inscrição Estadual do participante tomador do C 014 - OC
serviço
11 COD_MUN_DEST Código do município de destino, conforme a N 007* - O
tabela IBGE(Preencher com 9999999, se Exterior)
12 COD_MOD Código do modelo do documento fiscal, conforme C 002* - O
a Tabela 4.1.1
13 SER Série do documento fiscal C 004 - O
14 SUB Subsérie do documento fiscal N 003 - OC
15 NUM_DOC Número do documento fiscal N 009 - O
16 DT_DOC Data da emissão do documento fiscal N 008* - O
17 VL_DOC Valor total do documento fiscal N - 02 O
Observações:
Página 86 de 163

--- Página 87 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [D180]
Campo 03 - Valores Válidos: [0, 1]
Campo 04 - Preenchimento: informar o CNPJ, com 14 dígitos, ou o CPF, com 11 dígitos, do tomador de serviço.
Validação: se forem informados 14 caracteres, o campo será validado como CNPJ. Se forem informados 11 caracteres, o
campo será validado como CPF. O preenchimento com outra quantidade de caracteres será considerado inválido.
Campo 05 - Validação: o valor informado no campo deve existir na tabela de UF.
Campo 06 – Validação: a inscrição estadual será validada considerando-se a UF informada no campo UF_EMIT do
registro.
Campo 07 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 08 - – Preenchimento: informar o CNPJ, com 14 dígitos, ou o CPF, com 11 dígitos, do tomador de serviço.
Validação: se forem informados 14 caracteres, o campo será validado como CNPJ. Se forem informados 11 caracteres, o
campo será validado como CPF. O preenchimento com outra quantidade de caracteres será considerado inválido.
Campo 09 - Validação: o valor informado no campo deve existir na tabela de UF.
Campo 10 - Validação: a inscrição estadual será validada considerando-se a UF informada no campo UF_TOM do
registro.
Campo 11 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 15 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 16 - Preenchimento: informar a data de emissão do documento fiscal, no formato “ddmmaaaa”, excluindo-se
quaisquer caracteres de separação, tais como: “.”, “/”, “-”.
Validação: o valor informado no campo deve ser menor ou igual ao campo DT_FIN do registro 0000.
REGISTRO D190: REGISTRO ANALÍTICO DOS DOCUMENTOS (CÓDIGO 07, 08,
8B, 09, 10, 11, 26, 27 e 57).
Este registro tem por objetivo informar as Notas Fiscais de Serviço de Transporte (Código 07) e demais
documentos elencados no título deste registro e especificados no registro D100, totalizados pelo agrupamento das
combinações dos valores de CST, CFOP e Alíquota dos itens de cada documento.
Obs.: Nas operações de entradas, informar o CST que constar no documento fiscal de aquisição dos serviços.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D190" C 004 - O O
02 CST_ICMS Código da Situação Tributária, conforme a tabela N 003* - O O
indicada no item 4.3.1
Código Fiscal de Operação e Prestação, conforme O O
03 CFOP N 004* -
a tabela indicada no item 4.2.2
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC OC
VL_OPR Valor da operação correspondente à combinação O O
05 N - 02
de CST_ICMS, CFOP, e alíquota do ICMS.
Parcela correspondente ao "Valor da base de O O
06 VL_BC_ICMS cálculo do ICMS" referente à combinação N - 02
CST_ICMS, CFOP, e alíquota do ICMS
Parcela correspondente ao "Valor do ICMS" O O
07 VL_ICMS referente à combinação CST_ICMS, CFOP e N - 02
alíquota do ICMS
08 VL_RED_BC Valor não tributado em função da redução da base N - 02 O O
de cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
Página 87 de 163

--- Página 88 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
09 COD_OBS Código da observação do lançamento fiscal C 006 - OC OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [D190]
Campo 02 - Preenchimento: Nos documentos fiscais de emissão própria o campo deverá ser preenchido com o código da
Situação Tributária sob o enfoque do declarante. Nas operações de entradas (documentos de terceiros), informar o CST que
constar no documento fiscal de aquisição dos produtos.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, indicada no item
4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, sendo que o primeiro caractere sempre será Zero.
O campo VL_RED_BC só pode ser preenchido se os dois últimos dígitos deste campo forem iguais a 20 ou 70.
Campo 03 - Preenchimento: informar o código aplicável à prestação de serviço constante no documento. Não podem ser
utilizados códigos que correspondam aos títulos dos agrupamentos de CFOP (códigos com caracteres finais 00 ou 50. Por
exemplo: 5100).
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme Ajuste
SINIEF 07/01.
Campo 06 - Validação: o valor informado deve ser igual ao valor do campo VL_BC_ICMS do registro D100, pai deste
registro D190.
Campo 07 - Validação: o valor informado deve ser igual ao valor do campo VL_ICMS do registro D100, pai deste
registro D190.
Campo 08 - Validação: o campo VL_RED_BC só pode ser preenchido se o campo CST_ICMS for igual a 20 ou 70.
REGISTRO D300: REGISTRO ANALÍTICO DOS BILHETES CONSOLIDADOS DE
PASSAGEM RODOVIÁRIO (CÓDIGO 13), DE PASSAGEM AQUAVIÁRIO (CÓDIGO 14),
DE PASSAGEM E NOTA DE BAGAGEM (CÓDIGO 15) E DE PASSAGEM FERROVIÁRIO
(CÓDIGO 16).
Este registro deve ser apresentado por todos os contribuintes prestadores dos serviços de transporte de passageiros
e bagagens. A consolidação deve ser feita obedecendo à combinação CST, CFOP e Alíquota, considerando o modelo, série
e subsérie. A numeração dos documentos cancelados deve estar inclusa em cada consolidação.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D300" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, conforme C 002* - apresentar O
a Tabela 4.1.1
03 SER Série do documento fiscal C 004 - O
04 SUB Subsérie do documento fiscal N 003 - OC
05 NUM_DOC_INI Número do primeiro documento fiscal emitido N 006 - O
(mesmo modelo, série e subsérie)
06 NUM_DOC_FIN Número do último documento fiscal emitido N - - O
(mesmo modelo, série e subsérie)
07 CST_ICMS Código da Situação Tributária, conforme a Tabela N 003* - O
indicada no item 4.3.1
08 CFOP Código Fiscal de Operação e Prestação conforme N 004* - O
tabela indicada no item 4.2.2
09 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
10 DT_DOC Data da emissão dos documentos fiscais N 008* - O
11 VL_OPR Valor total acumulado das operações N - 02 O
correspondentes à combinação de CST_ICMS,
CFOP e alíquota do ICMS, incluídas as despesas
acessórias e acréscimos.
12 VL_DESC Valor total dos descontos N - 02 OC
Página 88 de 163

--- Página 89 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
13 VL_SERV Valor total da prestação de serviço N - 02 O
14 VL_SEG Valor de seguro N - 02 OC
15 VL_OUT DESP Valor de outras despesas N - 02 OC
16 VL_BC_ICMS Valor total da base de cálculo do ICMS N - 02 O
17 VL_ICMS Valor total do ICMS N - 02 O
18 VL_RED_BC Valor não tributado em função da redução da base N - 02 O
de cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
19 COD_OBS Código da observação do lançamento fiscal C 006 - OC
(campo 02 do Registro 0460)
20 COD_CTA Código da conta analítica contábil C - - OC
debitada/creditada
Observações:
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [D300]
Campo 02 - Valores válidos: [13, 14, 15, 16]
Campo 05 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 06 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 07- Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o 1º dígito
deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na Tabela B
constante no Anexo do Convênio SN/70.
Validação: ICMS Normal:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos VL_BC_ICMS,
ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero).
O campo VL_RED_BC só pode ser preenchido se os dois últimos dígitos deste campo forem iguais a 20, 70 ou 90.
Campo 08 - Preenchimento: informar o código aplicável à prestação de serviço constante no documento. Não podem ser
utilizados códigos que correspondam aos títulos dos agrupamentos de CFOP (códigos com caracteres finais 00 ou 50. Por
exemplo: 5100).
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme Ajuste
SINIEF 07/01.
Campo 10 - Preenchimento: informar a data de emissão dos documentos fiscais contidos neste registro; no formato
“ddmmaaaa”, excluindo-se quaisquer caracteres de separação, tais como: “.”, “/”, “-”.
Validação: o valor informado no campo deve ser menor ou igual ao valor informado no campo DT_FIN do registro 0000.
Campo 11 – Preenchimento: este valor deve corresponder à soma dos campos VL_SERV, VL_SEG e VL_OUT_DESP,
subtraindo o valor do campo VL_DESC.
Valor total da Validação: o valor informado nesse campo deve ser maior que “0” (zero).
Campo 13 – Preenchimento: é o valor do serviço prestado, sem considerar despesas acessórias, seguros e demais
acréscimos.
Validação: o valor informado nesse campo deve ser maior que “0” (zero).
O valor informado neste campo deve ser igual à soma do valor do campo VL_SERV do registro D310 (agrupamento por
município).
Campo 16 - Validação: o valor informado neste campo deve ser igual à soma do valor do campo VL_BC_ICMS do
registro D310 (agrupamento por município).
Campo 17 - Validação: o valor informado neste campo deve ser igual à soma do valor do campo VL_ICMS do registro
D310 (agrupamento por município).
Página 89 de 163

--- Página 90 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 18 - Validação: este campo só pode ser preenchido se os dois últimos dígitos do campo 07 (CST_ICMS) forem
iguais a 20, 70 ou 90.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_MOD, SER, SUB, NUM_DOC_INI e NUM_DOC_FIN.
Não é permitida a sobreposição de intervalos de documentos.
REGISTRO D301: DOCUMENTOS CANCELADOS DOS BILHETES DE PASSAGEM
RODOVIÁRIO (CÓDIGO 13), DE PASSAGEM AQUAVIÁRIO (CÓDIGO 14), DE
PASSAGEM E NOTA DE BAGAGEM (CÓDIGO 15) E DE PASSAGEM FERROVIÁRIO
(CÓDIGO 16).
Este registro tem por objetivo informar os números dos documentos fiscais cancelados no intervalo constante no
registro pai.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D301" C 004 - Não O
02 NUM_DOC_CANC Número do documento fiscal cancelado N - - apresentar O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D301]
Campo 02 - Validação: o valor informado nesse campo deve ser maior que “0” (zero).
REGISTRO D310: COMPLEMENTO DOS BILHETES (CÓDIGO 13, 14, 15 E 16).
Este registro tem por objetivo agrupar por município de origem os valores dos documentos fiscais resumidos no
registro D300.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D310" C 004 - Não O
02 COD_MUN_ORIG Código do município de origem do serviço, N 007* - apresentar O
conforme a tabela IBGE
03 VL_SERV Valor total da prestação de serviço N - 02 O
04 VL_BC_ICMS Valor total da base de cálculo do ICMS N - 02 OC
05 VL_ICMS Valor total do ICMS N - 02 OC
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D310]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Validação do Registro: não podem ser informados dois ou mais registros com o mesmo valor para o campo
COD_MUN_ORIG.
REGISTRO D350 EQUIPAMENTO ECF (CÓDIGOS 2E, 13, 14, 15 e 16).
Este registro tem por objetivo identificar os equipamentos de ECF por todos os contribuintes que emitam Cupom
Fiscal Bilhete de Passagem (Código 2E), Bilhete de Passagem Rodoviário (13), Bilhete de Passagem Aquaviário (14),
Bilhete de Passagem e Nota de Bagagem (15) e Bilhete de Passagem Ferroviário (16).
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D350" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, conforme C 002* - apresentar O
a Tabela 4.1.1
03 ECF_MOD Modelo do equipamento C 020 - O
Página 90 de 163

--- Página 91 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
04 ECF_FAB Número de série de fabricação do ECF C 020 - O
05 ECF_CX Número do caixa atribuído ao ECF N 003 - O
Observações:
Nível hierárquico - 2
Ocorrência – 1:N
Campo 01 - Valor válido: [D350]
Campo 02 - Valores válidos: [2E, 13, 14, 15, 16].
Campo 05 - Preenchimento: informar o número do caixa atribuído pelo estabelecimento ao Equipamento Emissor de
Cupom Fiscal.
Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO D355 REDUÇÃO Z (CÓDIGOS 2E, 13, 14, 15 e 16).
Este registro deve ser apresentado com as informações da Redução Z de cada equipamento em funcionamento na
data das prestações à qual se refere a redução. Este registro inclui todos os documentos ficais, totalizados na Redução Z,
incluindo as prestações realizadas durante o período de tolerância do Equipamento ECF.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D355" C 004 - Não O
02 DT_DOC Data do movimento a que se refere a Redução Z N 008* - apresentar O
03 CRO Posição do Contador de Reinício de Operação N 003 - O
04 CRZ Posição do Contador de Redução Z N 006 - O
05 NUM_COO_FIN Número do Contador de Ordem de Operação do N 006 - O
último documento emitido no dia. (Número do
COO na Redução Z)
06 GT_FIN Valor do Grande Total final N - 02 O
07 VL_BRT Valor da venda bruta N - 02 O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor válido: [D355]
Campo 02 - Preenchimento: considerar a data do movimento, que inclui as operações de venda realizadas durante o
período de tolerância do Equipamento ECF, no formato “ddmmaaaa”, sem os caracteres de separação, tais como: ".", "/", "-
".
Validação: o valor informado deve ser menor ou igual à DT_FIN deste arquivo.
Campo 03 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 04 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 05 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 06 - Validação: o valor deste campo deve ser igual ou maior que o valor do campo VL_BRT.
Campo 07 - Preenchimento: valor acumulado no totalizador de venda bruta.
Validação: deve ser igual ao somatório do campo VLR_ACUM_TOT do registro D365 para os valores informados no
campo COD_TOT_PAR do registro D365.
REGISTRO D360: PIS E COFINS TOTALIZADOS NO DIA (CÓDIGOS 2E, 13, 14, 15 e 16).
Este registro somente deve ser apresentado para informar os valores de PIS e COFINS totalizados no dia.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D360" C 004 - Não O
02 VL_PIS Valor total do PIS N - 02 apresentar OC
03 VL_COFINS Valor total da COFINS N - 02 OC
Página 91 de 163

--- Página 92 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Observações:
Nível hierárquico - 4
Ocorrência – 1:1
Campo 01 - Valor Válido: [D360]
REGISTRO D365: REGISTRO DOS TOTALIZADORES PARCIAIS DA REDUÇÃO Z
(CÓDIGOS 2E, 13, 14, 15 e 16).
Este registro deve ser apresentado para discriminar os valores por código de totalizador da Redução Z.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D365" C 004 - Não O
02 COD_TOT_PAR Código do totalizador, conforme Tabela 4.4.6 C 007 - apresentar O
03 VLR_ACUM_TOT Valor acumulado no totalizador, relativo à N - 02 O
respectiva Redução Z.
04 NR_TOT Número do totalizador quando ocorrer mais de N 002 - OC
uma situação com a mesma carga tributária
efetiva.
05 DESCR_NR_TOT Descrição da situação tributária relativa ao C - - OC
totalizador parcial, quando houver mais de um
com a mesma carga tributária efetiva.
Observações:
Nível hierárquico - 4
Ocorrência - vários (por arquivo)
Campo 01 - Valor válido: [D365]
Campo 02 - Preenchimento: informar o código de totalizador parcial da Redução Z.
Para totalizadores tributáveis pelo ICMS, o conteúdo deste campo deve ser somente “Tnnnn”, onde “nnnn” corresponde à
alíquota informada no campo ALIQ_ICMS do registro D390. O valor “xx”, do formato “xxTnnnn”, conforme Convênio
80/07, para código de totalizador tributável pelo ICMS, deve ser informado no campo NR_TOT deste registro.
Validação: o valor informado deve existir na Tabela 4.4.6 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, que
discrimina os códigos dos Totalizadores Parciais da REDUÇÃO Z, prevista também na subseção 6.6 deste guia.
Campo 03 - Preenchimento: informar o valor acumulado no totalizador da situação tributária/alíquota.
Validação: somente para os totalizadores tributáveis pelo ICMS (campo COD_TOT_PAR) deste registro, com valor
“Tnnnn” ou “xxTnnnn”, o valor deste campo deve ser igual à soma do campo VL_BC_ICMS do registro D390 e também
deve ser igual à soma do campo VL_SERV do registro D370.
Campo 04 - Validação: o valor “xx”, do formato “xxTnnnn”, conforme Convênio 80/07, para código de totalizador
tributável pelo ICMS, deve ser informado no campo NR_TOT deste registro. Da mesma forma, este campo somente deve
ser preenchido com o número do totalizador parcial quando o campo COD_TOT_PARC for igual a xxTnnnn e houver
totalizadores distintos com a mesma carga tributária efetiva. O valor informado deve ser maior que “0” (zero).
Campo 05 - Validação: só deve ser preenchido se o campo NR_TOT estiver preenchido.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_TOT_PAR e NR_TOT.
REGISTRO D370: COMPLEMENTO DOS DOCUMENTOS INFORMADOS (CÓDIGOS 13,
14, 15 e 16 e 2E)
Este registro tem por objetivo agrupar por município de origem os valores dos totalizadores parciais da redução Z.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D370" C 004 - Não O
Página 92 de 163

--- Página 93 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
02 COD_MUN_ORIG Código do município de origem do serviço, N 007* - apresentar O
conforme a tabela IBGE
03 VL_SERV Valor total da prestação de serviço N - 02 O
04 QTD_BILH Quantidade de bilhetes emitidos N - - O
05 VL_BC_ICMS Valor total da base de cálculo do ICMS N - 02 OC
06 VL_ICMS Valor total do ICMS N - 02 OC
Observações:
Nível hierárquico - 5
Ocorrência – 1:N
Campo 01 - Valor válido: [D370]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Validação de Registro: registro obrigatório quando o valor no campo COD_TOT_PAR, do registro D365, seguir o
formato xxTnnnn, Tnnnn, Fn, In, Nn.
REGISTRO D390: REGISTRO ANALÍTICO DO MOVIMENTO DIÁRIO (CÓDIGOS 13, 14,
15, 16 E 2E).
Este registro representa a escrituração dos documentos fiscais emitidos por ECF e totalizados pela combinação de
CST, CFOP e Alíquota.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D390" C 004 - Não O
02 CST_ICMS Código da Situação Tributária, conforme a N 003* - apresentar O
Tabela indicada no item 4.3.1.
03 CFOP Código Fiscal de Operação e Prestação N 004* - O
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
05 VL_OPR Valor da operação correspondente à combinação N - 02 O
de CST_ICMS, CFOP, e alíquota do ICMS,
incluídas as despesas acessórias e acréscimos
06 VL_BC_ISSQN Valor da base de cálculo do ISSQN N - 02 OC
07 ALIQ_ISSQN Alíquota do ISSQN N 006 02 OC
08 VL_ISSQN Valor do ISSQN N - 02 OC
09 VL_BC_ICMS Base de cálculo do ICMS acumulada relativa à N - 02 O
alíquota informada
10 VL_ICMS Valor do ICMS acumulado relativo à alíquota N - 02 O
informada
11 COD_OBS Código da observação do lançamento fiscal C 006 - OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 4
Ocorrência – 1:N
Campo 01 - Valor válido: [D390]
Campo 02 – Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o 1º dígito
deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na Tabela B
constante no Anexo do Convênio SN/70.Validação:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero).
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos CST_ICMS, CFOP e ALIQ_ICMS.
Página 93 de 163

--- Página 94 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
REGISTRO D400: RESUMO DE MOVIMENTO DIÁRIO - RMD (CÓDIGO 18).
Este registro tem por objetivo a apresentação dos documentos emitidos pelas agências, postos, filiais ou veículos
de estabelecimentos que executam serviços de transporte com inscrição centralizada, quando autorizados pelo fisco
estadual.
Para cada registro D400, obrigatoriamente deve ser apresentado, pelo menos, um registro D420, observadas as
exceções abaixo relacionadas:
Exceção 1: Para documentos com código de situação (campo COD_SIT) cancelado (código “02”) ou cancelado
extemporâneo (código “03”), preencher somente os campos REG, COD_SIT, COD_MOD, SER, SUB e NUM_DOC.
Demais campos deverão ser apresentados com conteúdo VAZIO “||”.
Exceção 2: Notas Fiscais Complementares e Notas Fiscais Complementares Extemporâneas (campo COD_SIT igual a
“06” ou “07”): nesta situação, somente os campos REG, COD_PART, COD_MOD, COD_SIT, SER, SUB, NUM_DOC e
DT_DOC são obrigatórios. Os demais campos são facultativos (se forem preenchidos, serão validados e aplicadas as regras
de campos existentes). Demais registros filhos deverão ser informados, se houverem.
Exceção 3: Notas Fiscais emitidas por regime especial ou norma específica (campo COD_SIT igual a “08”). Para
documentos fiscais emitidos com base em regime especial ou norma específica, deverá ser apresentado o registro D400,
obrigatoriamente, e os demais registros “filhos”, se estes forem exigidos pela legislação fiscal. Nesta situação, somente os
campos REG, COD_PART, COD_MOD, COD_SIT, SER, SUB, NUM_DOC e DT_DOC são obrigatórios. Os demais
campos são facultativos (se forem preenchidos, serão validados e aplicadas as regras de campos existentes).
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D400" C 004 - Não O
02 COD_PART Código do participante (campo 02 do Registro C 060 - apresentar O
0150):
- agência, filial ou posto
03 COD_MOD Código do modelo do documento fiscal, conforme C 002* - O
a Tabela 4.1.1
04 COD_SIT Código da situação do documento fiscal, conforme N 002* - O
a Tabela 4.1.2
05 SER Série do documento fiscal C 004 - OC
06 SUB Subsérie do documento fiscal N 003 - OC
07 NUM_DOC Número do documento fiscal resumo. N 006 - O
08 DT_DOC Data da emissão do documento fiscal N 008* - O
09 VL_DOC Valor total do documento fiscal N - 02 O
10 VL_DESC Valor acumulado dos descontos N - 02 OC
11 VL_SERV Valor acumulado da prestação de serviço N - 02 O
12 VL_BC_ICMS Valor total da base de cálculo do ICMS N - 02 OC
13 VL_ICMS Valor total do ICMS N - 02 OC
14 VL_PIS Valor do PIS N - 02 OC
15 VL_COFINS Valor da COFINS N - 02 OC
16 COD_CTA Código da conta analítica contábil C - - OC
debitada/creditada
Observações:
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [D400]
Campo 02 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 03 - Valor Válido: [18]
Campo 04 - Valores Válidos: [00, 01, 02, 03, 06, 07, 08]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3.
Campo 07 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 08 - Preenchimento: informar a data no formato “ddmmaaaa”, sem separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 09 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Página 94 de 163

--- Página 95 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 16 – Preenchimento: informar o código da conta analítica. Exemplos: estoques, receitas, despesas, ativos. Deve
ser a conta credora ou devedora principal, podendo ser informada a conta sintética (nível acima da conta analítica).
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_PART, SER, NUM_DOC e DT_DOC.
REGISTRO D410: DOCUMENTOS INFORMADOS (CÓDIGOS 13, 14, 15 E 16).
Este registro tem por objetivo informar os documentos consolidados no Resumo de Movimento Diário (Código
18). Neste registro, deverão ser informados os documentos Bilhete de Passagem Rodoviário (Código 13), Bilhete de
Passagem Aquaviário (Código 14), Bilhete de Passagem Ferroviário (Código 16) e Bilhete de Passagem e Nota de
Bagagem (Código 15), não emitidos por ECF.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D410" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal , conforme C 002* - apresentar O
a Tabela 4.1.1
03 SER Série do documento fiscal C 004 - O
04 SUB Subsérie do documento fiscal N 003 - OC
05 NUM_DOC_INI Número do documento fiscal inicial (mesmo N 006 - O
modelo, série e subsérie)
06 NUM_DOC_FIN Número do documento fiscal final(mesmo modelo, N - - O
série e subsérie)
07 DT_DOC Data da emissão dos documentos fiscais N 008* - O
08 CST_ICMS Código da Situação Tributária, conforme a Tabela N 003* - O
indicada no item 4.3.1
09 CFOP Código Fiscal de Operação e Prestação N 004* - O
10 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
11 VL_OPR Valor total acumulado das operações N - 02 O
correspondentes à combinação de CST_ICMS,
CFOP e alíquota do ICMS, incluídas as despesas
acessórias e acréscimos.
12 VL_DESC Valor acumulado dos descontos N - 02 OC
13 VL_SERV Valor acumulado da prestação de serviço N - 02 O
14 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 O
15 VL_ICMS Valor acumulado do ICMS N - 02 O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D410]
Campo 02 - Valor Válido: [13, 14, 15, 16]
Campo 05 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 06 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 07 - Preenchimento: informar a data da emissão dos documentos fiscais, no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor do campo DT_FIN do registro 0000.
Campo 08 – Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o 1º dígito
deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na Tabela B
constante no Anexo do Convênio SN/70.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, constante do
Artigo 5º do Convênio SN/70.
Campo 09 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Anexo do Convênio SN/70.
Página 95 de 163

--- Página 96 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_MOD, SER, SUB, NUM_DOC_INI, NUM_DOC_FIN, CST_ICMS, CFOP e ALIQ_ICMS.
O valor no campo DT_DOC deve ser igual ao valor do campo DT_DOC do registro D400.
REGISTRO D411: DOCUMENTOS CANCELADOS DOS DOCUMENTOS INFORMADOS
(CÓDIGO 13, 14, 15 e 16).
Este registro tem por objetivo informar os números dos documentos fiscais cancelados.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D411" C 004 - Não O
02 NUM_DOC_CANC Número do documento fiscal cancelado N - - apresentar O
Observações:
Nível hierárquico - 4
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [D411]
Campo 02 - Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO D420: COMPLEMENTO DOS DOCUMENTOS INFORMADOS (CÓDIGO 13,
14, 15 e 16).
Este registro tem por objetivo agrupar por município de origem os valores resumidos no registro D400.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D420" C 004 - Não O
02 COD_MUN_ORIG Código do município de origem do serviço, N 007* - apresentar O
conforme a tabela IBGE
03 VL_SERV Valor total da prestação de serviço N - 02 O
04 VL_BC_ICMS Valor total da base de cálculo do ICMS N - 02 O
05 VL_ICMS Valor total do ICMS N - 02 O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D420]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
REGISTRO D500: NOTA FISCAL DE SERVIÇO DE COMUNICAÇÃO (CÓDIGO 21) E
NOTA FISCAL DE SERVIÇO DE TELECOMUNICAÇÃO (CÓDIGO 22).
Este registro tem por objetivo apresentar as notas fiscais de serviços de comunicações. Na aquisição de serviço,
será utilizado por todos os contribuintes; nas prestações de serviço, pelos contribuintes não enquadrados no Convênio
ICMS 115/03. Empresas sujeitas ao disposto no Convênio ICMS 115/03 deverão utilizar este registro para informar os
documentos emitidos nos modelos 21 e 22, nos casos não previstos no referido convênio, se houver.
Para cada registro D500, obrigatoriamente deve ser apresentado, pelo menos, um registro D590, observadas as
exceções abaixo relacionadas:
Exceção 1: Para documentos com código de situação (campo COD_SIT) cancelado (código “02”) ou cancelado
extemporâneo (código “03”), preencher somente os campos REG, IND_OPER, IND_EMIT, COD_MOD, COD_SIT, SER,
NUM_DOC e DT_DOC. Demais campos deverão ser informados com conteúdo VAZIO “||”.
Exceção 2: Notas Fiscais emitidas por regime especial ou norma específica (campo COD_SIT igual a “08”). Para
documentos fiscais emitidos com base em regime especial ou norma específica, deverão ser apresentados os registros D500
e D590, obrigatoriamente, e os demais registros “filhos”, se estes forem exigidos pela legislação fiscal. Nesta situação, no
registro D500, somente os campos REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT, SER,
NUM_DOC e DT_DOC são obrigatórios. Os demais campos são facultativos (se forem preenchidos, serão validados e
aplicadas as regras de campos existentes). No registro D590 deverão ser observados os campos obrigatórios.
Página 96 de 163

--- Página 97 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D500" C 004 - O O
02 IND_OPER Indicador do tipo de operação: C 001* - O O
0- Aquisição;
1- Prestação
03 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O O
0- Emissão própria;
1- Terceiros
04 COD_PART Código do participante (campo 02 do Registro C 060 - O O
0150):
- do prestador do serviço, no caso de aquisição;
- do tomador do serviço, no caso de prestação.
05 COD_MOD Código do modelo do documento fiscal, conforme C 002* - O O
a Tabela 4.1.1
06 COD_SIT Código da situação do documento fiscal, conforme N 002* - O O
a Tabela 4.1.2
07 SER Série do documento fiscal C 004 - OC OC
08 SUB Subsérie do documento fiscal N 003 - OC OC
09 NUM_DOC Número do documento fiscal N 009 - O O
10 DT_DOC Data da emissão do documento fiscal N 008* - O O
11 DT_A_P Data da entrada (aquisição) ou da saída (prestação N 008* - O O
do serviço)
12 VL_DOC Valor total do documento fiscal N - 02 O O
13 VL_DESC Valor total do desconto N - 02 OC OC
14 VL_SERV Valor da prestação de serviços N - 02 O O
15 VL_SERV_NT Valor total dos serviços não-tributados pelo ICMS N - 02 OC O
16 VL_TERC Valores cobrados em nome de terceiros N - 02 OC O
17 VL_DA Valor de outras despesas indicadas no documento N - 02 OC O
fiscal
18 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 OC O
19 VL_ICMS Valor do ICMS N - 02 OC O
20 COD_INF Código da informação complementar (campo 02 C 006 - OC OC
do Registro 0450)
21 VL_PIS Valor do PIS N - 02 OC OC
22 VL_COFINS Valor da COFINS N - 02 OC OC
23 COD_CTA Código da conta analítica contábil C - - OC OC
debitada/creditada
24 TP_ASSINANTE Código do Tipo de Assinante: N 001* - OC O
1 - Comercial/Industrial
2 - Poder Público
3 - Residencial/Pessoa física
4 - Público
5 - Semi-Público
6 - Outros
Observações: registro obrigatório nas operações de saídas, apenas para documentos emitidos fora do Convênio ICMS nº
115/2003, ou quando dispensados pela SEFAZ da entrega do arquivo previsto naquele convênio.Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [D500]
Campo 02 - Valores Válidos: [0,1]
Campo 03 - Valores Válidos: [0,1]
Campo 04 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 05 - Valores Válidos: [21, 22]
Campo 06 - Valores Válidos: [00, 01, 02, 03, 08]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3.
Página 97 de 163

--- Página 98 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 09 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 10 - Preenchimento: informar a data da emissão dos documentos fiscais, no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 11 - Preenchimento: informar a data da entrada ou saída da prestação do serviço, no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 20 - Validação: o valor informado deve ser informado no campo COD_INF do registro 0450.
Validação do Registro: não podem ser informados dois ou mais registros com a combinação de mesmos valores dos
campos IND_OPER, IND_EMIT, COD_PART, SER, SUB, NUM_DOC e DT+DOC.
Campo 24 - Valores Válidos: [1, 2, 3, 4, 5, 6]
REGISTRO D510: ITENS DO DOCUMENTO – NOTA FISCAL DE SERVIÇO DE
COMUNICAÇÃO (CÓDIGO 21) E SERVIÇO DE TELECOMUNICAÇÃO (CÓDIGO 22).
Este registro tem por objetivo informar os itens das Notas Fiscais de Serviços de Comunicação (código 21 da
Tabela Documentos Fiscais do ICMS) e Notas Fiscais de Serviços de Telecomunicação (código 22 da Tabela Documentos
Fiscais do ICMS). Não deve ser informado pelos adquirentes dos serviços.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D510" C 004 - Não O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - apresentar O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 COD_CLASS Código de classificação do item do serviço de N 004* - O
comunicação ou de telecomunicação, conforme a
Tabela 4.4.1
05 QTD Quantidade do item N - 03 O
06 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
07 VL_ITEM Valor do item N - 02 O
08 VL_DESC Valor total do desconto N - 02 OC
09 CST_ICMS Código da Situação Tributária, conforme a Tabela N 003* - O
indicada no item 4.3.1
10 CFOP Código Fiscal de Operação e Prestação N 004* - O
11 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 OC
12 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
13 VL_ICMS Valor do ICMS creditado/debitado N - 02 OC
14 VL_BC_ICMS_U Valor da base de cálculo do ICMS de outras UFs N - 02 OC
F
15 VL_ICMS_UF Valor do ICMS de outras UFs N - 02 OC
16 IND_REC Indicador do tipo de receita: C 001* - O
0- Receita própria - serviços prestados;
1- Receita própria - cobrança de débitos;
2- Receita própria - venda de mercadorias;
3- Receita própria - venda de serviço pré-pago;
4- Outras receitas próprias;
5- Receitas de terceiros (co-faturamento);
9- Outras receitas de terceiros
17 COD_PART Código do participante (campo 02 do Registro C 060 - OC
0150) receptor da receita, terceiro da operação, se
houver.
18 VL_PIS Valor do PIS N - 02 OC
19 VL_COFINS Valor da COFINS N - 02 OC
20 COD_CTA Código da conta analítica contábil C - - OC
debitada/creditada
Página 98 de 163

--- Página 99 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D510]
Campo 03 - Validação: o valor informado deve existir no campo COD_ITEM do registro 0200.
Campo 04 - Validação: o valor informado no campo deve existir na Tabela de Classificação de itens de Energia Elétrica,
Serviços de Comunicação e Telecomunicação, constante no item 4.4.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de
2008.
Campo 06 -Preenchimento: o valor informado deve constar no registro 0190, campo UNID.
Campo 09 Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o 1º dígito
deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na Tabela B
constante no Anexo do Convênio SN/70.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, constante do
Artigo 5º do Convênio SN/70.
Campo 10 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01.
Não podem ser utilizados os títulos dos agrupamentos de CFOP.
Campo 11 – Validação: Este campo deve ser igual a “0” (zero) caso o valor do Campo IND_REC seja 1, 5 ou 9.
Campo 12 – Validação: Este campo deve ser igual a “0” (zero) caso o valor do Campo IND_REC seja 1, 5 ou 9.
Campo 13 – Validação: Este campo deve ser igual a “0” (zero) caso o valor do Campo IND_REC seja 1, 5 ou 9.
Campo 16 - Valores Válidos: [0, 1, 2, 3, 4, 5, 9]
Validação: se o valor for 1, 5 ou 9, então os valores dos campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser
iguais a “0” (zero).
Campo 17 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 20 - Preenchimento: deve ser a conta credora ou devedora principal, podendo ser informada a conta sintética
(nível acima da conta analítica).
Validação do Registro: não podem ser informados dois ou mais registros com a combinação de mesmos valores dos
campos NUM_ITEM, COD_ITEM e COD_CLASS. O primeiro caractere do campo CFOP deve ser o mesmo para todos os
itens do documento.
REGISTRO D530: TERMINAL FATURADO.
Este registro tem por objetivo informar o terminal faturado de Nota Fiscal de Serviços de Comunicação (código 21
da Tabela Documentos Fiscais do ICMS) e Nota Fiscal de Serviços de Telecomunicação (código 22 da Tabela Documentos
Fiscais do ICMS).
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D530" C 004 - Não O
02 IND_SERV Indicador do tipo de serviço prestado: C 001* - apresentar O
0- Telefonia;
1- Comunicação de dados;
2- TV por assinatura;
3- Provimento de acesso à Internet;
4- Multimídia;
9- Outros
03 DT_INI_SERV Data em que se iniciou a prestação do serviço N 008* - OC
04 DT_FIN_SERV Data em que se encerrou a prestação do serviço N 008* - OC
Página 99 de 163

--- Página 100 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
05 PER_FISCAL Período fiscal da prestação do serviço N 006* - O
(MMAAAA)
06 COD_AREA Código de área do terminal faturado C - - OC
07 TERMINAL Identificação do terminal faturado N - - OC
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D530]
Campo 02 - Valores Válidos: [0, 1, 2, 3, 4, 9]
Campo 03 - Preenchimento: informar a data em que se iniciou a prestação de serviços, no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 04 - Preenchimento: informar a data em que encerrou a prestação de serviços, no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 05 - Preenchimento: informar o período fiscal da prestação do serviço, no formato “mmaaaa”.
REGISTRO D590: REGISTRO ANALÍTICO DO DOCUMENTO (CÓDIGO 21 E 22).
Este registro tem por objetivo apresentar a escrituração das Notas Fiscais de Serviços de Comunicação (código 21
da Tabela Documentos Fiscais do ICMS) e Notas Fiscais de Serviços de Telecomunicação (código 22 da Tabela
Documentos Fiscais do ICMS), prestadas no registro D500 e totalizados pela combinação de CST, CFOP e Alíquota.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D590" C 004 - O O
02 CST_ICMS Código da Situação Tributária, conforme a tabela N 003* - O O
indicada no item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação, conforme N 004* - O O
a tabela indicada no item 4.2.2
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC OC
05 VL_OPR Valor da operação correspondente à combinação N - 02 O O
de CST_ICMS, CFOP, e alíquota do ICMS,
incluídas as despesas acessórias e acréscimos
06 VL_BC_ICMS Parcela correspondente ao "Valor da base de N - 02 O O
cálculo do ICMS" referente à combinação
CST_ICMS, CFOP, e alíquota do ICMS
07 VL_ICMS Parcela correspondente ao "Valor do ICMS" N - 02 O O
referente à combinação CST_ICMS, CFOP, e
alíquota do ICMS
08 VL_BC_ICMS_U Parcela correspondente ao valor da base de N - 02 O O
F cálculo do ICMS de outras UFs, referente à
combinação de CST_ICMS, CFOP e alíquota do
ICMS.
09 VL_ICMS_UF Parcela correspondente ao valor do ICMS de N - 02 O O
outras UFs, referente à combinação de
CST_ICMS, CFOP, e alíquota do ICMS.
10 VL_RED_BC Valor não tributado em função da redução da base N - 02 O O
de cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
11 COD_OBS Código da observação (campo 02 do Registro C 006 - OC OC
0460)
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Página 100 de 163

--- Página 101 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 01 - Valor Válido: [D590]
Campo 02 - Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o 1º dígito
deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na Tabela B
constante no Anexo do Convênio SN/70.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, constante do
Artigo 5º do Convênio SN/70.
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme anexo do Convênio SN/70.
Campo 06 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_BC_ICMS
dos registros D510 (itens), se existirem, que possuam a mesma combinação dos campos CST_ICMS, CFOP e ALIQ_ICMS
deste registro.
Campo 07 - Preenchimento: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS
dos registros D510 (itens), que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 10 – Preenchimento: o valor deste campo só pode ser preenchido se os dois últimos dígitos do campo CST_ICMS
forem iguais a 20, 70 ou 90.
Validação: o valor informado neste campo deve ser maior que “0” (zero), se os dois últimos dígitos do campo CST_ICMS
forem iguais a 20 ou 70.
Campo 11 - Validação: o valor informado neste campo deve existir no campo COD_OBS do registro 0460.
Preenchimento: informar o código da observação.
Validação do Registro: não podem ser informados dois ou mais registros com a combinação de mesmos valores dos
campos CST_ICMS, CFOP e ALIQ_ICMS para o mesmo documento. A combinação CST_ICMS, CFOP e ALIQ_ICMS
deve existir no respectivo registro de itens do C510, quando este registro for exigido.
REGISTRO D600: CONSOLIDAÇÃO DA PRESTAÇÃO DE SERVIÇOS - NOTAS DE
SERVIÇO DE COMUNICAÇÃO (CÓDIGO 21) E DE SERVIÇO DE TELECOMUNICAÇÃO
(CÓDIGO 22).
Este registro tem por objetivo consolidar as Notas Fiscais de Serviço de Comunicação (Código 21 da Tabela
Documentos Fiscais do ICMS) e Notas Fiscais de Serviço de Telecomunicação (Código 22 da Tabela Documentos Fiscais
do ICMS) para empresas não obrigadas ao Convênio ICMS 115/2003. Este registro deve ser fornecido apenas para
prestações de saída.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D600" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, C 002* - aprese O
conforme a Tabela 4.1.1 ntar
03 COD_MUN Código do município dos terminais N 007* - O
faturados, conforme a tabela IBGE
04 SER Série do documento fiscal C 004 - O
05 SUB Subsérie do documento fiscal N 003 - OC
06 COD_CONS Código de classe de consumo dos serviços N 002* - O
de comunicação ou de telecomunicação,
conforme a Tabela 4.4.4
07 QTD_CONS Quantidade de documentos consolidados N - - O
neste registro
08 DT_DOC Data dos documentos consolidados N 008* - O
09 VL_DOC Valor total acumulado dos documentos N - 02 O
fiscais
10 VL_DESC Valor acumulado dos descontos N - 02 OC
11 VL_SERV Valor acumulado das prestações de serviços N - 02 O
tributados pelo ICMS
12 VL_SERV_N Valor acumulado dos serviços não- N - 02 OC
T tributados pelo ICMS
Página 101 de 163

--- Página 102 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
13 VL_TERC Valores cobrados em nome de terceiros N - 02 OC
14 VL_DA Valor acumulado das despesas acessórias N - 02 OC
15 VL_BC_ICMS Valor acumulado da base de cálculo do N - 02 O
ICMS
16 VL_ICMS Valor acumulado do ICMS N - 02 O
17 VL_PIS Valor do PIS N - 02 OC
18 VL_COFINS Valor da COFINS N - 02 OC
Observações: registro obrigatório nas operações de saídas, apenas para documentos emitidos fora do Convênio ICMS nº
115/2003, ou quando dispensados pela SEFAZ da entrega do arquivo previsto naquele convênio.
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [D600]
Campo 02 - Valores Válidos: [21, 22]
Preenchimento: informar o Código do modelo do documento fiscal, conforme a Tabela 4.1.1
Campo 03 - Preenchimento: informar o código do município dos terminais faturados.
Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 06 - Validação: o valor informado no campo deve existir na Tabela 4.4.4 do Ato COTEPE/ICMS nº 09, de 18 de
abril de 2008.
Campo 07 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 08 - Preenchimento: informar a data dos documentos consolidados, no formato “ddmmaaaa”, sem os separadores
de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo 05 (DT_FIN) do registro 0000.
Validação do Registro: não podem ser informados dois ou mais registros com a combinação de mesmos valores dos
campos COD_MOD, COD_MUN, SER, SUB, COD_CONS e DT_DOC.
REGISTRO D610: ITENS DO DOCUMENTO CONSOLIDADO (CÓDIGO 21 E 22).
Este registro tem por objetivo informar os itens das Notas Fiscais de Serviços de Comunicação (código 21 da
Tabela Documentos Fiscais do ICMS) e Notas Fiscais de Serviços de Telecomunicação (código 22 da Tabela Documentos
Fiscais do ICMS) consolidadas no registro D600.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D610" C 004 - Não O
02 COD_CLASS Código de classificação do item do serviço de N 004* - apresent O
comunicação ou de telecomunicação, conforme ar
a Tabela 4.4.1
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 QTD Quantidade acumulada do item N - 03 O
05 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
06 VL_ITEM Valor acumulado do item N - 02 O
07 VL_DESC Valor acumulado dos descontos N - 02 OC
08 CST_ICMS Código da Situação Tributária, conforme a N 003* - O
Tabela indicada no item 4.3.1
09 CFOP Código Fiscal de Operação e Prestação N 004* - O
conforme tabela indicada no item 4.2.2.
10 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
11 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 O
12 VL_ICMS Valor acumulado do ICMS debitado N - 02 O
13 VL_BC_ICMS Valor da base de cálculo do ICMS de outras N - 02 OC
_UF UFs
14 VL_ICMS_UF Valor do ICMS de outras UFs N - 02 OC
Página 102 de 163

--- Página 103 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
15 VL_RED_BC Valor não tributado em função da redução da N - 02 OC
base de cálculo do ICMS, referente à
combinação de CST_ICMS, CFOP e alíquota
do ICMS.
16 VL_PIS Valor acumulado do PIS N - 02 OC
17 VL_COFINS Valor acumulado da COFINS N - 02 OC
18 COD_CTA Código da conta analítica contábil C - - OC
debitada/creditada
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D610]
Campo 02 - Preenchimento: informar o código de classificação do item do serviço de comunicação ou de
telecomunicação, conforme a Tabela 4.4.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 03 - Validação: o valor informado deve constar no campo 02 (COD_ITEM) do registro 0200.
Campo 05 - Validação: o valor informado deve existir no registro 0190.
Campo 08 - Campo 09 Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o
1º dígito deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na
Tabela B constante no Anexo do Convênio SN/70.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, constante do
Anexo do Convênio SN/70 e obedecer as seguintes regras:
ICMS Normal:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero).
Campo 09 - Preenchimento: informar o Código Fiscal de Operação e Prestação.
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme anexo
Convênio SN/70.
Campo 18 - Preenchimento: informar o código da conta analítica contábil debitada/creditada.
Validação do Registro: o primeiro caractere do CFOP deve ser o mesmo para todos os itens do documento.
Não podem ser informados dois ou mais registros com o mesmo valor para o campo COD_ITEM, na combinação
COD_ITEM, CST_ICMS, CFOP e ALIQ_ICMS.
REGISTRO D690: REGISTRO ANALÍTICO DOS DOCUMENTOS (CÓDIGOS 21 e 22).
Este registro tem por objetivo apresentar a escrituração da consolidação das Notas Fiscais de Serviços de
Comunicação (código 21 da Tabela Documentos Fiscais do ICMS) e Notas Fiscais de Serviços de Telecomunicação
(código 22 da Tabela Documentos Fiscais do ICMS), prestadas no registro D600 e totalizados pela combinação de CST,
CFOP e Alíquota.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "D690" C 004 - Não O
02 CST_ICMS Código da Situação Tributária, conforme a tabela N 003* - apresent O
indicada no item 4.3.1 ar
03 CFOP Código Fiscal de Operação e Prestação, conforme N 004* - O
a tabela indicada no item 4.2.2
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
Página 103 de 163

--- Página 104 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
05 VL_OPR Valor da operação correspondente à combinação N - 02 O
de CST_ICMS, CFOP, e alíquota do ICMS,
incluídas as despesas acessórias e acréscimos
06 VL_BC_ICMS Parcela correspondente ao "Valor da base de N - 02 O
cálculo do ICMS" referente à combinação
CST_ICMS, CFOP, e alíquota do ICMS
07 VL_ICMS Parcela correspondente ao "Valor do ICMS" N - 02 O
referente à combinação CST_ICMS, CFOP, e
alíquota do ICMS
VL_BC_ICMS Parcela correspondente ao valor da base de N - 02 O
_UF cálculo do ICMS de outras UFs, referente
08
à combinação de CST_ICMS, CFOP e alíquota
do ICMS.
VL_ICMS_UF Parcela correspondente ao valor do ICMS de N - 02 O
09 outras UFs, referente à combinação de
CST_ICMS, CFOP, e alíquota do ICMS.
10 VL_RED_BC Valor não tributado em função da redução da base N - 02 O
de cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
11 COD_OBS Código da observação do lançamento fiscal C 006 - OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D690]
Campo 02 – Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o 1º dígito
deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na Tabela B
constante no Anexo do Convênio SN/70.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, constante do
Artigo 5º Anexo do Convênio SN/70 e obedecer as seguintes regras:
ICMS Normal:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero).
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Anexo do Convênio SN/70.
Campo 06 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS_ST dos
registros D610 (itens), se existirem, que possuam a mesma combinação de valores dos campos CST_ICMS, CFOP e
ALIQ_ICMS deste registro.
Campo 07 – Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS dos
registros D610 (itens), que possuam a mesma combinação de valores dos campos CST, CFOP e Alíquota deste registro.
Campo 08 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo
VL_BC_ICMS_ST dos registros D610 (itens), que possuam a mesma combinação de valores dos campos CST, CFOP e
Alíquota deste registro.
Campo 09 – Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS_ST
dos registros D610 (itens), que possuam a mesma combinação de valores dos campos CST, CFOP e Alíquota deste registro.
Campo 10 - Preenchimento: o valor deste campo só pode ser preenchido se os dois últimos dígitos do campo CST_ICMS
forem iguais a 20, 70 ou 90.
Validação: o valor informado neste campo deve ser maior que “0” (zero), se os dois últimos dígitos do campo CST_ICMS
forem iguais a 20 ou 70.
Página 104 de 163

--- Página 105 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 11 - Validação: O valor informado deve existir no campo COD_OBS do registro 0460.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos CST_ICMS, CFOP e ALIQ_ICMS. A combinação CST_ICMS, CFOP e ALIQ_ICMS deve existir no respectivo
registro de itens do (reg. D610), quando este registro for exigido.
REGISTRO D695: CONSOLIDAÇÃO DA PRESTAÇÃO DE SERVIÇOS - NOTAS DE
SERVIÇO DE COMUNICAÇÃO (CÓDIGO 21) E DE SERVIÇO DE TELECOMUNICAÇÃO
(CÓDIGO 22) (EMPRESAS OBRIGADAS À ENTREGA DOS ARQUIVOS PREVISTOS NO
CONVÊNIO ICMS 115/03).
Este registro tem por objetivo apresentar a consolidação das Notas Fiscais de Serviços de Comunicação (código 21
da Tabela Documentos Fiscais do ICMS) e Notas Fiscais de Serviços de Telecomunicação (código 22 da Tabela
Documentos Fiscais do ICMS) pelas empresas obrigadas ao Convênio ICMS 115/2003.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D695" C 004 - Não O
Código do modelo do documento fiscal, aprese O
02 COD_MOD C 002* -
conforme a Tabela 4.1.1. ntar
03 SER Série do documento fiscal C 004 - O
04 NRO_ORD_INI Número de ordem inicial N 009 - O
05 NRO_ORD_FIN Número de ordem final N 009 - O
Data de emissão inicial dos documentos / Data O
06 DT_DOC_INI N 008* -
inicial de vencimento da fatura
Data de emissão final dos documentos / Data O
07 DT_DOC_FIN N 008* -
final do vencimento da fatura
08 NOM_MEST Nome do arquivo Mestre de Documento Fiscal C 015 - O
Chave de codificação digital do arquivo Mestre O
09 CHV_COD_DIG C 032 -
de Documento Fiscal
Observações:
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [D695]
Campo 02 - Valores Válidos: [21, 22]
Preenchimento: informar o código do modelo do documento fiscal, conforme a Tabela 4.1.1.
Campo 06 - Preenchimento: informar a data de emissão inicial dos documentos, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 07 - Preenchimento: informar a data de emissão final dos documentos, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 08 - Preenchimento: informar o nome do volume do arquivo mestre de documento fiscal, conforme Convênio
ICMS 115/03.
Campo 09 - Preenchimento: informar a chave de codificação digital do arquivo mestre de documento fiscal, conforme
Parágrafo Único da Cláusula Segunda do Convênio ICMS 115/2003. Informar sempre o hash do arquivo extraído
(Convênio ICMS 52/05) entregue na UF do tomador de serviços quando diferente do prestador.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_MOD, SER, NRO_ORD_INI e NRO_ORD_FIN.
Não pode ocorrer sobreposição de intervalos para a mesma série.
Página 105 de 163

--- Página 106 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
REGISTRO D696: REGISTRO ANALÍTICO DOS DOCUMENTOS (CÓDIGO 21 E 22).
Este registro tem o objetivo de resumir o tratamento tributário aplicado aos documentos fiscais de serviços de
comunicação e telecomunicação, especificados no Registro D695, totalizados pelo CST, CFOP e Alíquota.
Este registro representa a escrituração da consolidação das Notas Fiscais de Serviços de Comunicação (código 21
da Tabela Documentos Fiscais do ICMS) e Notas Fiscais de Serviços de Telecomunicação (código 22 da Tabela
Documentos Fiscais do ICMS) prestadas no registro D695 e totalizadas pela combinação de CST, CFOP e Alíquota, em
conformidade com os documentos constantes dos arquivos referentes ao Convênio ICMS nº 115/03.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores
dos campos CST_ICMS, CFOP e ALIQ_ICMS.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D696" C 004 - Não O
Código da Situação Tributária, conforme a tabela N 003* - aprese O
02 CST_ICMS
indicada no item 4.3.1 ntar
Código Fiscal de Operação e Prestação, conforme a O
03 CFOP N 004* -
tabela indicada no item 4.2.2
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
VL_OPR Valor da operação correspondente à combinação de O
05 CST_ICMS, CFOP, e alíquota do ICMS, incluídas N - 02
as despesas acessórias e acréscimos
Parcela correspondente ao "Valor da base de O
06 VL_BC_ICMS cálculo do ICMS" referente à combinação N - 02
CST_ICMS, CFOP, e alíquota do ICMS
Parcela correspondente ao "Valor do ICMS" O
07 VL_ICMS referente à combinação CST_ICMS, CFOP, e N - 02
alíquota do ICMS
Parcela correspondente ao valor da base de cálculo O
VL_BC_ICMS
08 do ICMS de outras UFs, referente à combinação de N - 02
_UF
CST_ICMS, CFOP e alíquota do ICMS
Parcela correspondente ao valor do ICMS de outras O
09 VL_ICMS_UF UFs, referente à combinação de CST_ICMS, N - 02
CFOP, e alíquota do ICMS
10 VL_RED_BC Valor não tributado em função da redução da base N - 02 O
de cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
11 COD_OBS Código da observação do lançamento fiscal (campo C 006 - OC
02 do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [D696]
Campo 02 – Preenchimento: o código de Situação Tributária é composto de três dígitos na forma ABB, onde o 1º dígito
deve ser sempre 0 (zero), para este registro, e os 2º e 3º dígitos indicam a tributação pelo ICMS, com base na Tabela B
constante no Anexo do Convênio SN/70.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, constante do
Anexo do Convênio SN/70 e obedecer as seguintes regras:
ICMS Normal:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero).
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme anexo do Convênio SN/70.
Campo 06 – Preenchimento (Orientações exclusivas para empresas prestadoras de serviços de TV por assinatura –
via satélite):
Página 106 de 163

--- Página 107 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
1. Na unidade federada do prestador de serviços: informar o valor correspondente ao somatório da base de cálculo
utilizada de todos os documentos do volume do arquivo referente ao Convênio ICMS nº 115/03.
2. Na unidade federada do tomador dos serviços: informar o valor correspondente ao somatório da base de cálculo
utilizada dos documentos emitidos referentes a clientes da UF do tomador de serviços e constantes do volume do
arquivo extraído, citado no Convênio ICMS nº 52/05.
Campo 07 – Preenchimento (Orientações exclusivas para empresas prestadoras de serviços de TV por assinatura –
via satélite):
1. na unidade federada do prestador de serviços: informar o valor correspondente ao somatório dos valores de
ICMS de todos os documentos do volume do arquivo referente ao Convênio ICMS nº 115/03.
2. na unidade federada do tomador dos serviços: informar o valor correspondente ao somatório dos valores de
ICMS dos documentos emitidos referentes a clientes da UF do tomador de serviços e constantes do volume do
arquivo extraído, citado no Convênio ICMS nº 52/05.
Campo 08 – Preenchimento (Orientações exclusivas para empresas prestadoras de serviços de TV por assinatura –
via satélite): Informar somente na unidade federada do prestador de serviços - informar o valor correspondente ao
somatório da base de cálculo utilizada de todos os documentos emitidos para clientes situados nas demais UFs e constantes
do volume do arquivo citado no Convênio ICMS nº 115/03.
Preencher com Zero quando for EFD da UF do tomador de serviços.
Campo 09 – Preenchimento (Orientações exclusivas para empresas prestadoras de serviços de TV por assinatura –
via satélite): Informar somente na unidade federada do prestador de serviços - informar o valor correspondente ao
somatório do valor do ICMS de todos os documentos emitidos para clientes situados nas demais UFs e constantes do
volume do arquivo citado no Convênio ICMS nº 115/03.
Preencher com Zero quando for EFD da UF do tomador de serviços.
Campo 10 – Validação: o valor informado neste campo deve ser maior que “0” (zero) se os dois últimos dígitos do campo
CST_ICMS forem iguais a 20 ou 70.
Campo 11 - Validação: o valor informado deve existir no campo COD_OBS do registro 0460.
REGISTRO D697: REGISTRO DE INFORMAÇÕES DE OUTRAS UFs, RELATIVAMENTE
AOS SERVIÇOS “NÃO-MEDIDOS” DE TELEVISÃO POR ASSINATURA VIA SATÉLITE.
Este registro deve ser apresentado para a UF do prestador de serviços pelas empresas do setor, para informar os
valores da base de cálculo e o valor de ICMS, totalizados por UF dos tomadores de serviços, conforme documentos
emitidos e constantes dos arquivos do Convênio ICMS nº 115/03.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "D697" C 004 - Não O
02 UF Sigla da unidade da federação C 002* - O
03 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 apresen O
tar O
04 VL_ICMS Valor do ICMS N - 02
Observações:
Nível hierárquico - 4
Ocorrência – 1:N
Campo 01 - Valor Válido: [D697]
Campo 02 - Validação: o valor deve ser a sigla de uma unidade da federação (UF) válida.
Campo 03 – Preenchimento: informar o somatório dos valores de base de cálculo de ICMS de todos os documentos
emitidos para a UF informada no campo 02.
Campo 04 – Preenchimento: informar o somatório dos valores de ICMS à UF informada no campo 02.
REGISTRO D990: ENCERRAMENTO DO BLOCO D.
Este registro tem por objetivo identificar o encerramento do bloco D e informar a quantidade de linhas (registros)
existentes no bloco.
Página 107 de 163

--- Página 108 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
01 REG Texto fixo contendo "D990" C 004 - O O
02 QTD_LIN_D Quantidade total de linhas do Bloco D N - - O O
Observações:
Nível hierárquico - 1
Ocorrência – um por arquivo
Campo 01 - Valor Válido: [D990]
Campo 02 - Preenchimento: A quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco.
Validação: O número de linhas (registros) existentes no bloco D é igual ao valor informado no campo QTD_LIN_D.
BLOCO E: APURAÇÃO DO ICMS E DO IPI
Bloco de registros dos dados relativos à apuração do ICMS e do IPI.
REGISTRO E001: ABERTURA DO BLOCO E
Este registro tem por objetivo abrir o Bloco E e indica se há informações sobre apuração do ICMS e do IPI.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E001" C 004 - O
02 IND_MOV Indicador de movimento: C 001 - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [E001]
Campo 02 - Valor Válido: [0]
Validação: além dos registros de abertura e encerramento, sempre devem ser informados os registros E100 (período de
apuração) e E110 (valores da apuração própria).
REGISTRO E100: PERÍODO DA APURAÇÃO DO ICMS.
Este registro tem por objetivo informar o(s) período(s) de apuração do ICMS. Os períodos informados devem
abranger todo o intervalo da escrituração fiscal, sem sobreposição ou omissão de datas ou períodos.
Não podem ser informados dois ou mais registros com a mesma combinação de valores dos campos 02 (DT_INI),
03 (DT_FIN). Não devem existir lacunas ou sobreposições de datas nos períodos de apuração informados nestes registros,
em comparação com as datas informadas no registro 0000.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E100" C 004 - O
02 DT_INI Data inicial a que a apuração se refere N 008* - O
03 DT_FIN Data final a que a apuração se refere N 008* - O
Observações:
Nível hierárquico – 2
Ocorrência – 1:N
Campo 01 - Valores válidos: [E100]
Campo 02 - Preenchimento: informar a data inicial a que se refere a apuração, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000 e maior ou
igual ao valor no campo DT_INI do registro 0000. A data informada no campo deve ser menor ou igual à data informada
no campo DT_FIN do registro E100. .
Página 108 de 163

