# Bloco 1 - Versão 2.0.0

**Data de Criação:** 2009-12-17  
**Páginas:** 123-137  
**Versão:** 2.0.0

---

--- Página 123 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
05 VL_UNIT Valor unitário do item N - 06 O
06 VL_ITEM Valor do item N - 02 O
07 IND_PROP Indicador de propriedade/posse do item: C 001* - O
0- Item de propriedade do informante e em seu poder;
1- Item de propriedade do informante em posse de terceiros;
2- Item de propriedade de terceiros em posse do informante
08 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - OC
- proprietário/possuidor que não seja o informante do arquivo
09 TXT_COMPL Descrição complementar. C - - OC
10 COD_CTA Código da conta analítica contábil debitada/creditada C - - O
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [H010]
Campo 02 - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
Campo 03 - Validação: o valor deve ser informado no registro 0200, campo UNID_INV.
Campo 07 - Valores Válidos: [0, 1, 2]
Validação: se preenchido com valor ‘1’ (posse de terceiros) ou ‘2’ (propriedade de terceiros), o campo COD_PART será
obrigatório.
Campo 08 – Preenchimento obrigatório quando o indicador de propriedade do item do campo 07 for “1” ou “2”.
Validação: o valor fornecido deve constar no campo COD_PART do registro 0150.
Campo 10 - Preenchimento: informar o código da conta analítica contábil correspondente. Deve ser a conta credora ou
devedora principal, podendo ser a informada a conta sintética (nível acima da conta analítica). Nas situações de um mesmo
código de item possuir mais de uma destinação deve ser informada a conta referente ao item de maior relevância.
REGISTRO H990: ENCERRAMENTO DO BLOCO H.
Este registro destina-se a identificar o encerramento do bloco H e a informar a quantidade de linhas (registros) existentes no
bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H990" C 004 - O
02 QTD_LIN_H Quantidade total de linhas do Bloco H N - - O
Observações:
Nível hierárquico - 1
Ocorrência –um por arquivo
Campo 01 - Valor Válido: [H990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de aber-
tura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco H é igual ao valor informado no campo QTD_LIN_H.
BLOCO 1: OUTRAS INFORMAÇÕES
Este bloco destina-se à prestação de outras informações exigidas pelo fisco.
REGISTRO 1001: ABERTURA DO BLOCO 1
Este registro deverá ser gerado para abertura do Bloco 1 e indicará se há informações no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1001" C 004 - O
02 IND_MOV Indicador de movimento: N 001* - O
Página 123 de 158

--- Página 124 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico – 1
Ocorrência - um por arquivo
Campo 01 - Valor Válido: [1001]
Campo 02 - Valores Válidos: [0, 1]
Validação: se preenchido com ‘1’ (sem dados informados), então somente pode ser informado o registro 1990 (encerra-
mento do Bloco). Se preenchido com ‘0’, então deve ser informado pelo menos um registro além dos registros 1001 (aber-
tura do Bloco) e 1990 (encerramento do Bloco).
REGISTRO 1100: REGISTRO DE INFORMAÇÕES SOBRE EXPORTAÇÃO.
Este registro deve ser preenchido no mês em que se concluir a exportação direta ou indireta pelo efetivo exportador.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “1100” C 004 - O
02 IND_DOC Informe o tipo de documento: N 001* - O
0 – Declaração de Exportação;
1 - Declaração Simplificada de Exportação.
03 NRO_DE Número da declaração N 011 - O
04 DT_DE Data da declaração (DDMMAAAA) N 008* - O
05 NAT_EXP Preencher com: N 001* - O
0 - Exportação Direta
1 - Exportação Indireta
06 NRO_RE Nº do registro de Exportação N 012 - OC
07 DT_RE Data do Registro de Exportação (DDMMAAAA) N 008* - OC
08 CHC_EMB Nº do conhecimento de embarque C 018 - OC
09 DT_CHC Data do conhecimento de embarque (DDMMAAAA) N 008* - OC
10 DT_AVB Data da averbação da Declaração de exportação (ddmmaaaa) N 008* - O
11 TP_CHC Informação do tipo de conhecimento de embarque: N 002* - O
01 – AWB;
02 – MAWB;
03 – HAWB;
04 – COMAT;
06 – R. EXPRESSAS;
07 – ETIQ. REXPRESSAS;
08 – HR. EXPRESSAS;
09 – AV7;
10 – BL;
11 – MBL;
12 – HBL;
13 – CRT;
14 – DSIC;
16 – COMAT BL;
17 – RWB;
18 – HRWB;
19 – TIF/DTA;
20 – CP2;
91 – NÂO IATA;
92 – MNAO IATA;
93 – HNAO IATA;
99 – OUTROS.
12 PAIS Código do país de destino da mercadoria (Preencher confor- N 003 - O
me tabela do SISCOMEX)
Observações:
Página 124 de 158

--- Página 125 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Nível hierárquico - 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1100]
Campo 02 – Preenchimento: quando for DE ou DDE, preencher com código 0.
Valores Válidos: [0, 1]
Campo 04 - Preenchimento: informar a data da declaração no formato “ddmmaaaa”, sem separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 05 - Valores Válidos: [0, 1]
Campo 06 – Preenchimento: este campo deve ser preenchido se o campo IND_DOC for “0” (zero).
Campo 07 - Preenchimento: informar a data do registro de exportação no formato “ddmmaaaa”, sem separadores de for-
matação. Este campo deve ser preenchido se o campo IND_DOC for “0” (zero).
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 09 - Preenchimento: informar a data do conhecimento de embarque no formato “ddmmaaaa”, sem separadores de
formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 10 - Preenchimento: informar a data da averbação da declaração de exportação no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000
REGISTRO 1105: DOCUMENTOS FISCAIS DE EXPORTAÇÃO.
Este registro deve ser apresentado para discriminar os documentos fiscais vinculados à exportação.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1105" C 004 - O
02 COD_MOD Código do modelo da NF, conforme tabela 4.1.1 C 002* - O
03 SERIE Série da Nota Fiscal C 003 - OC
04 NUM_DOC Número de Nota Fiscal de Exportação emitida pelo Exportador N 009 - O
05 CHV_NFE Chave da Nota Fiscal Eletrônica N 044* - OC
06 DT_DOC Data da emissão da NF de exportação N 008* - O
07 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [1105]
Campo 02 - Valores Válidos: [01, 55]
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Validação: se modelo da nota fiscal for 55, o campo é obrigatório.
O dígito verificador da chave NF-e será validado.
Para confirmação inequívoca de que a chave da NF-e informada corresponde aos dados informados sobre o documento,
será comparado o CNPJ existente na CHV_NFE com o campo CNPJ do registro 0000, que corresponde ao CNPJ do infor-
mante do arquivo. Será verificada a consistência da informação do campo NUM_DOC e o número do documento contido
na chave da NFe. Será também comparada a UF codificada na Chave da NF-e com o campo 09 (UF) no registro 0000.
Campo 06 - Preenchimento: informar a data da emissão da nota fiscal de exportação no formato “ddmmaaaa”, sem sepa-
radores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Página 125 de 158

--- Página 126 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Campo 07 - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
REGISTRO 1110: OPERAÇÕES DE EXPORTAÇÃO INDIRETA DE PRODU-
TOS NÃO INDUSTRIALIZADOS PELO ESTABELECIMENTO EMITENTE.
Este registro deve ser apresentado para informar a origem das mercadorias adquiridas para a exportação.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1110" C 004 - O
02 COD_PART Código do participante-Fornecedor da Mercadoria destinada à C 060 - O
exportação (campo 02 do Registro 0150)
03 COD_MOD Código do documento fiscal, conforme a Tabela 4.1.1 C 002* O
04 SER Série do documento fiscal recebido com fins específicos de expor- C 004 - OC
tação.
05 NUM_DOC Número do documento fiscal recebido com fins específicos de N 009 - O
exportação.
06 DT_DOC Data da emissão do documento fiscal recebido com fins específi- N 008* - O
cos de exportação
07 CHV_NFE Chave da Nota Fiscal Eletrônica N 044* - OC
08 NR_ MEMO Número do Memorando de Exportação N OC
09 QTD Quantidade do item efetivamente exportado. N - 03 O
10 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [1110]
Campo 02 - Validação: o valor fornecido deve estar no campo COD_PART do registro 0150.
Campo 03 - Valores Válidos: [01, 1B, 04, 55]
Campo 05 – Preenchimento: informar o número do documento fiscal emitido pelo participante para o exportador.
Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 06 - Preenchimento: informar a data da emissão do documento fiscal no formato “ddmmaaaa”, sem separadores
de formatação.
Validação: o valor informado no campo deve ser uma data válida.
Campo 07 – Preenchimento: informar a chave da NF-e emitida pelo participante para o exportador.
Validação: se o modelo da nota fiscal for 55, o campo é obrigatório.
O dígito verificador da Chave da NF-e será validado.
Será verificada a consistência da informação do campo NUM_DOC e o número do documento contido na chave da NFE.
Será verificado o CNPJ constante da chave da Nota Fiscal Eletrônica com o CNPJ constante do registro 0150.
Campo 08 - Preenchimento: informar o número do Memorando de Exportação, quando houver.
Campo 09 - Validação: o valor informado no campo deve ser maior que “0” (zero)
Campo 10 - Validação: o valor deve estar informado no registro 0190.
REGISTRO 1200: CONTROLE DE CRÉDITOS FISCAIS - ICMS.
Este registro demonstra a conta corrente dos créditos fiscais de ICMS, controlados extra-apuração. Cada UF determinará a
obrigatoriedade de apresentação deste registro.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1200" C 004 - O
02 COD_AJ_APUR Código de ajuste, conforme informado na Tabela indi- C 008* - O
Página 126 de 158

--- Página 127 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
cada no item 5.1.1.
03 SLD_CRED Saldo de créditos fiscais de períodos anteriores N - 02 O
04 CRÉD_APR Total de crédito apropriado no mês N - 02 O
05 CRED_RECEB Total de créditos recebidos por transferência N - 02 O
06 CRED_UTIL Total de créditos utilizados no período N - 02 O
Saldo de crédito fiscal acumulado a transportar para o N - 02 O
07 SLD_CRED_FIM
período seguinte
Observações:
Nível hierárquico - 2
Ocorrência – 1:N
Campo 01 - Valor Válido: [1200]
Campo 02 - Validação: O valor informado deve existir na Tabela 5.1.1 (Tabela de Códigos de Ajustes da Apuração do
ICMS) do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, que discrimina os códigos de ajustes previstos pelos Estados
para a apuração do ICMS.
Campo 04 – Preenchimento: o valor a ser informado neste campo corresponde ao valor do crédito fiscal que o contribu-
inte apropriou ou adquiriu durante o período.
Campo 06 – Preenchimento: o valor a ser informado neste campo corresponde ao valor total dos créditos utilizados no
período, que aparecem de forma detalhada nos registros 1210.
Validação: o valor informado neste campo deve ser igual ao somatório do campo VL_CRED_UTIL do Registro 1210.
Campo 07 – Preenchimento: informar o valor do saldo de crédito fiscal após a utilização (informado nos registros 1210)
no período, saldo este a ser transportado para o período seguinte. Este valor representa a soma dos campos SLD_CRED,
CRÉD_APR e CRED_RECEB, menos o campo CRED_UTIL.
Validação: o valor desse campo deve ser igual a soma dos valores dos campos SLD_CRED, CRÉD_APR e
CRED_RECEB, diminuída do valor do campo CRED_UTIL.
REGISTRO 1210: UTILIZAÇÃO DE CRÉDITOS FISCAIS – ICMS.
Este registro deve ser apresentado para detalhar a utilização de créditos fiscais de ICMS no período.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1210" C 004 - O
02 TIPO_UTIL Tipo de utilização do crédito, conforme tabela indicada no item 5.5. C 004* - O
03 NR_DOC Número do documento utilizado na baixa de créditos C - - OC
VL_CRED_U N - 02 O
04 Total de crédito utilizado
TIL
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válid: [1210]
Campo 02 - Validação: o valor informado deve estar de acordo com a tabela publicada pela UF do informante do arquivo.
Em caso de não publicação, pela UF, a tabela a ser informada é a constante no item 5.5 do Ato COTEPE/ICMS nº 09, de 18
de abril de 2008, constante também da subseção 6.5 deste guia.
Campo 04 - Preenchimento: informar o total de crédito utilizado para esta situação, que é definida pelo campo TI-
PO_UTIL deste registro.
Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO 1300: MOVIMENTAÇÃO DIÁRIA DE COMBUSTÍVEIS
Este registro deve ser apresentado pelos contribuintes do ramo varejista de combustíveis (postos de combustíveis). Este
registro se refere à movimentação diária de combustíveis, havendo apenas um registro por tipo de combustível e por data
do fechamento da movimentação (campo COD_ITEM e campo DT_FECH), independente de ocorrerem intervenções. Não
pode haver mais de um registro com o mesmo código de combustível e mesma data de fechamento.
Página 127 de 158

--- Página 128 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1300" C 004 - O
02 COD_ITEM Código do Produto, constante do registro 0200 C 060 - O
03 DT_FECH Data do fechamento da movimentação N 008* - O
04 ESTQ_ABERT Estoque no inicio do dia, em litros N - 03 O
05 VOL_ENTR Volume Recebido no dia (em litros) N - 03 O
06 VOL_DISP Volume Disponível (04 + 05), em litros N - 03 O
07 VOL_SAIDAS Volume Total das Saídas, em litros N - 03 O
08 ESTQ_ESCR Estoque Escritural (06 – 07), litros N - 03 O
09 VAL_AJ_PERDA Valor da Perda, em litros N - 03 O
10 VAL_AJ_GANHO Valor do ganho, em litros N - 03 O
11 FECH_FISICO Estoque de Fechamento, em litros N - 03 O
Observações:
Nível hierárquico – 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1300]
Campo 02 - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
Campo 03 - Preenchimento: informar a data da movimentação no formato “ddmmaaaa”, sem separadores de formatação.
Validação: o valor informado no campo deve ser uma data válida. A data informada deve ser maior ou igual ao campo
DT_INI do registro 0000 e menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 04 - Preenchimento: informar o estoque do início do dia, mesmo que tenha ocorrido intervenção posterior.
Campo 05 - Preenchimento: informar o volume de combustível recebido no dia da movimentação (registro C171).
Campo 06 - Preenchimento: informar o volume disponível, que corresponde à soma dos campos ESTQ_ABERT e
VOL_ENTR.
Campo 07 - Preenchimento: informar o volume (em litros) total das saídas, que corresponde à soma dos registros de vo-
lume de vendas.
Campo 08 - Preenchimento: informar o estoque escritural, que corresponde ao valor constante no campo VOL_DISP
menos o valor constante no campo VOL_SAIDAS.
Campo 11 - Preenchimento: informar o estoque do fim do dia.
REGISTRO 1310: MOVIMENTAÇÃO DIÁRIA DE COMBUSTÍVEIS POR
TANQUE
Este registro deve ser apresentado para informar a movimentação diária por tanque. Não pode haver mais de um registro
com o mesmo número de tanque.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1310" C 004 - O
02 NUM_TANQUE Tanque que armazena o combustível. N - - O
03 ESTQ_ABERT Estoque no inicio do dia, em litros N - 03 O
04 VOL_ENTR Volume Recebido no dia (em litros) N - 03 O
05 VOL_DISP Volume Disponível (03 + 04), em litros N - 03 O
06 VOL_SAIDAS Volume Total das Saídas, em litros N - 03 O
07 ESTQ_ESCR Estoque Escritural(05 – 06), litros N - 03 O
08 VAL_AJ_PERDA Valor da Perda, em litros N - 03 O
09 VAL_AJ_GANHO Valor do ganho, em litros N - 03 O
10 FECH_FISICO Volume aferido no tanque, em litros. Estoque de fechamen- N - 03 O
to físico do tanque.
Observações:
Página 128 de 158

--- Página 129 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [1310]
Campo 03 - Preenchimento: informar o estoque do início do dia para o tanque especificado no campo NUM_TANQUE,
mesmo que tenha ocorrido intervenção posterior na bomba.
Campo 04 - Preenchimento: o valor fornecido deve corresponder ao volume de combustível informado nos documentos
fiscais (registro C171), especificado por tanque, para o dia da movimentação.
Campo 05 - Preenchimento: informar o volume disponível, que corresponde à soma dos campos ESTQ_ABERT e
VOL_ENTR, para o tanque especificado no campo NUM_TANQUE.
Campo 06 - Preenchimento: informar o volume (em litros) total das saídas, que corresponde à soma dos registros de vo-
lume de vendas, para o tanque especificado no campo NUM_TANQUE.
Campo 07 - Preenchimento: informar o estoque escritural, que corresponde ao valor constante no campo VOL_DISP
menos o valor constante no campo VOL_SAIDAS, para o tanque especificado no campo NUM_TANQUE.
Campo 10 - Preenchimento: informar o estoque do fim do dia para o tanque especificado no campo NUM_TANQUE.
REGISTRO 1320: VOLUME DE VENDAS
Este registro deve ser apresentado para discriminar o volume das vendas no dia, considerando-se vendas todas as saídas
promovidas a qualquer título. Não havendo intervenção, haverá apenas um registro por bico e os campos NR_INTERV,
MOT_INTERV, NOM_INTERV, CNPJ_INTERV e CPF_INTERV estarão sem informação. Para cada intervenção ocorri-
da na bomba associada ao bico, um novo registro deve ser preenchido com dados da intervenção e os valores totalizados
desde a intervenção até uma próxima intervenção ou o fim do dia.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1320" C 004 - O
02 NUM_BICO Bico Ligado à Bomba N - - O
03 NR_INTERV Número da intervenção N - - OC
04 MOT_INTERV Motivo da Intervenção C 050 - OC
05 NOM_INTERV Nome do Interventor C 030 - OC
06 CNPJ_INTERV CNPJ da empresa responsável pela intervenção N 014* - OC
07 CPF_INTERV CPF do técnico responsável pela intervenção N 011* - OC
08 VAL_FECHA Valor da leitura final do contador, no fechamento do bico. N - 03 O
09 VAL_ABERT Valor da leitura inicial do contador, na abertura do bico. N - 03 O
10 VOL_AFERI Aferições da Bomba, em litros N - 03 OC
11 VOL_VENDAS Vendas (08 – 09 - 10 ) do bico , em litros N - 03 O
Observações:
Nível hierárquico – 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [1320]
Campo 02 - Preenchimento: informar o número do bico associado ao tanque do respectivo registro pai.
Campo 03 - Preenchimento: numeração atribuída à intervenção pelo órgão competente ou, na falta deste, um número
seqüencial criado pelo próprio declarante. Se não ocorrer intervenção no bico este campo não deverá ser preenchido.
Campo 04 - Preenchimento: nome da empresa responsável pela intervenção. Se não ocorrer intervenção no bico este
campo não deverá ser preenchido.
Campo 05 - Preenchimento: NOM_INTERV: nome do técnico autorizado (mecânico) pelo INMETRO (através de suas
unidades estaduais) para atuar em manutenção de bombas medidoras de combustível (a autorização é especifica para essas).
Se não ocorrer intervenção no bico este campo não deverá ser preenchido.
Página 129 de 158

--- Página 130 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Campo 06 - Preenchimento: CNPJ_INTERV: CNPJ da empresa responsável pelo contrato de manutenção, para quem o
técnico autorizado trabalha (quando houver). Se não ocorrer intervenção no bico este campo não deverá ser preenchido.
Campo 07 - Preenchimento: CPF_INT ERV: CPF do técnico autorizado (mecânico), vinculado ao campo
[NOM_INTERV]. Se não ocorrer intervenção no bico este campo não deverá ser preenchido.
Campo 08 - Preenchimento: fornecer a leitura final do contador (encerrante), no momento do fechamento. O valor aqui é
o do contador, e não em litros.
Campo 09 - Preenchimento: fornecer a leitura inicial do contador (encerrante), no momento da abertura. O valor aqui é o
do contador, e não em litros.
Campo 10 - Preenchimento: informar o volume, em litros, relativo às aferições efetuadas.
Campo 11 - Preenchimento: informar o volume de vendas por bico, ligado ao tanque, que corresponde ao valor fornecido
no campo VAL_FECHA menos a soma do campo VAL_ABERT com o campo VOL_AFERI.
REGISTRO 1350: BOMBAS
Este registro deve ser apresentado para discriminar as bombas pertencentes ao varejista.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1350" C 004 - O
02 SERIE Número de Série da Bomba C - - O
03 FABRICANTE Nome do Fabricante da Bomba C 060 - O
04 MODELO Modelo da Bomba C - - O
05 TIPO_MEDICAO Identificador de medição: C 001 - O
0 - analógico;
1 – digital
Observações:
Nível hierárquico – 2
Ocorrência - 1:N
Campo 01 - Valor Válido [1350]
Campo 05 - Valores Válidos: [0, 1]
REGISTRO 1360: LACRES DA BOMBA
Este registro deve ser apresentado para discriminar os lacres aplicados à bomba referenciada no registro pai.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1360" C 004 - O
02 NUM_LACRE Número do Lacre associado na Bomba C 020 - O
03 DT_APLICACAO Data de aplicação do Lacre N 008* - O
Observações:
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [1360]
Campo 03 - Preenchimento: informar a data de aplicação do lacre no formato “ddmmaaaa”, sem separadores de formata-
ção.
Validação: o valor informado no campo deve ser uma data válida.
REGISTRO 1370: BICOS DA BOMBA
Este registro deve ser apresentado para discriminar os bicos pertencentes à bomba referenciada no registro pai.
Página 130 de 158

--- Página 131 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1370" C 004 - O
02 NUM_BICO Número seqüencial do bico ligado a bomba N 003 - O
03 COD_ITEM Código do Produto, constante do registro 0200 C 060 - O
04 NUM_TANQUE Tanque que armazena o combustível. N - - O
Observações:
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido [1370]
Campo 02 – Preenchimento: caso o tanque não esteja ligado à bicos de bomba, servindo apenas como reservatório
de combustível para as demais bombas, informar código “990” em diante.
Campo 03 - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
REGISTRO 1400: INFORMAÇÃO SOBRE VALORES AGREGADOS
Este registro tem como objetivo fornecer informações para o cálculo do valor adicionado por Município, sendo utilizado
para subsidiar cálculos de índices de participação e deve ser apresentado apenas se a unidade federada do declarante assim
o exigir.
Deve ser preenchido pelos seguintes contribuintes:
• empresas que adquirirem, diretamente de produtor, produtos agrícolas, pastoris, extrativos minerais, pescados
ou outros produtos extrativos ou agropecuários;
• empresas que emitem documentos fiscais de entrada de produção própria, de produtos agrícolas, pastoris, ex-
trativos minerais, pescados ou outros produtos extrativos ou agropecuários;
• empresas de transporte intermunicipal e interestadual;
• empresas de telecomunicação e comunicação;
• empresas de energia;
• serviço de utilidade pública de distribuição de água;
• inscrição centralizada;
• demais casos que influenciem no valor agregado.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1400" C 004 - O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - OC
03 MUN Código do Município de origem N 007* - O
04 VALOR Valor mensal correspondente ao município N - 2 O
Observações:
Nível hierárquico - 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1400]
Campo 02 - Validação: o valor informado deve existir no campo COD_ITEM do registro 0200.
Campo 03 – Preenchimento: regras para os contribuintes obrigados, conforme o tipo de empresa:
1. empresas que adquirirem produtos agrícolas, pastoris, extrativos minerais, pescados ou outros produ-
tos, de pessoa física ou pessoa jurídica não inscrita no cadastro da Fazenda Estadual, oriundos de
municípios do Estado do informante, através de nota fiscal de entrada, modelos 1, 1A ou 55 , ou no-
ta fiscal avulsa a elas destinada. Excetuam-se, destes casos, as notas fiscais de venda futura. Preen-
chimento: município de origem dos produtos;
2. empresas que emitem documentos fiscais de entrada de produção própria, de produtos agrícolas, pas-
toris, extrativos minerais, pescados ou outros produtos extrativos ou agropecuários. Preenchimento:
município de origem dos produtos;
3. transporte intermunicipal e interestadual - Preenchimento: município onde ocorreu o fato gerador, ou
seja, o município onde ocorreu o início da prestação do serviço;
4. telecomunicação e comunicação – Preenchimento: município onde ocorreu a prestação de serviço;
Página 131 de 158

--- Página 132 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
5. energia – Preenchimento: se distribuidora - município onde ocorreu o fornecimento;
6. serviço de utilidade pública de distribuição de água – Preenchimento: se distribuidora - município
onde ocorreu a distribuição;
Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 04 – Preenchimento: regras para os contribuintes obrigados, conforme o tipo de empresa:
1. transporte intermunicipal e interestadual - Preenchimento: valor contábil, dos serviços prestados, por
municípios onde foram cobrados, deduzido as aquisições ou prestações de serviço;
2. telecomunicação e comunicação – Preenchimento: valor contábil, dos serviços prestados, por muni-
cípios onde foram cobrados, deduzido as aquisições ou prestações de serviço;
3. energia – Preenchimento: se distribuidora - valor contábil total do fornecimento de energia, deduzido
o valor do suprimento (compra de energia de outras concessionárias e ou custo da geração própria);
4. serviço de utilidade pública de distribuição de água –se for distribuidora, o valor contábil total do
fornecimento, deduzido o valor do suprimento e/ou do custo da geração própria;
5. para as demais empresas, o valor referente às entradas.
Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO 1500: NOTA FISCAL/CONTA DE ENERGIA ELÉTRICA (CÓDI-
GO 06) – OPERAÇÕES INTERESTADUAIS.
Este registro deve ser apresentado, nas operações de saída interestaduais, pelos contribuintes do segmento de energia elétri-
ca, obrigados ao Convênio 115/2003.
Para apresentação do registro 1500 e filhos devem ser observadas as exceções abaixo relacionadas:
Exceção 1: Notas Fiscais Complementares e Notas Fiscais Complementares Extemporâneas (campo COD_SIT igual a
“06” ou “07”): nesta situação, somente os campos REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT,
SER, SUB, NUM_DOC e DT_DOC são obrigatórios. Os demais campos são facultativos (se forem preenchidos, serão
validados e aplicadas as regras de campos existentes). Os registros filhos do registro 1500 deverão ser informados, se exis-
tirem.
Exceção 2: Notas Fiscais emitidas por regime especial ou norma específica (campo COD_SIT igual a “08”). Para documen-
tos fiscais emitidos com base em regime especial ou norma específica, deverá ser apresentado o registro 1500, obrigatoria-
mente, e os registros “filhos”, se estes forem exigidos pela legislação fiscal. Nesta situação, somente os campos REG,
IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT, SER, SUB, NUM_DOC e DT_DOC são obrigatórios. Os
demais campos são facultativos (se forem preenchidos, serão validados e aplicadas as regras de campos existentes).
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "1500" C 004 - O
02 IND_OPER Indicador do tipo de operação: C 001* - O
1- Saída
03 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O
0- Emissão própria;
04 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - O
- do adquirente, no caso das saídas.
05 COD_MOD Código do modelo do documento fiscal, conforme a C 002* - O
Tabela 4.1.1
06 COD_SIT Código da situação do documento fiscal, conforme a N 002* - O
Tabela 4.1.2
07 SER Série do documento fiscal C 004 - OC
08 SUB Subsérie do documento fiscal N 003 - OC
09 COD_CONS Código de classe de consumo de energia elétrica: C 002* - O
01 - Comercial
02 - Consumo Próprio
03 - Iluminação Pública
04 - Industrial
05 - Poder Público
06 - Residencial
07 - Rural
08 -Serviço Público
Página 132 de 158

--- Página 133 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
10 NUM_DOC Número do documento fiscal N 009 - O
11 DT_DOC Data da emissão do documento fiscal N 008* - O
12 DT_E_S Data da entrada ou da saída N 008* - O
13 VL_DOC Valor total do documento fiscal N - 02 O
14 VL_DESC Valor total do desconto N - 02 OC
15 VL_FORN Valor total fornecido/consumido N - 02 O
16 VL_SERV_NT Valor total dos serviços não-tributados pelo ICMS N - 02 OC
17 VL_TERC Valor total cobrado em nome de terceiros N - 02 OC
18 VL_DA Valor total de despesas acessórias indicadas no documen- N - 02 OC
to fiscal
19 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 OC
20 VL_ICMS Valor acumulado do ICMS N - 02 OC
21 VL_BC_ICMS_ST Valor acumulado da base de cálculo do ICMS substitui- N - 02 OC
ção tributária
22 VL_ICMS_ST Valor acumulado do ICMS retido por substituição tribu- N - 02 OC
tária
23 COD_INF Código da informação complementar do documento C 006 - OC
fiscal (campo 02 do Registro 0450)
24 VL_PIS Valor do PIS N - 02 OC
25 VL_COFINS Valor da COFINS N - 02 OC
26 TP_LIGACAO Código de tipo de Ligação N 001* - OC
1 - Monofásico
2 - Bifásico
3 - Trifásico
27 COD_GRUPO_TENSAO Código de grupo de tensão: C 002* - OC
01 - A1 - Alta Tensão (230kV ou mais)
02 - A2 - Alta Tensão (88 a 138kV)
03 - A3 - Alta Tensão (69kV)
04 - A3a - Alta Tensão (30kV a 44kV)
05 - A4 - Alta Tensão (2,3kV a 25kV)
06 - AS - Alta Tensão Subterrâneo 06
07 - B1 - Residencial 07
08 - B1 - Residencial Baixa Renda 08
09 - B2 - Rural 09
10 - B2 - Cooperativa de Eletrificação Rural
11 - B2 - Serviço Público de Irrigação
12 - B3 - Demais Classes
13 - B4a - Iluminação Pública - rede de distribuição
14 - B4b - Iluminação Pública - bulbo de lâmpada
Observações:
Nível hierárquico - 2
Ocorrência - vários (por arquivo)
Campo 01 - Valor válido: [1500]
Campo 02 - Valor válido: [1]
Campo 03 - Valor válido: [0]
Campo 04 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 05 - Valor válido: [06]
Campo 06 - Valores válidos: [00, 01, 06, 07, 08]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3.
Campo 09 - Valores válidos: [“01”, “02”, “03’, “04”, “05”, “06”, “07”, “08”]
Campo 10 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 11 - Preenchimento: data de emissão da nota fiscal no formato “ddmmaaaa”.
Validação: o valor informado no campo deve ser menor ou igual que o valor do campo DT_FIN do registro 0000.
Página 133 de 158

--- Página 134 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Campo 12 - Preenchimento: data de entrada ou saída da nota fiscal no formato “ddmmaaaa”.
Campo 13 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 15 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 23 - Validação: o valor informado no campo deve existir no registro 0450.
Campo 26 - Valores válidos: [1, 2, 3]
Campo 27 - Valores válidos: [01, 02, 03, 04, 05, 06, 07, 08, 09, 10, 11, 12, 13, 14]
REGISTRO 1510: ITENS DO DOCUMENTO NOTA FISCAL/CONTA ENER-
GIA ELÉTRICA (CÓDIGO 06)
Este registro deve ser apresentado para informar os itens das Notas Fiscais/Contas de Energia Elétrica (código 06 da Tabela
Documentos Fiscais do ICMS) apresentadas nos registros 1500.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "1510" C 004 - O
02 NUM_ITEM Número seqüencial do item no documento fiscal N 003 - O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 COD_CLASS Código de classificação do item de energia elétrica, conforme N 004* - O
a Tabela 4.4.1
05 QTD Quantidade do item N - 03 OC
06 UNID Unidade do item (Campo 02 do registro 0190) C 006 - OC
07 VL_ITEM Valor do item N - 02 O
08 VL_DESC Valor total do desconto N - 02 OC
09 CST_ICMS Código da Situação Tributária, conforme a Tabela indicada N 003* - O
no item 4.3.1
10 CFOP Código Fiscal de Operação e Prestação N 004* - O
11 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 OC
12 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
13 VL_ICMS Valor do ICMS creditado/debitado N - 02 OC
14 VL_BC_ICMS_ST Valor da base de cálculo referente à substituição tributária N - 02 OC
15 ALIQ_ST Alíquota do ICMS da substituição tributária na unidade da N - 02 OC
federação de destino
16 VL_ICMS_ST Valor do ICMS referente à substituição tributária N - 02 OC
17 IND_REC Indicador do tipo de receita: C 001* - O
0- Receita própria;
1- Receita de terceiros
18 COD_PART Código do participante receptor da receita, terceiro da opera- C 060 OC
ção (campo 02 do Registro 0150)
19 VL_PIS Valor do PIS N - 02 OC
20 VL_COFINS Valor da COFINS N - 02 OC
21 COD_CTA Código da conta analítica contábil debitada/creditada C - - OC
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [1510]
Campo 03 - Validação: o valor informado no campo deve existir no registro 0200, campo COD_ITEM.
Campo 04 - Validação: o valor informado no campo deve existir na Tabela de Classificação de Itens de Energia Elétrica,
Serviços de Comunicação e Telecomunicação, constante no item 4.4.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de
2008.
Campo 06 - Validação: o valor deve estar informado no registro 0190.
Página 134 de 158

--- Página 135 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Campo 09 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS,
referenciada no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
ICMS Normal:
d) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
e) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
f) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero);
ICMS ST:
d) se os dois últimos caracteres deste campo forem 10, 30 ou 70, os valores dos campos VL_BC_ST, A-
LIQ_ST e VL_ICMS_ST deverão ser maiores ou iguais “0” (zero).
b) se os dois últimos caracteres deste campo forem diferentes de 10, 30 ou 70, os valores dos campos
VL_BC_ST, ALIQ_ST e VL_ICMS_ST deverão ser iguais a “0” (zero).
Campo 10 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01.
O primeiro caractere do CFOP deve ser igual a 6.
O primeiro caractere do CFOP deve ser o mesmo para todos os itens do documento.
Não podem ser utilizados códigos que correspondam aos títulos dos agrupamentos de CFOP.
Campo 17 - Valores válidos: [0, 1]
Campo 18 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
REGISTRO 1600: TOTAL DAS OPERAÇÕES COM CARTÃO DE CRÉDITO
E/OU DÉBITO
Este registro destina-se a identificar o valor total das operações de vendas realizadas pelo declarante cujo recebimento pelo
estabelecimento tenha sido por cartão de débito ou de crédito, discriminado por administradora. Deve ser informado o valor
total dos recebimentos em cartões excluídos os estornos, cancelamentos e outros recebimentos não vinculados à sua ativi-
dade operacional. A obrigatoriedade deste registro deve ser verificada junto a cada uma das unidades federativas.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "1600" C 004 - O
02 COD_PART Código do participante (campo 02 do Registro 0150): iden- C 060 - O
tificação da administradora do cartão de débito/crédito
03 TOT_CREDITO Valor total das operações realizadas no período referente a N - 002 O
Cartão de Crédito
04 TOT_DEBITO Valor total das operações realizadas no período referente a N - 002 O
Cartão de Débito
Observações:
Nível hierárquico – 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1600]
Campo 02 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
REGISTRO 1700 - DOCUMENTOS FISCAIS UTILIZADOS
Neste registro devem ser informados os documentos emitidos no período da EFD. A obrigatoriedade deste registro deve ser
verificada junto a cada uma das unidades federativas.
Nº Campo Tipo Tam Dec
Descrição
01 REG Texto fixo contendo “1700”. C 004 -
02 COD_DISP Código dispositivo autorizado: C 002* -
Página 135 de 158

--- Página 136 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
00 - Formulário de Segurança
01 - FS-DA – Formulário de Segurança para Impressão de DANFE
02 – Formulário de segurança - NF-e
03 - Formulário Contínuo
04 – Blocos
05 - Jogos Soltos
03 COD_MOD Código do modelo do documento fiscal, conforme a Tabela 4.1.1 C 002* -
04 SER Série do documento fiscal C 004 -
05 SUB Subsérie do documento fiscal C 003 -
06 NUM_DOC_INI Número do documento fiscal inicial N 012 -
07 NUM_DOC_FIN Número do documento fiscal final N 012 -
08 NUM_AUT Número da autorização, conforme dispositivo autorizado N 060 -
Observações:
Nível hierárquico - 2
Ocorrência – V
Campo 01 - Valor Válido: [1700]
Campo 02 - Valores Válidos: [“00”,“01”,“02”,“03”,“04”,“05”]
01 - FS-DA – Formulário de Segurança para Impressão de DANFE – Formulário utilizado para NF-e em contingência, con-
forme Ajuste Sinief 07/2005 e suas alterações.
02 – Formulário de Segurança - NF-e - Formulário solicitado para emissão de NF-e em contingência,
conforme Ajuste Sinief 07/2005 e suas alterações.
Campo 03 - Preenchimento: o valor informado deve constar na tabela 4.1.1 do Ato COTEPE/ICMS nº 09, de 18 de abril
de 2008.
Campo 06 - Preenchimento: Número inicial do intervalo do documento, informado no campo 02, utilizado no período da
EFD.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos respec-
tivos documentos utilizados.
Campo 07 - Preenchimento: Número final do intervalo do documento, informado no campo 02, utilizado no período da
EFD.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos respec-
tivos documentos utilizados.
Campo 08 - Preenchimento: Número da autorização, emitida pela Secretaria estadual, para utilização dos documentos
informados no campo 2, do respectivo intervalo informado.
REGISTRO 1710 - DOCUMENTOS FISCAIS CANCELADOS/INUTILIZADOS
Neste registro devem ser informados os documentos cancelados/inutilizados no intervalo constante do Registro 1700.
Nº Campo Descrição Tipo Tam Dec
01 REG Texto fixo contendo “1710”. C 004 -
02 NUM_DOC_INI Número do documento fiscal inicial N 012 -
03 NUM_DOC_FIN Número do documento fiscal final N 012 -
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [1710]
Campo 02 - Preenchimento: Número inicial do documento cancelado ou intervalo, informado no campo 02.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos respec-
tivos documentos utilizados.
Observação: Quando o cancelamento não for contínuo, o número inicial deverá ser igual ao número final.
Exemplo : Reg 1700 Campo 06 35; Campo 07 55
Canceladas: 45; 50 a 52. Então, teremos: Reg 1710 Campo 02 45; Campo 03 45
Reg 1710 Campo 02 50; Campo 03 52
Página 136 de 158

--- Página 137 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Campo 03 - Preenchimento: Número final do documento ou intervalo, informado no campo 02.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos respec-
tivos documentos utilizados.
REGISTRO 1800 – DCTA – DEMONSTRATIVO DE CRÉDITO DO ICMS SO-
BRE TRANSPORTE AÉREO
Este registro deve ser informado para explicitar os estornos de créditos de ICMS, pela empresas de transporte aéreo.
Nº Campo Descrição Tipo Tam Dec
01 REG Texto fixo contendo “1800”. C 004* -
02 VL_CARGA Valor das prestações cargas (Tributado) N - 02
03 VL_PASS Valor das prestações passageiros/cargas (Não Tributado) N - 02
04 VL_FAT Valor total do faturamento (2+3) N - 02
05 IND_RAT Índice para rateio(2 / 4) N 006 02
06 VL_ICMS_ANT Valor total dos créditos do ICMS N - 02
07 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02
08 VL_ICMS_APUR Valor do ICMS apurado no cálculo (5 x 6) N - 02
09 VL_BC_ICMS_APUR Valor da base de cálculo do ICMS apurada (5 x 7) N - 02
10 Valor da diferença a ser levada a estorno de crédito na apuração 02
VL_DIF N -
(6 - 8)
Observações:
Nível hierárquico - 2
Ocorrência – 1:1
Campo 01 - Valor Válido: [1800]
REGISTRO 1990: ENCERRAMENTO DO BLOCO 1
Este registro destina-se a identificar o encerramento do Bloco 1 e a informar a quantidade de linhas (registros) existentes no
bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1990" C 004 - O
02 QTD_LIN_1 Quantidade total de linhas do Bloco 1 N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [1990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de aber-
tura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco 1 é igual ao valor informado no campo QTD_LIN_1.
Página 137 de 158

