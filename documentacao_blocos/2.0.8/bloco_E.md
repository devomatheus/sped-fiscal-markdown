# Bloco E - Versão 2.0.8

**Data de Criação:** 2012-03-01  
**Páginas:** 115-130  
**Versão:** 2.0.8

---

--- Página 115 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
REGISTRO D990: ENCERRAMENTO DO BLOCO D.
Este registro tem por objetivo identificar o encerramento do bloco D e informar a quantidade de linhas (registros)
existentes no bloco.
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
Página 115 de 174

--- Página 116 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
Campo 02 - Preenchimento: informar a data inicial a que se refere a apuração, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000 e maior ou
igual ao valor no campo DT_INI do registro 0000. A data informada no campo deve ser menor ou igual à data informada
no campo DT_FIN do registro E100. .
Campo 03 - Preenchimento: informar a data final a que se refere a apuração no formato “ddmmaaaa”, sem os separadores
de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000 e maior ou
igual ao valor no campo DT_INI do registro 0000.
REGISTRO E110: APURAÇÃO DO ICMS – OPERAÇÕES PRÓPRIAS.
Este registro tem por objetivo informar os valores relativos à apuração do ICMS referentes às operações próprias.
O registro deve ser apresentado inclusive nos casos de períodos sem movimento. Neste caso, os valores deverão ser
apresentados zerados.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E110" C 004 - O
02 VL_TOT_DEBITOS Valor total dos débitos por "Saídas e prestações N - 02 O
com débito do imposto"
03 VL_AJ_DEBITOS Valor total dos ajustes a débito decorrentes do N - 02 O
documento fiscal.
04 VL_TOT_AJ_DEBITOS Valor total de "Ajustes a débito" N - 02 O
05 VL_ESTORNOS_CRED Valor total de Ajustes “Estornos de créditos” N - 02 O
06 VL_TOT_CREDITOS Valor total dos créditos por "Entradas e N - 02 O
aquisições com crédito do imposto"
07 VL_AJ_CREDITOS Valor total dos ajustes a crédito decorrentes do N - 02 O
documento fiscal.
08 VL_TOT_AJ_CREDITOS Valor total de "Ajustes a crédito" N - 02 O
09 VL_ESTORNOS_DEB Valor total de Ajustes “Estornos de Débitos” N - 02 O
10 VL_SLD_CREDOR_ANT Valor total de "Saldo credor do período N - 02 O
anterior"
11 VL_SLD_APURADO Valor do saldo devedor apurado N - 02 O
12 VL_TOT_DED Valor total de "Deduções" N - 02 O
13 VL_ICMS_RECOLHER Valor total de "ICMS a recolher (11-12) N - 02 O
14 VL_SLD_CREDOR_TRANSPORTAR Valor total de "Saldo credor a transportar para o N - 02 O
período seguinte”
15 DEB_ESP Valores recolhidos ou a recolher, extra- N - 02 O
apuração.
Observações:
Nível hierárquico – 3 – registro obrigatório
Ocorrência – um por período
Campo 01 - Valor Válido: [E110]
Campo 02 - Validação: o valor informado deve corresponder ao somatório de todos os documentos fiscais de saída que
geram débito de ICMS. Deste somatório, estão excluídos os documentos extemporâneos (COD_SIT com valor igual ‘01’),
os documentos complementares extemporâneos (COD_SIT com valor igual ‘07’) e os documentos fiscais com CFOP 5605.
Devem ser incluídos os documentos fiscais com CFOP igual a 1605.
O valor neste campo deve ser igual à soma dos VL_ICMS de todos os registros C190, C320, C390, C490, C590, C690,
C790, D190, D300, D390, D410, D590, D690, D696, com as datas dos campos DT_DOC (C300, C405, C600, D300,
D355, D400, D600) ou DT_E_S (C100, C500) ou DT_DOC_FIN (C700, D695) ou DT_A_P (D100, D500) dentro do
período informado no registro E100.
Quando o campo DT_E_S ou DT_A_P não for informado, utilizar o campo DT_DOC.
Para os estados que utilizam como data da escrituração a data de emissão, todos os documentos devem ser declarados na
competência da emissão. Neste caso, se a data de saída (DT_E_S ou DT_A_P) for posterior à data final informada no
campo 03 do registro E100, o campo referente à data de saída não deve ser preenchido.
Página 116 de 174

--- Página 117 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
Para os estados que utilizam como data da escrituração a data de efetiva saída, todos os documentos devem ser declarados
na competência específica da data de saída como documento regular (COD_SIT igual a ‘00’), obedecendo à legislação
estadual pertinente.
Campo 03 - Validação: o valor informado deve corresponder ao somatório do campo VL_ICMS dos registros C197 e
D197, se o terceiro caractere do campo COD_AJ dos registros C197 ou D197 for igual a ‘3’, ‘4’ ou ‘5’ e o quarto
caractere for igual a “0”, “3”, “4” ou “5”. Deste somatório, estão excluídos os documentos extemporâneos (COD_SIT com
valor igual ‘01’) e os documentos complementares extemporâneas (COD_SIT com valor igual ‘07’), cujos valores devem
ser prestados no campo DEB_ESP juntamente com os demais valores extra-apuração.
Serão considerados os registros cujos documentos estejam compreendidos no período informado no registro E100,
utilizando para tanto o campo DT_E_S (C100). Quando o campo DT_E_S (C100) for vazio, utilizar o campo DT_DOC.
Campo 04 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ_APUR dos registros E111,
se o terceiro caractere for igual a ‘0’ e o quarto caractere do campo COD_AJ_APUR do registro E111 for igual a ‘0’.
Campo 05 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ_APUR dos registros E111,
se o terceiro caractere for igual a ‘0’ e o quarto caractere do campo COD_AJ_APUR do registro E111 for igual a ‘1’.
Campo 06 - Validação: o valor informado deve corresponder ao somatório de todos os documentos fiscais de entrada que
geram crédito de ICMS. O valor neste campo deve ser igual à soma dos VL_ICMS de todos os registros C190, C590, D190
e D590. Deste somatório, estão excluídos os documentos fiscais com CFOP 1605 e incluídos os documentos fiscais com
CFOP 5605. Os documentos fiscais devem ser somados conforme o período informado no registro E100 e a data informada
no campo DT_E_S (C100, C500) ou campo DT_A_P (D100, D500), exceto se COD_SIT do documento for igual a “01”
(extemporâneo) ou igual a 07 (NF Complementar extemporânea), cujo valor será somado no primeiro período de apuração
informado no registro E100.
Quando o campo DT_E_S ou DT_A_P não for informado, é utilizada a data constante no campo DT_DOC.
Campo 07 - Validação: o valor informado deve corresponder ao somatório do campo VL_ICMS dos registros C197 e
D197, se o terceiro caractere do código de ajuste dos registros C197 ou D197 for ‘0’, ‘1’ ou ‘2’ e o quarto caractere for
‘0’, “3”, “4” ou “5”. Devem ser considerados os documentos fiscais compreendidos no período informado no registro
E100, analisando-se as datas informadas no campo DT_E_S do registro C100, exceto se COD_SIT do registro C100 for
igual a ‘01’ (extemporâneo) ou igual a ‘07’ (NF Complementar extemporânea), cujo valor deve ser somado no primeiro
período de apuração informado no registro E100.
Campo 08 - Validação: o valor informado deve corresponder ao somatório dos valores constantes dos registros E111,
quando o terceiro caractere for igual a ‘0’ e o quarto caractere for igual a ‘2’, do COD_AJ_APUR do registro E111.
Campo 09 - Validação: o valor informado deve corresponder ao somatório do VL_AJ_APUR dos registros E111, quando
o terceiro caractere for igual a ‘0’ e o quarto caractere for igual a ‘3’, do COD_AJ_APUR do registro E111.
Campo 11 - Validação: o valor informado deve ser preenchido com base na expressão: soma do total de débitos
(VL_TOT_DEBITOS) com total de ajustes (VL_AJ_DEBITOS +VL_TOT_AJ_DEBITOS) com total de estorno de crédito
(VL_ESTORNOS_CRED) menos a soma do total de créditos (VL_TOT_CREDITOS) com total de ajuste de créditos
(VL_,AJ_CREDITOS + VL_TOT_AJ_CREDITOS) com total de estorno de débito (VL_ESTORNOS_DEB) com saldo
credor do período anterior (VL_SLD_CREDOR_ANT). Se o valor da expressão for maior ou igual a “0” (zero), então este
valor deve ser informado neste campo e o campo 14 (VL_SLD_CREDOR_TRANSPORTAR) deve ser igual a “0” (zero).
Se o valor da expressão for menor que “0” (zero), então este campo deve ser preenchido com “0” (zero) e o valor absoluto
da expressão deve ser informado no campo VL_SLD_CREDOR_TRANSPORTAR.
Campo 12 - Validação: o valor informado deve corresponder ao somatório do campo VL_ICMS dos registros C197 e
D197, se o terceiro caractere do código de ajuste do registro C197 ou D197, for ‘6’ e o quarto caractere for ‘0’, somado ao
valor total informado nos registros E111, quando o terceiro caractere for igual a ‘0’ e o quarto caractere for igual a ‘4’, do
campo COD_AJ_APUR do registro E111.
Para o somatório do campo VL_ICMS dos registros C197 e D197 devem ser considerados os documentos fiscais
compreendidos no período informado no registro E100, comparando com a data informada no campo DT_E_S do registro
C100, exceto se COD_SIT do registro C100 for igual a ‘01’ (extemporâneo) ou igual a ‘07’ (NF Complementar
extemporânea), cujo valor deve ser somado no primeiro período de apuração informado no registro E100, quando houver
mais de um período de apuração. Quando o campo DT_E_S não for informado, utilizar o campo DT_DOC.
Neste campo são informados os valores que, segundo a legislação da UF, devam ser tratados como “Dedução do imposto”,
ainda que no campo VL_SLD_APURADO tenha como resultado o valor zero.
Página 117 de 174

--- Página 118 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
Campo 13 – Validação: o valor informado deve corresponder à diferença entre o campo VL_SLD_APURADO e o campo
VL_TOT_DED. Se o resultado dessa operação for negativo, informe o valor zero neste campo, e o valor absoluto
correspondente no campo VL_SLD_CREDOR_TRANSPORTAR. Verificar se a legislação da UF permite que dedução
seja maior que o saldo devedor.
O valor da soma deste campo com o campo DEB_ESP deve ser igual à soma dos valores do campo VL_OR do registro
E116.
Campo 14 – Validação: se o valor da expressão: soma do total de débitos (VL_TOT_DEBITOS) com total de ajustes
(VL_AJ_DEBITOS + VL_TOT_AJ_DEBITOS) com total de estorno de crédito (VL_ESTORNOS_CRED) menos a soma
do total de créditos (VL_TOT_CREDITOS) com total de ajuste de créditos (VL_AJ_CREDITOS +
VL_TOT_AJ_CREDITOS) com total de estorno de débito (VL_ESTORNOS_DEB) com saldo credor do período anterior
(VL_SLD_CREDOR_ANT) for maior que “0” (zero), este campo deve ser preenchido com “0” (zero) e o campo 11
(VL_SLD_APURADO) deve ser igual ao valor do resultado. Se for menor que “0” (zero), o valor absoluto do resultado
deve ser informado neste campo e o campo VL_SLD_APURADO deve ser informado com “0” (zero).
Campo 15 – Preenchimento: Informar o correspondente ao somatório dos valores:
a) de ICMS correspondentes aos documentos fiscais extemporâneos (COD_SIT igual a “01”) e das notas fiscais
complementares extemporâneas (COD_SIT igual a “07”). No PVA, estes valores podem ser verificados no resumo
do Relatório dos Registros Fiscais de Documentos de Saídas (totalização por CST_ICMS e CFOP), constante das
últimas páginas.
b) de ajustes do campo VL_ICMS dos registros C197 e D197, se o terceiro caractere do código informado no campo
COD_AJ do registro C197 for igual a “7” (débitos especiais) e o quarto caractere for igual a “0” ou “2” (operações
próprias ou outras apurações) referente aos documentos compreendidos no período a que se refere a escrituração.
No PVA, estes valores podem ser verificados no resumo do Relatório dos Registros Fiscais de Documentos de
Saídas e de Entradas (totalização dos ajustes constante das últimas páginas); e
c) de ajustes do campo VL_AJ_APUR do registro E111, se o terceiro caractere do código informado no campo
COD_AJ_APUR do registro E111 for igual a “0” (apuração ICMS próprio) e o quarto caractere for igual a
“5”(débito especial). No PVA, estes valores podem ser verificados nos demonstrativos dos ajustes ao final do
Relatório de Registros Fiscais da Apuração do ICMS – Registro E111 - códigos específicos para débitos especiais.
Validação: O valor da soma deste campo com o campo VL_ICMS_RECOLHER deve ser igual à soma dos valores do
campo VL_OR do registro E116.
REGISTRO E111: AJUSTE/BENEFÍCIO/INCENTIVO DA APURAÇÃO DO ICMS.
Este registro tem por objetivo discriminar todos os ajustes lançados nos campos VL_TOT_AJ_DEBITOS,
VL_ESTORNOS_CRED, VL_TOT_AJ_CREDITOS, VL_ESTORNOS_DEB, VL_TOT_DED e DEB_ESP, todos do
registro E110.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E111" C 004 - O
02 COD_AJ_APUR Código do ajuste da apuração e dedução, conforme a C 008* - O
Tabela indicada no item 5.1.1.
03 DESCR_COMPL_AJ Descrição complementar do ajuste da apuração. C - - OC
04 VL_AJ_APUR Valor do ajuste da apuração N - 02 O
Observações:
Nível hierárquico – 4
Ocorrência – 1:N
Campo 01 - Valor Válido: [E111]
Campo 02 - Preenchimento: o valor informado no campo deve existir na tabela de código do ajuste da apuração e
dedução de cada Secretaria de Fazenda, conforme a UF do declarante, campo UF do registro 0000 ou, não havendo esta
tabela, o valor informado no campo deve existir na tabela de código do ajuste da apuração e dedução, constante da
observação do Item 5.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
O código do ajuste utilizado deve ter seu terceiro caractere como “0” (zero), indicando ajuste de ICMS, não incluindo
ajustes de ICMS-ST.
O quarto caractere deve ser preenchido, conforme item 5.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, com
um dos códigos abaixo:
0 – Outros débitos;
1 – Estorno de créditos;
Página 118 de 174

--- Página 119 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
2 – Outros créditos;
3 – Estorno de débitos;
4 – Deduções do imposto apurado;
5 – Débitos Especiais.
Obs.: Na existência de mais de um tipo de crédito que se enquadre no mesmo código de ajuste, deverão ser apresentados
tantos registros E111 quantos forem os tipos de créditos.
REGISTRO E112: INFORMAÇÕES ADICIONAIS DOS AJUSTES DA APURAÇÃO DO
ICMS.
Este registro tem por objetivo detalhar os ajustes do registro E111 quando forem relacionados a processos judiciais
ou fiscais ou a documentos de arrecadação, observada a legislação estadual pertinente. Valores recolhidos, com influência
na apuração do ICMS – Operações Próprias, devem ser detalhados neste registro, com identificação do documento de
arrecadação específico.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E112" C 004 - O
02 NUM_DA Número do documento de arrecadação estadual, se C - - OC
houver
03 NUM_PROC Número do processo ao qual o ajuste está vinculado, se C 015 - OC
houver
04 IND_PROC Indicador da origem do processo: C 001* - OC
0- Sefaz;
1- Justiça Federal;
2- Justiça Estadual;
9- Outros
05 PROC Descrição resumida do processo que embasou o C - - OC
lançamento
06 TXT_COMPL Descrição complementar C - - OC
Observações:
Nível hierárquico – 5
Ocorrência – 1:N
Campo 01 - Valor Válido: [E112]
Campo 02 - Preenchimento: este campo deve ser preenchido se o ajuste for referente a um documento de arrecadação, tais
como pagamentos indevidos, pagamentos antecipados e outros.
Campo 03 - Preenchimento: o valor deve ter até 15 caracteres.
Campo 04 - Valores válidos: [0, 1, 2, 9]
Campo 06 - Preenchimento: Outras informações complementares.
REGISTRO E113: INFORMAÇÕES ADICIONAIS DOS AJUSTES DA APURAÇÃO DO
ICMS – IDENTIFICAÇÃO DOS DOCUMENTOS FISCAIS.
Este registro tem por objetivo identificar os documentos fiscais relacionados ao ajuste.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E113" C 004 - O
02 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - O
- do emitente do documento ou do remetente das
mercadorias, no caso de entradas;
- do adquirente, no caso de saídas
03 COD_MOD Código do modelo do documento fiscal, conforme a C 002* - O
Tabela 4.1.1
04 SER Série do documento fiscal C 004 - OC
05 SUB Subserie do documento fiscal N 003 - OC
Página 119 de 174

--- Página 120 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
06 NUM_DOC Número do documento fiscal N 009 - O
07 DT_DOC Data da emissão do documento fiscal N 008* - O
08 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - OC
09 VL_AJ_ITEM Valor do ajuste para a operação/item N - 02 O
Observações:
Nível hierárquico - 5
Ocorrência – 1:N
Campo 01 - Valor Válido: [E113]
Campo 02 - Preenchimento: no caso de entrada, deve constar a informação referente ao emitente do documento ou ao
remetente das mercadorias ou serviços. No caso de saída, deve constar a informação referente ao destinatário. O valor deve
ter até 60 caracteres.
Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 03 - Validação: o valor informado no campo deve existir na tabela de Documentos Fiscais do ICMS, conforme
Item 4.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 06 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 07 - Preenchimento: informar a data de emissão do documento fiscal, no formato “ddmmaaaa”, sem os
separadores de formatação.
Campo 08 – Preenchimento: este campo só deve ser informado quando o ajuste se referir a um determinado item/produto
do documento.
Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
REGISTRO E115: INFORMAÇÕES ADICIONAIS DA APURAÇÃO – VALORES
DECLARATÓRIOS.
Este registro tem o objetivo de informar os valores declaratórios relativos ao ICMS, conforme definição da
legislação estadual pertinente. Esses valores são meramente declaratórios e não são computados na apuração do
ICMS.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E115" C 004 - O
02 COD_INF_ADIC Código da informação adicional conforme tabela a ser C 008* - O
definida pelas SEFAZ, conforme tabela definida no
item 5.2.
03 VL_INF_ADIC Valor referente à informação adicional N - 02 O
04 DESCR_COMPL_AJ Descrição complementar do ajuste C - - OC
Observações:
Nível hierárquico - 4
Ocorrência – 1:N
Campo 01 - Valor Válido: [E115]
Campo 02 - Preenchimento: o código da informação adicional deve obedecer à tabela definida pelas Secretarias de
Fazenda dos Estados. Caso não haja publicação da referida tabela, o registro não deve ser apresentado.
REGISTRO E116: OBRIGAÇÕES DO ICMS RECOLHIDO OU A RECOLHER –
OPERAÇÕES PRÓPRIAS.
Este registro tem o objetivo de discriminar os pagamentos realizados (débitos especiais) ou a realizar, referentes à
apuração do ICMS – Operações Próprias do período. A soma do valor das obrigações deste registro deve ser igual à soma
dos campos VL_ICMS_RECOLHER e DEB_ESP, do registro E110.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E116" C 004 - O
02 COD_OR Código da obrigação a recolher, conforme a Tabela 5.4 C 003* - O
Página 120 de 174

--- Página 121 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
03 VL_OR Valor da obrigação a recolher N - 02 O
04 DT_VCTO Data de vencimento da obrigação N 008* - O
05 COD_REC Código de receita referente à obrigação, próprio da C - - O
unidade da federação, conforme legislação estadual,
06 NUM_PROC Número do processo ou auto de infração ao qual a C 015 - OC
obrigação está vinculada, se houver.
07 IND_PROC Indicador da origem do processo: C 001* - OC
0- SEFAZ;
1- Justiça Federal;
2- Justiça Estadual;
9- Outros
08 PROC Descrição resumida do processo que embasou o C - - OC
lançamento
09 TXT_COMPL Descrição complementar das obrigações a recolher. C - - OC
10 MES_REF* Informe o mês de referência no formato “mmaaaa” N 006* - O
Observações: * O campo 10 – MES_REF somente deverá ser incluído no leiaute a partir de períodos de apuração de
janeiro de 2011.
Nível hierárquico - 4
Ocorrência – 1:N
Campo 01 - Valor Válido: [E116]
Campo 02 - Valores válidos: [000, 003, 004, 005, 006, 090]
Campo 03 – Preenchimento: o valor da soma deste campo deve corresponder à soma dos campos
VL_ICMS_RECOLHER e DEB_ESP do registro E110. Não informar acréscimos legais, se houver.
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
REGISTRO E200: PERÍODO DA APURAÇÃO DO ICMS - SUBSTITUIÇÃO TRIBUTÁRIA.
Este registro tem por objetivo informar o(s) período(s) de apuração do ICMS – Substituição Tributária para cada
UF onde o informante seja inscrito como substituto tributário, inclusive para o seu estado, nas operações internas que
envolvam substituição, e também para UF para a qual o declarante tenha comercializado e que não tenha inscrição como
substituto. Os períodos informados devem abranger todo o período previsto no registro 0000, sem haver sobreposição ou
omissão de datas, por UF.
Este registro, também, deverá ser informado pelo substituído, se este for o responsável pelo recolhimento do
imposto devido nas operações subsequentes, quando recebe mercadoria de outra unidade da federação, sujeita ao regime de
substituição tributária, na hipótese do remetente não estar obrigado a retenção do imposto.
Validação do Registro:
o registro é obrigatório se a soma, por UF, dos valores do campo VL_ICMS_ST dos registros C190, C590, C690, C791, for
maior que “0” (zero), ou se existir registro 0015 (substituto tributário) para a UF.
Não pode haver mais de um registro com a mesma combinação de valores para os campos UF, DT_INI e DT_FIN, nem
sobreposição ou omissão de períodos para a combinação.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E200" C 004 - O
02 UF Sigla da unidade da federação a que se refere a apuração C 002* - O
do ICMS ST
03 DT_INI Data inicial a que a apuração se refere N 008* - O
Página 121 de 174

--- Página 122 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
04 DT_FIN Data final a que a apuração se refere N 008* - O
Observações:
Nível hierárquico - 2
Ocorrência – 1:N
Campo 01 - Valor Válido: [E200]
Campo 02 - Validação o valor informado no campo deve existir na tabela de UF.
Campo 03 - Preenchimento: informar a data inicial a que a apuração se refere, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: verifica se a data informada é maior ou igual ao valor no campo DT_INI do registro 0000 e menor ou igual ao
valor no campo DT_FIN do registro 0000. A data informada no campo deve ser menor ou igual ao valor do campo DT_FIN
deste registro.
Campo 04 - Preenchimento: informar a data final a que a apuração se refere, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: verifica se a data informada é maior ou igual ao valor no campo DT_INI do registro 0000 e menor ou igual ao
valor no campo DT_FIN do registro 0000.
REGISTRO E210: APURAÇÃO DO ICMS – SUBSTITUIÇÃO TRIBUTÁRIA.
Este registro tem por objetivo informar valores relativos à apuração do ICMS de substituição tributária, mesmo
nos casos de períodos sem movimento.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E210" C 004 - O
02 IND_MOV_ST Indicador de movimento: C 001 - O
0 – Sem operações com ST
1 – Com operações de ST
03 VL_SLD_CRED_ANT_ST Valor do "Saldo credor de período anterior – N - 02 O
Substituição Tributária"
04 VL_DEVOL_ST Valor total do ICMS ST de devolução de N - 02 O
mercadorias
05 VL_RESSARC_ST Valor total do ICMS ST de ressarcimentos N - 02 O
06 VL_OUT_CRED_ST Valor total de Ajustes "Outros créditos ST" e N - 02 O
“Estorno de débitos ST”
07 VL_AJ_CREDITOS_ST Valor total dos ajustes a crédito de ICMS ST, N - 02 O
provenientes de ajustes do documento fiscal.
08 VL_RETENÇAO_ST Valor Total do ICMS retido por Substituição N - 02 O
Tributária
09 VL_OUT_DEB_ST Valor Total dos ajustes "Outros débitos ST" " e N - 02 O
“Estorno de créditos ST”
10 VL_AJ_DEBITOS_ST Valor total dos ajustes a débito de ICMS ST, N - 02 O
provenientes de ajustes do documento fiscal.
11 VL_SLD_DEV_ANT_ST Valor total de Saldo devedor antes das deduções N - 02 O
12 VL_DEDUÇÕES_ST Valor total dos ajustes "Deduções ST" N - 02 O
13 VL_ICMS_RECOL_ST Imposto a recolher ST (11-12) N - 02 O
14 VL_SLD_CRED_ST_TRAN Saldo credor de ST a transportar para o período N - 02 O
SPORTAR seguinte [(03+04+05+06+07)– (08+09+10)].
15 DEB_ESP_ST Valores recolhidos ou a recolher, extra- N - 02 O
apuração.
Observações:
Nível hierárquico - 3
Ocorrência – um por período
Campo 01 - Valor Válido: [E210]
Campo 02 - Valores válidos: [0, 1]
Campo 04 - Validação: o valor informado deve corresponder à soma do campo VL_ICMS_ST do registro C190, quando o
valor do campo CFOP for igual a 1410, 1411, 1414, 1415, 1660, 1661, 1662, 2410, 2411, 2414, 2415, 2660, 2661 ou 2662
Página 122 de 174

--- Página 123 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
e para documentos com data (campo DT_E_S ou DT_DOC do registro C100) compreendida no período de apuração do
registro E200. Só será considerada a data do campo DT_DOC, quando o campo DT_E_S estiver em branco.
Obs.: O preenchimento deste campo deverá estar de acordo com o disposto na legislação tributária da unidade federada do
contribuinte substituído.
Campo 05 – Preenchimento: só deve ser informado valor neste campo se o ressarcimento tiver origem em documento
fiscal.
Validação: o valor informado deve corresponder à soma do campo VL_ICMS_ST do registro C190, quando o valor do
campo CFOP for igual a 1603 ou 2603 e para documentos com data, campo DT_E_S ou campo DT_DOC do registro
C100, compreendida no período de apuração do registro E200. Só será considerada a data do campo DT_DOC, quando o
campo DT_E_S estiver em branco.
Campo 06 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ_APUR dos registros E220
quando o terceiro caractere for igual a ‘1’ e o quarto caractere do campo COD_AJ_APUR for igual a ‘2’ ou ‘3’ mais a
soma do campo VL_ICMS_ST do registro C190 (demais CFOPs), quando o primeiro caractere do campo CFOP for ‘1’ ou
‘2’, exceto se o valor do campo CFOP for 1410, 1411, 1414, 1415, 1660, 1661, 1662, 2410, 2411, 2414, 2415, 2660, 2661
ou 2662. Para documentos com data (campo DT_E_S ou DT_DOC do Registro C100) compreendida no período de
apuração do Registro E200. Só será considerada a data do Campo DT_DOC, quando o Campo DT_E_S estiver em
branco.
Campo 07 – Validação: o valor informado deve corresponder ao somatório do campo VL_ICMS do registro C197, por
UF, se o terceiro caractere do código de ajuste no campo COD_AJ do registro C197 for “0”, “1” ou “2” e o quarto
caractere for “1”(um) para todos os registros onde os documentos estejam compreendidos no período informado no registro
E200, considerando a UF, utilizando para tanto o campo DT_E_S (C100). Quando o campo DT_E_S (C100) não estiver
preenchido, a data considerada é a informada no campo DT_DOC.
Para os documentos extemporâneos (campo COD_SIT, do registro C100, com valor igual ‘01’), assim como para os
documentos complementares extemporâneos (campo COD_SIT, do registro C100, com valor igual ‘07’), estes valores
devem ser informados no primeiro período no registro E200, para a UF.
Campo 08 – Validação: o valor informado deve corresponder ao somatório do campo VL_ICMS_ST de todos os registros
C190, C590, C690, C791, D590 e D690, por UF, se o primeiro caractere do campo CFOP for igual a 5 ou 6, considerando
o período, por UF. Para o registro C791, o CFOP a ser considerado é o do registro “pai” C790. Nesta soma, devem constar
apenas os documentos fiscais compreendidos no período informado no registro E200, utilizando-se, para tanto, os campos
DT_DOC (C600, D600) ou DT_E_S (C100, C500, D500) ou DT_DOC_FIN (C700, D695).
Quando a data do campo DT_E_S não for informada, será utilizada a data do campo DT_DOC.
Campo 09 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ_APUR do registro E220,
quando o terceiro caractere for igual a ‘1’ e o quarto for igual a ‘0’ ou ‘1’, ambos do campo COD_AJ_APUR do registro
E220.
Campo 10 - Validação: o valor informado deve corresponder ao somatório do campo VL_ICMS do registro C197, por
UF, se o terceiro caractere do código de ajuste (campo COD_AJ) do registro C197 for ‘3’, ‘4’ ou ‘5’ e o quarto caractere
for ‘1’, para todos os registros onde os documentos estejam compreendidos no período informado no registro E200, por
UF, utilizando-se, para tanto, o campo DT_E_S (C100).
Quando a data do campo DT_E_S (C100) não estiver preenchida, é utilizada a data do campo DT_DOC.
Devem ser excluídos os documentos extemporâneos (campo COD_SIT do registro C100 com valor igual ‘01’) e os
documentos complementares extemporâneos (campo COD_SIT do registro C100 com valor igual ‘07’), cujos valores
devem ser informados no campo DEB_ESP_ST junto com os demais valores extra-apuração.
Campo 11 - Validação: o valor informado deve ser preenchido com base na expressão: soma do total de retenção por ST,
campo VL_RETENCAO_ST, com total de outros débitos por ST, campo VL_OUT_DEB_ST, com total de ajustes de
débito por ST, campo VL_AJ_DEBITOS_ST, menos a soma do saldo credor do período anterior por ST, campo
VL_SLD_CRED_ANT_ST, com total de devolução por ST, campo VL_DEVOL_ST, com total de ressarcimento por ST,
campo VL_RESSARC_ST, com o total de outros créditos por ST, campo VL_OUT_CRED_ST, com o total de ajustes de
crédito por ST, campo VL_AJ_CREDITOS_ST. Se o valor da expressão for maior ou igual a “0” (zero), então este valor
deve ser informado neste campo e o campo VL_SLD_CRED_ST_TRANSPORTAR deve ser igual a “0” (zero). Se o valor
da expressão for menor que “0” (zero), então este campo deve ser preenchido com “0” (zero) e o valor absoluto da
expressão deve ser informado no campo VL_SLD_CRED_ST_TRANSPORTAR.
Campo 12 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ_APUR do registro E220,
por UF, quando o terceiro caractere for igual a ‘1’ e o quarto caractere do campo COD_AJ_APUR for igual a ‘4’, mais a
soma do campo VL_ICMS do registro C197, se o terceiro caractere do campo COD_AJ for ‘6’ e o quarto caractere for
Página 123 de 174

--- Página 124 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
‘1’, para todos os registros onde os documentos estejam compreendidos no período informado no registro E200, por UF,
utilizando-se, para tanto, o campo DT_E_S, do registro C100. Quando o campo DT_E_S do registro C100 não estiver
preenchido, utilizar o campo DT_DOC do mesmo registro.
Campo 13 - Validação: o valor informado deve corresponder à diferença entre o campo VL_SLD_DEV_ANT_ST e o
campo VL_DEDUCOES_ST.
O valor da soma deste campo com o campo DEB_ESP_ST deve corresponder à soma dos valores do campo VL_OR do
registro E250.
Campo 14 - Validação: se o valor da expressão: soma do total de retenção por ST, campo VL_RETENCAO_ST, com total
de outros débitos por ST, campo VL_OUT_DEB_ST, com total de ajustes de débito por ST, campo
VL_AJ_DEBITOS_ST, menos a soma do saldo credor do período anterior por ST, campo VL_SLD_CRED_ANT_ST, com
total de devolução por ST, campo VL_DEVOL_ST, com total de ressarcimento por ST, campo VL_RESSARC_ST, com o
total de outros créditos por ST, campo VL_OUT_CRED_ST, com o total de ajustes de crédito por ST, campo
VL_AJ_CREDITOS_ST, for maior ou igual a “0” (zero), este campo deve ser preenchido com “0” (zero). Se for menor que
“0” (zero), o valor absoluto do resultado deve ser informado.
Campo 15 – Preenchimento: Informar por UF, valor correspondente ao somatório dos valores:
a) de ICMS_ST referente aos documentos fiscais extemporâneos (COD_SIT igual a “01”) e das notas fiscais
complementares extemporâneas (COD_SIT igual a “07”). ;
b) de ajustes do campo VL_ICMS do registro C197, se o terceiro caractere do código informado no campo COD_AJ
do registro C197 for igual a “7” (débitos especiais) e o quarto caractere for igual a “1” (operações por ST)
referente aos documentos compreendidos no período a que se refere a escrituração; e
c) de ajustes do campo VL_AJ_APUR do registro E220, se o terceiro caractere do código informado no campo
COD_AJ_APUR do registro E220 for igual a “1” (ICMS- ST) e o quarto caractere for igual a “5”(débito especial).
Validação: O valor da soma do campo DEB_ESP_ST com o campo VL_ICMS_RECOL_ST deve corresponder à soma
dos valores do campo VL_OR do registro E250.
REGISTRO E220: AJUSTE/BENEFÍCIO/INCENTIVO DA APURAÇÃO DO ICMS
SUBSTITUIÇÃO TRIBUTÁRIA.
Este registro deve ser apresentado para discriminar os ajustes lançados nos campos VL_OUT_CRED_ST,
VL_OUT_DEB_ST e VL_DEDUÇOES_ST e os valores informados no campo DEB_ESP_ST, todos do registro E210.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E220" C 004 - O
02 COD_AJ_APUR Código do ajuste da apuração e dedução, conforme a C 008* - O
Tabela indicada no item 5.1.1
03 DESCR_COMPL_AJ Descrição complementar do ajuste da apuração C - - OC
04 VL_AJ_APUR Valor do ajuste da apuração N - 02 O
Observações:
Nível hierárquico - 4
Ocorrência – 1:N
Campo 01 - Valor Válido: [E220]
Campo 02 - o valor informado no campo deve existir na tabela de código do ajuste da apuração e dedução de cada
Secretaria de Fazenda, conforme a UF do contribuinte substituído ou, não havendo esta tabela, o valor informado no campo
deve existir na tabela de código do ajuste da apuração e dedução constante na observação do Item 5.1.1. do Ato
COTEPE/ICMS nº 09, de 18 de abril de 2008 (tabela genérica).
O código do ajuste utilizado deve ter seu terceiro caractere como um, indicando ajuste de ICMS-ST.
O quarto caractere deve ser preenchido, conforme item 5.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, com
um dos códigos abaixo:
0 – Outros débitos;
1 – Estorno de créditos;
2 – Outros créditos;
3 – Estorno de débitos;
4 – Deduções do imposto apurado;
5 – Débitos Especiais.
Página 124 de 174

--- Página 125 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO E230: INFORMAÇÕES ADICIONAIS DOS AJUSTES DA APURAÇÃO DO
ICMS SUBSTITUIÇÃO TRIBUTÁRIA.
Este registro deve ser apresentado para detalhar os ajustes do registro E220 quando forem relacionados a processos
judiciais ou fiscais ou a documentos de arrecadação, observada a legislação estadual pertinente. Valores recolhidos, com
influência na apuração do ICMS-ST, devem ser informados neste registro, com identificação do documento de arrecadação
específico.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E230" C 004 - O
02 NUM_DA Número do documento de arrecadação estadual, se C - - OC
houver
03 NUM_PROC Número do processo ao qual o ajuste está vinculado, se C 015 - OC
houver
04 IND_PROC Indicador da origem do processo: N 001* - OC
0- Sefaz;
1- Justiça Federal;
2- Justiça Estadual;
9- Outros
05 PROC Descrição resumida do processo que embasou o C - - OC
lançamento
06 TXT_COMPL Descrição complementar C - - OC
Observações:
Nível hierárquico - 5
Ocorrência – 1:N
Campo 01 - Valor Válido: [E230]
Campo 02 - Preenchimento: este campo deve ser preenchido se o ajuste for referente a um documento de arrecadação
conforme dispuser a legislação pertinente.
Campo 03 - Preenchimento: o valor deve ter até 15 caracteres.
Campo 04 - Valores válidos: [0, 1, 2, 9]
Campo 06 - Preenchimento: Outras informações complementares.
REGISTRO E240: INFORMAÇÕES ADICIONAIS DOS AJUSTES DA APURAÇÃO DO
ICMS SUBSTITUIÇÃO TRIBUTÁRIA – IDENTIFICAÇÃO DOS DOCUMENTOS
FISCAIS.
Este registro deve ser apresentado para identificação dos documentos fiscais relacionados ao ajuste.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E240" C 004 - O
02 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - O
- do emitente do documento ou do remetente das
mercadorias, no caso de entradas;
- do adquirente, no caso de saídas
03 COD_MOD Código do modelo do documento fiscal, conforme a C 002* - O
Tabela 4.1.1
04 SER Série do documento fiscal C 004 - OC
05 SUB Subsérie do documento fiscal N 003 - OC
06 NUM_DOC Número do documento fiscal N 009 - O
07 DT_DOC Data da emissão do documento fiscal N 008* - O
08 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - OC
09 VL_AJ_ITEM Valor do ajuste para a operação/item N - 02 O
Observações:
Nível hierárquico - 5
Página 125 de 174

--- Página 126 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
Ocorrência – 1:N
Campo 01 - Valor Válido: [E240]
Campo 02 - Preenchimento: no caso de entrada, deve constar a informação referente ao emitente do documento ou do
remetente das mercadorias. No caso de saída, deve constar a informação referente ao adquirente. O valor deve ter até 15
caracteres.
Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 03 - Validação: o valor informado no campo deve existir na tabela de Documentos Fiscais do ICMS, conforme
Item 4.1.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 06 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 07 - Preenchimento: informar a data de emissão do documento fiscal, no formato “ddmmaaaa”, sem os
separadores de formatação.
Campo 08 – Preenchimento: este campo só deve ser informado quando o ajuste se referir a um determinado item/produto
do documento.
Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
REGISTRO E250: OBRIGAÇÕES DO ICMS RECOLHIDO OU A RECOLHER –
SUBSTITUIÇÃO TRIBUTÁRIA.
Este registro deve ser apresentado para discriminar os pagamentos realizados (Débitos especiais) ou a realizar,
referentes à apuração do ICMS devido por Substituição Tributária do período, por UF. A soma do valor das obrigações a
serem discriminadas neste registro deve ser igual ao campo VL_ICMS_RECOL_ST (registro E210) somado ao campo
DEB_ESP_ST (registro E210) e o somatório dos valores informados no registro C197 (cujo terceiro e quarto caractere seja
igual a “71”).
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "E250" C 004 - O
02 COD_OR Código da obrigação a recolher, conforme a Tabela 5.4 C 003* - O
03 VL_OR Valor da obrigação ICMS ST a recolher N - 02 O
04 DT_VCTO Data de vencimento da obrigação N 008* - O
05 COD_REC Código de receita referente à obrigação, próprio da C - - O
unidade da federação do contribuinte substituído.
06 NUM_PROC Número do processo ou auto de infração ao qual a C 015 - OC
obrigação está vinculada, se houver
07 IND_PROC Indicador da origem do processo: C 001* - OC
0- SEFAZ;
1- Justiça Federal;
2- Justiça Estadual;
9- Outros
08 PROC Descrição resumida do processo que embasou o C - - OC
lançamento
09 TXT_COMPL Descrição complementar das obrigações a recolher C - - OC
10 MES_REF* Informe o mês de referência no formato “mmaaaa” N 006* - O
Observações: * O campo 10 – MES_REF somente deverá ser incluído no leiaute a partir de períodos de apuração de
janeiro de 2011.
Nível hierárquico - 4
Ocorrência – 1:N
Campo 01 - Valor Válido: [E250]
Campo 02 - Valores válidos: [001, 002, 006, 999]
Campo 03 – Validação: o valor da soma deste campo deve corresponder à soma dos campos VL_ICMS_RECOL_ST e
DEB_ESP_ST do registro E210.
Página 126 de 174

--- Página 127 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
Campo 04 - Preenchimento: informar a data de vencimento da obrigação, no formato “ddmmaaaa”, sem os separadores
de formatação.
Validação: o valor informado no campo deve ser uma data válida.
Campo 06 - Validação: se este campo estiver preenchido, os campos IND_PROC e PROC deverão estar preenchidos. Se
este campo não estiver preenchido, os campos IND_PROC e PROC não deverão estar preenchidos. O valor deve ter até 15
caracteres.
Campo 07 - Valores válidos: [0, 1, 2, 9]
Campo 09 - preenchimento: quando este registro se referir a recolhimento extemporâneo, informar neste campo o mês e
ano de referência de cada um dos débitos extemporâneos do período, no formato mmaaaa, sem utilizar os caracteres
especiais de separação. Exemplo: para débito extemporâneo do mês de abril de 2009 o campo deve ser preenchido,
simplesmente, com os caracteres 042009.
REGISTRO E500: PERÍODO DE APURAÇÃO DO IPI.
Este registro deve ser apresentado pelos estabelecimentos industriais ou equiparados, conforme dispõe o
Regulamento do IPI, para identificação do(s) período(s) de apuração. O(s) período(s) informado(s) deve(m) abranger todo
o período previsto no registro 0000. Poderá coexistir um período mensal com períodos decendiais. Para os períodos
decendiais, não poderá haver sobreposição ou omissão de datas.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E500" C 004 - O
02 IND_APUR Indicador de período de apuração do IPI: C 1* - O
0 - Mensal;
1 - Decendial
03 DT_INI Data inicial a que a apuração se refere N 008* - O
04 DT_FIN Data final a que a apuração se refere N 008* - O
Observações:
Nível hierárquico - 2
Ocorrência –um ou vários (por arquivo)
Campo 01 - Valor Válido: [E500]
Campo 02 - Valores válidos: [0, 1]
Campo 03 - Preenchimento: informar a data inicial a que a apuração se refere, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: verifica se a data informada é maior ou igual ao campo DT_INI do registro 0000 e menor ou igual ao valor no
campo DT_FIN do registro 0000.
Campo 04 - Preenchimento: informar a data final a que a apuração se refere, no formato “ddmmaaaa”, sem os
separadores de formatação.
Validação: verifica se a data informada é maior ou igual ao valor no campo DT_INI do registro 0000 e menor ou igual ao
valor no campo DT_FIN do registro 0000.
REGISTRO E510: CONSOLIDAÇÃO DOS VALORES DO IPI.
Este registro deve ser preenchido com os valores consolidados do IPI, de acordo com o período informado no
registro E500, tomando-se por base as informações prestadas no registro C170.
A consolidação se dará pela sumarização do valor contábil, base de cálculo e imposto relativo a todas as
operações, conforme a combinação de CFOP e código da situação tributária do IPI (CST_IPI).
As informações oriundas dos itens dos documentos fiscais – registro C170 ou do documento NF-e de emissão
própria – serão consideradas no período de apuração mensal ou decendial, conforme preenchimento do campo IND_APUR.
Chave do registro: CFOP e CST_IPI
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E510" C 004 - O
02 CFOP Código Fiscal de Operação e Prestação do agrupamento N 004* - O
de itens
Página 127 de 174

--- Página 128 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
03 CST_IPI Código da Situação Tributária referente ao IPI, C 002* - O
conforme a Tabela indicada no item 4.3.2.
04 VL_CONT_IPI Parcela correspondente ao "Valor Contábil" referente ao N - 02 O
CFOP e ao Código de Tributação do IPI
05 VL_BC_IPI Parcela correspondente ao "Valor da base de cálculo do N - 02 O
IPI" referente ao CFOP e ao Código de Tributação do
IPI, para operações tributadas
06 VL_IPI Parcela correspondente ao "Valor do IPI" referente ao N - 02 O
CFOP e ao Código de Tributação do IPI, para operações
tributadas
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [E510]
Campo 02 - Preenchimento: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e
Prestação, conforme Ajuste SINIEF 07/01.
Campo 03 - Preenchimento: O campo deverá ser preenchido somente se o declarante for contribuinte do IPI. A tabela do
CST_IPI consta publicada na Instrução Normativa RFB nº 932, de 14/04/2009, atualizada pela IN RFB 1009/2010.
Código Descrição
00 Entrada com recuperação de crédito
01 Entrada tributada com alíquota zero
02 Entrada isenta
03 Entrada não-tributada
04 Entrada imune
05 Entrada com suspensão
49 Outras entradas
50 Saída tributada
51 Saída tributada com alíquota zero
52 Saída isenta
53 Saída não-tributada
54 Saída imune
55 Saída com suspensão
99 Outras saídas
Campo 06 - Validação: O total de créditos e dos débitos informados neste registro deverá ser igual ao total dos créditos e
débitos dos registros C190 e do registro E520.
REGISTRO E520: APURAÇÃO DO IPI.
Este registro deve ser preenchido para demonstração da apuração do IPI no período.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "E520" C 004 - O
02 VL_SD_ANT_IPI Saldo credor do IPI transferido do período anterior N - 02 O
03 VL_DEB_IPI Valor total dos débitos por "Saídas com débito do N - 02 O
imposto"
04 VL_CRED_IPI Valor total dos créditos por "Entradas e aquisições com N - 02 O
crédito do imposto"
05 VL_OD_IPI Valor de "Outros débitos" do IPI (inclusive estornos de N - 02 O
crédito)
06 VL_OC_IPI Valor de "Outros créditos" do IPI (inclusive estornos de N - 02 O
débitos)
07 VL_SC_IPI Valor do saldo credor do IPI a transportar para o período N - 02 O
seguinte
08 VL_SD_IPI Valor do saldo devedor do IPI a recolher N - 02 O
Observações:
Nível hierárquico - 3
Página 128 de 174

--- Página 129 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
Ocorrência - 1:1
Campo 01 - Valor Válido: [E520]
Campo 03 - Validação: o valor informado deve corresponder ao somatório do campo VL_IPI do registro E510, quando o
CFOP iniciar por ‘5’ ou ‘6” dos registros C190.
Campo 04 - Validação: o valor informado deve corresponder ao somatório do campo VL_IPI do registro E510, quando o
CFOP iniciar por ‘1’, ‘2’ ou ‘3’ dos registros C190.
Campo 05 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ do registro E530, quando o
campo IND_AJ do registro E530 for igual a ‘0’.
Campo 06 - Validação: o valor informado deve corresponder ao somatório do campo VL_AJ do registro E530, quando o
campo IND_AJ do registro E530 for igual a ‘1’.
Campo 07 - Validação: se a soma dos campos VL_DEB_IPI e VL_OD_IPI menos a soma dos campos VL_SD_ANT_IPI,
VL_CRED_IPI e VL_OC_IPI for menor que “0” (zero), então o campo VL_SC_IPI deve ser igual ao valor absoluto da
expressão, e o valor do campo VL_SD_IPI deve ser igual a “0” (zero).
Campo 08 - Validação: se a soma dos campos VL_DEB_IPI e VL_OD_IPI menos a soma dos campos VL_SD_ANT_IPI,
VL_CRED_IPI e VL_OC_IPI for maior ou igual a “0” (zero), então o campo 08 (VL_SD_IPI) deve ser igual ao resultado
da expressão, e o valor do campo VL_SC_IPI deve ser igual a “0” (zero).
REGISTRO E530: AJUSTES DA APURAÇÃO DO IPI.
Este registro deve ser apresentado para discriminar os ajustes lançados nos campos Outros Débitos e Outros
Créditos do registro E520.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E530" C 004 - O
02 IND_AJ Indicador do tipo de ajuste: C 001* - O
0- Ajuste a débito;
1- Ajuste a crédito
03 VL_AJ Valor do ajuste N - 02 O
04 COD_AJ Código do ajuste da apuração, conforme a Tabela C 003* O
indicada no item 4.5.4.
05 IND_DOC Indicador da origem do documento vinculado ao ajuste: C 001* - OC
0 - Processo Judicial;
1 - Processo Administrativo;
2 - PER/DCOMP;
9 – Outros.
06 NUM_DOC Número do documento / processo / declaração ao qual o C - - OC
ajuste está vinculado, se houver
07 DESCR_AJ Descrição detalhada do ajuste, com citação dos C - - O
documentos fiscais.
Observações:
Nível hierárquico - 4
Ocorrência – 1:N por Período
Campo 01 - Valor Válido: [E530]
Campo 02 - Valores válidos: [0, 1]
Campo 03 – Preenchimento: informar o valor dos ajustes lançados nos campos outros débitos e outros créditos que não
constam dos documentos fiscais, exceto no caso de transferência de crédito de IPI, conforme o disposto na IN SRF 600 de
2005.
Campo 04 - Validação: o valor informado no campo deve existir na Tabela de Ajustes da Apuração IPI, publicada pela
RFB (Instrução Normativa RFB nº 932, de 14/04/2009, atualizada pela IN RFB 1009/2010).
Código Descrição Natureza (*) Detalhamento
Página 129 de 174

--- Página 130 ---
Guia Prático EFD – Versão 2.0.8
Atualização: março de 2012
001 Estorno de débito C Valor do débito do IPI estornado
002 Crédito recebido por C Valor do crédito do IPI recebidos por transferência, de
transferência outro(s) estabelecimento(s) da mesma empresa
010 Crédito Presumido de IPI - C valor do crédito presumido de IPI decorrente do ressarcimento
ressarcimento do PIS/Pasep e da do PIS/Pasep e da Cofins nas operações de exportação de
Cofins - Lei nº 9.363/1996 produtos industrializados (Lei nº 9.363/1996, art. 1º)
011 Crédito Presumido de IPI - C valor do crédito presumido de IPI decorrente do ressarcimento
ressarcimento do PIS/Pasep e da do PIS/Pasep e da Cofins nas operações de exportação de
Cofins - Lei nº 10.276/2001 produtos industrializados (Lei nº 10.276/2001, art. 1º)
012 Crédito Presumido de IPI - C valor do crédito presumido relativo ao IPI incidente nas
regiões incentivadas - Lei nº saídas, do estabelecimento industrial, dos produtos
9.826/1999 classificados nas posições 8702 a 8704 da Tipi (Lei nº
9.826/1999, art. 1º)
013 Crédito Presumido de IPI - frete C valor do crédito presumido de IPI relativamente à parcela do
- MP 2.158/2001 frete cobrado pela prestação do serviço de transporte dos
produtos classificados nos códigos 8433.53.00, 8433.59.1,
8701.10.00, 8701.30.00, 8701.90.00, 8702.10.00 Ex 01,
8702.90.90 Ex 01, 8703, 8704.2, 8704.3 e 87.06.00.20, da
TIPI (MP nº 2.158/2001, art. 56)
019 Crédito Presumido de IPI - C outros valores de crédito presumido de IPI
outros
098 Créditos decorrentes de medida C valores de crédito de IPI decorrentes de medida judicial
judicial
099 Outros créditos C Valor de outros créditos do IPI
101 Estorno de crédito D Valor do crédito do IPI estornado
102 Transferência de crédito D Valor do crédito do IPI transferido no período, para outro(s)
estabelecimento(s) da mesma empresa, conforme previsto na
legislação tributária.
103 Ressarcimento / compensação D Valor do crédito de IPI, solicitado junto à RFB/MF
de créditos de IPI
199 Outros débitos D Valor de outros débitos do IPI
(*) Natureza: "C" - Crédito; "D" - Débito
Campo 05 - Valores válidos: [0, 1, 2, 9]
Campo 07 – Preenchimento: informar a descrição resumida do ajuste, incluindo, se for o caso, o período a que se refere o
ajuste, especialmente quando se tratar de períodos de apuração anteriores.
REGISTRO E990: ENCERRAMENTO DO BLOCO E
Este registro destina-se a identificar o encerramento do Bloco “E” e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E990" C 004 - O
02 QTD_LIN_E Quantidade total de linhas do Bloco E N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [E990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco E é igual ao valor informado no campo QTD_LIN_E.
Página 130 de 174

