# Bloco 1 - Versão 2.0.12

**Data de Criação:** 2013-03-01  
**Páginas:** 143-165  
**Versão:** 2.0.12

---

--- Página 143 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
BLOCO 1: OUTRAS INFORMAÇÕES
Este bloco destina-se à prestação de outras informações exigidas pelo fisco.
REGISTRO 1001: ABERTURA DO BLOCO 1
Este registro deverá ser gerado para abertura do bloco 1 e indicará se há informações no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1001" C 004 - O
02 IND_MOV Indicador de movimento: N 001* - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico – 1
Ocorrência - um por arquivo
Campo 01 - Valor Válido: [1001]
Campo 02 - Valores Válidos: [0, 1]
Validação: além dos registros de abertura e encerramento, sempre deve ser informado o registro 1010 (Obrigatoriedade de
Registros do Bloco 1).
REGISTRO 1010: OBRIGATORIEDADE DE REGISTROS DO BLOCO 1
Este registro deverá ser apresentado por todos os contribuintes. Caso a resposta seja “S”, o contribuinte está
obrigado à apresentação do registro respectivo. Se houver dispensa de apresentação do registro pela unidade federada, a
resposta para o campo específico do registro deverá ser “N”.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1010" C 004* - O
02 IND_EXP Reg. 1100 - Ocorreu averbação (conclusão) de exportação no C 001* - O
período:
S – Sim
N - Não
03 IND_CCRF Reg 1200 – Existem informações acerca de créditos de ICMS a C 001* - O
serem controlados, definidos pela Sefaz:
S – Sim
N - Não
04 IND_COMB Reg. 1300 – É comercio varejista de combustíveis com C 001* - O
movimentação e/ou estoque no período:
S – Sim
N - Não
05 IND_USINA Reg. 1390 – Usinas de açúcar e/álcool – O estabelecimento é C 001* - O
produtor de açúcar e/ou álcool carburante com movimentação e/ou
estoque no período:
S – Sim
N - Não
06 IND_VA Reg 1400 – Sendo o registro obrigatório em sua Unidade de C 001* - O
Federação, existem informações a serem prestadas neste registro:
S – Sim;
N - Não
07 IND_EE Reg 1500 - A empresa é distribuidora de energia e C 001* - O
ocorreu fornecimento de energia elétrica para consumidores de
outra UF:
S – Sim;
N - Não
08 IND_CART Reg 1600 - Realizou vendas com Cartão de Crédito ou de débito: C 001* - O
Página 143 de 188

--- Página 144 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
S – Sim;
N - Não
09 IND_FORM Reg. 1700 – Foram emitidos documentos fiscais em papel no C 001* - O
período em unidade da federação que exija o controle de
utilização de documentos fiscais:
S – Sim
N - Não
10 IND_AER Reg 1800 – A empresa prestou serviços de transporte aéreo de C 001* - O
cargas e de passageiros:
S – Sim
N - Não
Obs.:
Nível hierárquico - 2
Ocorrência – 1:1
Campo 04 – Preenchimento : Se não houver movimentação e/ou estoque no período, informar Não.
Campo 05 – Preenchimento : Se não houver movimentação e/ou estoque no período, informar Não.
Campo 09 – Preenchimento: Sim, somente quando emitir documento fiscal em papel com autorização de impressão.
REGISTRO 1100: REGISTRO DE INFORMAÇÕES SOBRE EXPORTAÇÃO.
Este registro deve ser preenchido no mês em que se concluir a exportação direta ou indireta pelo efetivo
exportador.
No caso de ocorrer mais de um Registro de Exportação (RE) para uma mesma Declaração de Exportação (DE),
deve ser informado um registro 1100 para cada RE.
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
Página 144 de 188

--- Página 145 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
92 – MNAO IATA;
93 – HNAO IATA;
99 – OUTROS.
12 PAIS Código do país de destino da mercadoria (Preencher N 003 - O
conforme tabela do SISCOMEX)
Observações:
Nível hierárquico - 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1100]
Campo 02 – Preenchimento: quando for DE ou DDE, preencher com código 0.
Valores Válidos: [0, 1]
Campo 04 - Preenchimento: informar a data da declaração no formato “ddmmaaaa”, sem separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 05 - Valores Válidos: [0, 1]
Campo 06 – Preenchimento: este campo deve ser preenchido se o campo IND_DOC for “0” (zero).
Campo 07 - Preenchimento: informar a data do registro de exportação no formato “ddmmaaaa”, sem separadores de
formatação. Este campo deve ser preenchido se o campo IND_DOC for “0” (zero).
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 09 - Preenchimento: informar a data do conhecimento de embarque no formato “ddmmaaaa”, sem separadores de
formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 10 - Preenchimento: informar a data da averbação da declaração de exportação no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000
Campo 12 - Validação: O valor informado no campo deverá existir na tabela de Países do SISCOMEX.
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
Campo 02 - Valores Válidos: [01, 55] – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Validação: se modelo da nota fiscal for 55, o campo é obrigatório e o dígito verificador da chave NF-e será
validado.
Página 145 de 188

--- Página 146 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Serão verificados a consistência da informação do campo NUM_DOC e o número do documento contido na chave da NF-
e.
Campo 06 - Preenchimento: informar a data da emissão da nota fiscal de exportação no formato “ddmmaaaa”, sem
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 07 - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
REGISTRO 1110: OPERAÇÕES DE EXPORTAÇÃO INDIRETA - MERCADORIAS DE
TERCEIROS.
Este registro deve ser apresentado para informar a origem das mercadorias adquiridas para a exportação.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1110" C 004 - O
02 COD_PART Código do participante-Fornecedor da Mercadoria destinada à C 060 - O
exportação (campo 02 do Registro 0150)
03 COD_MOD Código do documento fiscal, conforme a Tabela 4.1.1 C 002* O
04 SER Série do documento fiscal recebido com fins específicos de C 004 - OC
exportação.
05 NUM_DOC Número do documento fiscal recebido com fins específicos de N 009 - O
exportação.
06 DT_DOC Data da emissão do documento fiscal recebido com fins N 008* - O
específicos de exportação
07 CHV_NFE Chave da Nota Fiscal Eletrônica N 044* - OC
08 NR_ MEMO Número do Memorando de Exportação N OC
09 QTD Quantidade do item efetivamente exportado. N - 03 O
10 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [1110]
Campo 02 - Validação: o valor fornecido deve estar no campo COD_PART do registro 0150.
Campo 03 - Valores Válidos: [01, 1B, 04, 55] – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 05 – Preenchimento: informar o número do documento fiscal emitido pelo participante para o exportador.
Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 06 - Preenchimento: informar a data da emissão do documento fiscal no formato “ddmmaaaa”, sem separadores
de formatação.
Validação: o valor informado no campo deve ser uma data válida.
Campo 07 – Preenchimento: informar a chave da NF-e emitida pelo participante para o exportador.
Validação: se o modelo da nota fiscal for 55, o campo é obrigatório. Serão verificados: o dígito verificador da chave de
acesso, o número do documento informado e o constante na chave e o CNPJ constante no registro 0150.
Campo 08 - Preenchimento: informar o número do Memorando de Exportação, quando houver.
Campo 09 - Validação: o valor informado no campo deve ser maior que “0” (zero)
Campo 10 - Validação: o valor deve estar informado no registro 0190.
Página 146 de 188

--- Página 147 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
REGISTRO 1200: CONTROLE DE CRÉDITOS FISCAIS - ICMS.
Este registro demonstra a conta corrente dos créditos fiscais de ICMS, controlados extra-apuração. Cada UF
determinará a obrigatoriedade de apresentação deste registro.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1200" C 004 - O
02 COD_AJ_APUR Código de ajuste, conforme informado na Tabela C 008* - O
indicada no item 5.1.1.
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
A partir de janeiro de 2013, somente poderão ser utilizados os códigos nos quais o quarto caractere seja igual a “9”.
Campo 04 – Preenchimento: o valor a ser informado neste campo corresponde ao valor do crédito fiscal que o
contribuinte apropriou ou adquiriu durante o período.
Campo 06 – Preenchimento: o valor a ser informado neste campo corresponde ao valor total dos créditos utilizados no
período, que aparecem de forma detalhada nos registros 1210.
Validação: o valor informado neste campo deve ser igual ao somatório do campo VL_CRED_UTIL do registro 1210.
Campo 07 – Preenchimento: informar o valor do saldo de crédito fiscal após a utilização (informado nos registros 1210)
no período, saldo este a ser transportado para o período seguinte. Este valor representa a soma dos campos SLD_CRED,
CRÉD_APR e CRED_RECEB, menos o campo CRED_UTIL.
Validação: o valor desse campo deve ser igual à soma dos valores dos campos SLD_CRED, CRED_APR e
CRED_RECEB, diminuída do valor do campo CRED_UTIL.
REGISTRO 1210: UTILIZAÇÃO DE CRÉDITOS FISCAIS – ICMS.
Este registro deve ser apresentado para detalhar a utilização de créditos fiscais de ICMS no período. O somatório
dos valores do campo 04 deste registro deve corresponder ao informado no campo 06 do registro 1200.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1210" C 004 - O
02 TIPO_UTIL Tipo de utilização do crédito, conforme tabela indicada no item C 004* - O
5.5.
03 NR_DOC Número do documento utilizado na baixa de créditos C - - OC
VL_CRED_U N - 02 O
04 Total de crédito utilizado
TIL
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [1210]
Campo 02 - Validação: o valor informado deve estar de acordo com a tabela publicada pela UF do informante do arquivo.
Em caso de não publicação, pela UF, a tabela a ser informada é a constante no item 5.5 do Ato COTEPE/ICMS nº 09, de 18
de abril de 2008, constante também da subseção 6.5 deste guia.
Página 147 de 188

--- Página 148 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Campo 04 - Preenchimento: informar o total de crédito utilizado para esta situação, que é definida pelo campo
TIPO_UTIL deste registro.
Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO 1300: MOVIMENTAÇÃO DIÁRIA DE COMBUSTÍVEIS
Este registro deve ser apresentado pelos contribuintes do ramo varejista de combustíveis (postos de combustíveis).
Este registro se refere à movimentação diária de combustíveis (Portaria DNC Nº 26, de 13/11/92, instituiu o LIVRO DE
MOVIMENTAÇÃO DE COMBUSTÍVEIS (LMC), pelo Posto Revendedor (PR), dos estoques e das movimentações de
compra e venda de gasolinas, óleo diesel, querosene iluminante, álcool etílico hidratado carburante e mistura óleo
diesel/biodiesel especificada pela ANP), havendo apenas um registro por tipo de combustível e por data do fechamento da
movimentação (campo COD_ITEM e campo DT_FECH), independente de ocorrerem intervenções. Não pode haver mais
de um registro com o mesmo código de combustível e mesma data de fechamento.
Obs.: Não há previsão no livro para controle do GNV.
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
Campo 07 - Preenchimento: informar o volume (em litros) total das saídas, que corresponde à soma dos registros de
volume de vendas.
Campo 08 - Preenchimento: informar o estoque escritural, que corresponde ao valor constante no campo VOL_DISP
menos o valor constante no campo VOL_SAIDAS.
Campo 11 - Preenchimento: informar o estoque do fim do dia.
REGISTRO 1310: MOVIMENTAÇÃO DIÁRIA DE COMBUSTÍVEIS POR TANQUE
Este registro deve ser apresentado para informar a movimentação diária por tanque. Não pode haver mais de um
registro com o mesmo número de tanque.
Obs.: Nos casos em que dois ou mais tanques de combustíveis estiverem interligados ou a saída deles passe por
um único filtro de combustível, de forma que não seja possível identificar qual tanque alimentou um determinado "Bico",
os valores dos tanques deverão ser agrupados (somados), como se fossem um único tanque e informados em um
Página 148 de 188

--- Página 149 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
único registro 1310. Neste caso, o campo NUM_TANQUE deverá, sempre, conter o número de um dos tanques, que deve
ser referenciado no registro 1370.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1310" C 004 - O
02 NUM_TANQUE Tanque que armazena o combustível. C 003 - O
03 ESTQ_ABERT Estoque no inicio do dia, em litros N - 03 O
04 VOL_ENTR Volume Recebido no dia (em litros) N - 03 O
05 VOL_DISP Volume Disponível (03 + 04), em litros N - 03 O
06 VOL_SAIDAS Volume Total das Saídas, em litros N - 03 O
07 ESTQ_ESCR Estoque Escritural(05 – 06), litros N - 03 O
08 VAL_AJ_PERDA Valor da Perda, em litros N - 03 O
09 VAL_AJ_GANHO Valor do ganho, em litros N - 03 O
10 FECH_FISICO Volume aferido no tanque, em litros. Estoque de N - 03 O
fechamento físico do tanque.
Observações:
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [1310]
Campo 03 - Preenchimento: informar o estoque do início do dia para o tanque especificado no campo NUM_TANQUE,
mesmo que tenha ocorrido intervenção posterior na bomba.
Campo 04 - Preenchimento: o valor fornecido deve corresponder ao volume de combustível informado nos documentos
fiscais (registro C171), especificado por tanque, para o dia da movimentação.
Campo 05 - Preenchimento: informar o volume disponível, que corresponde à soma dos campos ESTQ_ABERT e
VOL_ENTR, para o tanque especificado no campo NUM_TANQUE.
Campo 06 - Preenchimento: informar o volume (em litros) total das saídas, que corresponde à soma dos registros de
volume de vendas, para o tanque especificado no campo NUM_TANQUE.
Campo 07 - Preenchimento: informar o estoque escritural, que corresponde ao valor constante no campo VOL_DISP
menos o valor constante no campo VOL_SAIDAS, para o tanque especificado no campo NUM_TANQUE.
Campo 10 - Preenchimento: informar o estoque do fim do dia para o tanque especificado no campo NUM_TANQUE.
REGISTRO 1320: VOLUME DE VENDAS
Este registro deve ser apresentado para discriminar o volume das vendas no dia, considerando-se vendas todas as
saídas promovidas a qualquer título. Não havendo intervenção, em princípio, haverá apenas um registro por bico e os
campos NR_INTERV, MOT_INTERV, NOM_INTERV, CNPJ_INTERV e CPF_INTERV estarão sem informação. Para
cada intervenção ocorrida na bomba associada ao bico, um novo registro deve ser preenchido com dados da intervenção e
os valores totalizados desde a intervenção até uma próxima intervenção ou o fim do dia.
Obs.: No caso em que o contador atingir o seu valor máximo de leitura, deverão ser informados dois registros
1320: o primeiro, informando o valor da leitura inicial até o valor máximo de leitura do contador, e o segundo registro
informando como valor inicial de leitura o valor ZERO e informar o valor da leitura final.
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
Página 149 de 188

--- Página 150 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
11 VOL_VENDAS Vendas (08 – 09 - 10 ) do bico , em litros N - 03 O
Observações:
Nível hierárquico – 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [1320]
Campo 02 - Preenchimento: informar o número do bico associado ao tanque do respectivo registro pai.
Campo 03 - Preenchimento: numeração atribuída à intervenção pelo órgão competente ou, na falta deste, um número
sequencial criado pelo próprio declarante. Se não ocorrer intervenção no bico, este campo não deverá ser preenchido.
Campo 04 - Preenchimento: nome da empresa responsável pela intervenção. Se não ocorrer intervenção no bico, este
campo não deverá ser preenchido.
Campo 05 - Preenchimento: NOM_INTERV: nome do técnico autorizado (mecânico) pelo INMETRO (por meio de suas
unidades estaduais) para atuar em manutenção de bombas medidoras de combustível (a autorização é especifica para essas).
Se não ocorrer intervenção no bico, este campo não deverá ser preenchido.
Campo 06 - Preenchimento: CNPJ_INTERV: CNPJ da empresa responsável pelo contrato de manutenção, para quem o
técnico autorizado trabalha (quando houver). Se não ocorrer intervenção no bico, este campo não deverá ser preenchido.
Campo 07 - Preenchimento: CPF_INT ERV: CPF do técnico autorizado (mecânico), vinculado ao campo
[NOM_INTERV]. Se não ocorrer intervenção no bico, este campo não deverá ser preenchido.
Campo 08 - Preenchimento: fornecer a leitura final do contador (encerrante), no momento do fechamento. O valor é o do
contador.
Campo 09 - Preenchimento: fornecer a leitura inicial do contador (encerrante), no momento da abertura. O valor é o do
contador.
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
Página 150 de 188

--- Página 151 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1360" C 004 - O
02 NUM_LACRE Número do Lacre associado na Bomba C 020 - O
03 DT_APLICACAO Data de aplicação do Lacre N 008* - O
Observações:
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [1360]
Campo 03 - Preenchimento: informar a data de aplicação do lacre no formato “ddmmaaaa”, sem separadores de
formatação.
Validação: o valor informado no campo deve ser uma data válida.
REGISTRO 1370: BICOS DA BOMBA
Este registro deve ser apresentado para discriminar os bicos pertencentes à bomba referenciada no registro pai.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1370" C 004 - O
02 NUM_BICO Número sequencial do bico ligado a bomba N 003 - O
03 COD_ITEM Código do Produto, constante do registro 0200 C 060 - O
04 NUM_TANQUE Tanque que armazena o combustível. C 003 - O
Observações:
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido [1370]
Campo 02 – Preenchimento: caso o tanque não esteja ligado à bicos de bomba, servindo apenas como reservatório
de combustível para as demais bombas, informar código “990” em diante.
Campo 03 - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
REGISTRO 1390: CONTROLE DE PRODUÇÃO DE USINA
Este registro deve ser apresentado pelos fabricantes de açúcar e álcool (Usinas), para controle de produção. Não
pode haver mais de um registro com o mesmo código de produto. Obs.: O registro somente poderá ser informado em
períodos de apuração posteriores a julho de 2012.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1390" C 004 - O
02 COD_PROD Código do produto: N 002* - O
01 – Álcool Etílico Hidratado Carburante
02 - Álcool Etílico Anidro Carburante
03 – Açúcar
Observações:
Nível hierárquico - 2
Ocorrência – 1:N
Campo 01 - Valor Válido: [1390]
Campo 02 - Valores válidos: [01, 02 ou 03]
Preenchimento: indicar o código do produto, cuja produção diária será registrada.
REGISTRO 1391: PRODUÇÃO DIÁRIA DA USINA
Este registro deve ser apresentado para detalhar a produção diária de cada produto especificado no registro 1390.
Não pode haver mais de um registro com a mesma data de produção.
Nº Campo Descrição Tipo Tam Dec Obrig
Página 151 de 188

--- Página 152 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
01 REG Texto fixo contendo "1391" C 004 - O
02 DT_REGISTRO Data de produção (DDMMAAAA) C 008* - O
03 QTD_MOID Quantidade de cana esmagada (toneladas) N - 02 OC
04 ESTQ_INI Estoque inicial (litros / Kg) N - 02 O
05 QTD_PRODUZ Quantidade produzida (litros / Kg) N - 02 OC
06 ENT_ANID_HID Entrada de álcool anidro decorrente da transformação do N - 02 OC
álcool hidratado ou
Entrada de álcool hidratado decorrente da transformação do
álcool anidro (litros)
07 OUTR_ENTR Outras entradas (litros / Kg) N - 02 OC
08 PERDA Evaporação (litros) ou Quebra de peso (Kg) N - 02 OC
09 CONS Consumo (litros) N - 02 OC
10 SAI_ANI_HID Saída para transformação (litros). N - 02 OC
11 SAÍDAS Saídas (litros / Kg) OC
12 ESTQ_FIN Estoque final (litros / Kg) N - 02 O
13 ESTQ_INI_MEL Estoque inicial de mel residual (Kg) N - 02 OC
14 PROD_DIA_MEL Produção de mel residual (Kg) e entradas de mel (Kg) N - 02 OC
15 UTIL_MEL Mel residual utilizado (Kg) e saídas de mel (Kg) N - 02 OC
16 PROD_ALC_MEL Produção de álcool (litros) ou açúcar (Kg) proveniente do N - 02 OC
mel residual.
17 OBS Observações C - - OC
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [1391]
Campo 02 - Preenchimento: informar a data da produção, no formato “ddmmaaaa”, excluindo-se quaisquer caracteres de
separação, tais como: “.”, “/”, “-”.
Validação: o valor informado no campo deve ser menor ou igual ao valor do campo DT_FIN do registro 0000.
Campo 03 - Preenchimento: informar a quantidade total (toneladas) de cana esmagada para fabricação do produto
especificado no registro 1390.
Campo 04 - Preenchimento: informar o estoque inicial do dia. O valor apresentado será em litros, se o COD_PROD do
registro 1390 for igual a 01 ou 02 (Álcool) e em kilogramas, se for igual a 03 (Açúcar).
Campo 05 - Preenchimento: informar a quantidade produzida. O valor apresentado será em litros, se o COD_PROD do
registro 1390 for igual a 01 ou 02 (Álcool) e em kilogramas, se for igual a 03(Açúcar).
Campo 06 - Preenchimento: informar a quantidade (litros) de álcool anidro resultante da transformação do álcool
hidratado (Se COD_PROD do registro 1390 for igual a 02) ou a quantidade (litros) de álcool hidratado resultante da
transformação do álcool anidro (Se COD_PROD do registro 1390 for igual a 01).
Validação: Deverá ser preenchido apenas se o COD_PROD do registro 1390 for igual a 01 ou 02.
Campo 07 - Preenchimento: informar a quantidade de produto recebido de terceiros, devoluções e outras entradas não
especificadas. O valor apresentado será em litros, se o COD_PROD do registro 1390 for igual a 01 ou 02 (Álcool) e em
kilogramas, se for igual a 03 (Açúcar).
Campo 08 - Preenchimento: informar o total das perdas por evaporação (litros) no caso do álcool ou o total da quebra de
peso (Kg) para o açúcar.
Campo 9 - Preenchimento: informar a quantidade total (litros ou Kg) utilizada para consumo próprio, conforme produto
especificado no campo 02 do registro 1390.
Campo 10 - Preenchimento: informar a quantidade (litros) de álcool anidro utilizada para transformação em álcool
hidratado (se campo 02 do registro 1390 for igual a 02) ou a quantidade (litros) de álcool hidratado utilizada para
transformação em álcool anidro (se campo 02 do registro 1390 for igual a 01).
Campo 11 - Preenchimento: informar a quantidade total das saídas (litros ou Kg).
Página 152 de 188

--- Página 153 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Campo 12 - Preenchimento: informar o estoque final do dia (litros ou Kg).
Campo 13 – Preenchimento: informar a quantidade (Kg) do estoque inicial de mel residual.
Validação: Deverá ser preenchido apenas se o campo 02 do registro 1390 for igual a 03 (Açúcar).
Campo 14 – Preenchimento: informar a quantidade (Kg) de todas as entradas de mel residual. Devem ser consideradas a
quantidade produzida e as demais entradas.
Validação: Deverá ser preenchido apenas se o campo 02 do registro 1390 for igual a 03 (Açúcar).
Campo 15 – Preenchimento: informar a quantidade (Kg) de mel residual utilizado na produção e as demais saídas.
Validação: Deverá ser preenchido apenas se o campo 02 do registro 1390 for igual a 03 (Açúcar).
Campo 16 – Preenchimento: informar a quantidade de álcool produzida (litros) ou açúcar (Kg) a partir da utilização de
mel residual.
REGISTRO 1400: INFORMAÇÃO SOBRE VALORES AGREGADOS
Este registro tem como objetivo fornecer informações para o cálculo do valor adicionado por município, sendo
utilizado para subsidiar cálculos de índices de participação e deve ser apresentado apenas se a unidade federada do
declarante assim o exigir.
Deve ser preenchido pelos seguintes contribuintes:
• empresas que adquirirem, diretamente de produtor, produtos agrícolas, pastoris, extrativos minerais, pescados
ou outros produtos extrativos ou agropecuários;
• empresas que emitem documentos fiscais de entrada de produção própria, de produtos agrícolas, pastoris,
extrativos minerais, pescados ou outros produtos extrativos ou agropecuários;
• empresas de transporte intermunicipal e interestadual;
• empresas de telecomunicação e comunicação;
• distribuidoras de energia;
• serviço de utilidade pública de distribuição de água;
• inscrição centralizada;
• demais casos que influenciem no valor agregado.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1400" C 004 - O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
03 MUN Código do Município de origem N 007* - O
04 VALOR Valor mensal correspondente ao município N - 2 O
Observações:
Nível hierárquico - 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1400]
Campo 02 - Validação: o valor informado deve existir no campo COD_ITEM do registro 0200.
Campo 03 – Preenchimento: regras para os contribuintes obrigados, conforme o tipo de empresa:
1. empresas que adquirirem produtos agrícolas, pastoris, extrativos minerais, pescados ou outros
produtos, de pessoa física ou pessoa jurídica não inscrita no cadastro da Fazenda Estadual, oriundos
de municípios do Estado do informante, por meio de nota fiscal de entrada, modelos 1, 1A ou 55 , ou
nota fiscal avulsa a elas destinada. Excetuam-se, destes casos, as notas fiscais de venda futura.
Preenchimento: município de origem dos produtos;
2. empresas que emitem documentos fiscais de entrada de produção própria, de produtos agrícolas,
pastoris, extrativos minerais, pescados ou outros produtos extrativos ou agropecuários.
Preenchimento: município de origem dos produtos;
3. transporte intermunicipal e interestadual - Preenchimento: município onde ocorreu o fato gerador, ou
seja, o município onde ocorreu o início da prestação do serviço;
4. telecomunicação e comunicação – Preenchimento: município onde ocorreu a prestação de serviço;
5. energia – Preenchimento: se distribuidora - município onde ocorreu o fornecimento;
6. serviço de utilidade pública de distribuição de água – Preenchimento: se distribuidora - município
onde ocorreu a distribuição;
Página 153 de 188

--- Página 154 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 04 – Preenchimento: regras para os contribuintes obrigados, conforme o tipo de empresa:
1. transporte intermunicipal e interestadual - Preenchimento: valor contábil, dos serviços prestados, por
municípios onde foram cobrados, deduzidas as aquisições de serviço;
2. telecomunicação e comunicação – Preenchimento: valor contábil, dos serviços prestados, por
municípios onde foram cobrados, deduzidas as aquisições de serviço;
3. energia – Preenchimento: se distribuidora - valor contábil total do fornecimento de energia, deduzido
o valor do suprimento (compra de energia de outras concessionárias e ou custo da geração própria);
4. serviço de utilidade pública de distribuição de água –se for distribuidora, o valor contábil total do
fornecimento, deduzido o valor do suprimento e/ou do custo da geração própria;
5. para as demais empresas, o valor referente às entradas.
Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO 1500: NOTA FISCAL/CONTA DE ENERGIA ELÉTRICA (CÓDIGO 06) –
OPERAÇÕES INTERESTADUAIS.
Este registro deve ser apresentado, nas operações de saída interestaduais, pelos contribuintes do segmento de
energia elétrica, obrigados ao Convênio 115/2003.
Para apresentação do registro 1500 e filhos devem ser observadas as exceções abaixo relacionadas:
Exceção 1: Notas Fiscais Complementares e Notas Fiscais Complementares Extemporâneas (campo COD_SIT igual a
“06” ou “07”): nesta situação, somente os campos REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT,
SER, SUB, NUM_DOC e DT_DOC são obrigatórios. Os demais campos são facultativos (se forem preenchidos, serão
validados e aplicadas as regras de campos existentes). Os registros filhos do registro 1500 deverão ser informados, se
existirem.
Exceção 2: Notas Fiscais emitidas por regime especial ou norma específica (campo COD_SIT igual a “08”). Para
documentos fiscais emitidos com base em regime especial ou norma específica, deverá ser apresentado o registro 1500,
obrigatoriamente, e os registros “filhos”, se estes forem exigidos pela legislação fiscal. Nesta situação, somente os campos
REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT, SER, SUB, NUM_DOC e DT_DOC são
obrigatórios. Os demais campos são facultativos (se forem preenchidos, serão validados e aplicadas as regras de campos
existentes).
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "1500" C 004 - O
02 IND_OPER Indicador do tipo de operação: C 001* - O
1- Saída
03 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O
0- Emissão própria;
04 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - O
- do adquirente, no caso das saídas.
05 COD_MOD Código do modelo do documento fiscal, conforme a Tabela C 002* - O
4.1.1
06 COD_SIT Código da situação do documento fiscal, conforme a Tabela N 002* - O
4.1.2
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
10 NUM_DOC Número do documento fiscal N 009 - O
11 DT_DOC Data da emissão do documento fiscal N 008* - O
12 DT_E_S Data da entrada ou da saída N 008* - O
13 VL_DOC Valor total do documento fiscal N - 02 O
14 VL_DESC Valor total do desconto N - 02 OC
Página 154 de 188

--- Página 155 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
15 VL_FORN Valor total fornecido/consumido N - 02 O
16 VL_SERV_NT Valor total dos serviços não-tributados pelo ICMS N - 02 OC
17 VL_TERC Valor total cobrado em nome de terceiros N - 02 OC
18 VL_DA Valor total de despesas acessórias indicadas no documento N - 02 OC
fiscal
19 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 OC
20 VL_ICMS Valor acumulado do ICMS N - 02 OC
21 VL_BC_ICMS_ST Valor acumulado da base de cálculo do ICMS substituição N - 02 OC
tributária
22 VL_ICMS_ST Valor acumulado do ICMS retido por substituição tributária N - 02 OC
23 COD_INF Código da informação complementar do documento fiscal C 006 - OC
(campo 02 do Registro 0450)
24 VL_PIS Valor do PIS N - 02 OC
25 VL_COFINS Valor da COFINS N - 02 OC
26 TP_LIGACAO Código de tipo de Ligação N 001* - OC
1 - Monofásico
2 - Bifásico
3 - Trifásico
27 COD_GRUPO_TE Código de grupo de tensão: C 002* - OC
NSAO 01 - A1 - Alta Tensão (230kV ou mais)
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
Campo 05 - Valor válido: [06] – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 06 - Valores válidos: [00, 01, 06, 07, 08]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3.
Campo 09 - Valores válidos: [“01”, “02”, “03’, “04”, “05”, “06”, “07”, “08”]
Campo 10 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 11 - Preenchimento: data de emissão da nota fiscal no formato “ddmmaaaa”.
Validação: o valor informado no campo deve ser menor ou igual ao valor do campo DT_FIN do registro 0000.
Campo 12 - Preenchimento: data de entrada ou saída da nota fiscal no formato “ddmmaaaa”.
Campo 13 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Página 155 de 188

--- Página 156 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Campo 15 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 23 - Validação: o valor informado no campo deve existir no registro 0450.
Campo 24 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo.
Campo 25 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo.
Campo 26 - Valores válidos: [1, 2, 3]
Campo 27 - Valores válidos: [01, 02, 03, 04, 05, 06, 07, 08, 09, 10, 11, 12, 13, 14]
REGISTRO 1510: ITENS DO DOCUMENTO NOTA FISCAL/CONTA ENERGIA ELÉTRICA
(CÓDIGO 06)
Este registro deve ser apresentado para informar os itens das Notas Fiscais/Contas de Energia Elétrica (código 06
da Tabela Documentos Fiscais do ICMS) apresentadas nos registros 1500.
Nº Campo Descrição Tipo Tam De Obrig.
c
01 REG Texto fixo contendo "1510" C 004 - O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 COD_CLASS Código de classificação do item de energia elétrica, N 004* - O
conforme a Tabela 4.4.1
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
18 COD_PART Código do participante receptor da receita, terceiro da C 060 OC
operação (campo 02 do Registro 0150)
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
Página 156 de 188

--- Página 157 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Campo 06 - Validação: o valor deve estar informado no registro 0190.
Campo 09 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS,
referenciada no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 10 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01.
O primeiro caractere do CFOP deve ser igual a 6.
O primeiro caractere do CFOP deve ser o mesmo para todos os itens do documento.
Não podem ser utilizados códigos que correspondam aos títulos dos agrupamentos de CFOP.
Campo 17 - Valores válidos: [0, 1]
Campo 18 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 19 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 20 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO 1600: TOTAL DAS OPERAÇÕES COM CARTÃO DE CRÉDITO E/OU DÉBITO
Este registro destina-se a identificar o valor total das operações de vendas realizadas pelo declarante por meio de
cartão de débito ou de crédito, discriminado por administradora. Deve ser informado o valor total destas vendas , excluídos
os estornos, cancelamentos e outros recebimentos não vinculados à sua atividade operacional. A obrigatoriedade deste
registro deve ser verificada junto a cada uma das unidades federativas.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1600" C 004 - O
02 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - O
identificação da administradora do cartão de débito/crédito
03 TOT_CREDITO Valor total das operações realizadas no período referente a N - 002 O
Cartão de Crédito
04 TOT_DEBITO Valor total das operações realizadas no período referente a N - 002 O
Cartão de Débito
Observações:
Nível hierárquico – 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1600]
Campo 02 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
REGISTRO 1700: DOCUMENTOS FISCAIS UTILIZADOS
Neste registro devem ser informados os dispositivos autorizados e utilizados na emissão de documentos fiscais no
período da EFD-ICMS/IPI. A obrigatoriedade deste registro deve ser verificada junto a cada uma das unidades federativas.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo “1700”. C 004 - O
02 COD_DISP Código dispositivo autorizado: C 002* - O
00 - Formulário de Segurança – impressor autônomo
01 - FS-DA – Formulário de Segurança para Impressão de
DANFE
02 – Formulário de segurança - NF-e
03 - Formulário Contínuo
04 – Blocos
05 - Jogos Soltos
03 COD_MOD Código do modelo do dispositivo autorizado, conforme a C 002* - O
Tabela 4.1.1
Página 157 de 188

--- Página 158 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
04 SER Série do dispositivo autorizado C 004 - OC
05 SUB Subsérie do dispositivo autorizado C 003 - OC
06 NUM_DOC_INI Número do dispositivo autorizado (utilizado) inicial N 012 - O
07 NUM_DOC_FIN Número do dispositivo autorizado (utilizado) final N 012 - O
08 NUM_AUT Número da autorização, conforme dispositivo autorizado N 060 - O
Observações:
Nível hierárquico - 2
Ocorrência – V
Campo 01 - Valor Válido: [1700]
Campo 02 - Valores Válidos: [“00”,“01”,“02”,“03”,“04”,“05”]
00 – Formulário de Segurança – Formulário utilizado pelo impressor autônomo nos termos dos Convênios ICMS nº
58/95 e 131/95 (vigentes até 30/06/2009) e Convênio ICMS nº 96/09 (com efeitos a partir de 01/07/2010);
01 - FS-DA – Formulário de Segurança para Impressão de Documento Auxiliar de Documentos Fiscais eletrônicos (NF-e,
CT-e)– Formulário utilizado para contingência de Documentos Fiscais eletrônicos, conforme Convênio ICMS nº 110/08
(vigente até 30/06/2009) e Convênio ICMS nº 96/0909 (com efeitos a partir de 01/07/2010).
02 – Formulário de Segurança - NF-e - Formulário autorizado nos termos dos Convênios ICMS 58/95 e 131/95 (vigentes
até 30/06/2009) e utilizados para emissão de NF-e em contingência, conforme Convênio ICMS 110/08 (vigente até
30/06/2009) e Convênio ICMS 96/0909 (com efeitos a partir de 01/07/2010) e Ajuste SINIEF nº 07/2005 e suas alterações.
Campo 03 - Preenchimento: o valor informado deve constar na tabela 4.1.1 do Ato COTEPE/ICMS nº 09, de 18 de abril
de 2008. – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 06 - Preenchimento: Número inicial do intervalo do documento, informado no campo 02, utilizado no período da
EFD-ICMS/IPI.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos
respectivos documentos utilizados.
Campo 07 - Preenchimento: Número final do intervalo do documento, informado no campo 02, utilizado no período da
EFD-ICMS/IPI.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos
respectivos documentos utilizados.
Campo 08 - Preenchimento: Número da autorização, emitida pela Secretaria estadual, para utilização dos documentos
informados no campo 2, do respectivo intervalo informado.
REGISTRO 1710: DOCUMENTOS FISCAIS CANCELADOS/INUTILIZADOS
Neste registro devem ser informados os documentos cancelados/inutilizados no intervalo constante do registro
1700.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo “1710”. C 004 - O
02 NUM_DOC_INI Número do dispositivo autorizado (inutilizado) inicial N 012 - O
03 NUM_DOC_FIN Número do dispositivo autorizado (inutilizado) final N 012 - O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [1710]
Campo 02 - Preenchimento: Número inicial do documento cancelado ou intervalo, informado no campo 02.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos
respectivos documentos utilizados.
Observação: Quando o cancelamento não for contínuo, o número inicial deverá ser igual ao número final.
Exemplo : Reg 1700 Campo 06 35; Campo 07 55
Canceladas: 45; 50 a 52.
Então, teremos: Reg 1710 Campo 02 45; Campo 03 45
Reg 1710 Campo 02 50; Campo 03 52
Página 158 de 188

--- Página 159 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Campo 03 - Preenchimento: Número final do documento ou intervalo, informado no campo 02.
Nos casos de documentos eletrônicos deverão ser informados a seriação, se existir, e os números pré-impressos nos
respectivos documentos utilizados.
REGISTRO 1800: DCTA – DEMONSTRATIVO DE CRÉDITO DO ICMS SOBRE
TRANSPORTE AÉREO
Este registro deve ser informado, pelas empresas de transporte aéreo, para explicitar os estornos de créditos de
ICMS.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo “1800”. C 004* - O
02 VL_CARGA Valor das prestações cargas (Tributado) N - 02 O
03 VL_PASS Valor das prestações passageiros/cargas (Não Tributado) N - 02 O
04 VL_FAT Valor total do faturamento (2+3) N - 02 O
05 IND_RAT Índice para rateio(2 / 4) N 008 06 O
06 VL_ICMS_ANT Valor total dos créditos do ICMS N - 02 O
07 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 O
08 VL_ICMS_APUR Valor do ICMS apurado no cálculo (5 x 6) N - 02 O
09 VL_BC_ICMS_APUR Valor da base de cálculo do ICMS apurada (5 x 7) N - 02 O
10 Valor da diferença a ser levada a estorno de crédito na 02 O
VL_DIF N -
apuração (6 - 8)
Observações:
Nível hierárquico - 2
Ocorrência – 1:1
Campo 01 - Valor Válido: [1800]
REGISTRO 1900: INDICADOR DE SUB-APURAÇÃO DO ICMS
Este registro tem por objetivo escriturar o ICMS de operações especificadas em legislação estadual como
obrigadas a apurações em separado. Este registro deverá ser apresentado pelos contribuintes dos estados do Pará e do
Espírito Santo, sujeitos a outras apurações.
Registro obrigatório se houver registro C197 ou D197 onde o 4º (quarto) dígito do campo 02 - COD_AJ, for “3”,
“4” ou “5”, ou na existência de saldo credor no campo 08- VL_SLD_CREDOR_ANT_OA do registro 1920, em valor
maior que Zero.
Não podem ser informados dois ou mais registros com o mesmo código de indicador de apuração (campo 2 -
IND_APUR_ICMS).
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "1900" C 004 - O
02 IND_APUR_ICMS Indicador de outra apuração do ICMS: C 001* - O
3 – APURAÇÃO 1;
4 – APURAÇÃO 2;
5 – APURAÇÃO 3.
03 DESCR_COMPL_OUT_APUR Descrição complementar de Outra Apuração C - - O
do ICMS
Observações:
Nível hierárquico - 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [1900]
Campo 02 - Valores Válidos: [“3”,“4”,“5”]
 Código “3” –Apuração em separado 1 (tem que haver pelo menos um registro C197 ou D197 onde o 4º
(quarto) dígito do COD_AJ, campo 02, seja 3, ou valor maior que “zero” no campo 08-
VL_SLD_CREDOR_ANT_OA do registro 1920).
 Código “4” – Apuração em separado 2 (tem que haver pelo menos um registro C197 ou D197 onde o 4º
(quarto) dígito do COD_AJ, campo 02, seja 4, ou valor maior que “zero” no campo 08-
VL_SLD_CREDOR_ANT_OA do registro 1920).
Página 159 de 188

--- Página 160 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
 Código “5” – Apuração em separado 3 (tem que haver pelo menos um registro C197 ou D197 onde o 4º
(quarto) dígito do COD_AJ, campo 02, seja 5, ou valor maior que “zero” no campo 08-
VL_SLD_CREDOR_ANT_OA do registro 1920).
Campo 03 - Preenchimento: Descrever a norma legal que exige esta apuração em separado.
REGISTRO 1910: PERÍODO DA SUB-APURAÇÃO DO ICMS
Este registro tem por objetivo informar o(s) período(s) das apurações em separado do ICMS. Os períodos
informados devem abranger todo o intervalo da escrituração fiscal, sem sobreposição ou omissão de datas ou períodos.
Não podem ser informados dois ou mais registros com a mesma combinação de valores dos campos 02 (DT_INI) e
03 (DT_FIN). Não devem existir lacunas ou sobreposições de datas nos períodos de apuração informados nestes registros,
em comparação com as datas informadas no registro 0000.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1910" C 004 - O
02 DT_INI Data inicial da sub-apuração N 008* - O
03 DT_FIN Data final da sub-apuração N 008* - O
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor válido: [1910]
Campo 02 - Preenchimento: informar a data inicial a que se refere a apuração em separado (sub-apuração), no formato
“ddmmaaaa”, sem os separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000 e maior ou
igual ao valor no campo DT_INI do registro 0000. A data informada no campo deve ser menor ou igual à data informada
no campo DT_FIN do registro E100.
Campo 03 - Preenchimento: informar a data final a que se refere a apuração em separado (sub-apuração) no formato
“ddmmaaaa”, sem os separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000 e maior ou
igual ao valor no campo DT_INI do registro 0000.
REGISTRO 1920: SUB-APURAÇÃO DO ICMS
Este registro tem por objetivo informar os valores relativos a apurações especificadas no registro 1900, que se
referem aos valores do ICMS das operações próprias estornados do registro E110 por meio de ajustes decorrentes de
documentos, nos campos 03 (VL_AJ_DEBITOS) e 07 (VL_AJ_CREDITOS), e por meio de ajustes de apuração nos
campos 05 (VL_ESTORNOS_CRED) e 09 (VL_ESTORNOS_DEB).
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1920" C 004 - O
02 VL_TOT_TRANSF_DEBITOS_OA Valor total dos débitos por "Saídas e N - 02 O
prestações com débito do imposto"
03 VL_TOT_AJ_DEBITOS_OA Valor total de "Ajustes a débito" N - 02 O
04 VL_ESTORNOS_CRED_OA Valor total de Ajustes “Estornos de N - 02 O
créditos”
05 VL_TOT_TRANSF_CREDITOS_OA Valor total dos créditos por "Entradas e N - 02 O
aquisições com crédito do imposto"
06 VL_TOT_AJ_CREDITOS_OA Valor total de "Ajustes a crédito" N - 02 O
07 VL_ESTORNOS_DEB_OA Valor total de Ajustes “Estornos de N - 02 O
Débitos”
08 VL_SLD_CREDOR_ANT_OA Valor total de "Saldo credor do período N - 02 O
anterior"
09 VL_SLD_APURADO_OA Valor do saldo devedor apurado N - 02 O
10 VL_TOT_DED Valor total de "Deduções" N - 02 O
11 VL_ICMS_RECOLHER_OA Valor total de "ICMS a recolher (09-10) N - 02 O
12 VL_SLD_CREDOR_TRANSP_OA Valor total de "Saldo credor a transportar N - 02 O
Página 160 de 188

--- Página 161 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
para o período seguinte”
13 DEB_ESP_OA Valores recolhidos ou a recolher, extra- N - 02 O
apuração.
Observações:
Nível hierárquico - 4
Ocorrência - um (por período)
Campo 01 - Valor Válido: [1920]
Campo 02 - Validação: Se o campo 02- IND_APUR_ICMS do registro 1900 for igual a:
a) “3” - o valor informado deve corresponder ao somatório dos valores do campo 07- VL_ICMS dos registros C197 e
D197 onde o terceiro e quarto caracteres do código de ajuste forem iguais a “2” e “3”;
b) “4” - o valor informado deve corresponder ao somatório dos valores do campo 07- VL_ICMS dos registros C197 e
D197 onde o terceiro e quarto caracteres do código de ajuste forem iguais a “2” e “4”;
c) “5” - o valor informado deve corresponder ao somatório dos valores do campo 07- VL_ICMS dos registros C197 e
D197 onde o terceiro e quarto caracteres do código de ajuste forem iguais a “2” e “5”.
Os citados registros C197 e D197 devem ser originados em documentos fiscais de saídas que geraram débitos de ICMS
de operações próprias.
Ficam excluídos os documentos extemporâneos (COD_SIT com valor igual ‘01’) e os documentos complementares
extemporâneos (COD_SIT com valor igual ‘07’).
Serão considerados os registros cujos documentos estejam compreendidos no período informado no registro 1910
utilizando, para tanto, o campo DT_E_S (C100) e DT_DOC ou DT_A_P (D100). Quando o campo DT_E_S ou DT_A_P
do registro C100 não for informado, utilizar o campo DT_DOC.
Campo 03 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ_APUR dos registros 1921,
se o terceiro caractere for igual a ‘0’ e o quarto caractere do campo COD_AJ_APUR do registro 1921 for igual a ‘0’.
Campo 04 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ_APUR dos registros 1921,
se o terceiro caractere for igual a ‘0’ e o quarto caractere do campo COD_AJ_APUR do registro 1921 for igual a ‘1’.
Campo 05 - Validação: Se o campo 02- IND_APUR_ICMS do registro 1900 for igual a:
a) “3” - o valor informado deve corresponder ao somatório dos valores do campo 07- VL_ICMS dos registros C197 e
D197 onde o terceiro e quarto caracteres do código de ajuste forem iguais a “5” e “3”;
b) “4” - o valor informado deve corresponder ao somatório dos valores do campo 07- VL_ICMS dos registros C197 e
D197 onde o terceiro e quarto caracteres do código de ajuste forem iguais a “5” e “4”;
c) “5” - o valor informado deve corresponder ao somatório dos valores do campo 07- VL_ICMS dos registros C197 e
D197 onde o terceiro e quarto caracteres do código de ajuste forem iguais a “5” e “5”.
Os citados registros C197 e D197 devem ser originados em documentos fiscais de entradas que geraram créditos de
ICMS de operações próprias.
Ficam excluídos os documentos extemporâneos (COD_SIT com valor igual ‘01’) e os documentos complementares
extemporâneos (COD_SIT com valor igual ‘07’).
Serão considerados os registros cujos documentos estejam compreendidos no período informado no registro 1910,
utilizando para tanto o campo DT_E_S (C100) e DT_DOC ou DT_A_P (D100). Quando o campo DT_E_S ou DT_A_P do
registro C100 não for informado, utilizar o campo DT_DOC.
Campo 06 - Validação: o valor informado deve corresponder ao somatório dos valores constantes dos registros 1921,
quando o terceiro caractere for igual a ‘0’ e o quarto caractere for igual a ‘2’, do COD_AJ_APUR do registro 1921.
Campo 07 - Validação: o valor informado deve corresponder ao somatório do VL_AJ_APUR dos registros 1921, quando
o terceiro caractere for igual a ‘0’ e o quarto caractere for igual a ‘3’, do COD_AJ_APUR do registro 1921.
Campo 08 - Preenchimento: Informar o saldo credor do período anterior da respectiva apuração em separado (sub-
apuração).
Campo 09 - Validação: o valor informado deve ser preenchido com base na expressão: soma do total de débitos
transferidos (VL_TOT_TRANSF_DEBITOS_OA) com total de ajustes a débito (VL_TOT_AJ_DEBITOS_OA) com total
de estorno de crédito (VL_ESTORNOS_CRED_OA) menos a soma do total de créditos transferidos
(VL_TOT_TRANSF_CREDITOS_OA) com total de ajustes a crédito (VL_AJ_CREDITOS_OA) com total de estorno de
débito (VL_ESTORNOS_DEB_OA) com saldo credor do período anterior (VL_SLD_CREDOR_ANT_OA). Se o valor da
expressão for maior ou igual a “0” (zero), então este valor deve ser informado neste campo e o campo 12
(VL_SLD_CREDOR_TRANSP_OA) deve ser igual a “0” (zero). Se o valor da expressão for menor que “0” (zero), então
Página 161 de 188

--- Página 162 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
este campo deve ser preenchido com “0” (zero) e o valor absoluto da expressão deve ser informado no campo
VL_SLD_CREDOR_TRANSP_OA.
Campo 10 - Validação: o valor informado deve corresponder ao somatório do campo VL_ICMS dos registros C197 e
D197, se o terceiro caractere do código de ajuste dos registros C197 e D197, for “6”’ e o quarto caractere for “3”, “4” ou
“5”, somado ao valor total informado nos registros 1921, quando o terceiro caractere for igual a ‘0’ e o quarto caractere
for igual a ‘4’, do campo COD_AJ_APUR do registro 1921.
Para o somatório do campo VL_ICMS dos registros C197 e D197 devem ser considerados os documentos fiscais
compreendidos no período informado no registro 1910, comparando com a data constante no campo DT_E_S do registro
C100 e DT_DOC ou DT_A_P do registro D100, exceto se COD_SIT do registro C100 for igual a ‘01’ (extemporâneo) ou
igual a ‘07’ (Complementar extemporânea), cujo valor deve ser somado no primeiro período de apuração informado no
registro 1910, quando houver mais de um período de apuração. Quando o campo DT_E_S não for informado, utilizar o
campo DT_DOC.
Campo 11 – Validação: o valor informado deve corresponder à diferença entre o campo VL_SLD_APURADO_OA e o
campo VL_TOT_DED. O valor da soma deste campo com o campo DEB_ESP_OA deve ser igual à soma dos valores do
campo VL_OR do registro 1926.
Campo 12 – Validação: se o valor da expressão: “soma do total de débitos (VL_TOT_TRANSF_DEBITOS_OA) mais
total de ajustes a débito (VL_AJ_DEBITOS_OA) mais total de estorno de crédito (VL_ESTORNOS_CRED_OA)” menos
“a soma do total de créditos transferidos (VL_TOT_TRANSF_CREDITOS_OA) mais total de ajuste a crédito
(VL_AJ_CREDITOS_OA) mais total de estorno de débito (VL_ESTORNOS_DEB_OA) mais saldo credor do período
anterior (VL_SLD_CREDOR_ANT_OA)”, for maior que ZERO, este campo deve ser preenchido com “0” (zero) e o
campo 11 (VL_SLD_APURADO) deve ser igual ao valor do resultado. Se for menor que “0” (zero), o valor absoluto do
resultado deve ser informado neste campo e o campo VL_SLD_APURADO deve ser informado com “0” (zero).
Campo 13 – Preenchimento: Informar o correspondente ao somatório dos valores:
a) de ICMS correspondentes aos documentos fiscais extemporâneos (COD_SIT igual a “01”) e dos documentos
fiscais complementares extemporâneos (COD_SIT igual a “07”), referentes às apurações em separado;
b) de ajustes do campo VL_ICMS dos registros C197 e D197, se o terceiro caractere do código informado no campo
COD_AJ dos registros C197 e D197 for igual a “7” (débitos especiais) e o quarto caractere for igual a “3”, “4” ou
“5” (“Apuração 1 – Bloco 1900” ou “Apuração 2 – Bloco 1900” ou “Apuração 3 – Bloco 1900”) referente aos
documentos compreendidos no período a que se refere a escrituração; e
c) de ajustes do campo VL_AJ_APUR do registro 1921, se o terceiro caractere do código informado no campo
COD_AJ_APUR do registro 1921 for igual a “0” (apuração ICMS próprio) e o quarto caractere for igual a
“5”(débito especial).
Validação: O valor da soma deste campo com o campo VL_ICMS_RECOLHER_OA deve ser igual à soma dos valores
do campo VL_OR do registro 1926.
REGISTRO 1921: AJUSTE/BENEFÍCIO/INCENTIVO DA SUB-APURAÇÃO DO ICMS
Este registro tem por objetivo discriminar todos os ajustes lançados nos campos VL_TOT_AJ_DEBITOS_OA,
VL_ESTORNOS_CRED_OA, VL_TOT_AJ_CREDITOS_OA, VL_ESTORNOS_DEB_OA, VL_TOT_DED e
DEB_ESP_OA, todos do registro 1920.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1921" C 004 - O
02 COD_AJ_APUR Código do ajuste da SUB-APURAÇÃO e dedução, C 008* - O
conforme a Tabela indicada no item 5.1.1.
03 DESCR_COMPL_AJ Descrição complementar do ajuste da apuração. C - - OC
04 VL_AJ_APUR Valor do ajuste da apuração N - 02 O
Observações:
Nível hierárquico - 5
Ocorrência - 1:N
Campo 01 - Valor Válido: [1921]
Campo 02 - Preenchimento: o valor informado no campo deve existir na tabela de código do ajuste da apuração e
dedução de cada Secretaria de Fazenda, conforme a UF do declarante, campo UF do registro 0000 ou, não havendo esta
tabela, o valor informado no campo deve existir na tabela de código do ajuste da apuração e dedução, constante da
observação do Item 5.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Página 162 de 188

--- Página 163 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
O código do ajuste utilizado deve ter seu terceiro caractere como “0” (zero), indicando ajuste de ICMS, não incluindo
ajustes de ICMS-ST.
O quarto caractere deve ser preenchido, conforme item 5.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, com
um dos códigos abaixo:
0 – Outros débitos;
1 – Estorno de créditos;
2 – Outros créditos;
3 – Estorno de débitos;
4 – Deduções do imposto apurado;
5 – Débitos Especiais.
REGISTRO 1922: INFORMAÇÕES ADICIONAIS DOS AJUSTES DA SUB-APURAÇÃO
DO ICMS
Este registro tem por objetivo detalhar os ajustes do registro 1921 quando forem relacionados a processos judiciais
ou fiscais ou a documentos de arrecadação, observada a legislação estadual pertinente. Valores recolhidos, com influência
nesta apuração em separado (sub-apuração) do ICMS, devem ser detalhados neste registro, com identificação do
documento de arrecadação específico.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1922" C 004 - O
02 NUM_DA Número do documento de arrecadação estadual, se houver C - - OC
03 NUM_PROC Número do processo ao qual o ajuste está vinculado, se houver C 015 - OC
04 IND_PROC Indicador da origem do processo: C 001* - OC
0- SEFAZ;
1- Justiça Federal;
2- Justiça Estadual;
9- Outros
05 PROC Descrição resumida do processo que embasou o lançamento C - - OC
06 TXT_COMPL Descrição complementar C - - OC
Observações:
Nível hierárquico - 6
Ocorrência - 1:N
Campo 01 - Valor Válido: [1922]
Campo 02 - Preenchimento: este campo deve ser preenchido se o ajuste for referente a um documento de arrecadação, tais
como pagamentos indevidos, pagamentos antecipados e outros.
Campo 03 - Preenchimento: o valor deve ter até 15 caracteres.
Campo 04 - Valores válidos: [0, 1, 2, 9]
Campo 06 - Preenchimento: Outras informações complementares.
REGISTRO 1923: INFORMAÇÕES ADICIONAIS DOS AJUSTES DA SUB-APURAÇÃO
DO ICMS – IDENTIFICAÇÃO DOS DOCUMENTOS FISCAIS
Este registro tem por objetivo identificar os documentos fiscais relacionados ao ajuste.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1923" C 004 - O
02 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - O
- do emitente do documento ou do remetente das mercadorias,
no caso de entradas;
- do adquirente, no caso de saídas
03 COD_MOD Código do modelo do documento fiscal, conforme a Tabela C 002* - O
4.1.1
04 SER Série do documento fiscal C 004 - OC
Página 163 de 188

--- Página 164 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
05 SUB Subserie do documento fiscal N 003 - OC
06 NUM_DOC Número do documento fiscal N 009 - O
07 DT_DOC Data da emissão do documento fiscal N 008* - O
08 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - OC
09 VL_AJ_ITEM Valor do ajuste para a operação/item N - 02 O
Observações:
Nível hierárquico - 6
Ocorrência - 1:N
Campo 01 - Valor Válido: [1923]
Campo 02 - Preenchimento: no caso de entrada, deve constar a informação referente ao emitente do documento ou ao
remetente das mercadorias ou serviços. No caso de saída, deve constar a informação referente ao destinatário. O valor deve
ter até 60 caracteres.
Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 03 - Validação: o valor informado no campo deve existir na tabela de Documentos Fiscais do ICMS, conforme
Item 4.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008. – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 06 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 07 - Preenchimento: informar a data de emissão do documento fiscal, no formato “ddmmaaaa”, sem os
separadores de formatação.
Campo 08 – Preenchimento: este campo só deve ser informado quando o ajuste se referir a um determinado item/produto
do documento.
Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
REGISTRO 1925: INFORMAÇÕES ADICIONAIS DA SUB-APURAÇÃO – VALORES
DECLARATÓRIOS
Este registro tem o objetivo de informar os valores declaratórios relativos ao ICMS desta apuração em separado
(sub-apuração), conforme definição da legislação estadual pertinente. Esses valores são meramente declaratórios e não são
computados nesta apuração em separado (sub-apuração) do ICMS.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1925" C 004 - O
02 COD_INF_ADIC Código da informação adicional conforme tabela a ser C 008* - O
definida pelas SEFAZ, conforme tabela definida no item 5.2.
03 VL_INF_ADIC Valor referente à informação adicional N - 02 O
04 DESCR_COMPL_AJ Descrição complementar do ajuste C - - OC
Observações:
Nível hierárquico - 5
Ocorrência – 1:N
Campo 01 - Valor Válido: [1925]
Campo 02 - Preenchimento: o código da informação adicional deve obedecer à tabela definida pelas Secretarias de
Fazenda dos Estados. Caso não haja publicação da referida tabela, o registro não deve ser apresentado.
REGISTRO 1926: OBRIGAÇÕES DO ICMS A RECOLHER – OPERAÇÕES REFERENTES
À SUB-APURAÇÃO
Este registro tem o objetivo de discriminar os pagamentos realizados (débitos especiais) ou a realizar, referentes à
apuração em separado (sub-apuração) do ICMS identificada no registro 1900. A soma do valor das obrigações deste
registro deve ser igual à soma dos campos VL_ICMS_RECOLHER_OA e DEB_ESP_OA, do registro 1920.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1926" C 004 - O
02 COD_OR Código da obrigação a recolher, conforme a Tabela 5.4 C 003* - O
Página 164 de 188

--- Página 165 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
03 VL_OR Valor da obrigação a recolher N - 02 O
04 DT_VCTO Data de vencimento da obrigação N 008* - O
05 COD_REC Código de receita referente à obrigação, próprio da unidade da C - - O
federação, conforme legislação estadual,
06 NUM_PROC Número do processo ou auto de infração ao qual a obrigação C 015 - OC
está vinculada, se houver.
07 IND_PROC Indicador da origem do processo: C 001* - OC
0- SEFAZ;
1- Justiça Federal;
2- Justiça Estadual;
9- Outros
08 PROC Descrição resumida do processo que embasou o lançamento C - - OC
09 TXT_COMPL Descrição complementar das obrigações a recolher. C - - OC
10 MES_REF* Informe o mês de referência no formato “mmaaaa” N 006* - O
Observações: * O campo 10 – MES_REF somente deverá ser incluído no leiaute a partir de períodos de apuração de janeiro
de 2011.
Nível hierárquico – 5
Ocorrência - 1:N
Campo 01 - Valor Válido: [1926]
Campo 02 - Valores válidos: [000, 003, 004, 005, 006, 090]
Campo 03 – Preenchimento: o valor da soma deste campo deve corresponder à soma dos campos
VL_ICMS_RECOLHER_OA e DEB_ESP_OA do registro 1920. Não informar acréscimos legais, se houver.
Campo 04 - Preenchimento: informar a data de vencimento da obrigação, no formato “ddmmaaaa”, sem os separadores
de formatação.
Validação: o valor informado no campo deve ser uma data válida.
Campo 06 - Preenchimento: o valor deve ter até 15 caracteres.
Validação: se este campo estiver preenchido, os campos IND_PROC e PROC também devem estar preenchidos.
Campo 07 - Valores válidos: [0, 1, 2, 9]
Campo 09 - preenchimento: quando este registro se referir a recolhimento extemporâneo, informar neste campo o mês e
ano de referência de cada um dos débitos extemporâneos do período, no formato mmaaaa, sem utilizar os caracteres
especiais de separação. Exemplo: para débito extemporâneo do mês de abril de 2009 o campo deve ser preenchido,
simplesmente, com os caracteres 042009.
REGISTRO 1990: ENCERRAMENTO DO BLOCO 1
Este registro destina-se a identificar o encerramento do bloco 1 e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1990" C 004 - O
02 QTD_LIN_1 Quantidade total de linhas do Bloco 1 N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [1990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco 1 é igual ao valor informado no campo QTD_LIN_1.
Página 165 de 188

