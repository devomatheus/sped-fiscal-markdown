# Bloco C - Versão 2.0.14

**Data de Criação:** 2014-03-01  
**Páginas:** 32-86  
**Versão:** 2.0.14

---

--- Página 32 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nível hierárquico - 1
Ocorrência – um por arquivo
Campo 01 - Valor Válido: [0990]
Campo 02 - Preenchimento: a quantidade de linhas (registros) a ser informada deve considerar também os próprios
registros de abertura e encerramento do bloco. Para este cálculo, o registro 0000, mesmo não pertencendo ao bloco 0, deve
ser somado.
Validação: o número de linhas (registros) existentes no bloco 0 é igual ao valor informado neste campo.
BLOCO C: DOCUMENTOS FISCAIS I - MERCADORIAS (ICMS/IPI)
REGISTRO C001: ABERTURA DO BLOCO C
Este registro tem por objetivo identificar a abertura do bloco C, indicando se há informações sobre documentos
fiscais.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "C001" C 004 - O
02 IND_MOV Indicador de movimento: C 001 - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência - um por arquivo
Campo 01 - Valor válido: [C001]
Campo 02 - Valores válidos: [0, 1]
Validação: se o valor deste campo for igual a “1” (um), somente podem ser informados os registros de abertura e
encerramento do bloco. Se o valor neste campo for igual a “0” (zero), deve ser informado pelo menos um registro além dos
registros de abertura e encerramento do bloco.
REGISTRO C100: NOTA FISCAL (CÓDIGO 01), NOTA FISCAL AVULSA (CÓDIGO
1B), NOTA FISCAL DE PRODUTOR (CÓDIGO 04), NF-e (CÓDIGO 55) e
NFC-e (CÓDIGO 65).
Este registro deve ser gerado para cada documento fiscal código 01, 1B, 04, 55 e 65, conforme item 4.1.1 do Ato
COTEPE/ICMS nº 09, de 18 de abril de 2008, registrando a entrada ou saída de produtos ou outras situações que envolvam
a emissão dos documentos fiscais mencionados.
A partir do mês de referência abril de 2012, a informação do campo CHV_NFE passa a ser obrigatória em todas as
situações, exceto para NFe com numeração inutilizada (COD_SIT = 05).
IMPORTANTE: para documentos de entrada, os campos de valor de imposto, base de cálculo e
alíquota só devem ser informados se o adquirente tiver direito à apropriação do crédito (enfoque do
declarante).
Para cada registro C100, obrigatoriamente deve ser apresentado, pelo menos, um registro C170 e um registro
C190, observadas as exceções abaixo relacionadas:
Exceção 1: Para documentos com código de situação (campo COD_SIT) cancelado (código “02”), cancelado
extemporâneo (código “03”), Nota Fiscal Eletrônica (NF-e) denegada (código “04”), preencher somente os campos REG,
IND_OPER, IND_EMIT, COD_MOD, COD_SIT, SER, NUM_DOC e CHV_NF-e. Para COD-SIT = 05 (numeração
inutilizada), todos os campos referidos anteriormente devem ser preenchidos, exceto o campo CHV_NF-e. Demais campos
deverão ser apresentados com conteúdo VAZIO “||”. Não informar registros filhos. A partir de janeiro de 2011, no caso de
NF-e de emissão própria com código de situação (campo COD_SIT) cancelado (código “02”) e cancelado extemporâneo
(código “03”) deverão ser informados os campos acima citados incluindo ainda a chave da NF-e.
Página 32 de 209

--- Página 33 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Exceção 2: Notas Fiscais Eletrônicas - NF-e de emissão própria: regra geral, devem ser apresentados somente os registros
C100 e C190, e, se existirem ajustes de documento fiscais determinados por legislação estadual (tabela 5.3 do Ato
COTEPE ICMS 09/08), devem ser apresentados também os registros C195 e C197; somente será admitida a informação
do registro C170 quando também houver sido informado o registro C176, hipótese de emissão de documento fiscal quando
houver direito a Ressarcimento de ICMS em Operações com Substituição Tributária. A critério de cada UF, informar os
registros C110 e C120, a partir de julho de 2012. ;
Exceção 3: Notas Fiscais Complementares e Notas Fiscais Complementares Extemporâneas (campo COD_SIT igual a
“06” ou “07”): nesta situação, somente os campos REG, IND_EMIT, COD_PART, COD_MOD, COD_SIT, NUM_DOC,
CHV_NFE e DT_DOC são de preenchimento obrigatório, devendo ser preenchida a data de efetiva saída, para os
contribuintes das UFs que utilizam a data de saída para a apuração. Os demais campos são facultativos (se forem
preenchidos, inclusive com valores iguais a zero, serão validadas e aplicadas as regras de campos existentes). O registro
C190 é sempre obrigatório e deve ser totalmente preenchido. Os demais campos e registros filhos do registro C100 serão
informados, quando houver informação a ser prestada. Se for informado o registro C170 o campo NUM_ITEM deve ser
preenchido.
Exceção 4: Notas Fiscais emitidas por regime especial ou norma específica (campo COD_SIT igual a “08”). Para
documentos fiscais emitidos com base em regime especial ou norma específica, deverão ser apresentados os registros C100
e C190, obrigatoriamente, e os demais registros “filhos”, se estes forem exigidos pela legislação fiscal. Nesta situação, para
o registro C100, somente os campos REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT, NUM_DOC e
DT_DOC são de preenchimento obrigatório. A partir do mês de referência abril de 2012 a informação do campo
CHV_NFE passa a ser obrigatória neste caso para modelo 55. Os demais campos, com exceção do campo NUM_ITEM do
registro C170, são facultativos (se forem preenchidos, inclusive com valores iguais a Zero, serão validados e aplicadas as
regras de campos existentes) e deverão ser preenchidos, quando houver informação a ser prestada. Exemplos: a) Nota fiscal
emitida em substituição ao cupom fiscal – CFOP igual a 5.929 ou 6.929 – (lançamento efetuado em decorrência de emissão
de documento fiscal relativo à operação ou à prestação também registrada em equipamento Emissor de Cupom Fiscal –
ECF, exceto para o contribuinte do Estado do Paraná, que deve efetuar a escrituração de acordo com a regra estabelecida na
tabela de código de ajustes); b) Nos casos em que a legislação estadual permitir a emissão de NF sem informações do
destinatário, preencher os dados do próprio emitente. Obs.: a partir de janeiro de 2012, para todos os documentos diferentes
de NF-e e com COD_SIT igual a “08”, deverá ser informada no registro C110 a norma legal que autoriza o preenchimento
do documento fiscal nessa situação.
Exceção 5: Para os documentos fiscais emitidos de acordo com o estabelecido em regimes especiais ou normas específicas,
devidamente autorizados pelo fisco (campo COD_SIT igual a “08”), será permitida a informação de data de emissão de
documento maior que a data de entrada ou saída. Ex. aquisição de cana-de-açúcar, venda de derivados de petróleo, etc. Será
emitida Advertência pelo PVA-EFD-ICMS/IPI.
Exceção 6: Venda de produtos que geram direito a ressarcimento com utilização de NF-e: Nos casos de vendas, para
outro estado, de produtos tributados por ST na operação anterior o contribuinte deverá indicar no registro C176 os dados
para futura solicitação de ressarcimento. O registro C170 deverá ser preenchido apenas com os itens da NF que gerem
direito ao pedido de ressarcimento, devendo também ser preenchido o registro C176 (utilização a partir de 01/06/2009). A
UF determinará a obrigatoriedade deste registro.
Exceção 7: Escrituração de documentos emitidos por terceiros: os casos de escrituração de documentos fiscais, inclusive
NF-e, emitidos por terceiros (como por ex. o consórcio constituído nos termos do disposto nos arts. 278 e 279 da Lei nº
6.404, de 15 de dezembro de 1976) e das NF-e “avulsas” emitidas pelas UF (séries 890 a 899) devem ser informados como
emissão de terceiros, com o código de situação do documento igual a “08 - Documento Fiscal emitido com base em
Regime Especial ou Norma Específica”. O PVA-EFD-ICMS/IPI exibirá a mensagem de Advertência para esses
documentos.
Obs: Os documentos fiscais emitidos pelas filiais das empresas que possuam inscrição estadual única ou sejam autorizadas
pelos fiscos estaduais a centralizar suas escriturações fiscais deverão ser informados como sendo de emissão própria e
código de situação igual a “00 – Documento regular”.Excepcionalmente, até junho de 2012, poderão ser informados como
sendo de emissão de terceiros e código de situação de documento como sendo “08”.
Exceção 8: NF-e com o campo UF de consumo preenchido: nos casos de NF-e de emissão própria, quando o campo UF
de consumo for preenchido (onde a UF de consumo é diversa da UF do destinatário), deve ser informado no registro C105.
Exceção 9 - Para notas fiscais eletrônicas ao consumidor final (NFC-e), modelo 65: regra geral, devem ser apresentados
somente os registros C100 e C190. No registro C100, não devem ser informados os campos COD_PART,
VL_BC_ICMS_ST, VL_ICMS_ST, VL_IPI, VL_PIS, VL_COFINS, VL_PIS_ST e VL_COFINS_ST. Os demais campos
seguirão a obrigatoriedade definida pelo registro.
Não podem ser informados, para um mesmo documento fiscal, dois ou mais registros com a mesma combinação
de valores dos campos formadores da chave do registro. A chave deste registro é:
• para documentos com campo IND_EMIT igual a “1” (um) – emissão por terceiros: campo IND_OPER,
campo IND_EMIT, campo COD_PART, campo COD_MOD, campo COD_SIT, campo SER e campo
NUM_DOC;
Página 33 de 209

--- Página 34 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
• para documentos com campo (IND_EMIT igual “0” (zero) – emissão própria: campo IND_OPER, campo
IND_EMIT, campo COD_MOD, campo COD_SIT, campo SER e campo NUM_DOC.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C100" C 004 - O O
02 IND_OPER Indicador do tipo de operação: C 001* - O O
0- Entrada;
1- Saída
03 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O O
0- Emissão própria;
1- Terceiros
04 COD_PART Código do participante (campo 02 do Registro C 060 - O O
0150):
- do emitente do documento ou do remetente das
mercadorias, no caso de entradas;
- do adquirente, no caso de saídas
05 COD_MOD Código do modelo do documento fiscal, conforme C 002* - O O
a Tabela 4.1.1
06 COD_SIT Código da situação do documento fiscal, N 002* - O O
conforme a Tabela 4.1.2
07 SER Série do documento fiscal C 003 - OC OC
08 NUM_DOC Número do documento fiscal N 009 - O O
09 CHV_NFE Chave da Nota Fiscal Eletrônica N 044* - O O
10 DT_DOC Data da emissão do documento fiscal N 008* - O O
11 DT_E_S Data da entrada ou da saída N 008* - O OC
12 VL_DOC Valor total do documento fiscal N - 02 O O
13 IND_PGTO Indicador do tipo de pagamento: C 001* - O O
0- À vista;
1- A prazo;
9- Sem pagamento.
Obs.: A partir de 01/07/2012 passará a ser:
Indicador do tipo de pagamento:
0- À vista;
1- A prazo;
2 - Outros
14 VL_DESC Valor total do desconto N - 02 OC OC
15 VL_ABAT_NT Abatimento não tributado e não comercial Ex. N - 02 OC OC
desconto ICMS nas remessas para ZFM.
16 VL_MERC Valor total das mercadorias e serviços N - 02 O OC
17 IND_FRT Indicador do tipo do frete: C 001* - O O
0- Por conta de terceiros;
1- Por conta do emitente;
2- Por conta do destinatário;
9- Sem cobrança de frete.
Obs.: A partir de 01/01/2012 passará a ser:
Indicador do tipo do frete:
0- Por conta do emitente;
1- Por conta do destinatário/remetente;
2- Por conta de terceiros;
9- Sem cobrança de frete.
18 VL_FRT Valor do frete indicado no documento fiscal N - 02 OC OC
19 VL_SEG Valor do seguro indicado no documento fiscal N - 02 OC OC
20 VL_OUT_DA Valor de outras despesas acessórias N - 02 OC OC
21 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 OC OC
22 VL_ICMS Valor do ICMS N - 02 OC OC
23 VL_BC_ICMS_ST Valor da base de cálculo do ICMS substituição N - 02 OC OC
tributária
Página 34 de 209

--- Página 35 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
24 VL_ICMS_ST Valor do ICMS retido por substituição tributária N - 02 OC OC
25 VL_IPI Valor total do IPI N - 02 OC OC
26 VL_PIS Valor total do PIS N - 02 OC OC
27 VL_COFINS Valor total da COFINS N - 02 OC OC
28 VL_PIS_ST Valor total do PIS retido por substituição N - 02 OC OC
tributária
29 VL_COFINS_ST Valor total da COFINS retido por substituição N - 02 OC OC
tributária
Observações:
Nível hierárquico - 2
Ocorrência – vários (por arquivo)
Campo 01 - Valor Válido: [C100]
Campo 02 - Valores válidos: [0, 1]
Preenchimento: indicar a operação, conforme os códigos. Podem ser informados como documentos de entrada os
emitidos por terceiros ou pelo próprio informante da EFD-ICMS/IPI.
Campo 03 - Valores válidos: [0, 1]
Preenchimento: consideram-se de emissão própria somente os documentos fiscais emitidos pelo estabelecimento
informante (campo CNPJ do registro 0000) da EFD-ICMS/IPI. Documentos emitidos por outros estabelecimentos ainda
que da mesma empresa, devem ser considerados como documentos emitidos por terceiros. Nos casos de escrituração de
documentos fiscais de terceiros em operações de saídas (ex. consórcios de empresas), deve ser informado no campo 06
(COD_SIT) o código “08”.
Se a legislação estadual a que estiver submetido o contribuinte obrigá-lo a escriturar notas fiscais avulsas em operação de
saída, este campo deve ser informado com valor igual a “0” (zero).
Validação: se este campo tiver valor igual a “1” (um), o campo IND_OPER deve ser igual a “0” (zero).
Campo 04 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 05 - Valores válidos: [01, 1B, 04, 55, 65]
Preenchimento: o valor informado deve constar na tabela 4.1.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008,
reproduzida na subseção 6.4 deste guia. O “código” a ser informado não é exatamente o “modelo” do documento, devendo
ser consultada a tabela 4.1.1. Exemplo: o código “01” deve ser utilizado para os modelos “1” ou “1A".
Campo 06 - Valores válidos: [00, 01, 02, 03, 04, 05, 06, 07, 08]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3. Para todo documento diferente de NF-e
de emissão própria com COD_SIT igual a “08” é obrigatório preencher o registro C110 para informar os dispositivos legais
que permitem a emissão do documento fiscal naquela situação.
Validação: os valores “04” e “05” só são possíveis para NF-e.
Campo 08 – Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 09 - Preenchimento: campo de preenchimento obrigatório para NF-e, COD_MOD igual a “55”, de emissão
própria ou de terceiros e para NFC-e, COD_MOD igual a “65”. A partir de abril de 2012, a chave da NF-e é obrigatória em
todas as situações, exceto para NFe com numeração inutilizada (COD_SIT = 05).
Validação: é conferido o dígito verificador (DV) da chave da NF-e e da NFC-e. Este campo é de preenchimento
obrigatório para COD_MOD igual a “55” e “65”. Para confirmação inequívoca de que a chave da NF-e/NFC-e corresponde
aos dados informados do documento, é comparado o CNPJ existente na CHV_NFE com o campo CNPJ do registro 0000,
que corresponde ao CNPJ do informante do arquivo, no caso de IND_EMIT = 0 (emissão própria). São verificados a
consistência da informação do campo NUM_DOC e o número do documento contido na chave da NF-e. É também
comparada a UF codificada na chave da NF-e com o campo UF informado no registro 0000.
Campo 10 - Preenchimento: informar a data de emissão do documento, no formato “ddmmaaaa”, excluindo-se quaisquer
caracteres de separação, tais como: “.”, “/”, “-”.
Validação: o valor informado no campo deve ser menor ou igual ao valor do campo DT_FIN do registro 0000.
Campo 11 - Preenchimento: informar a data de entrada ou saída, conforme a operação, no formato ddmmaaaa; excluindo-
se quaisquer caracteres de separação, tais como: “.”, “/”, “-”. Quando o campo IND_OPER indicar operação de “saída”,
este campo será informado apenas se o contribuinte possuir este dado em seus sistemas.
Página 35 de 209

--- Página 36 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Validação: este campo deve ser menor ou igual ao valor do campo DT_FIN do registro 0000. Para operações de entrada ou
saída este valor deve ser maior ou igual à data de emissão (campo DT_DOC).
Nas operações de entradas de produtos este campo é sempre de preenchimento obrigatório.
Importante: Se a legislação do ICMS definir que o imposto deve ser apropriado com base na data de emissão dos
documentos fiscais, proceder da seguinte forma: todos os documentos de saídas com código de situação de documento
igual a “00” (documento regular) devem ser lançados no período de apuração informado no registro 0000, considerando a
data de emissão do documento, e, se a data de saída for maior que a data final do período de apuração, este campo não pode
ser preenchido.
Se a legislação do ICMS definir que o imposto deve ser apropriado com base na data da saída dos produtos, proceder da
seguinte forma: todos os documentos de saídas com código de situação de documento igual a “00” (documento regular)
devem ser lançados no período de apuração informado no registro 0000, considerando a data de saída do produto informada
no documento.
Campo 12 – Validação: o valor informado neste campo deve ser igual à soma do campo VL_OPR dos registros C190
(“filhos” deste registro C100). Nos casos em que houver divergência entre o valor total da nota fiscal e o somatório dos
valores da operação informados no reg. C190, serão exibidas mensagens de “Advertência”.
Campo 13 - Valores válidos: [0, 1, 2, 9]
Campo 14 - Preenchimento: informar o valor do desconto incondicional discriminado na nota fiscal.
Campo 16 - Validação: se o campo COD_MOD for diferente de “55”, campo IND_EMIT for diferente de “0” e o campo
COD_SIT for igual a “00” ou “01”, o valor informado no campo deve ser igual à soma do campo VL_ITEM dos registros
C170 (“filhos” deste registro C100).
Campo 17 - Valores válidos: [0, 1, 2, 9]
Preenchimento: Em operações tais como: remessas simbólicas, faturamento simbólico, transporte próprio, venda balcão,
informar o código “9 - sem frete”, ou seja, operações sem cobrança de frete.
Quando houver transporte com mais de um responsável pelo seu pagamento, deve ser informado o indicador do frete
relativo ao responsável pelo primeiro percurso.
Se o campo COD_MOD for igual a “65”, informar somente “9”.
Campo 21 - Validação: a soma dos valores do campo VL_BC_ICMS dos registros analíticos (C190) deve ser igual ao
valor informado neste campo.
Campo 22 – Preenchimento: informar o valor do ICMS creditado na operação de entrada ou o valor do ICMS debitado
na operação de saída.
Validação: a soma dos valores do campo VL_ICMS dos registros analíticos (C190) deve ser igual ao valor informado neste
campo.
Campo 23 - Validação: a soma dos valores do campo VL_BC_ICMS_ST dos registros analíticos (C190) deve ser igual ao
valor informado neste campo.
Campo 24 - Preenchimento: informar o valor do ICMS creditado/debitado por substituição tributária, nas operações de
entrada ou saída, conforme legislação aplicada.
Validação: A soma dos valores do campo VL_ICMS_ST dos registros analíticos (C190) deve ser igual ao valor informado
neste campo.
Campo 25 - Validação: a soma dos valores do campo VL_IPI dos registros analíticos (C190) deve ser igual ao valor
informado neste campo.
Campo 26 - Preenchimento: informar o valor do montante creditado, se existente, nas operações de entrada e o montante
debitado, se existente, nas operações de saída. Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo
período de apuração do registro 0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 27 - Preenchimento: informar o valor do montante creditado, se existente, nas operações de entrada e o montante
debitado, se existente, nas operações de saída. Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo
período de apuração do registro 0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Página 36 de 209

--- Página 37 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 28 - Preenchimento: informar o valor do montante creditado, se existente, nas operações de entrada e o montante
debitado, se existente, nas operações de saída. Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo
período de apuração do registro 0000 estão dispensados do preenchimento deste campo.
Campo 29 - Preenchimento: informar o valor do montante creditado, se existente, nas operações de entrada e o montante
debitado, se existente, nas operações de saída. Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo
período de apuração do registro 0000 estão dispensados do preenchimento deste campo.
Perguntas e Respostas
1) Como deve ser a apresentação da nota fiscal nesse registro quando ocorrerem situações em que a legislação disponha
que alguns valores devem ser zerados na escrituração da nota fiscal? Deve seguir a mesma regra de escrituração dos livros
fiscais? Ou deve ser apresentado o valor conforme destacado no documento?
Resposta: O contribuinte obrigado à EFD-ICMS/IPI deve seguir as regras estaduais de escrituração existentes, lançando ou
não o ICMS e o ICMS ST a ser efetivamente debitado ou creditado.
2) Campo 15 - Valor do abatimento não tributado e não comercial: além do exemplo do desconto da ZFM em qual outra
situação deve ser preenchido?
Resposta: Cada legislação estadual prevê situações específicas. Abaixo, exemplo de duas situações previstas no
Regulamento do ICMS/MG.
Sit. 1 - Quando a aplicação da redução de base de cálculo ficar condicionada ao repasse para o contribuinte do valor
equivalente ao imposto dispensado na operação. Exemplo: SEF MG - RICMS/02, Anexo IV, item 2 (condição 2.1, b).
Sit. 2 - Isenção com repasse para o contribuinte na saída, em operação interna, de mercadoria ou bem destinado a órgãos da
administração pública estadual direta, suas fundações e autarquias. Exemplo: SEF MG - RICMS/02, Anexo I, item 136.
REGISTRO C105: OPERAÇÕES COM ICMS ST RECOLHIDO PARA UF DIVERSA
DO DESTINATÁRIO DO DOCUMENTO FISCAL (CÓDIGO 55).
Este registro tem por objetivo identificar a UF destinatária do recolhimento do ICMS ST, quando esta for diversa
da UF do destinatário do produto. Ex. Leasing de veículo quando a entidade financeira está localizada em uma UF e o
destinatário do produto em outra UF.
Durante o ano de 2009, as empresas sujeitas ao recolhimento a UFs diferentes do destinatário dos produtos
deverão estornar o débito correspondente à UF do destinatário do documento fiscal e deverão adicionar o valor
correspondente na apuração do ICMS ST para a UF do recolhimento do tributo.
A partir de período de apuração de janeiro de 2010, essas empresas deverão utilizar o registro C105 para que possa
ser identificada a UF de destino do ICMS ST.
Nº Campo Descrição Tipo Tam Dec Entr. Saídas
1 REG Texto fixo contendo "C105" C 004 - O O
2 OPER Indicador do tipo de operação: N 001* - O O
0- Combustíveis e Lubrificantes;
1- leasing de veículos ou faturamento direto.
3 UF Sigla da UF de destino do ICMS_ST C 002* - O O
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor Válido: [C105]
Campo 02 - Valores Válidos: [0, 1]
Campo 03 - Validação: o valor deve ser a sigla da unidade da federação (UF) de destino do ICMS ST.
REGISTRO C110: INFORMAÇÃO COMPLEMENTAR DA NOTA FISCAL (CÓDIGO
01, 1B, 04 e 55).
Este registro tem por objetivo identificar os dados contidos no campo Informações Complementares da Nota
Fiscal, que sejam de interesse do fisco, conforme dispõe a legislação. Devem ser discriminadas em registros “filhos
Página 37 de 209

--- Página 38 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
próprios” as informações relacionadas com documentos fiscais, processos, cupons fiscais, documentos de arrecadação e
locais de entrega ou coleta que foram explicitamente citadas no campo “Informações Complementares” da Nota Fiscal.
Não podem ser informados para um mesmo documento fiscal, dois ou mais registros com o mesmo conteúdo no
campo COD_INF.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C110" C 004 - O O
02 COD_INF Código da informação complementar do C 006 - O O
documento fiscal (campo 02 do Registro 0450)
03 TXT_COMPL Descrição complementar do código de referência. C - - OC OC
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor válido: [C110]
Campo 02 - Validação: o valor informado no campo deve existir no registro 0450 - Tabela de informação complementar.
REGISTRO C111: PROCESSO REFERENCIADO
Este registro deve ser apresentado, obrigatoriamente, quando no campo – “Informações Complementares” da nota
fiscal - constar a discriminação de processos referenciados no documento fiscal.
Não podem ser informados dois ou mais registros com o mesmo conteúdo no campo NUM_PROC para um
mesmo registro C110.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C111" C 004 - O O
02 NUM_PROC Identificação do processo ou ato concessório. C 015 - O O
03 IND_PROC Indicador da origem do processo: C 001* - O O
0 - SEFAZ;
1 - Justiça Federal;
2 - Justiça Estadual;
3 - SECEX/SRF
9 - Outros.
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C111]
Campo 03 - Valores válidos: [0, 1, 2, 3, 9]
REGISTRO C112: DOCUMENTO DE ARRECADAÇÃO REFERENCIADO.
Este registro deve ser apresentado, obrigatoriamente, quando no campo – “Informações Complementares” da
nota fiscal - constar a identificação de um documento de arrecadação.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C112" C 004 - O O
02 COD_DA Código do modelo do documento de arrecadação : C 001* - O O
0 - documento estadual de arrecadação
1 – GNRE
03 UF Unidade federada beneficiária do recolhimento C 002* - O O
04 NUM_DA Número do documento de arrecadação C - - OC OC
05 COD_AUT Código completo da autenticação bancária C - - OC OC
06 VL_DA Valor do total do documento de arrecadação N - 02 O O
(principal, atualização monetária, juros e multa)
07 DT_VCTO Data de vencimento do documento de arrecadação N 008* - O O
08 DT_PGTO Data de pagamento do documento de arrecadação, N 008* - O O
ou data do vencimento, no caso de ICMS
antecipado a recolher.
Página 38 de 209

--- Página 39 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C112]
Campo 02 - Valores válidos: [0, 1]
Campo 03 – Validação: o valor deve ser a sigla da UF beneficiária do recolhimento.
Campo 05 - Validação: se não for informado valor no campo NUM_DA, obrigatoriamente, o campo COD_AUT deve ser
informado.
Campo 06 - Preenchimento: informar o valor total do documento de arrecadação, ainda que este documento seja
referenciado em mais de uma nota fiscal, situação em que haverá um registro C112, idêntico e vinculado a cada nota fiscal
(C100).
Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 07 - Preenchimento: informar a data de vencimento do documento de arrecadação no formato “ddmmaaaa”.
Campo 08 - Preenchimento: informar a data de pagamento do documento de arrecadação no formato “ddmmaaaa”.
Como a data de pagamento é uma informação obrigatória, deve ser preenchida mesmo que o documento de arrecadação
ainda não tenha sido pago, situação em que a data de vencimento deve ser informada neste campo. Por exemplo, nos casos
de ICMS antecipado.
REGISTRO C113: DOCUMENTO FISCAL REFERENCIADO.
Este registro tem por objetivo informar, detalhadamente, outros documentos fiscais que tenham sido mencionados
nas informações complementares do documento que está sendo escriturado no registro C100, exceto cupons fiscais, que
devem ser informados no registro C114. Exemplos: nota fiscal de remessa de mercadoria originária de venda para entrega
futura e nota fiscal de devolução de compras.
Não podem ser informados, para um mesmo documento fiscal, dois ou mais registros com a mesma combinação
de valores dos campos formadores da chave do registro. A chave deste registro é:
• para documentos emitidos por terceiros: campos IND_EMIT, COD_PART, COD_MOD, SER e
NUM_DOC.
• para documentos de emissão própria: campos IND_EMIT, COD_MOD, SER e NUM_DOC.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C113" C 004 - O O
02 IND_OPER Indicador do tipo de operação: C 001* - O O
0- Entrada/aquisição;
1- Saída/prestação
03 IND_EMIT Indicador do emitente do título: C 001* - O O
0- Emissão própria;
1- Terceiros
04 COD_PART Código do participante emitente (campo 02 do C 060 - O O
Registro 0150) do documento referenciado.
05 COD_MOD Código do documento fiscal, conforme a Tabela C 002* - O O
4.1.1
06 SER Série do documento fiscal C 004 - OC OC
07 SUB Subsérie do documento fiscal N 003 - OC OC
08 NUM_DOC Número do documento fiscal N 009 - O O
09 DT_DOC Data da emissão do documento fiscal. N 008* - O O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C113]
Campo 02 - Valores válidos: [0, 1]
Página 39 de 209

--- Página 40 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 03 - Valores válidos: [0, 1]
Validação: se o valor neste campo for igual a “1” (um), então o campo IND_OPER deve ser igual a “0” (zero).
Campo 04 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 05 - Preenchimento: informar o código do documento fiscal, conforme tabela 4.1.1 do Ato COTEPE/ICMS nº 09,
de 18 de abril de 2008, reproduzida na subseção 6.4 deste guia.O código a ser informado não é exatamente o “modelo” do
documento. Por exemplo: o código “01” deve ser utilizado para os modelos “1” ou “1A".
Validação: o valor informado no campo deve existir na Tabela de Documentos Fiscais do ICMS (tabela 4.1.1 do Ato
COTEPE/ICMS nº 09, de 18 de abril de 2008). O valor informado neste campo deve ser diferente de “2D”, “02” e “2E”.
Campo 08 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 09 - Preenchimento: data da emissão da NF no formato “ddmmaaaa”.
Validação: o valor informado neste campo deve ser menor ou igual ao valor do campo DT_DOC do registro C100.
REGISTRO C114: CUPOM FISCAL REFERENCIADO.
Este registro será utilizado para informar, detalhadamente, nas operações de saídas, cupons fiscais que tenham sido
mencionados nas informações complementares do documento que está sendo escriturado no registro C100. Nas operações
de entradas, somente informar quando o emitente do cupom fiscal for o próprio informante do arquivo. Não podem ser
informados para um mesmo documento fiscal, dois ou mais registros com a mesma combinação de conteúdo nos campos
ECF_FAB, NUM_DOC e DT_DOC.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C114" C 004 - O O
02 COD_MOD Código do modelo do documento fiscal, conforme C 002* - O O
a tabela indicada no item 4.1.1
03 ECF_FAB Número de série de fabricação do ECF C 021 - O O
04 ECF_CX Número do caixa atribuído ao ECF N 003 - O O
05 NUM_DOC Número do documento fiscal N 009 O O
06 DT_DOC Data da emissão do documento fiscal N 008* - O O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C114]
Campo 02 - Valores válidos: [02, 2D, 2E] – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Preenchimento: número do Contador de Ordem de Operação (COO).
Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 06 - Preenchimento: data da emissão do cupom no formato “ddmmaaaa”.
Validação: o valor informado neste campo deve ser menor ou igual ao valor do campo DT_DOC do registro C100.
REGISTRO C115: LOCAL DA COLETA E/OU ENTREGA (CÓDIGO 01, 1B E 04).
Este registro tem por objetivo informar o local de coleta, quando este for diferente do endereço do emitente do
documento fiscal e/ou local de entrega, quando este for diferente do endereço do destinatário do documento fiscal, além de
informar a modalidade de transporte utilizada. As informações prestadas referem-se a transporte próprio ou de terceiros.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C115" C 004 - Não O
Página 40 de 209

--- Página 41 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Indicador do tipo de transporte: Apresen- O
0 – Rodoviário; tar
1 – Ferroviário;
2 – Rodo-Ferroviário;
02 IND_CARGA N 001* -
3 – Aquaviário;
4 – Dutoviário;
5 – Aéreo;
9 – Outros.
Número do CNPJ do contribuinte do local de OC
03 CNPJ_COL N 014* -
coleta
Inscrição Estadual do contribuinte do local de OC
04 IE_COL C 014 -
coleta
CPF_COL CPF do contribuinte do local de coleta das OC
05 N 011* -
mercadorias.
06 COD_MUN_COL Código do Município do local de coleta N 007* - OC
Número do CNPJ do contribuinte do local de OC
07 CNPJ_ENTG N 014* -
entrega
Inscrição Estadual do contribuinte do local de OC
08 IE_ENTG C 014 -
entrega
09 CPF_ENTG Cpf do contribuinte do local de entrega N 011* - OC
10 COD_MUN_ENTG Código do Município do local de entrega N 007* - OC
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C115]
Campo 02 - Valores Válidos: [0, 1, 2, 3, 4, 5, 9]
Campo 03 – Preenchimento: não utilizar os caracteres especiais de formatação, tais como: “.”, “/”, “-”.
Validação: é conferido se o dígito verificador é válido.
Somente um dos campos CPF_COL ou CNPJ_COL deve ser preenchido.
Campo 04 - Preenchimento: não utilizar os caracteres especiais de formatação, tais como: “.”, “/”, “-”.
Validação: é conferido o dígito verificador da Inscrição Estadual, considerando-se a UF obtida no código de município
informado no campo COD_MUN_COL.
Campo 05 - Preenchimento: não utilizar os caracteres especiais de formatação, tais como: “.”, “/”, “-”.
Validação: é conferido se o dígito verificador é válido.
Campo 06 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Mesmo não havendo dados de coleta, este campo deve ser preenchido.
Campo 07 - Preenchimento: não utilizar os caracteres especiais de formatação, tais como: “.”, “/”, “-”.
Validação: é conferido se o dígito verificador é válido.
Somente um dos campos CPF_ENTG ou CNPJ_ENTG deve ser preenchido.
Campo 08 - Preenchimento: não utilizar os caracteres especiais de formatação, tais como: “.”, “/”, “-”.
Validação: é conferido o dígito verificador da inscrição estadual, considerando-se a UF obtida no código de município
informado no campo COD_MUN_ENTG.
Campo 09 - Preenchimento: não utilizar os caracteres especiais de formatação, tais como: “.”, “/”, “-”.
Validação: é conferido se o dígito verificador é válido.
Campo 10 – Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Mesmo não havendo dados de entrega, este campo deve ser preenchido.
Página 41 de 209

--- Página 42 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
REGISTRO C116: CUPOM FISCAL ELETRÔNICO REFERENCIADO
Este registro será utilizado para informar, detalhadamente, nas operações de saídas, cupons fiscais eletrônicos
que tenham sido mencionados nas informações complementares do documento que está sendo escriturado no registro C100.
Nas operações de entradas no registro C100, somente informar quando o emitente do cupom fiscal for o próprio informante
do arquivo. Não podem ser informados para um mesmo documento fiscal, dois ou mais registros com a mesma combinação
de conteúdo nos campos NR_SAT, NUM_CFE e DT_DOC.
Este registro está relacionado ao documento fiscal informado no registro C800 ou C860.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C116" C 004 - O O
02 COD_MOD Código do modelo do documento fiscal, conforme a Tabela C 002 -
O O
4.1.1
03 NR_SAT Número de Série do equipamento SAT N 009 - O O
04 CHV_CFE Chave do Cupom Fiscal Eletrônico N 044 - O O
05 NUM_CFE Número do cupom fiscal eletrônico N 006 - O O
06 DT_DOC Data da emissão do documento fiscal N 008 - O O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 – Valor Válido: [C116]
Campo 02 – Preenchimento: deve corresponder ao código Cupom Fiscal Eletrônico (Valor Válido: [59])- – Ver tabela
reproduzida na subseção 6.4 deste guia.
Campo 04 – Validação: é conferido o dígito verificador (DV) da chave do CF-e. Para confirmação inequívoca de que a
chave da NF-e corresponde aos dados informados no documento, será comparado o CNPJ existente na CHV_CFE com o
campo CNPJ do registro 0000, que corresponde ao CNPJ do informante do arquivo. Serão verificados a consistência da
informação do campo NUM_CFE e o número do documento contido na chave do CF-e, bem como comparado se a
informação do AAMM de emissão contido na chave do CFE corresponde ao ano e mês da data de emissão do CF-e. Será
também comparada a UF codificada na chave do CF-e com o campo UF informado no registro 0000.
Campo 06 – Preenchimento: informar a data de emissão do documento, no formato “ddmmaaaa”, excluindo-se quaisquer
caracteres de separação, tais como: “.”, “/”, “-”.
REGISTRO C120: COMPLEMENTO DE DOCUMENTO - OPERAÇÕES DE
IMPORTAÇÃO (CÓDIGOS 01 e 55).
Este registro tem por objetivo informar detalhes das operações de importação, que estejam sendo documentadas
pela nota fiscal escriturada no registro C100, quando o campo IND_OPER for igual a “0” (zero), indicando operação de
entrada.
Não podem ser informados para um mesmo documento fiscal, dois ou mais registros com o mesmo conteúdo no
campo NUM_DOC__IMP e NUM_ACDRAW.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C120" C 004 - O Não
02 COD_DOC_IMP Documento de importação: C 001* - O apresentar
0 – Declaração de Importação;
1 – Declaração Simplificada de Importação.
03 NUM_DOC__IM Número do documento de Importação. C 012 - O
P
04 PIS_IMP Valor pago de PIS na importação N - 02 OC
05 COFINS_IMP Valor pago de COFINS na importação N - 02 OC
06 NUM_ACDRAW Número do Ato Concessório do regime C 020 - OC
Drawback
Página 42 de 209

--- Página 43 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Observações: Alteração do tamanho do campo 06 – NUM_ACDRAW de 11 para 20 caracteres a partir de 01/01/2011.
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C120]
Campo 02 - Valores válidos: [0, 1]
Campo 04 – Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 05 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C130: ISSQN, IRRF E PREVIDÊNCIA SOCIAL.
Este registro tem por objetivo informar dados da prestação de serviços sob não-incidência ou não tributados pelo
ICMS e ainda detalhes sobre a retenção de Imposto de Renda Retido na Fonte (IRRF) e de contribuições previdenciárias.
Essas três situações possuem características próprias e tratamentos específicos na legislação, não guardando entre elas
nenhuma relação.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C130" C 004 - Não O
02 VL_SERV_NT Valor dos serviços sob não-incidência ou não- N - 02 apresentar O
tributados pelo ICMS
03 VL_BC_ISSQN Valor da base de cálculo do ISSQN N - 02 O
04 VL_ISSQN Valor do ISSQN N - 02 OC
05 VL_BC_IRRF Valor da base de cálculo do Imposto de Renda N - 02 OC
Retido na Fonte
06 VL_ IRRF Valor do Imposto de Renda - Retido na Fonte N - 02 OC
07 VL_BC_PREV Valor da base de cálculo de retenção da N - 02 OC
Previdência Social
08 VL_ PREV Valor destacado para retenção da Previdência N - 02 OC
Social
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor Válido: [C130]
REGISTRO C140: FATURA (CÓDIGO 01)
Este registro tem por objetivo informar dados da fatura comercial, sempre que a aquisição ou venda de
mercadorias for a prazo, por meio de notas fiscais modelo 1 ou 1A. Devem ser consideradas as informações quando da
emissão do documento fiscal, incluindo a parcela paga no ato da operação, se for o caso.
Nos casos onde uma única fatura diz respeito a diversas notas fiscais, para cada nota apresentada no C100, a fatura
deve aqui ser informada, sempre com o seu valor original, sem nenhum rateio.
Havendo mais de um tipo de título, informar o campo IND_TIT com o código ‘99’ (Outros). No campo
DESC_TIT identificar cada um dos títulos, com números e valores. No campo VL_TIT informar o valor total da fatura.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C140" C 004 - O O
02 IND_EMIT Indicador do emitente do título: C 001* - O O
0- Emissão própria;
1- Terceiros
03 IND_TIT Indicador do tipo de título de crédito: C 002* - O O
00- Duplicata;
01- Cheque;
Página 43 de 209

--- Página 44 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
02- Promissória;
03- Recibo;
99- Outros (descrever)
04 DESC_TIT Descrição complementar do título de crédito C - - OC OC
05 NUM_TIT Número ou código identificador do título de C - - O O
crédito
06 QTD_PARC Quantidade de parcelas a receber/pagar N 002 - O O
07 VL_TIT Valor total dos títulos de créditos N - 02 O O
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor Válido: [C140]
Campo 02 - Valores válidos: [0, 1]
Campo 03 - Valores válidos: [00, 01, 02, 03, 99]
Preenchimento: informar o tipo de título de crédito e utilizar o indicador “99” (Outros) quando houver diversos tipos de
títulos, inclusive documentos eletrônicos, descrevendo os tipos no campo seguinte.
Campo 06 - Validação: o valor neste campo corresponde ao total de ocorrências dos registros C141.
Campo 07 - Preenchimento: o valor neste campo corresponde ao valor original do título, mesmo nos casos onde uma
única fatura diz respeito a diversas notas fiscais.
REGISTRO C141: VENCIMENTO DA FATURA (CÓDIGO 01).
Este registro deve ser apresentado, obrigatoriamente, sempre que for informado o registro C140, devendo ser
discriminados o valor e a data de vencimento de cada uma das parcelas.
Não podem ser informados dois ou mais registros com o mesmo conteúdo para o campo NUM_PARC.
Nº Campo Descrição Tipo Tam Dec Entr. Saída
01 REG Texto fixo contendo "C141" C 004 - O O
02 NUM_PARC Número da parcela a receber/pagar N 002 - O O
03 DT_VCTO Data de vencimento da parcela N 008* - O O
04 VL_PARC Valor da parcela a receber/pagar N - 02 O O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor válido: [C141]
Campo 03 - Preenchimento: informar a data de vencimento da parcela, no formato “ddmmaaaa”.
Validação: o valor neste campo deve ser maior ou igual ao valor do campo DT_DOC do registro C100.
REGISTRO C160: VOLUMES TRANSPORTADOS (CÓDIGO 01 E 04) - EXCETO
COMBUSTÍVEIS.
Este registro tem por objetivo informar detalhes dos volumes, do transportador e do veículo empregado no
transporte nas operações de saídas.
Nº Campo Descrição Tipo Tam Dec Entr. Saída
01 REG Texto fixo contendo "C160" C 004 - Não O
02 COD_PART Código do participante (campo 02 do Registro C 060 - apresentar OC
0150):
- transportador, se houver
03 VEIC_ID Placa de identificação do veículo automotor C 007 - OC
04 QTD_VOL Quantidade de volumes transportados N - - O
05 PESO_BRT Peso bruto dos volumes transportados (em Kg) N - 02 O
06 PESO_LIQ Peso líquido dos volumes transportados (em Kg) N - 02 O
07 UF_ID Sigla da UF da placa do veículo C 002 - OC
Página 44 de 209

--- Página 45 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor Válido: [C160]
Campo 02 - Validação: o valor informado deve existir no campo COD_PART do registro 0150. Quando o transportador
for o próprio emitente do documento, este campo não deve ser preenchido.
Campo 03 - Preenchimento: informar a placa do veículo transportador, quando disponível nos sistemas de informação do
contribuinte. Este campo se refere à placa do veículo tracionado (com cadastro no RENAVAM), quando se tratar de
reboque ou semi-reboque deste tipo de veículo. Quando houver mais de um veículo tracionado, a placa deve ser indicada
no registro C110. Na hipótese de veículo não rodoviário, não é necessário preencher.
REGISTRO C165: OPERAÇÕES COM COMBUSTÍVEIS (CÓDIGO 01).
Este registro deve ser apresentado pelas empresas do segmento de combustíveis (distribuidoras, refinarias,
revendedoras) em operações de saída. Postos de combustíveis não devem apresentar este registro. Não podem ser
informados para um mesmo documento fiscal, dois ou mais registros com a mesma combinação de conteúdo nos campos
COD_PART e VEIC_ID.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C165” C 004 - Não O
COD_PART Código do participante (campo 02 do Registro C 060 - apresentar OC
02 0150):
- transportador, se houver
03 VEIC_ID Placa de identificação do veículo C 007 - O
Código da autorização fornecido pela SEFAZ OC
04 COD_AUT C - -
(combustíveis)
05 NR_PASSE Número do Passe Fiscal C - - OC
06 HORA Hora da saída das mercadorias N 006* - O
Temperatura em graus Celsius utilizada para OC
07 TEMPER N - 01
quantificação do volume de combustível
08 QTD_VOL Quantidade de volumes transportados N - - O
09 PESO_BRT Peso bruto dos volumes transportados (em Kg) N - 02 O
10 PESO_LIQ Peso líquido dos volumes transportados (em Kg) N - 02 O
11 NOM_MOT Nome do motorista C 060 - OC
12 CPF CPF do motorista N 011* - OC
13 UF_ID Sigla da UF da placa do veículo C 002 - OC
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C165]
Campo 02 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 06 - Preenchimento: informar, conforme o padrão “hhmmss”, excluindo-se quaisquer caracteres de separação, tais
como: ".", ":", "-", " ", etc.
Campo 12 - Preenchimento: não utilizar os caracteres especiais de formatação, tais como: “.”, “/”, “-”.
Validação: se preenchido, é conferido se o dígito verificador é válido.
REGISTRO C170: ITENS DO DOCUMENTO (CÓDIGO 01, 1B, 04 e 55).
Registro obrigatório para discriminar os itens da nota fiscal (mercadorias e/ou serviços constantes em notas
conjugadas), inclusive em operações de entrada de mercadorias acompanhadas de Nota Fiscal Eletrônica (NF-e) de emissão
de terceiros.
Conforme item 2.4.2.2.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, o termo "item" é aplicado às
operações fiscais que envolvam mercadorias, serviços, produtos ou quaisquer outros itens concernentes às transações
Página 45 de 209

--- Página 46 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
fiscais suportadas pelo documento, como, por exemplo, nota fiscal complementar, nota fiscal de ressarcimento,
transferências de créditos e outros casos.
Não podem ser informados para um mesmo documento fiscal dois ou mais registros com o mesmo conteúdo no
campo NUM_ITEM.
IMPORTANTE: para documentos de entrada, os campos de valor de imposto, base de cálculo e alíquota só devem ser
informados se o adquirente tiver direito à apropriação do crédito (enfoque do declarante).
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C170" C 004 - O O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - O O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O O
04 DESCR_COMPL Descrição complementar do item como adotado C - - OC OC
no documento fiscal
05 QTD Quantidade do item N - 05 O O
06 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O O
07 VL_ITEM Valor total do item (mercadorias ou serviços) N - 02 O O
08 VL_DESC Valor do desconto comercial N - 02 OC OC
09 IND_MOV Movimentação física do ITEM/PRODUTO: C 001* - O O
0. SIM
1. NÃO
10 CST_ICMS Código da Situação Tributária referente ao N 003* - O O
ICMS, conforme a Tabela indicada no item 4.3.1
11 CFOP Código Fiscal de Operação e Prestação N 004* - O O
12 COD_NAT Código da natureza da operação (campo 02 do C 010 - OC OC
Registro 0400)
13 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 OC OC
14 ALIQ_ICMS Alíquota do ICMS N 006 02 OC OC
15 VL_ICMS Valor do ICMS creditado/debitado N - 02 OC OC
16 VL_BC_ICMS_ST Valor da base de cálculo referente à substituição N - 02 OC OC
tributária
17 ALIQ_ST Alíquota do ICMS da substituição tributária na N - 02 OC OC
unidade da federação de destino
18 VL_ICMS_ST Valor do ICMS referente à substituição tributária N - 02 OC OC
19 IND_APUR Indicador de período de apuração do IPI: C 001* - OC OC
0 - Mensal;
1 - Decendial
20 CST_IPI Código da Situação Tributária referente ao IPI, C 002* - OC OC
conforme a Tabela indicada no item 4.3.2.
21 COD_ENQ Código de enquadramento legal do IPI, conforme C 003* - OC OC
tabela indicada no item 4.5.3.
22 VL_BC_IPI Valor da base de cálculo do IPI N - 02 OC OC
23 ALIQ_IPI Alíquota do IPI N 006 02 OC OC
24 VL_IPI Valor do IPI creditado/debitado N - 02 OC OC
25 CST_PIS Código da Situação Tributária referente ao PIS. N 002* - OC OC
26 VL_BC_PIS Valor da base de cálculo do PIS N 02 OC OC
27 ALIQ_PIS Alíquota do PIS (em percentual) N 008 04 OC OC
28 QUANT_BC_PIS Quantidade – Base de cálculo PIS N 03 OC OC
29 ALIQ_PIS Alíquota do PIS (em reais) N 04 OC OC
30 VL_PIS Valor do PIS N - 02 OC OC
31 CST_COFINS Código da Situação Tributária referente ao N 002* - OC OC
COFINS.
32 VL_BC_COFINS Valor da base de cálculo da COFINS N 02 OC OC
33 ALIQ_COFINS Alíquota do COFINS (em percentual) N 008 04 OC OC
34 QUANT_BC_COFINS Quantidade – Base de cálculo COFINS N 03 OC OC
35 ALIQ_COFINS Alíquota da COFINS (em reais) N 04 OC OC
36 VL_COFINS Valor da COFINS N - 02 OC OC
37 COD_CTA Código da conta analítica contábil C - - OC OC
debitada/creditada
Observações:
Nível hierárquico - 3
Ocorrência - 1:N (um ou vários por registro C100)
Página 46 de 209

--- Página 47 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 01 - Valor Válido: [C170]
Campo 02 - Validação: deve iniciar com “1” e incrementada de “1”.
Campo 03 - Validação: o valor informado neste campo deve existir no registro 0200. Atentar para a premissa de que a
informação deve ser prestada pela ótica do contribuinte, ou seja, nas operações de entradas de mercadorias, os códigos
informados devem ser os definidos pelo próprio informante e não aqueles constantes do documento fiscal.
Campo 05 - Preenchimento: informar a quantidade do item expressa na unidade informada no campo UNID.
Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 06 - Preenchimento: informar a unidade de medida de comercialização do item utilizada no documento fiscal.
Validação: o valor informado neste campo deve existir no registro 0190.
Campo 07 - Preenchimento: informar o valor total do item/produto, somente o valor das mercadorias (equivalente à
quantidade vezes preço unitário) ou do serviço.
Validação: a soma de valores dos registros C170 deve ser igual ao valor informado no campo VL_MERC do registro
C100.
Campo 08 - Preenchimento: informar o valor do desconto comercial, ou seja, os descontos incondicionais constantes do
próprio documento fiscal.
Campo 09 - Valores válidos: [0, 1]
Preenchimento: indicar a movimentação física do item ou produto. Será informado o código “1” em todas as situações em
que não houver movimentação de mercadorias, por exemplo: notas fiscais complementares, simples faturamento, remessas
simbólicas, etc.
Campo 10 – Preenchimento: o campo deverá ser preenchido com o código da Situação Tributária sob o enfoque do
declarante. Ex.1 - Aquisição de mercadorias tributadas para uso e consumo (cid:4) informar código “90” da tabela B. Ex. 2 -
Aquisição de mercadorias para comercialização com ICMS retido por ST (cid:4) informar código “60” da tabela B. Nas
operações de aquisição de produtos de empresas do Simples Nacional, deverá ser indicado o CST_ICMS definido pelo
Convênio S/N de 1970.
Para os estabelecimentos informantes da EFD-ICMS/IPI, optantes pelo Simples Nacional e que recolham o ICMS por este
regime, na escrituração de documentos fiscais de saída deverá ser utilizada a Tabela B do CSOSN e na escrituração dos
documentos fiscais de entrada, informar o CST_ICMS sob o enfoque do declarante.
Até 30-06-2012, nas operações de entradas (documentos de terceiros), poderá ser informado o CST que constar no
documento fiscal de aquisição dos produtos.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, constante do
Artigo 5º do Convênio SN/70 e/ou Ajuste SINIEF nº 03/2010.
Outras regras a serem executadas somente nas operações de saídas:
ICMS Normal:
a) se os dois últimos dígitos deste campo forem iguais a 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 20, 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero).
ICMS ST:
a) se os dois últimos caracteres deste campo forem 10, 30 ou 70, os valores dos campos VL_BC_ST, ALIQ_ST
e VL_ICMS_ST deverão ser maiores ou iguais a “0” (zero).
b) se os dois últimos caracteres deste campo forem diferentes de 10, 30 ou 70, os valores dos campos
VL_BC_ST, ALIQ_ST e VL_ICMS_ST deverão ser iguais a “0” (zero).
Campo 11 - Preenchimento: nas operações de entradas, devem ser registrados os códigos de operação que correspondem
ao tratamento tributário relativo à destinação do item.
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme Ajuste
SINIEF 07/01.
Página 47 de 209

--- Página 48 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Se o campo IND_OPER do registro C100 for igual a “0” (zero), então o primeiro caractere do CFOP deve ser igual a 1, 2
ou 3. Se campo IND_OPER do registro C100 for igual a “1” (um), então o primeiro caractere do CFOP deve ser igual a 5,
6 ou 7.
O primeiro caractere deve ser o mesmo para todos os itens de um documento fiscal.
Campo 12 - Validação: o valor informado no campo deve existir no registro 0400 -Tabela de Natureza da Operação.
Campo 14 - Validação: nas operações de saídas, se os dois últimos caracteres do CST_ICMS forem 00, 10, 20 ou 70, o
campo ALIQ_ICMS deve ser maior que “0” (zero).
Campo 19 - Valores válidos: [0, 1]
Preenchimento: informar o período de apuração do IPI (0-Mensal ou 1-Decendial). Este campo servirá para identificar
quais documentos serão considerados em cada apuração do IPI para períodos distintos no mesmo mês, nos casos em que
um mesmo contribuinte esteja submetido simultaneamente a mais de uma apuração.
Campo 20 - Preenchimento: O campo deverá ser preenchido somente se o declarante for contribuinte do IPI. A tabela do
CST_IPI consta publicada na Instrução Normativa RFB nº 932, de 14/04/2009. A partir de 01 de abril de 2010, IN RFB nº
1009, de 10 de fevereiro de 2010.
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
Campo 21 - Não preencher.
Campo 22 - Preenchimento: O frete e despesas acessórias, quando destacados no documento fiscal, devem ser rateados
por item de mercadoria e compõem a base de cálculo do IPI.
Campo 23 - Preenchimento: preencher com a alíquota do IPI estabelecida na TIPI e NÃO preencher, quando a forma de
tributação do IPI for fixada em reais e calculada por unidade ou por determinada quantidade de produto.
Campo 24 - Preenchimento: Deverão ser destacados e informados neste campo todos os débitos e/ou créditos de IPI da
operação. Esses valores serão totalizados para o registro C190, na combinação de CST_ICMS + CFOP + ALIQ_ICMS,
bem como, comparados com o total informado no registro C100.
Campo 25 - Validação: o valor deve constar da Tabela de Código da Situação Tributária referente ao PIS, constante da
Instrução Normativa RFB nº 932, de 14/04/2009.
Obs.: Nos casos de regime cumulativo na apuração do PIS ou COFINS os campos 25 a 36 podem ser informados como
campos de conteúdo VAZIO, ou seja, “||”.Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período
de apuração do registro 0000 estão dispensados do preenchimento dos campos 25 a 36. Apresentar conteúdo VAZIO “||”.
Código Descrição
01 Operação Tributável (base de cálculo = valor da operação alíquota normal (cumulativo/não cumulativo)).
02 Operação Tributável (base de cálculo = valor da operação (alíquota diferenciada)).
03 Operação Tributável (base de cálculo = quantidade vendida x alíquota por unidade de produto).
04 Operação Tributável (tributação monofásica (alíquota zero)).
06 Operação Tributável (alíquota zero).
07 Operação Isenta da Contribuição.
08 Operação Sem Incidência da Contribuição.
09 Operação com Suspensão da Contribuição.
Página 48 de 209

--- Página 49 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
99 Outras Operações.
A partir de 01 de abril de 2010, Instrução Normativa RFB nº 1009, de 10 de fevereiro de 2010.
Código Descrição
01 Operação Tributável com Alíquota Básica
02 Operação Tributável com Alíquota Diferenciada
03 Operação Tributável com Alíquota por Unidade de Medida de Produto
04 Operação Tributável Monofásica - Revenda a Alíquota Zero
05 Operação Tributável por Substituição Tributária
06 Operação Tributável a Alíquota Zero
07 Operação Isenta da Contribuição
08 Operação sem Incidência da Contribuição
09 Operação com Suspensão da Contribuição
49 Outras Operações de Saída
50 Operação com Direito a Crédito - Vinculada Exclusivamente a Receita Tributada no Mercado Interno
51 Operação com Direito a Crédito – Vinculada Exclusivamente a Receita Não Tributada no Mercado Interno
52 Operação com Direito a Crédito - Vinculada Exclusivamente a Receita de Exportação
53 Operação com Direito a Crédito - Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno
54 Operação com Direito a Crédito - Vinculada a Receitas Tributadas no Mercado Interno e de Exportação
55 Operação com Direito a Crédito - Vinculada a Receitas Não-Tributadas no Mercado Interno e de Exportação
56 Operação com Direito a Crédito - Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno, e de Exportação
60 Crédito Presumido - Operação de Aquisição Vinculada Exclusivamente a Receita Tributada no Mercado Interno
61 Crédito Presumido - Operação de Aquisição Vinculada Exclusivamente a Receita Não-Tributada no Mercado Interno
62 Crédito Presumido - Operação de Aquisição Vinculada Exclusivamente a Receita de Exportação
63 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno
64 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Tributadas no Mercado Interno e de Exportação
65 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Não-Tributadas no Mercado Interno e de Exportação
66 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno, e de Exportação
67 Crédito Presumido - Outras Operações
70 Operação de Aquisição sem Direito a Crédito
71 Operação de Aquisição com Isenção
72 Operação de Aquisição com Suspensão
73 Operação de Aquisição a Alíquota Zero
74 Operação de Aquisição sem Incidência da Contribuição
75 Operação de Aquisição por Substituição Tributária
98 Outras Operações de Entrada
99 Outras Operações
Campo 28 - Preenchimento: Neste campo deverá ser informada a quantidade de produtos vendidos na unidade de
tributação prevista na legislação.
De acordo com a legislação em vigor em fevereiro de 2009, a apuração das contribuições sociais, com base de
cálculo determinada sobre a quantidade de produtos vendidos, alcança:
1. As receitas decorrentes da venda e da produção sob encomenda de embalagens para bebidas (refrigerantes,
cervejas e águas, classificadas nas posições 22.01, 22.02 e 22.03 da TIPI) pelas pessoas jurídicas industriais ou comerciais
e pelos importadores, conforme disposto no art. 51 da Lei nº 10.833/03;
2. As receitas decorrentes da venda de bebidas frias (refrigerantes, cervejas e águas, classificadas nas posições
22.01, 22.02 e 22.03 da TIPI) e preparações compostas classificadas no código 2106.90.10, ex 02, da TIPI, pelas pessoas
jurídicas industriais e pelos importadores, conforme disposto no art. 52 da Lei nº 10.833/03 (fatos geradores até
31.12.2008) e pela Lei nº 10.865/04;
3. As receitas decorrentes da venda de bebidas frias (refrigerantes, cervejas e águas, classificadas nas posições
22.01, 22.02 e 22.03 da TIPI) e preparações compostas classificadas no código 2106.90.10, ex 02, da TIPI, pelas pessoas
jurídicas industriais e pelos importadores, conforme disposto nos arts. 58-A a 58-U2 da Lei nº 10.833/03, incluídos pela lei
nº 11.727 (fatos geradores a partir de 01.01.2009) e pela Lei nº 10.865/04;
4. As receitas decorrentes da venda de gasolinas e suas correntes, exceto gasolina de aviação, de óleo diesel e
suas correntes, de gás liquefeito de petróleo - GLP, derivado de petróleo e de gás natura e de querosene de aviação,
pelas pessoas jurídicas industriais e pelos importadores, conforme disposto no art. 23 da Lei nº 10.865/04 e pela Lei nº
10.865/04.
Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro 0000 estão
dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 31 - Validação: o valor deve constar da Tabela de Código da Situação Tributária referente ao COFINS, constante
da Instrução Normativa RFB nº 932, de 14/04/2009.
Código Descrição
Página 49 de 209

--- Página 50 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
01 Operação Tributável (base de cálculo = valor da operação alíquota normal (cumulativo/não cumulativo)).
02 Operação Tributável (base de cálculo = valor da operação (alíquota diferenciada)).
03 Operação Tributável (base de cálculo = quantidade vendida x alíquota por unidade de produto).
04 Operação Tributável (tributação monofásica (alíquota zero)).
06 Operação Tributável (alíquota zero).
07 Operação Isenta da Contribuição.
08 Operação Sem Incidência da Contribuição.
09 Operação com Suspensão da Contribuição.
99 Outras Operações.
A partir de 01 de abril de 2010, Instrução Normativa RFB nº 1009, de 10 de fevereiro de 2010.
Código Descrição
01 Operação Tributável com Alíquota Básica
02 Operação Tributável com Alíquota Diferenciada
03 Operação Tributável com Alíquota por Unidade de Medida de Produto
04 Operação Tributável Monofásica - Revenda a Alíquota Zero
05 Operação Tributável por Substituição Tributária
06 Operação Tributável a Alíquota Zero
07 Operação Isenta da Contribuição
08 Operação sem Incidência da Contribuição
09 Operação com Suspensão da Contribuição
49 Outras Operações de Saída
50 Operação com Direito a Crédito - Vinculada Exclusivamente a Receita Tributada no Mercado Interno
51 Operação com Direito a Crédito - Vinculada Exclusivamente a Receita Não-Tributada no Mercado Interno
52 Operação com Direito a Crédito - Vinculada Exclusivamente a Receita de Exportação
53 Operação com Direito a Crédito - Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno
54 Operação com Direito a Crédito - Vinculada a Receitas Tributadas no Mercado Interno e de Exportação
55 Operação com Direito a Crédito - Vinculada a Receitas Não Tributadas no Mercado Interno e de Exportação
56 Operação com Direito a Crédito - Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno e de Exportação
60 Crédito Presumido - Operação de Aquisição Vinculada Exclusivamente a Receita Tributada no Mercado Interno
61 Crédito Presumido - Operação de Aquisição Vinculada Exclusivamente a Receita Não-Tributada no Mercado Interno
62 Crédito Presumido - Operação de Aquisição Vinculada Exclusivamente a Receita de Exportação
63 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno
64 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Tributadas no Mercado Interno e de Exportação
65 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Não-Tributadas no Mercado Interno e de Exportação
66 Crédito Presumido - Operação de Aquisição Vinculada a Receitas Tributadas e Não-Tributadas no Mercado Interno e de Exportação
67 Crédito Presumido - Outras Operações
70 Operação de Aquisição sem Direito a Crédito
71 Operação de Aquisição com Isenção
72 Operação de Aquisição com Suspensão
73 Operação de Aquisição a Alíquota Zero
74 Operação de Aquisição sem Incidência da Contribuição
75 Operação de Aquisição por Substituição Tributária
98 Outras Operações de Entrada
99 Outras Operações
Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro 0000 estão
dispensados do preenchimento deste campo. Ou seja, deverá ser apresentados com conteúdo VAZIO “||”.
Campo 34 - Preenchimento: Idem campo 28.
Campo 37 - Preenchimento: informar o Código da Conta Analítica. Exemplos: estoques, receitas, despesas, ativos. Deve
ser a conta credora ou devedora principal, podendo ser informada a conta sintética (nível acima da conta analítica).
REGISTRO C171: ARMAZENAMENTO DE COMBUSTIVEIS (código 01, 55).
Este registro deve ser apresentado pelas empresas do comércio varejista de combustíveis, somente nas operações
de entrada, para informar o volume recebido (em litros), por item do documento fiscal, conforme Livro de Movimentação
de Combustíveis (LMC), Ajuste SINIEF 01/92.
Não podem ser informados para um mesmo documento fiscal, dois ou mais registros com o mesmo conteúdo no
campo NUM_TANQUE.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C171" C 004 - O não
02 NUM_TANQUE Tanque onde foi armazenado o combustível C 003 - O apresentar
03 QTDE Quantidade ou volume armazenado N - 03 O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Página 50 de 209

--- Página 51 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 01 - Valor Válido: [C171]
Campo 03 - Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO C172: OPERAÇÕES COM ISSQN (CÓDIGO 01)
Este registro tem por objetivo informar dados da prestação de serviços.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C172" C 004 - Não O
02 VL_BC_ISSQN Valor da base de cálculo do ISSQN N - 02 apresentar O
03 ALIQ_ISSQN Alíquota do ISSQN N 006 02 O
04 VL_ISSQN Valor do ISSQN N - 02 O
Observações:
Nível hierárquico - 4
Ocorrência - 1:1
Campo 01 - Valor Válido: [C172]
REGISTRO C173: OPERAÇÕES COM MEDICAMENTOS (CÓDIGO 01 e 55).
Este registro deve ser apresentado pelas empresas do segmento farmacêutico (distribuidoras, indústrias,
revendedoras e importadoras), exceto comércio varejista.
A obrigatoriedade deriva do §26 do art. 19 do Convênio S/N de 1970:
“Nova redação dada ao § 26 pelo Ajuste 07/04, efeitos a partir de 01.01.05.
§ 26. A Nota Fiscal emitida por fabricante, importador ou distribuidor, relativamente à saída para estabelecimento
atacadista ou varejista, dos produtos classificados nos códigos 3002, 3003, 3004 e 3006.60 da Nomenclatura Brasileira de
Mercadoria/Sistema Harmonizado - NBM/SH, exceto se relativa às operações com produtos veterinários, homeopáticos ou
amostras grátis, deverá conter, na descrição prevista na alínea “b” do inciso IV deste artigo, a indicação do valor
correspondente ao preço constante da tabela, sugerido pelo órgão competente para venda a consumidor e, na falta deste
preço, o valor correspondente ao preço máximo de venda a consumidor sugerido ao público pelo estabelecimento
industrial.”
Em caso de NF-e emitida por terceiros, a informação é obrigatória, desde que não seja destinado a comércio
varejista.
Não podem ser informados, para um mesmo item do documento fiscal (reg. C170), dois ou mais registros com a
mesma combinação de valores dos campos: LOTE_MED e QTD_ITEM.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C173" C 004 - O O
02 LOTE_MED Número do lote de fabricação do medicamento C - - O O
03 QTD_ITEM Quantidade de item por lote N - 003 O O
04 DT_FAB Data de fabricação do medicamento N 008* - O O
05 DT_VAL Data de expiração da validade do medicamento N 008* - O O
06 IND_MED Indicador de tipo de referência da base de cálculo C 001* - O O
do ICMS (ST) do produto farmacêutico:
0- Base de cálculo referente ao preço tabelado ou
preço máximo sugerido;
1- Base cálculo – Margem de valor agregado;
2- Base de cálculo referente à Lista Negativa;
3- Base de cálculo referente à Lista Positiva;
4- Base de cálculo referente à Lista Neutra
07 TP_PROD Tipo de produto: C 1* - O O
0- Similar;
1- Genérico;
2- Ético ou de marca;
08 VL_TAB_MAX Valor do preço tabelado ou valor do preço N - 02 O O
máximo
Observações:
Nível hierárquico - 4
Página 51 de 209

--- Página 52 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Ocorrência - 1:N
Campo 01 - Valor Válido: [C173]
Campo 04 - Preenchimento: informar a data de fabricação do medicamento no formato “ddmmaaaa”.
Campo 05 - Preenchimento: informar a data de expiração da validade do medicamento no formato “ddmmaaaa”.
Campo 06 - Valores válidos: [0, 1, 2, 3, 4]
Campo 07 - Valores válidos: [0, 1, 2] O código 2 é utilizado quando o tipo de produto for medicamento de referência.
Campo 08 - Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO C174: OPERAÇÕES COM ARMAS DE FOGO (CÓDIGO 01).
Este registro deve ser apresentado pelas empresas que realizam operações com armas de fogo (indústria, comércio
e demais) e deve ser fornecido apenas para operações de saída.
Não podem ser informados para um mesmo documento fiscal, dois ou mais registros com o mesmo valor do
campo NUM_ARM.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C174" C 004 - Não O
02 IND_ARM Indicador do tipo da arma de fogo: C 001* - apresentar O
0- Uso permitido;
1- Uso restrito
03 NUM_ARM Numeração de série de fabricação da arma C - - O
04 DESCR_COMPL Descrição da arma, compreendendo: número do C - - O
cano, calibre, marca, capacidade de cartuchos,
tipo de funcionamento, quantidade de canos,
comprimento, tipo de alma, quantidade e sentido
das raias e demais elementos que permitam sua
perfeita identificação
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C174]
Campo 02 - Valores válidos: [0, 1]
REGISTRO C175: OPERAÇÕES COM VEÍCULOS NOVOS (CÓDIGO 01 e 55).
Este registro deve ser apresentado pelas empresas do segmento automotivo (montadoras-capítulo 87 da NCM,
concessionárias e importadoras) para informar os itens relativos aos veículos novos. Deve ser informado nas operações de
entrada e saída (exceto pelos contribuintes emissores de NF-e), exceto quando se tratar de operações de exportação.
É considerada faturamento direto toda operação efetuada nos termos do Convênio ICMS nº 51/2000.
Não podem ser informados, para um mesmo registro C175, dois ou mais registros com o mesmo valor do campo
CHASSI_VEIC.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C175" C 004 - O O
02 IND_VEIC_OPER Indicador do tipo de operação com veículo: C 001* - O O
0- Venda para concessionária;
1- Faturamento direto;
2- Venda direta;
3- Venda da concessionária;
9- Outros
03 CNPJ CNPJ da Concessionária N 014* - OC OC
04 UF Sigla da unidade da federação da Concessionária C 002* - OC OC
05 CHASSI_VEIC Chassi do veículo C 017 - O O
Página 52 de 209

--- Página 53 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C175]
Campo 02 - Valores válidos: [0, 1, 2, 3, 9]
Campo 03 - Preenchimento: informar o CNPJ da concessionária envolvida na operação. Não utilizar os caracteres
especiais de formatação, tais como: “.”, “/”, “-”.
Validação: se o valor no campo IND_VEIC_OPER for igual a “1” (um), o campo CNPJ é obrigatório. O dígito verificador
é validado.
Campo 04 - Validação: o valor deve ser a sigla da UF da concessionária.
REGISTRO C176: RESSARCIMENTO DE ICMS EM OPERAÇÕES COM
SUBSTITUIÇÃO TRIBUTÁRIA (CÓDIGO 01, 55).
Este registro deve ser informado quando da emissão de documento fiscal, destinado a outra unidade federada, que
ensejará futuro pedido de ressarcimento de ICMS, em operações com produtos submetidos à substituição tributária na
operação anterior. Aplica-se somente aos contribuintes domiciliados nos estados, cuja legislação obriga a emissão de nota
fiscal para documentar processo de pedido de ressarcimento de ICMS/ST.
O documento informado neste registro deverá ser diferente do documento informado no registro pai (C100), pois é
o documento referente à última aquisição da mercadoria.
Este registro não se aplica a contribuintes que utilizam o SCANC.
Nº Campo Descrição Tipo Tam Dec Entr. Saída
01 REG Texto fixo contendo "C176” C 004 - Não O
02 COD_MOD_ULT_E Código do modelo do documento fiscal relativa a C 002* - aprese O
última entrada ntar
03 NUM_DOC_ULT_E Número do documento fiscal relativa a última N 009 - O
entrada
04 SER_ULT_E Série do documento fiscal relativa a última C 003 - OC
entrada
05 DT_ULT_E Data relativa a última entrada da mercadoria N 008* - O
06 COD_PART_ULT_E Código do participante (do emitente do C 060 - O
documento relativa a última entrada)
07 QUANT_ULT_E Quantidade do item relativa a última entrada N - 03 O
08 VL_UNIT_ULT_E Valor unitário da mercadoria constante na NF N - 03 O
relativa a última entrada inclusive despesas
acessórias.
09 VL_UNIT_BC_ST Valor unitário da base de cálculo do imposto N - 03 O
pago por substituição.
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C176]
Campo 02 - Valores Válidos: [01, 55]
Campo 03 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Validação: o valor informado deve ser no formato “ddmmaaaa”. O valor informado no campo deve ser menor
ou igual ao valor no Campo10 (DT_DOC) do registro C100.
Campo 06 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Página 53 de 209

--- Página 54 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
REGISTRO C177: OPERAÇÕES COM PRODUTOS SUJEITOS A SELO DE
CONTROLE IPI.
Este registro tem por objetivo informar o tipo e a quantidade de selo de controle utilizada na saída dos produtos
sujeitos ao selo de controle, pelos fabricantes ou importadores desses produtos. Ex. bebidas quentes, cigarros e relógios. Se
o produto vendido está sujeito à selagem, o registro é obrigatório. O registro não deve ser informado nas operações de
aquisição de produtos.
Nº Campo Descrição Tipo Tam Dec Entr. Saída
01 REG Texto fixo contendo "C177" C 004 - Não O
02 COD_SELO_IPI Código do selo de controle do IPI, conforme C 006* - Apresentar O
Tabela 4.5.2
03 QT_SELO_IPI Quantidade de selo de controle do IPI aplicada N 012 - O
Observações:
Nível hierárquico - 4
Ocorrência - 1:1
Campo 01 - Valor Válido: [C177]
Campo 02 - Validação: o valor informado no campo deve constar da Tabela de Código do Selo de Controle do IPI.
REGISTRO C178: OPERAÇÕES COM PRODUTOS SUJEITOS À TRIBUTAÇÀO
DE IPI POR UNIDADE OU QUANTIDADE DE PRODUTO.
O registro tem por objetivo fornecer informações adicionais sobre os produtos cuja forma de tributação do IPI,
fixada em reais, seja calculada por unidade ou por determinada quantidade de produto, conforme tabelas de classes de
valores.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C178" C 004 - Não O
02 CL_ENQ Código da classe de enquadramento do IPI, C 005 - apresentar O
conforme Tabela 4.5.1.
03 VL_UNID Valor por unidade padrão de tributação N - 02 O
04 QUANT_PAD Quantidade total de produtos na unidade padrão de N - 03 O
tributação
Observações:
Nível hierárquico - 4
Ocorrência - 1:1
Campo 01 - Valor Válido: [C178]
REGISTRO C179: INFORMAÇÕES COMPLEMENTARES ST (CÓDIGO 01).
Este registro tem por objetivo informar operações que envolvam repasse, dedução e complemento de ICMS_ST nas
operações interestaduais e nas operações com substituído intermediário.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C179” C 004 - Não O
Valor da base de cálculo ST na origem/destino apresentar O
02 BC_ST_ORIG_DEST N - 02
em operações interestaduais.
Valor do ICMS-ST a repassar/deduzir em O
03 ICMS_ST_REP N - 02
operações interestaduais
Valor do ICMS-ST a complementar à UF de OC
04 ICMS_ST_COMPL N - 02
destino
Valor da BC de retenção em remessa promovida OC
05 BC_RET N - 02
por Substituído intermediário
Valor da parcela do imposto retido em remessa OC
06 ICMS_RET N’ - 02
promovida por substituído intermediário
Observações:
Nível hierárquico - 4
Ocorrência - 1:1
Campo 01 - Valor Válido: [C179]
Página 54 de 209

--- Página 55 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
REGISTRO C190: REGISTRO ANALÍTICO DO DOCUMENTO (CÓDIGO 01, 1B, 04,
55 e 65).
Este registro tem por objetivo representar a escrituração dos documentos fiscais totalizados por CST, CFOP e
Alíquota de ICMS.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos: CST_ICMS, CFOP e ALIQ_ICMS. A combinação dos valores dos campos CST_ICMS, CFOP e ALIQ_ICMS
devem existir no respectivo registro de itens do C170, quando este registro for exigido.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C190" C 004 - O O
02 CST_ICMS Código da Situação Tributária, conforme a Tabela N 003* - O O
indicada no item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação do N 004* - O O
agrupamento de itens
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC OC
05 VL_OPR Valor da operação na combinação de CST_ICMS, N - 02 O O
CFOP e alíquota do ICMS, correspondente ao
somatório do valor das mercadorias, despesas
acessórias (frete, seguros e outras despesas
acessórias), ICMS_ST e IPI.
06 VL_BC_ICMS Parcela correspondente ao "Valor da base de N - 02 O O
cálculo do ICMS" referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
07 VL_ICMS Parcela correspondente ao "Valor do ICMS" N - 02 O O
referente à combinação de CST_ICMS, CFOP e
alíquota do ICMS.
08 VL_BC_ICMS_ST Parcela correspondente ao "Valor da base de N - 02 O O
cálculo do ICMS" da substituição tributária
referente à combinação de CST_ICMS, CFOP e
alíquota do ICMS.
09 VL_ICMS_ST Parcela correspondente ao valor N - 02 O O
creditado/debitado do ICMS da substituição
tributária, referente à combinação de CST_ICMS,
CFOP, e alíquota do ICMS.
10 VL_RED_BC Valor não tributado em função da redução da base N - 02 O O
de cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
11 VL_IPI Parcela correspondente ao "Valor do IPI" N - 02 O O
referente à combinação CST_ICMS, CFOP e
alíquota do ICMS.
12 COD_OBS Código da observação do lançamento fiscal C 006 - OC OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C190]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS,
constante do Artigo 5º do Convênio SN/70.
Campo 03 - Preenchimento: nas operações de entradas, devem ser registrados os códigos de operação que correspondem
ao tratamento tributário relativo à destinação do item.
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme Ajuste
SINIEF 07/01. Para Notas Fiscais Eletrônicas ao Consumidor Final (NFC-e) só poderão ser informados CFOP iniciados
com 5.
Página 55 de 209

--- Página 56 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 05 - Preenchimento: Na combinação de CST_ICMS, CFOP e ALIQ_ICMS, informar neste campo o valor das
mercadorias somadas aos valores de fretes, seguros e outras despesas acessórias e os valores de ICMS_ST e IPI (somente
quando o IPI está destacado na NF), subtraído o desconto incondicional.
Validação: O somatório dos valores deste campo deve, em princípio, corresponder ao valor total do documento informado
no registro C100. Na ocorrência de divergência entre os valores será emitida uma “Advertência” pelo PVA-EFD-ICMS/IPI,
o que não impedirá a assinatura e transmissão do arquivo.
Campo 06 - Preenchimento: informar a base de cálculo do ICMS, referente à combinação dos campos CST_ICMS, CFOP
e ALIQ_ICMS deste registro.
Validação: o valor constante neste campo deve corresponder à soma dos valores do Campo VL_BC_ICMS dos registros
C170 (itens), se existirem, que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 07 - Preenchimento: informar o valor do ICMS referente à combinação dos campos CST_ICMS, CFOP e
ALIQ_ICMS deste registro.
Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS do registro C170
(itens), se existirem, que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 08 - Preenchimento: informar a base de cálculo do ICMS-ST referente à combinação dos campos CST_ICMS,
CFOP e ALIQ_ICMS deste registro.
Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_BC_ICMS ST do registro
C170 (itens), se existirem, que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 09 - Preenchimento: informar o valor creditado/debitado do ICMS da substituição tributária, referente à
combinação dos campos CST_ICMS, CFOP, e ALIQ_ICMS deste registro.
Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS ST do registro C170
(itens), se existirem, que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 10 - Preenchimento: informar o valor não tributado em função da redução da base de cálculo do ICMS, referente
à combinação dos campos CST_ICMS, CFOP e ALIQ_ICMS deste registro.
Validação:. Quando o campo COD_SIT do registro mestre for igual a “00” ou “01” então o campo VL_RED_BC deve ser
maior que zero se o 2º e 3º caracteres do CST_ICMS forem iguais a 20 ou 70.
Campo 11 - Preenchimento: informar o valor do IPI referente à combinação dos campos CST_ICMS, CFOP e
ALIQ_ICMS deste registro.
Campo 12 - Preenchimento: este campo só deve ser informado pelos contribuintes localizados em UF que determine em
sua legislação o seu preenchimento.
Validação: o código informado deve constar do registro 0460.
REGISTRO C195: OBSERVAÇOES DO LANÇAMENTO FISCAL (CÓDIGO 01, 1B,
04 E 55)
Este registro deve ser informado quando, em decorrência da legislação estadual, houver ajustes nos documentos
fiscais, informações sobre diferencial de alíquota, antecipação de imposto e outras situações.
Estas informações equivalem às observações que são lançadas na coluna “Observações” dos Livros Fiscais
previstos no Convênio SN/70 – SINIEF, art. 63, I a IV.
Sempre que existir um ajuste (lançamentos referentes aos impostos que têm o cálculo detalhado em Informações
Complementares da NF; ou aos impostos que estão definidos na legislação e não constam na NF; ou aos recolhimentos
antecipados dos impostos), deve, conforme dispuser a legislação estadual, ocorrer uma observação.
Obs.: Não precisam ser informadas neste registro, salvo disposição contrária da legislação estadual, as informações que
constam do quadro Dados Adicionais das notas fiscais modelo 1 ou 1A e que não interferem na Apuração do ICMS.
Situação especial: Este registro será gerado também pelas empresas que são obrigadas a elaborar outras apurações nos
estados do Espírito Santo, Pará e Amazonas.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C195" C 004 - O O
02 COD_OBS Código da observação do lançamento fiscal (campo C 006 - O O
02 do Registro 0460)
03 TXT_COMPL Descrição complementar do código de observação. C - - OC OC
Observações:
Página 56 de 209

--- Página 57 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C195]
Campo 02 – Preenchimento: as observações de lançamento devem ser informadas neste campo, exceto quando a
legislação estadual prever o preenchimento do campo COD_OBS do registro C190.
Validação: o código informado deve constar do registro 0460.
Campo 03 - Preenchimento: utilizado para complementar observação, cujo código é de informação genérica.
REGISTRO C197: OUTRAS OBRIGAÇÕES TRIBUTÁRIAS, AJUSTES E
INFORMAÇÕES DE VALORES PROVENIENTES DE DOCUMENTO FISCAL.
Este registro tem por objetivo detalhar outras obrigações tributárias, ajustes e informações de valores do
documento fiscal do registro C195, que podem ou não alterar o cálculo do valor do imposto.
Os valores de ICMS ou ICMS ST (campo 07-VL_ICMS) serão somados diretamente na apuração, no registro
E110 – Apuração do ICMS – Operações Próprias, campo VL_AJ_DEBITOS ou campo VL_AJ_CREDITOS, e no registro
E210 – Apuração do ICMS – Substituição Tributária, campo VL_AJ_CREDITOS_ST e campo VL_AJ_DEBITOS_ST, de
acordo com a especificação do TERCEIRO CARACTERE do Código do Ajuste (Tabela 5.3 do Ato COTEPE/ICMS nº 09,
de 18 de abril de 2008 = Tabela de Ajustes e Valores provenientes do Documento Fiscal).
Obs.: Este registro será utilizado ainda por contribuinte onde a Administração Tributária Estadual exige, por meio
de legislação específica, apuração em separado (sub-apuração). Neste caso o Estado publicará a Tabela 5.3 com códigos
que contenham os dígitos “3”, “4”, “5”, “6”, “7” e “8” no quarto caractere (“Tipos de Apuração de ICMS”), sendo que cada
um dos dígitos possibilitará a escrituração de uma apuração em separado (sub-apuração) no registro 1900 e filhos. Para que
haja a apuração em separado do ICMS de determinadas operações ou itens de mercadorias, estes valores terão de ser
estornados da Apuração Normal (E110) e transferidos para as sub-apurações constantes do registro 1900 e filhos por meio
de lançamentos de ajustes neste registro. Isto ocorrerá quando:
1. o terceiro caractere do código de ajuste (tabela 5.3) do reg. C197 for igual a “2 – Estorno de
Débito” e o dígito do quarto caractere for igual a “3”; “4” , “5”, “6”, “7” e “8”. Neste caso o valor
informado no campo 07 - VL_ICMS irá gerar um ajuste a crédito (campo 07- VL_AJ_CREDITOS)
no registro E110 e também um outro lançamento a débito no registro 1920 (campo 02 -
VL_TOT_TRANSF_DEBITOS_OA) da apuração em separado (sub-apuração) definida no campo
02- IND_APUR_ICMS do registro 1900 por meio dos códigos “3”, “4”, “5”, “6”, “7” e “8”, que
deverá coincidir com o quarto caractere do COD_AJ; e
2. o terceiro caractere do código de ajuste (tabela 5.3) do reg. C197 for igual a “5 – Estorno de
Crédito” e o dígito do quarto caractere for igual a “3”; “4”, “5”, “6”, “7” e “8”. Neste caso o valor
informado no campo 07 - VL_ICMS irá gerar um ajuste a débito (campo 03- VL_AJ_DEBITOS) no
registro E110 e também um outro lançamento a crédito no registro 1920 (campo 05 -
VL_TOT_TRANSF_CRÉDITOS_OA) da apuração em separado (sub-apuração) que for definida no
campo 02 - IND_APUR_ICMS do registro 1900 por meio dos códigos “3”, “4” “5”, “6”, “7” e “8”,
que deverá coincidir com o quarto caractere do COD_AJ.
Os valores que gerarem crédito ou débito de ICMS (ou seja, aqueles que não são simplesmente informativos) serão
somados na apuração, assim como os registros C190.
Este registro só deve ser informado para as UF que publicarem a tabela constante no item 5.3 do Ato
COTEPE/ICMS nº 09, de 18 de abril de 2008 – Tabela de Ajustes e Valores provenientes do Documento Fiscal.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C197" C 004 - O O
02 COD_AJ Código do ajustes/benefício/incentivo, conforme C 010* - O O
tabela indicada no item 5.3.
03 DESCR_COMPL_AJ Descrição complementar do ajuste do documento C - - OC OC
fiscal
04 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - OC OC
05 VL_BC_ICMS Base de cálculo do ICMS ou do ICMS ST N - 02 OC OC
06 ALIQ_ICMS Alíquota do ICMS N 006 02 OC OC
07 VL_ICMS Valor do ICMS ou do ICMS ST N - 02 OC OC
08 VL_OUTROS Outros valores N - 02 OC OC
Página 57 de 209

--- Página 58 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C197]
Campo 02 - Validação: verifica se o COD_AJ está de acordo com a Tabela da UF do informante do arquivo.
Campo 04 - Preenchimento: deve ser informado se o ajuste/benefício for relacionado ao produto. Porém, quando não
houver registro C170, como NF-e de emissão própria, o COD_ITEM deverá ser informado no registro 0200.
Campo 07 - Preenchimento: valor do montante do ajuste do imposto. Para ajustes referentes a ICMS-ST, o campo
VL_ICMS deve conter o valor do ICMS-ST. Os dados que gerarem crédito ou débito (ou seja, aqueles que não são
simplesmente informativos) serão somados na apuração, assim como os registros C190.
Campo 08 - Preenchimento: preencher com outros valores, quando o código do ajuste for informativo, conforme Tabela
5.3 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
REGISTRO C300: RESUMO DIÁRIO DAS NOTAS FISCAIS DE VENDA A
CONSUMIDOR (CÓDIGO 02)
Este registro deve ser apresentado pelos contribuintes que utilizam notas fiscais de venda ao consumidor, não
emitidas por ECF. Trata-se de um resumo diário, por série e subsérie do documento fiscal, de todas as operações praticadas.
Existirão tantos registros C300 quantos forem os agrupamentos de séries e subséries dos documentos fiscais emitidos no
dia. Os valores de documentos fiscais cancelados não devem ser computados no valor total dos documentos (campo
VL_DOC).
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos SER, SUB, NUM_DOC_INI e NUM_DOC_FIN. Não é permitida a intersecção (sobreposição) de intervalos entre
os registros C300 informados com a mesma combinação de valores dos campos SER, SUB, NUM_DOC_INI e
NUM_DOC_FIN.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C300" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, conforme C 002* - apresentar O
a Tabela 4.1.1
03 SER Série do documento fiscal C 004 - O
04 SUB Subsérie do documento fiscal C 003 - OC
05 NUM_DOC_INI Número do documento fiscal inicial N 006 - O
06 NUM_DOC_FIN Número do documento fiscal final N 006 - O
07 DT_DOC Data da emissão dos documentos fiscais N 008* - O
08 VL_DOC Valor total dos documentos N - 02 O
09 VL_PIS Valor total do PIS N - 02 OC
10 VL_COFINS Valor total da COFINS N - 02 OC
11 COD_CTA Código da conta analítica contábil C - - OC
debitada/creditada
Observações:
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [C300]
Campo 02 - Valor Válido: [02] - – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 05 - Validação: valor informado deve ser maior que “0” (zero). O número do documento inicial deve ser menor
ou igual ao número do documento final.
Campo 06 - Validação: valor informado deve ser maior que “0” (zero).
Página 58 de 209

--- Página 59 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 07 - Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro
0000.
Campo 08 - Validação: o valor informado no campo deve ser igual à soma do campo VL_ITEM dos registros C321.
Campo 09 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 10 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C310: DOCUMENTOS CANCELADOS DE NOTAS FISCAIS DE
VENDA A CONSUMIDOR (CÓDIGO 02).
Este registro tem por objetivo informar os números dos documentos fiscais cancelados.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C310" C 004 - Não O
02 NUM_DOC_CANC Número do documento fiscal cancelado N - - apresentar O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [C310]
Campo 02 - Validação: o número do documento cancelado deve estar contido no intervalo informado no registro C300,
campos NUM_DOC_INI e NUM_DOC_FIN.
REGISTRO C320: REGISTRO ANALÍTICO DO RESUMO DIÁRIO DAS NOTAS
FISCAIS DE VENDA A CONSUMIDOR (CÓDIGO 02).
Este registro tem por objetivo informar a consolidação diária dos valores das notas fiscais de venda ao
consumidor, não emitidas por ECF, e deve ser apresentado de forma agrupada na combinação CST_ICMS, CFOP e
Alíquota de ICMS.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C320" C 004 - Não O
02 CST_ICMS Código da Situação Tributária, conforme a N 003* - apresentar O
Tabela indicada no item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação N 004* - O
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
05 VL_OPR Valor total acumulado das operações N - 02 O
correspondentes à combinação de CST_ICMS,
CFOP e alíquota do ICMS, incluídas as despesas
acessórias e acréscimos.
06 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS, N - 02 O
referente à combinação de CST_ICMS, CFOP, e
alíquota do ICMS.
07 VL_ICMS Valor acumulado do ICMS, referente à N - 02 O
combinação de CST_ICMS, CFOP e alíquota do
ICMS.
08 VL_RED_BC Valor não tributado em função da redução da N - 02 O
base de cálculo do ICMS, referente à combinação
de CST_ICMS, CFOP, e alíquota do ICMS.
09 COD_OBS Código da observação do lançamento fiscal C 006 - OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [C320]
Página 59 de 209

--- Página 60 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 02 - Validação: o valor informado neste campo deve existir na Tabela da Situação Tributária referente ao ICMS,
constante do Artigo 5º do Convênio SN/70, sendo que o primeiro caractere sempre será Zero.
Campo 03 – Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01. Não podem ser utilizados os títulos dos agrupamentos de CFOP.
Campo 06 - Validação: deve ser igual à soma do campo VL_BC_ICMS do registro C321.
Campo 07 - Validação: deve ser igual à soma do campo VL_ICMS do registro C321.
REGISTRO C321: ITENS DO RESUMO DIÁRIO DOS DOCUMENTOS (CÓDIGO
02).
Este registro é o detalhamento, por itens de mercadoria, da consolidação diária dos valores das notas fiscais de
venda ao consumidor, não emitidas por ECF.
Validação do Registro: não podem ser informados dois ou mais registros C321 com o mesmo valor para o campo
COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C321" C 004 - Não O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - apresentar O
03 QTD Quantidade acumulada do item N - 03 O
04 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
05 VL_ITEM Valor acumulado do item N - 02 O
06 VL_DESC Valor do desconto acumulado N - 02 OC
07 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 OC
08 VL_ICMS Valor acumulado do ICMS debitado N - 02 OC
09 VL_PIS Valor acumulado do PIS N - 02 OC
10 VL_COFINS Valor acumulado da COFINS N - 02 OC
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C321]
Campo 05 - Preenchimento: valor líquido acumulado do item, já considerado o valor do desconto incondicional.
Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 06 - Preenchimento: informar o valor do desconto acumulado. Valor meramente informativo.
Campo 09 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 10 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C350: NOTA FISCAL DE VENDA A CONSUMIDOR (CÓDIGO 02)
Este registro deve ser apresentado pelos contribuintes que utilizam notas fiscais de venda ao consumidor, não
emitidas por ECF. As notas fiscais canceladas não devem ser informadas.
Obs.: Os CNPJ e CPF citados neste registro NÃO devem ser informados no registro 0150.
Nº Campo Descrição Tipo Tam Dec Entr. Saída
01 REG Texto fixo contendo "C350" C 004 - Não O
02 SER Série do documento fiscal C 003 - apresen OC
03 SUB_SER Subsérie do documento fiscal C 003 - tar OC
04 NUM_DOC Número do documento fiscal N 006 - O
05 DT_DOC Data da emissão do documento fiscal N 008 - O
06 CNPJ_CPF CNPJ ou CPF do destinatário N 014 - OC
Página 60 de 209

--- Página 61 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
VL_MERC Valor das mercadorias constantes no documento N - 02
07 O
fiscal
08 VL_DOC Valor total do documento fiscal N - 02 O
09 VL_DESC Valor total do desconto N - 02 OC
10 VL_PIS Valor total do PIS N - 02 OC
11 VL_COFINS Valor total da COFINS N - 02 OC
COD_CTA Código da conta analítica contábil C - - OC
12
debitada/creditada
Observações:
Nível hierárquico - 2
Ocorrência – vários (por arquivo)
Campo 01 - Valor Válido: [C350]
Campo 05 - Preenchimento: o valor informado deve ser no formato “ddmmaaaa”.
Campo 06 - Validação: se forem informados 14 caracteres, o campo será validado como CNPJ. Se forem informados 11
caracteres, o campo será validado como CPF.
Campo 10 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 11 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo.
REGISTRO C370: ITENS DO DOCUMENTO (CÓDIGO 02)
Este registro é o detalhamento por itens das notas fiscais de venda ao consumidor, modelo 2.
A chave deste registro é formada pelos campos NUM_ITEM e COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Entr. Saída
01 REG Texto fixo contendo "C370" C 004 - Não O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - apresentar O
03 COD_ITEM Código do Item (campo 02 do registro 0200) C 060 - O
04 QTD Quantidade do item N - 3 O
05 UNID Unidade do item (campo 02 do registro 0190) C 006 - O
06 VL_ITEM Valor total do item N - 2 O
07 VL_DESC Valor total do desconto no item N - 2 OC
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [C370]
Campo 02 - Validação: deve iniciar com “1” e incrementada de “1”.
Campo 03 - Validação: o valor informado neste campo deve existir no registro 0200.
Campo 05 - Validação: o valor informado neste campo deve existir no registro 0190.
REGISTRO C390: REGISTRO ANALÍTICO DAS NOTAS FISCAIS DE VENDA A
CONSUMIDOR (CÓDIGO 02)
Este registro tem por objetivo informar as notas fiscais de venda ao consumidor, não emitidas por ECF, e deve ser
apresentado de forma agrupada na combinação CST_ICMS, CFOP e Alíquota de ICMS.
Nº Campo Descrição Tipo Tam Dec Entr. Saída
01 REG Texto fixo contendo "C390" C 004 - Não O
Página 61 de 209

--- Página 62 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
02 CST_ICMS Código da Situação Tributária, conforme a Tabela N 003* - apresentar O
indicada no item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação N 004* - O
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
05 VL_OPR Valor total acumulado das operações correspondentes à N - 02 O
combinação de CST_ICMS, CFOP e alíquota do
ICMS, incluídas as despesas acessórias e acréscimos.
06 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS, N - 02 OC
referente à combinação de CST_ICMS, CFOP, e
alíquota do ICMS.
07 VL_ICMS Valor acumulado do ICMS, referente à combinação de N - 02 OC
CST_ICMS, CFOP e alíquota do ICMS.
08 VL_RED_BC Valor não tributado em função da redução da base de N - 02 OC
cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP, e alíquota do ICMS.
09 COD_OBS Código da observação do lançamento fiscal (campo 02 C 006 - OC
do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [C390]
Campo 02 - Validação: o valor informado neste campo deve existir na Tabela da Situação Tributária referente ao ICMS,
constante do Artigo 5º do Convênio SN/70, sendo que o primeiro caractere sempre será Zero.
Campo 03 – Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01. Não podem ser utilizados os títulos dos agrupamentos de CFOP.
REGISTRO C400: EQUIPAMENTO ECF (CÓDIGO 02, 2D e 60).
Este registro tem por objetivo identificar os equipamentos de ECF e deve ser informado por todos os contribuintes
que utilizem tais equipamentos na emissão de documentos fiscais.
Validação do Registro: não podem ser informados dois ou mais registros C400 com a mesma combinação de valores dos
campos COD_MOD, ECF_MOD e ECF_FAB.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C400" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, C 002* - apresentar O
conforme a Tabela 4.1.1
03 ECF_MOD Modelo do equipamento C 020 - O
04 ECF_FAB Número de série de fabricação do ECF C 021 - O
05 ECF_CX Número do caixa atribuído ao ECF N 003 - O
Observações:
Nível hierárquico - 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [C400]
Campo 02 - Valores válidos: [02, 2D, 60] - – Ver tabela reproduzida na subseção 6.4 deste guia..
Campo 05 - Preenchimento: informar o número do caixa atribuído, pelo estabelecimento, ao equipamento emissor de
documento fiscal. Um mesmo valor do campo ECF_CX não pode ser usado por dois equipamentos ECF ao mesmo tempo.
Contudo, se o uso de um número for cessado, este mesmo número pode ser atribuído a outro equipamento de ECF, no
período.
Página 62 de 209

--- Página 63 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
REGISTRO C405: REDUÇÃO Z (CÓDIGO 02, 2D e 60).
Este registro deve ser apresentado com as informações da Redução Z de cada equipamento em funcionamento na
data das operações de venda à qual se refere a redução. Inclui todos os documentos fiscais totalizados na Redução Z,
inclusive as operações de venda realizadas durante o período de tolerância do Equipamento ECF.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C405" C 004 - Não O
02 DT_DOC Data do movimento a que se refere a Redução Z N 008* - apresentar O
03 CRO Posição do Contador de Reinício de Operação N 003 - O
04 CRZ Posição do Contador de Redução Z N 006 - O
05 NUM_COO_FIN Número do Contador de Ordem de Operação do N 009 - O
último documento emitido no dia. (Número do
COO na Redução Z)
06 GT_FIN Valor do Grande Total final N - 02 O
07 VL_BRT Valor da venda bruta N - 02 O
Observações: No caso de intervenção técnica no ECF, deve ser informado um registro para cada redução Z emitida.
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 - Valor Válido: [C405]
Campo 02 - Preenchimento: considerar a data do movimento, que inclui as operações de vendas realizadas durante o
período de tolerância do equipamento ECF.
Validação: o valor informado deve ser menor ou igual à DT_FIN deste arquivo.
Campo 03 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 04 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 05 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 06 - Preenchimento: valor acumulado no totalizador geral final.
Validação: o campo GT_FIN deve ser maior ou igual ao campo VL_BRT, exceto se houver reinício de operação. Quando
o GT_FIN for menor que o VL_BRT será exibida mensagem de “Advertência”.
Campo 07 - Preenchimento: valor acumulado no totalizador de venda bruta. Se o valor da venda bruta for igual a “0”
(zero), não devem ser apresentados registros filhos e o registro C490.
Validação: deve ser igual ao somatório do campo VLR_ACUM_TOT do registro C420 para os valores informados no
campo COD_TOT_PAR do registro C420, exceto "AT" (Acréscimo – ICMS), "AS" (Acréscimo – ISSQN), “OPNF”
(Operações não fiscais), “DO” (Desconto Operações não fiscais), “AO” (Acréscimo de operações não fiscais), “Can-O”
(Cancelamento de operações não fiscais) e “IOF” (Imposto Sobre Operações Financeiras).
REGISTRO C410: PIS E COFINS TOTALIZADOS NO DIA (CÓDIGO 02 e 2D).
Este registro deve ser apresentado sempre que houver produtos totalizados na Redução Z que acarretem valores de
PIS e COFINS a serem informados. Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de
apuração do registro 0000 estão dispensados do preenchimento deste registro.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C410" C 004 - Não O
02 VL_PIS Valor total do PIS N - 02 apresentar OC
03 VL_COFINS Valor total da COFINS N - 02 OC
Observações:
Nível hierárquico - 4
Ocorrência - 1:1
Campo 01 - Valor Válido: [C410]
Página 63 de 209

--- Página 64 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
REGISTRO C420: REGISTRO DOS TOTALIZADORES PARCIAIS DA REDUÇÃO Z
(COD 02, 2D e 60).
Este registro tem por objetivo discriminar os valores por código de totalizador da Redução Z.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_TOT_PAR e NR_TOT.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C420" C 004 - Não O
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
Ocorrência - 1:N
Campo 01 - Valor Válido: [C420]
Campo 02 - Preenchimento: informar o código de totalizador parcial da Redução Z, que deve existir na Tabela 4.4.6 do
Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, prevista também na subseção 6.6 deste guia. Deverão ser informados
todos os totalizadores parciais da Redução Z, que foram movimentados no dia.
Para totalizadores tributáveis pelo ICMS, o conteúdo deste campo deve ser “Tnnnn” ou “xxTnnnn”, onde “nnnn”
corresponde à alíquota informada no campo ALIQ_ICMS do registro C490. Caso o equipamento ECF seja autorizado a
emitir cupom fiscal com serviço tributado pelo município (ISS), os totalizadores desse serviço também deverão ser
informados nesse campo cujo conteúdo será Snnnn ou xxSnnnn, onde "nnnn" representa a carga tributária efetiva do
imposto com duas casas decimais.
Validação: o valor informado deve existir na Tabela 4.4.6 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008, que
discrimina os códigos dos Totalizadores Parciais da REDUÇÃO Z.
Campo 03 - Preenchimento: informar o valor acumulado no totalizador (venda líquida) da situação tributária/alíquota.
Validação: o valor deste campo deve ser igual à soma dos campos VL_OPER dos registros C490, para os totalizadores
tributáveis pelo ICMS e/ou ISS, indicado pelo campo COD_TOT_PAR com valor igual a “xxTnnnn” , “Tnnnn”, xxSnnnn
e Snnnn..
Se o declarante estiver enquadrado no Perfil B, o conteúdo deste campo deve ser igual à soma do campo VL_ITEM dos
registros C425.
Para os totalizadores Can-T, Can-S e Can-O, não informar o registro C490.
Campo 04 - Validação: o valor “xx”, do formato “xxTnnnn” ou “xxSnnnn, conforme Convênio 80/07, para código de
totalizador tributável pelo ICMS e/ou ISS, deve ser informado no campo NR_TOT deste registro. Da mesma forma, este
campo deve ser preenchido quando ocorrer cargas tributárias efetivas idênticas. Existindo apenas um totalizador, deixar o
campo vazio. O valor informado deve ser maior que “0” (zero). Ex: T1700 com NR_TOT igual a “1”(carga tributária de
17%); T1700 com NR_TOT igual a 2 (carga tributária efetiva de 17% decorrente de redução de base de cálculo).
Campo 05 - Validação: Só deve ser informado, se o campo NR_TOT estiver preenchido.
REGISTRO C425: RESUMO DE ITENS DO MOVIMENTO DIÁRIO (CÓDIGO 02 e 2D).
Este registro tem por objetivo identificar os produtos comercializados na data da movimentação relativa à Redução
Z informada, sendo obrigatório, quando os totalizadores forem iguais a xxTnnnn, Tnnnn, Fn, In, Nn.
Validação do Registro: não podem ser informados dois ou mais registros com o mesmo valor para o campo COD_ITEM
para cada C420.
É obrigatória a apresentação deste registro, se o valor no campo COD_TOT_PAR do registro C420 for Tnnnn, xxTnnnn,
Fn, In ou Nn.
Página 64 de 209

--- Página 65 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C425" C 004 - Não O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - apresentar O
03 QTD Quantidade acumulada do item N - 03 O
04 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
05 VL_ITEM Valor acumulado do item N - 02 O
06 VL_PIS Valor do PIS N - 02 OC
07 VL_COFINS Valor da COFINS N - 02 OC
Observações:
Nível hierárquico - 5
Ocorrência - 1:N
Campo 01 - Valor Válido: [C425]
Campo 03 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 04 - Validação: o valor deve ser informado no registro 0190.
Campo 05 - Validação: o valor informado no campo deve ser maior que “0” (zero) e corresponder ao somatório dos
valores líquidos de cada produto.
Campo 06 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 07 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C460: DOCUMENTO FISCAL EMITIDO POR ECF (CÓDIGO 02, 2D e
60).
Este registro deve ser apresentado para a identificação dos documentos fiscais emitidos pelos usuários de
equipamentos ECF, que foram totalizados na Redução Z.
Para cupom fiscal cancelado, informar somente os campos COD_MOD, COD_SIT e NUM_DOC, sem os
registros filhos.
Obs.: Os CNPJ e CPF citados neste registro NÃO devem ser informados no registro 0150.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_MOD, NUM_DOC e DT_DOC.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C460" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, C 002* - apresentar O
conforme a Tabela 4.1.1
03 COD_SIT Código da situação do documento fiscal, N 002* - O
conforme a Tabela 4.1.2
04 NUM_DOC Número do documento fiscal (COO) N 009 - O
05 DT_DOC Data da emissão do documento fiscal N 008* - O
06 VL_DOC Valor total do documento fiscal N - 02 O
07 VL_PIS Valor do PIS N - 02 OC
08 VL_COFINS Valor da COFINS N - 02 OC
09 CPF_CNPJ CPF ou CNPJ do adquirente N 014 - OC
10 NOM_ADQ Nome do adquirente C 060 - OC
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C460]
Campo 02 - Valores Válidos: [02, 2D, 60] - – Ver tabela reproduzida na subseção 6.4 deste guia.
Página 65 de 209

--- Página 66 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 03 - Valores Válidos: [00, 01, 02]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3.
Validação: se o valor neste campo for igual a 02, informar somente os campos REG, COD_MOD, NUM_DOC, e não deve
ser apresentado o registro C470.
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Preenchimento: em casos excepcionais, conforme Convênio 85/01, a data de emissão do documento fiscal
pode ser imediatamente posterior à data de movimentação relativa à Redução Z, em decorrência do período de duas horas
de tolerância dos equipamentos de ECF.
Campo 06 - Validação: o valor informado deve ser maior que “0” (zero). O valor informado deve ser igual à soma do
campo VL_ITEM dos registros C470.
Campo 07 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 08 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 09 - Preenchimento: informar o CNPJ, com 14 dígitos, ou o CPF, com 11 dígitos, do adquirente.
Validação: se forem informados 14 caracteres, o campo será validado como CNPJ. Se forem informados 11 caracteres, o
campo será validado como CPF. O preenchimento com outra quantidade de caracteres será considerado inválido.
REGISTRO C465: COMPLEMENTO DO CUPOM FISCAL ELETRÔNICO
EMITIDO POR ECF – CF-e-ECF (CÓDIGO 60).
Este registro deve ser apresentado para a identificação adicional dos cupons fiscais eletrônicos emitidos pelos
usuários de equipamentos ECF, que foram totalizados na Redução Z.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C465" C 004 - Não O
02 CHV_CFE Chave do Cupom Fiscal Eletrônico N 044 - apresentar O
03 NUM_CCF Número do Contador de Cupom Fiscal N 009 - O
Observações:
Nível hierárquico - 5
Ocorrência - 1:1
Campo 01 - Valor Válido: [C465]
Campo 02 - Validação: é conferido o dígito verificador (DV) da chave do Cupom Fiscal Eletrônico.
Campo 03 – Validação: campo deve ser maior que zero.
REGISTRO C470: ITENS DO DOCUMENTO FISCAL EMITIDO POR ECF (CÓDIGO
02 e 2D).
Este registro deve ser apresentado para informar os itens dos documentos fiscais emitidos pelos usuários de
equipamentos ECF, que foram totalizados na Redução Z. O serviço de competência municipal (sujeito ao ISSQN) também
deverá ser informado nesse registro. Para tanto, deverá ser criado o correspondente item no registro 0200, cujo conteúdo do
campo TIPO_ITEM será igual “09” (Serviços). Não informar o registro para o item cuja venda foi totalmente cancelada.
Não informar este registro no caso de Cupom Fiscal Eletrônico emitido por ECF - CF-e-ECF (Código 60).
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C470" C 004 - Não O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - apresentar O
03 QTD Quantidade do item N - 03 O
Página 66 de 209

--- Página 67 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
04 QTD_CANC Quantidade cancelada, no caso de cancelamento N - 03 OC
parcial de item
05 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
06 VL_ITEM Valor total do item N - 02 O
07 CST_ICMS Código da Situação Tributária, conforme a N 003* - O
Tabela indicada no item 4.3.1.
08 CFOP Código Fiscal de Operação e Prestação N 004* - O
09 ALIQ_ICMS Alíquota do ICMS – Carga tributária efetiva em N 006 02 OC
percentual
10 VL_PIS Valor do PIS N - 02 OC
11 VL_COFINS Valor da COFINS N - 02 OC
Observações:
Nível hierárquico - 5
Ocorrência - 1:N
Campo 01 - Valor Válido: [C470]
Campo 03 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 04 - Validação: o valor do campo deve ser menor que o valor do campo QTD.
Campo 05 - Validação: o valor deve ser informado no registro 0190.
Campo 06 - Validação: o valor informado deve ser maior que “0” (zero) e corresponder ao valor líquido do item no
cupom.
Campo 07 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária do ICMS referenciada
no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 08 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01. O código CFOP deve iniciar-se por “5”.
Campo 09 – Preenchimento: informar a carga tributária efetiva em percentual com dois decimais.
Campo 10 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 11 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C490: REGISTRO ANALÍTICO DO MOVIMENTO DIÁRIO (CÓDIGO 02,
2D e 60).
Este registro tem por objetivo representar a escrituração dos documentos fiscais emitidos por ECF e totalizados pela
combinação de CST, CFOP e Alíquota. Não informar este registro para os totalizadores Can-T, Can-S e Can-O informados
no C420.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores
dos campos CST_ICMS, CFOP e ALIQ_ICMS. A combinação CST_ICMS, CFOP e ALIQ_ICMS deve existir no
respectivo registro de itens do C470, quando este registro for exigido.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C490" C 004 - Não O
02 CST_ICMS Código da Situação Tributária, conforme a N 003* - apresentar O
Tabela indicada no item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação N 004* - O
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
05 VL_OPR Valor da operação correspondente à combinação N - 02 O
de CST_ICMS, CFOP, e alíquota do ICMS,
incluídas as despesas acessórias e acréscimos
Página 67 de 209

--- Página 68 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
06 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS, N - 02 O
referente à combinação de CST_ICMS, CFOP, e
alíquota do ICMS.
07 VL_ICMS Valor acumulado do ICMS, referente à N - 02 O
combinação de CST_ICMS, CFOP e alíquota do
ICMS.
08 COD_OBS Código da observação do lançamento fiscal C 006 - OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C490]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária do ICMS, referenciada
no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
ICMS Normal:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero);
Campo 03 – Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01. O código CFOP deve iniciar-se por “5”.
Campo 04 – Preenchimento: informar a carga tributária efetiva da operação.
Campo 05 - Preenchimento: valor líquido da operação, incluídas as despesas acessórias e acréscimos, excluídos os
descontos incondicionais.
Campo 06 - Validação: se o campo IND_PERFIL do registro 0000 for igual a “A”, o valor deste campo deve ser igual à
soma do campo VL_ITEM dos registros C470 que possuam a mesma combinação de valores para os campos CST_ICMS,
CFOP e ALIQ_ICMS deste registro.
Campo 07 - Validação: O valor do ICMS corresponde ao resultado da multiplicação da carga tributária efetiva pelo valor
da base de cálculo.
REGISTRO C495: RESUMO MENSAL DE ITENS DO ECF POR
ESTABELECIMENTO (CÓDIGO 02 e 2D).
Este registro deve ser apresentado pelo contribuinte domiciliado no estado da Bahia até 31/12/2013, resumindo
todas as informações num único registro por item de mercadorias, não dispensando a apresentação do registro C400 e
registros filhos. A partir de 01/01/2014, os contribuintes situados na Bahia não apresentam este registro e devem apresentar
o registro C425.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_ITEM e ALIQ_ICMS.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C495" C 004 - Não O
02 ALIQ_ICMS Alíquota do ICMS N 006 02 apresentar OC
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 QTD Quantidade acumulada do item N - 03 O
05 QTD_CANC Quantidade cancelada acumulada, no caso de N - 03 OC
cancelamento parcial de item
06 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
07 VL_ITEM Valor acumulado do item N - 02 O
08 VL_DESC Valor acumulado dos descontos N - 02 OC
09 VL_CANC Valor acumulado dos cancelamentos N - 02 OC
Página 68 de 209

--- Página 69 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
10 VL_ACMO Valor acumulado dos acréscimos N - 02 OC
11 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 OC
12 VL_ICMS Valor acumulado do ICMS N - 02 OC
13 VL_ISEN Valor das saídas isentas do ICMS N - 02 OC
14 VL_NT Valor das saídas sob não-incidência ou não- N - 02 OC
tributadas pelo ICMS
15 VL_ICMS_ST Valor das saídas de mercadorias adquiridas com N - 02 OC
substituição tributária do ICMS
Observações:
Nível hierárquico - 2
Ocorrência - vários
Campo 01 - Valor Válido: [C495]
Campo 02 – Preenchimento: informar a carga tributária efetiva da operação.
Campo 03 - Validação: o valor informado no campo deve existir no registro 0200, Campo COD_ITEM.
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Preenchimento: informar a quantidade acumulada cancelada, no caso de cancelamento parcial de item.
Campo 06 - Validação: o valor deve ser informado no registro 0190.
Campo 07 - Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO C500: NOTA FISCAL/CONTA DE ENERGIA ELÉTRICA (CÓDIGO 06),
NOTA FISCAL/CONTA DE FORNECIMENTO D'ÁGUA CANALIZADA
(CÓDIGO 29) E NOTA FISCAL CONSUMO FORNECIMENTO DE GÁS
(CÓDIGO 28).
Este registro deve ser apresentado, nas operações de saída, pelos contribuintes do segmento de energia elétrica e
não obrigadas ao Convênio ICMS 115/03, pelos contribuintes do segmento de fornecimento de gás e, nas operações de
entrada, por todos os contribuintes adquirentes.
IMPORTANTE: para documentos de entrada, os campos de valor de imposto, base de cálculo e alíquota só
devem ser informados se o adquirente tiver direito à apropriação do crédito (enfoque do declarante).
Nas emissões de documentos para cada registro C500, obrigatoriamente devem ser apresentados, pelo menos, um registro
C510 e um registro C590, observadas as exceções abaixo relacionadas:
Exceção 1: Para documentos com código de situação (campo COD_SIT) cancelado (código “02”) ou cancelado
extemporâneo (código “03”), preencher somente os campos REG, IND_OPER, IND_EMIT, COD_MOD, COD_SIT, SER,
NUM_DOC e DT_DOC. Demais campos deverão ser apresentados com conteúdo VAZIO “||”. Para esse documento não
poderá ser apresentado nenhum registro “filho”.
Exceção 2: Notas Fiscais Complementares e Notas Fiscais Complementares Extemporâneas (campo COD_SIT igual a
“06” ou “07”): nesta situação, somente os campos (do registro C500) REG, IND_OPER, IND_EMIT, COD_PART,
COD_MOD, COD_SIT, SER, NUM_DOC e DT_DOC são obrigatórios. Os demais campos são facultativos (se forem
preenchidos, serão validados e aplicadas as regras de campos existentes). O registro C590 é obrigatório e deverá ser
observada a obrigatoriedade de preenchimento de todos os campos. Os demais campos e registros filhos do registro C500
deverão ser informados, se existirem.
Exceção 3: Notas Fiscais emitidas por regime especial ou norma específica (campo COD_SIT igual a “08”). Para
documentos fiscais emitidos com base em regime especial ou norma específica, deverão ser apresentados os registros C500
e C590, obrigatoriamente, e os demais registros “filhos”, se estes forem exigidos pela legislação fiscal. Nesta situação,
somente os campos (do registro C500) REG, IND_OPER, IND_EMIT, COD_PART, COD_MOD, COD_SIT, SER,
NUM_DOC e DT_DOC são obrigatórios. Os demais campos são facultativos (se forem preenchidos, serão validados e
aplicadas as regras de campos existentes). No registro C590, exceto o campo ALIQ_ICMS que é facultativo, preencher os
demais campos obrigatoriamente.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos IND_OPER, IND_EMIT, COD_PART, SER, SUB, NUM_DOC e DT_DOC.
Página 69 de 209

--- Página 70 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C500" C 004 - O O
02 IND_OPER Indicador do tipo de operação: C 001* - O O
0- Entrada;
1- Saída
03 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O O
0- Emissão própria;
1- Terceiros
04 COD_PART Código do participante (campo 02 do Registro C 060 - O O
0150):
- do adquirente, no caso das saídas;
- do fornecedor no caso de entradas
05 COD_MOD Código do modelo do documento fiscal, C 002* - O O
conforme a Tabela 4.1.1
06 COD_SIT Código da situação do documento fiscal, N 002* - O O
conforme a Tabela 4.1.2
07 SER Série do documento fiscal C 004 - OC OC
08 SUB Subsérie do documento fiscal N 003 - OC OC
09 COD_CONS - Código de classe de consumo de energia C 002* - OC O
elétrica ou gás:
01 - Comercial
02 - Consumo Próprio
03 - Iluminação Pública
04 - Industrial
05 - Poder Público
06 - Residencial
07 - Rural
08 -Serviço Público.
- Código de classe de consumo de Fornecimento
D´água – Tabela 4.4.2.
10 NUM_DOC Número do documento fiscal N 009 - O O
11 DT_DOC Data da emissão do documento fiscal N 008* - O O
12 DT_E_S Data da entrada ou da saída N 008* - O O
13 VL_DOC Valor total do documento fiscal N - 02 O O
14 VL_DESC Valor total do desconto N - 02 OC OC
15 VL_FORN Valor total fornecido/consumido N - 02 O O
16 VL_SERV_NT Valor total dos serviços não-tributados pelo N - 02 OC OC
ICMS
17 VL_TERC Valor total cobrado em nome de terceiros N - 02 OC OC
18 VL_DA Valor total de despesas acessórias indicadas no N - 02 OC OC
documento fiscal
19 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 OC OC
20 VL_ICMS Valor acumulado do ICMS N - 02 OC OC
21 VL_BC_ICMS_ST Valor acumulado da base de cálculo do ICMS N - 02 OC OC
substituição tributária
22 VL_ICMS_ST Valor acumulado do ICMS retido por N - 02 OC OC
substituição tributária
23 COD_INF Código da informação complementar do C 006 - OC OC
documento fiscal (campo 02 do Registro 0450)
24 VL_PIS Valor do PIS N - 02 OC OC
25 VL_COFINS Valor da COFINS N - 02 OC OC
26 TP_LIGACAO Código de tipo de Ligação N 001* - OC OC
1 - Monofásico
2 - Bifásico
3 - Trifásico
27 COD_GRUPO_TENSAO Código de grupo de tensão: C 002* - OC OC
01 - A1 - Alta Tensão (230kV ou mais)
02 - A2 - Alta Tensão (88 a 138kV)
03 - A3 - Alta Tensão (69kV)
04 - A3a - Alta Tensão (30kV a 44kV)
05 - A4 - Alta Tensão (2,3kV a 25kV)
Página 70 de 209

--- Página 71 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
06 - AS - Alta Tensão Subterrâneo 06
07 - B1 - Residencial 07
08 - B1 - Residencial Baixa Renda 08
09 - B2 - Rural 09
10 - B2 - Cooperativa de Eletrificação Rural
11 - B2 - Serviço Público de Irrigação
12 - B3 - Demais Classes
13 - B4a - Iluminação Pública - rede de
distribuição
14 - B4b - Iluminação Pública - bulbo de
lâmpada
Observações: registro obrigatório nas operações de saídas, apenas para documentos emitidos fora do Convênio ICMS nº
115/2003, ou quando dispensados pela SEFAZ da entrega do arquivo previsto naquele convênio.
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [C500]
Campo 02 - Valores válidos: [0, 1]
Campo 03 - Valores válidos: [0, 1]
Campo 04 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 05 - Valores válidos: [06, 28, 29] - – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 06 - Valores válidos: [00, 01, 02, 03, 06, 07, 08]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3.
Campo 09 - Valores válidos e validação: Se o modelo for 06 (energia elétrica) ou 28 (gás canalizado), os valores válidos
são [01, 02, 03, 04, 05, 06, 07, 08]. Se o modelo for 29 (água canalizada), o valor deve constar da Tabela 4.4.2 do Ato
COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 10 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 11 - Preenchimento: data de emissão da nota fiscal no formato “ddmmaaaa”.
Validação: o valor informado no campo deve ser menor ou igual ao valor do campo DT_FIN do registro 0000.
Campo 12 - Preenchimento: data de entrada ou saída da nota fiscal no formato “ddmmaaaa”.
Campo 13 - Validação: o valor informado no campo deve ser maior ou igual a “0” (zero).
Campo 15 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Preenchimento: Informar o valor em reais referente ao fornecimento de energia elétrica.
Campo 23 - Validação: o valor informado no campo deve existir no registro 0450.
Campo 24 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 25 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 26 - Preenchimento obrigatório nas operações de saídas, se modelo igual a “06”.
Valores válidos: [1, 2, 3]
Campo 27 - Preenchimento obrigatório nas operações de saídas, se modelo igual a “06”.
Valores válidos: [01, 02, 03, 04, 05, 06, 07, 08, 09, 10, 11, 12, 13, 14]
Página 71 de 209

--- Página 72 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
REGISTRO C510: ITENS DO DOCUMENTO NOTA FISCAL/CONTA ENERGIA
ELÉTRICA (CÓDIGO 06), NOTA FISCAL/CONTA DE FORNECIMENTO
D'ÁGUA CANALIZADA (CÓDIGO 29) E NOTA FISCAL/CONTA DE
FORNECIMENTO DE GÁS (CÓDIGO 28).
Este registro deve ser apresentado para informar os itens das Notas Fiscais/Contas de Energia Elétrica (código 06
da Tabela Documentos Fiscais do ICMS), Notas Fiscais/Contas de fornecimento de água canalizada (código 29) e Notas
Fiscais Consumo Fornecimento de Gás (código 28 da Tabela Documentos Fiscais do ICMS), nas operações de saída.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores
dos campos NUM_ITEM e COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C510" C 004 - Não O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - apresentar O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 COD_CLASS Código de classificação do item de energia N 004* - OC
elétrica, conforme a Tabela 4.4.1
05 QTD Quantidade do item N - 03 OC
06 UNID Unidade do item (Campo 02 do registro 0190) C 006 - OC
07 VL_ITEM Valor do item N - 02 O
08 VL_DESC Valor total do desconto N - 02 OC
09 CST_ICMS Código da Situação Tributária, conforme a N 003* - O
Tabela indicada no item 4.3.1
10 CFOP Código Fiscal de Operação e Prestação N 004* - O
11 VL_BC_ICMS Valor da base de cálculo do ICMS N - 02 OC
12 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
13 VL_ICMS Valor do ICMS creditado/debitado N - 02 OC
14 VL_BC_ICMS_ST Valor da base de cálculo referente à substituição N - 02 OC
tributária
15 ALIQ_ST Alíquota do ICMS da substituição tributária na N 006 02 OC
unidade da federação de destino
16 VL_ICMS_ST Valor do ICMS referente à substituição tributária N - 02 OC
17 IND_REC Indicador do tipo de receita: C 001* - O
0- Receita própria;
1- Receita de terceiros
18 COD_PART Código do participante receptor da receita, C 060 OC
terceiro da operação (campo 02 do Registro
0150)
19 VL_PIS Valor do PIS N - 02 OC
20 VL_COFINS Valor da COFINS N - 02 OC
21 COD_CTA Código da conta analítica contábil C - - OC
debitada/creditada
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C510]
Campo 03 - Validação: o valor informado no campo deve existir no registro 0200, campo COD_ITEM.
Campo 04 - Validação: Somente deve ser informado se for energia elétrica e o valor informado no campo deve existir na
Tabela de Classificação de itens de Energia Elétrica, Serviços de Comunicação e Telecomunicação, constante no item 4.4.1
do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008. Para demais documentos o campo deve ser apresentado como campo
“vazio”.
Campo 06 - Validação: o valor deve estar informado no registro 0190.
Campo 07 - Preenchimento: informar o valor total do item (equivalente à quantidade vezes preço unitário).
Página 72 de 209

--- Página 73 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 09 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS,
referenciada no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
ICMS Normal:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero);
ICMS ST:
a) se os dois últimos caracteres deste campo forem 10, 30 ou 70, os valores dos campos VL_BC_ST,
ALIQ_ST e VL_ICMS_ST deverão ser maiores ou iguais “0” (zero).
se os dois últimos caracteres deste campo forem diferentes de 10, 30 ou 70, os valores dos campos VL_BC_ST, ALIQ_ST
e VL_ICMS_ST deverão ser iguais a “0” (zero).
Campo 10 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01.
Se o campo IND_OPER do registro C500 for igual a “0” (entrada), então o primeiro caractere do CFOP deve ser igual a 1,
2 ou 3. Se o campo IND_OPER do registro C500 for igual a “1” (saída), então o primeiro caractere do CFOP deve ser igual
a 5, 6 ou 7.
O primeiro caractere do CFOP deve ser o mesmo para todos os itens do documento.
Não podem ser utilizados códigos que correspondam aos títulos dos agrupamentos de CFOP (códigos com caracteres finais
00 ou 50. Por exemplo: 5100).
Campo 17 - Valores válidos: [0, 1]
Campo 18 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 19 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 20 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C590: REGISTRO ANALÍTICO DO DOCUMENTO - NOTA
FISCAL/CONTA DE ENERGIA ELÉTRICA (CÓDIGO 06), NOTA
FISCAL/CONTA DE FORNECIMENTO D'ÁGUA CANALIZADA (CÓDIGO 29)
E NOTA FISCAL CONSUMO FORNECIMENTO DE GÁS (CÓDIGO 28).
Este registro representa a escrituração dos documentos fiscais dos modelos especificados no C500, totalizados
pelo agrupamento das combinações dos valores de CST, CFOP e Alíquota dos itens de cada documento. Deve haver um
registro C590 com os totais de cada combinação de valores de CST, CFOP e Alíquota, informados nos itens dos registros
C510 (operações de saída) ou com base nos documentos fiscais de entrada.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores
dos campos CST_ICMS, CFOP e ALIQ_ICMS. A combinação CST_ICMS, CFOP e ALIQ_ICMS deve existir no
respectivo registro de itens do C510, quando este registro for exigido.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C590" C 004 - O O
02 CST_ICMS Código da Situação Tributária, conforme a Tabela N 003* - O O
indicada no item 4.3.1.
03 CFOP Código Fiscal de Operação e Prestação do N 004* - O O
agrupamento de itens
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC OC
05 VL_OPR Valor da operação correspondente à combinação N - 02 O O
de CST_ICMS, CFOP, e alíquota do ICMS.
06 VL_BC_ICMS Parcela correspondente ao "Valor da base de N - 02 OC O
cálculo do ICMS" referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
07 VL_ICMS Parcela correspondente ao "Valor do ICMS" N - 02 OC O
referente à combinação de CST_ICMS, CFOP e
alíquota do ICMS.
Página 73 de 209

--- Página 74 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
08 VL_BC_ICMS_ST Parcela correspondente ao "Valor da base de N - 02 OC O
cálculo do ICMS" da substituição tributária
referente à combinação de CST_ICMS, CFOP e
alíquota do ICMS.
09 VL_ICMS_ST Parcela correspondente ao valor N - 02 OC O
creditado/debitado do ICMS da substituição
tributária, referente à combinação de CST_ICMS,
CFOP, e alíquota do ICMS.
10 VL_RED_BC Valor não tributado em função da redução da base N - 02 OC O
de cálculo do ICMS, referente à combinação de
CST_ICMS, CFOP e alíquota do ICMS.
11 COD_OBS Código da observação do lançamento fiscal C 006 - OC OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência - 1:N (um ou vários por registro C500)
Campo 01 - Valor Válido: [C590]
Campo 02 - Preenchimento: Nos documentos fiscais de emissão própria o campo deverá ser preenchido com o código da
Situação Tributária sob o enfoque do declarante. Nas operações de entradas (documentos de terceiros), informar o CST que
constar no documento fiscal de aquisição dos produtos.
A partir julho de 2012, nas operações de aquisições de mercadorias o CST_ICMS deverá ser informado sob o enfoque do
declarante. Ex.1 - Aquisição de mercadorias tributadas para uso e consumo (cid:4) informar código “90” da tabela B. Ex. 2 -
Aquisição de mercadorias para comercialização com ICMS retido por ST (cid:4) informar código “60” da tabela B.
Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS, referenciada no
item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
ICMS Normal:
a) se os dois últimos dígitos deste campo forem 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero);
ICMS ST:
a) se os dois últimos caracteres deste campo forem 10, 30 ou 70, os valores dos campos 16 (VL_BC_ST), 17
(ALIQ_ST) e 18 (VL_ICMS_ST) deverão ser maiores ou iguais a “0” (zero).
b) se os dois últimos caracteres deste campo forem diferentes de 10, 30 ou 70, os valores dos campos 16
(VL_BC_ST), 17 (ALIQ_ST) e 18 (VL_ICMS_ST) deverão ser iguais a “0” (zero).
Campo 03 - Preenchimento: em se tratando de operações de entrada, devem ser registrados os códigos de operação que
correspondam ao tratamento tributário relativo à destinação do item.
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme Ajuste
SINIEF 07/01.
Não podem ser utilizados códigos que correspondam aos títulos dos agrupamentos de CFOP (códigos com caracteres finais
00 ou 50. Por exemplo: 5100).
Campo 05 – Preenchimento: Na combinação de CST_ICMS, CFOP e ALIQ_ICMS, informar neste campo o valor das
mercadorias somadas aos valores de outras despesas acessórias, subtraído o desconto incondicional.
Campo 06 - Validação: o valor constante neste campo deve corresponder à soma dos valores do Campo VL_BC_ICMS
dos registros C510 (itens), se existirem, que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 07 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS dos
registros C510 (itens), que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 08 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo
VL_BC_ICMS_ST dos registros C510 (itens), que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Campo 09 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS_ST dos
registros C510 (itens), que possuam a mesma combinação de CST, CFOP e Alíquota deste registro.
Página 74 de 209

--- Página 75 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 10 - Validação: este campo só pode ser preenchido, se os dois últimos dígitos do campo CST_ICMS forem iguais
a 20 ou 70.
Campo 11 - Validação: o valor informado no campo deve existir no registro 0460
REGISTRO C600: CONSOLIDAÇÃO DIÁRIA DE NOTAS FISCAIS/CONTAS DE
ENERGIA ELÉTRICA (CÓDIGO 06), NOTA FISCAL/CONTA DE
FORNECIMENTO D'ÁGUA CANALIZADA (CÓDIGO 29) E NOTA
FISCAL/CONTA DE FORNECIMENTO DE GÁS (CÓDIGO 28) (EMPRESAS
NÃO OBRIGADAS AO CONVÊNIO ICMS 115/03).
Este registro deve ser apresentado na consolidação diária de Notas Fiscais/Conta de Energia Elétrica (código 06 da
Tabela Documentos Fiscais do ICMS), Notas Fiscais de Fornecimento D’Água (código 29 da Tabela Documentos Fiscais
do ICMS) e Notas Fiscais/Conta de Fornecimento de Gás (código 28 da Tabela Documentos Fiscais do ICMS) para
empresas não obrigadas ao Convênio ICMS 115/2003.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores
dos campos COD_MOD, COD_MUN e COD_CONS. A apresentação deste registro implica a não apresentação do registro
C700 e C500.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C600" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, C 002* - apresentar O
conforme a Tabela 4.1.1
03 COD_MUN Código do município dos pontos de consumo, N 007* - O
conforme a tabela IBGE
04 SER Série do documento fiscal C 004 - OC
05 SUB Subsérie do documento fiscal N 003 - OC
06 COD_CONS - Código de classe de consumo de energia C 002* - O
elétrica ou gás:
01 - Comercial
02 - Consumo Próprio
03 - Iluminação Pública
04 - Industrial
05 - Poder Público
06 - Residencial
07 - Rural
08 -Serviço Público.
- Código de classe de consumo de Fornecimento
D´água – Tabela 4.4.2.
07 QTD_CONS Quantidade de documentos consolidados neste N - - O
registro
08 QTD_CANC Quantidade de documentos cancelados N - - OC
09 DT_DOC Data dos documentos consolidados N 008* - O
10 VL_DOC Valor total dos documentos N - 02 O
11 VL_DESC Valor acumulado dos descontos N - 02 OC
12 CONS Consumo total acumulado, em kWh (Código 06) N - - OC
13 VL_FORN Valor acumulado do fornecimento N - 02 OC
14 VL_SERV_NT Valor acumulado dos serviços não-tributados N - 02 OC
pelo ICMS
15 VL_TERC Valores cobrados em nome de terceiros N - 02 OC
16 VL_DA Valor acumulado das despesas acessórias N - 02 OC
17 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 OC
18 VL_ICMS Valor acumulado do ICMS N - 02 OC
19 VL_BC_ICMS_ST Valor acumulado da base de cálculo do ICMS N - 02 OC
substituição tributária
20 VL_ICMS_ST Valor acumulado do ICMS retido por N - 02 OC
substituição tributária
Página 75 de 209

--- Página 76 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
21 VL_PIS Valor acumulado do PIS N - 02 OC
22 VL_COFINS Valor acumulado COFINS N - 02 OC
Observações: registro obrigatório nas operações de saídas, apenas para documentos emitidos fora do Convênio ICMS nº
115/2003, ou quando dispensados pela SEFAZ da entrega do arquivo previsto naquele convênio.
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [C600]
Campo 02 - Valores válidos: [06, 28, 29] - – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 06 - Valores válidos e validação: Se o modelo for 06 (energia elétrica) ou 28 (gás canalizado), os valores válidos
são [01, 02, 03, 04, 05, 06, 07, 08]. Se o modelo for 29 (água canalizada), o valor deve constar da Tabela 4.4.2 do Ato
COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 07 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 08 - Validação: o valor deve ser menor ou igual ao valor do campo QTD_CONS, pois a quantidade de
documentos cancelados não pode ser maior que a quantidade de documentos consolidados. Este valor deve ser igual à
quantidade de ocorrências do registro C601 (documentos cancelados).
Campo 09 - Validação: o valor informado no campo deve ser menor ou igual ao valor do campo DT_FIN do registro
0000.
Campo 17 - Validação: o valor informado deve ser igual à soma do campo VL_BC_ICMS dos registros C610 (itens).
Campo 18 - Validação: o valor informado deve ser igual à soma do campo VL_ICMS dos registros C610 (itens).
Campo 19 - Validação: o valor informado deve ser igual à soma do campo VL_BC_ICMS_ST dos registros C610 (itens).
Campo 20 - Validação: o valor informado deve ser igual à soma do campo VL_ICMS_ST dos registros C610 (itens).
Campo 21 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 22 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C601: DOCUMENTOS CANCELADOS - CONSOLIDAÇÃO DIÁRIA DE
NOTAS FISCAIS/CONTAS DE ENERGIA ELÉTRICA (CÓDIGO 06), NOTA
FISCAL/CONTA DE FORNECIMENTO D'ÁGUA CANALIZADA (CÓDIGO 29)
E NOTA FISCAL/CONTA DE FORNECIMENTO DE GÁS (CÓDIGO 28)
Este registro tem por objetivo informar a numeração dos documentos cancelados da consolidação diária dos
documentos fiscais do C600.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C601" C 004 - Não O
02 NUM_DOC_CANC Número do documento fiscal cancelado N 009 - apresentar O
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C601]
Campo 02 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Página 76 de 209

--- Página 77 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
REGISTRO C610: ITENS DO DOCUMENTO CONSOLIDADO (CÓDIGO 06), NOTA
FISCAL/CONTA DE FORNECIMENTO D'ÁGUA CANALIZADA (CÓDIGO 29)
E NOTA FISCAL/CONTA DE FORNECIMENTO DE GÁS (CÓDIGO 28)
(EMPRESAS NÃO OBRIGADAS AO CONVÊNIO ICMS 115/03).
Este registro tem por objetivo discriminar por item os registros consolidados apresentados no C600.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos COD_CLASS, COD_ITEM e ALIQ_ICMS.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C610" C 004 - Não O
02 COD_CLASS Código de classificação do item de energia N 004* - apresentar OC
elétrica, conforme Tabela 4.4.1
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 QTD Quantidade acumulada do item N - 03 O
05 UNID Unidade do item (Campo 02 do registro 0190) C 006 - O
06 VL_ITEM Valor acumulado do item N - 02 O
07 VL_DESC Valor acumulado dos descontos N - 02 OC
08 CST_ICMS Código da Situação Tributária, conforme a N 003* - O
Tabela indicada no item 4.3.1
09 CFOP Código Fiscal de Operação e Prestação conforme N 004* - O
tabela indicada no item 4.2.2.
10 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
11 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS N - 02 OC
12 VL_ICMS Valor acumulado do ICMS debitado N - 02 OC
13 VL_BC_ICMS_ST Valor da base de cálculo do ICMS substituição N - 02 OC
tributária
14 VL_ICMS_ST Valor do ICMS retido por substituição tributária N - 02 OC
15 VL_PIS Valor do PIS N - 02 OC
16 VL_COFINS Valor da COFINS N - 02 OC
17 COD_CTA Código da conta analítica contábil C - - OC
debitada/creditada
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C610]
Campo 02 – Preenchimento: só deve ser preenchido no caso do campo COD_MOD do registro C600 ser igual a 06
(Energia Elétrica). Para demais modelos previstos, o campo deve ser apresentado como campo “vazio”.
Validação: Se o código de modelo de documentos for igual a “06”, então o valor informado no campo deve existir na
Tabela 4.4.1 referenciada no Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 03 - Validação: o valor informado no campo deve existir no registro 0200, campo COD_ITEM.
Campo 04 - Validação: o valor informado no campo deve ser maior que “0” (zero).
Campo 05 - Validação: o valor deve estar informado no registro 0190.
Campo 08 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS,
referenciada no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
ICMS Normal:
a) se os dois últimos dígitos deste campo forem iguais a 30, 40, 41, 50, ou 60, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser iguais a “0” (zero);
b) se os dois últimos dígitos deste campo forem diferentes de 30, 40, 41, 50, e 60, então os valores dos
campos VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores que “0” (zero);
c) se os dois últimos dígitos deste campo forem iguais a 51 ou 90, então os valores dos campos
VL_BC_ICMS, ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0” (zero);
Página 77 de 209

--- Página 78 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
ICMS ST:
a) se os dois últimos caracteres deste campo forem 10, 30 ou 70 os valores dos campos VL_BC_ST,
ALIQ_ST e VL_ICMS_ST deverão ser maiores ou iguais a “0” (zero).
b) se os dois últimos caracteres deste campo forem diferentes de 10, 30 ou 70, os valores dos campos
VL_BC_ST, ALIQ_ST e VL_ICMS_ST deverão ser iguais a “0” (zero).
Campo 09 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01.
O primeiro caractere do CFOP deve ser igual a 5, 6 ou 7.
Campo 15 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 16 - Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro
0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C690: REGISTRO ANALÍTICO DOS DOCUMENTOS (NOTAS
FISCAIS/CONTAS DE ENERGIA ELÉTRICA (CÓDIGO 06), NOTA
FISCAL/CONTA DE FORNECIMENTO D’ÁGUA CANALIZADA (CÓDIGO 29)
E NOTA FISCAL/CONTA DE FORNECIMENTO DE GÁS (CÓDIGO 28)
Este registro tem por objetivo representar a escrituração dos documentos fiscais dos modelos especificados no
C600, totalizados pelo agrupamento das combinações dos valores de CST, CFOP e Alíquota dos itens de cada registro
consolidado. Existirá um registro C690 para cada combinação de valores de CST, CFOP e Alíquota que existir nos itens
(registro C610), totalizando estes itens.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores
dos campos CST_ICMS, CFOP e ALIQ_ICMS. A combinação CST_ICMS, CFOP e ALIQ_ICMS deve existir no
respectivo registro de itens do C610, quando este registro for exigido.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C690" C 004 - Não O
02 CST_ICMS Código da Situação Tributária, conforme a tabela N 003* - apresentar O
indicada no item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação, conforme N 004* - O
a tabela indicada no item 4.2.2
04 ALIQ_ICMS Alíquota do ICMS N 006 2 OC
05 VL_OPR Valor da operação correspondente à combinação N - 2 O
de CST_ICMS, CFOP, e alíquota do ICMS.
06 VL_BC_ICMS Parcela correspondente ao "Valor da base de N - 2 O
cálculo do ICMS" referente à combinação
CST_ICMS, CFOP e alíquota do ICMS
07 VL_ICMS Parcela correspondente ao "Valor do ICMS" N - 2 O
referente à combinação CST_ICMS, CFOP e
alíquota do ICMS
08 VL_RED_BC Valor não tributado em função da redução da N - 02 O
base de cálculo do ICMS, referente à combinação
de CST_ICMS, CFOP e alíquota do ICMS.
09 VL_BC_ICMS_ST Valor da base de cálculo do ICMS substituição N - 02 O
tributária
10 VL_ICMS_ST Valor do ICMS retido por substituição tributária N - 02 O
11 COD_OBS Código da observação do lançamento fiscal C 006 - OC
(campo 02 do Registro 0460)
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C690]
Página 78 de 209

--- Página 79 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 02 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária do ICMS, referenciada
no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01.
Campo 06 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_BC_ICMS
dos registros C610 (itens), se existirem, para a mesma combinação de valores dos campos CST_ICMS, CFOP e
ALIQ_ICMS.
Campo 07 – Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS dos
registros C610 (itens), para a mesma combinação de valores dos campos CST_ICMS, CFOP e ALIQ_ICMS.
Campo 08 - Validação: o campo VL_RED_BC só pode ser preenchido se o valor do campo CST_ICMS for igual a 20 ou
70.
Campo 09 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo
VL_BC_ICMS_ST dos registros C610 (itens), para a mesma combinação de valores dos campos CST_ICMS, CFOP e
ALIQ_ICMS.
Campo 10 - Validação: o valor constante neste campo deve corresponder à soma dos valores do campo VL_ICMS_ST dos
registros C610 (itens), para a mesma combinação de valores dos campos CST_ICMS, CFOP e ALIQ_ICMS.
Campo 11 - Validação: o valor informado no campo COD_OBS deve existir no registro 0460.
REGISTRO C700: CONSOLIDAÇÃO DOS DOCUMENTOS NF/CONTA ENERGIA
ELÉTRICA (CÓD 06), EMITIDAS EM VIA ÚNICA (EMPRESAS OBRIGADAS À
ENTREGA DO ARQUIVO PREVISTO NO CONVÊNIO ICMS 115/03) E NOTA
FISCAL/CONTA DE FORNECIMENTO DE GÁS CANALIZADO (CÓDIGO 28)
Este registro deve ser apresentado com a consolidação das Notas Fiscais/Conta de Energia Elétrica (código 06 da
Tabela Documentos Fiscais do ICMS) pelas empresas obrigadas à entrega do arquivo previsto no Convênio ICMS
115/2003.
Este registro deve ser apresentado pelas empresas fornecedoras de gás canalizado domiciliadas nas unidades
federadas que utilizam o Convênio ICMS 115/2003.
Informações interestaduais devem estar englobadas na consolidação deste registro e também devem ser
informadas no registro 1500. Neste caso, as informações repetidas no 1500 terão apenas efeito declaratório, não sendo
consideradas no cálculo da apuração.
A apresentação deste registro implica a não apresentação do registro C600.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos SER, NRO_ORD_INI e NRO_ORD_FIN. Não pode haver sobreposição de intervalos para a mesma série.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C700" C 004 - Não O
Código do modelo do documento fiscal, apresentar O
02 COD_MOD C 002* -
conforme a Tabela 4.1.1
03 SER Série do documento fiscal C 004 - OC
04 NRO_ORD_INI Número de ordem inicial N 009 - O
05 NRO_ORD_FIN Número de ordem final N 009 - O
Data de emissão inicial dos documentos / Data O
06 DT_DOC_INI N 008* -
inicial de vencimento da fatura
Data de emissão final dos documentos / Data final O
07 DT_DOC_FIN N 008* -
do vencimento da fatura
08 NOM_MEST Nome do arquivo Mestre de Documento Fiscal C 015 - O
Chave de codificação digital do arquivo Mestre O
09 CHV_COD_DIG C 032 -
de Documento Fiscal
Observações:
Página 79 de 209

--- Página 80 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nível hierárquico - 2
Ocorrência – vários (por arquivo)
Campo 01 - Valor Válido: [C700]
Campo 02 - Valor Válido: [06, 28] - – Ver tabela reproduzida na subseção 6.4 deste guia.
Campo 04 - Validação: o valor informado deve ser maior que “0” (zero).
Campo 05 - Validação: o valor informado deve ser igual ou maior que o valor no campo NRO_ORD_INI.
Campo 06 - Preenchimento: informar data de emissão inicial dos documentos, formato “ddmmaaaa” ou a data inicial do
vencimento da fatura, conforme disposto na legislação estadual.
Validação: a data informada no campo deve ser maior ou igual ao valor no campo DT_INI do registro 0000. Este valor
deve ser menor ou igual ao valor do campo DT_DOC_FIN.
Campo 07 - Preenchimento: informar data de emissão final dos documentos, formato “ddmmaaaa” ou a data final do
vencimento da fatura, conforme disposto na legislação estadual.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 08 - Preenchimento: informar o nome do volume do arquivo mestre de documento fiscal, conforme item 4.5 do
Anexo Único (Manual de Orientação) do Convênio ICMS 115/2003.
Campo 09 - Preenchimento: chave de codificação digital do arquivo Mestre de Documento Fiscal, conforme Parágrafo
Único da Cláusula Segunda do Convênio ICMS 115/2003.
REGISTRO C790: REGISTRO ANALÍTICO DOS DOCUMENTOS (CÓDIGOS 06 e
28).
Este registro representa a escrituração dos documentos fiscais dos modelos especificados no C700, totalizados
pelo agrupamento das combinações dos valores de CST, CFOP e Alíquota dos itens de cada registro consolidado.
Validação do Registro: não podem ser informados dois ou mais registros com a mesma combinação de valores dos
campos CST_ICMS, CFOP e ALIQ_ICMS.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C790" C 004 - Não O
02 CST_ICMS Código da Situação Tributária, conforme a tabela N 003* - apresentar O
indicada no item 4.3.1
Código Fiscal de Operação e Prestação, conforme O
03 CFOP N 004* -
a tabela indicada no item 4.2.2
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
VL_OPR Valor da operação correspondente à combinação O
05 N - 02
de CST_ICMS, CFOP, e alíquota do ICMS.
Parcela correspondente ao "Valor da base de O
06 VL_BC_ICMS cálculo do ICMS" referente à combinação N - 02
CST_ICMS, CFOP, e alíquota do ICMS
Parcela correspondente ao "Valor do ICMS" O
07 VL_ICMS referente à combinação CST_ICMS, CFOP e N - 02
alíquota do ICMS
Valor da base de cálculo do ICMS substituição O
08 VL_BC_ICMS_ST N - 02
tributária
09 VL_ICMS_ST Valor do ICMS retido por substituição tributária N - 02 O
10 VL_RED_BC Valor não tributado em função da redução da N - 02 O
base de cálculo do ICMS, referente à combinação
de CST_ICMS, CFOP e alíquota do ICMS..
11 COD_OBS Código da observação do lançamento fiscal C 006 - OC
(campo 02 do Registro 0460)
Página 80 de 209

--- Página 81 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Observações:
Nível hierárquico - 3
Ocorrência - 1:N (um ou vários por registro C700)
Campo 01 - Valor Válido: [C790]
Campo 02 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária do ICMS, referenciada
no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 03 - Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação,
conforme Ajuste SINIEF 07/01.
Campo 10 - Validação: este campo só pode ser preenchido se os dois últimos dígitos do campo CST_ICMS forem iguais a
20 ou 70.
Campo 11 - Validação: o valor informado no campo deve existir no registro 0460.
REGISTRO C791: REGISTRO DE INFORMAÇÕES DE ST POR UF (COD 06)
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C791" C 004 - Não O
02 UF Sigla da unidade da federação a que se refere a C 002* - O
retenção ST apresentar
03 VL_BC_ICMS_ST Valor da base de cálculo do ICMS substituição N - 02 O
tributária
04 VL_ICMS_ST Valor do ICMS retido por substituição tributária N - 02 O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [C791]
Campo 02 - Validação: o valor informado no campo deve existir na tabela de UF.
REGISTRO C800: CUPOM FISCAL ELETRÔNICO – SAT (CF-E-SAT) (CÓDIGO 59)
Este registro deve ser gerado para cada CF-e-SAT (Código 59) emitido por equipamento SAT-CF-e, conforme
Ajuste SINIEF no 11, de 24 de setembro de 2010.
Não poderão ser informados dois ou mais registros com a mesma combinação de COD_SIT + NUM_CFE +
NUM_SAT + DT_DOC
Para cupom fiscal eletrônico cancelado, informar somente os campos REG, COD_MOD, COD_SIT, NUM_CFE,
NR_SAT e CHV_CFE.
Para cada registro C800 deve ser apresentado obrigatoriamente, pelo menos, um registro C850 observada a
exceção abaixo indicada:
Exceção 1: Para documentos com código de situação (campo COD_SIT) cancelado (código “02”) ou cancelado
extemporâneo (código “03”), não apresentar o registro filho (C850).
Nº Campo Descrição Tipo Tam Dec Entr Saídas
01 REG Texto fixo contendo "C800" C 004 - Não O
02 COD_MOD Código do modelo do documento fiscal, conforme a Tabela C 002 - apre O
4.1.1 sen
03 COD_SIT Código da situação do documento fiscal, conforme a Tabela N 002 - tar O
4.1.2
04 NUM_CFE Número do Cupom Fiscal Eletrônico N 006 - O
05 DT_DOC Data da emissão do Cupom Fiscal Eletrônico N 008 - O
06 VL_CFE Valor total do Cupom Fiscal Eletrônico N - 02 O
07 VL_PIS Valor total do PIS N - 02 OC
08 VL_COFINS Valor total da COFINS N - 02 OC
09 CNPJ_CPF CNPJ ou CPF do destinatário N 14 - OC
10 NR_SAT Número de Série do equipamento SAT N 009 - O
Página 81 de 209

--- Página 82 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
11 CHV_CFE Chave do Cupom Fiscal Eletrônico N 044 - O
12 VL_DESC Valor total de descontos N - 02 O
13 VL_MERC Valor total das mercadorias e serviços N - 02 O
14 VL_OUT_DA Valor total de outras despesas acessórias e acréscimos N - 02 O
15 VL_ICMS Valor do ICMS N - 02 O
16 VL_PIS_ST Valor total do PIS retido por subst. trib. N - 02 O
17 VL_COFINS_ST Valor total da COFINS retido por subst. trib. N - 02 O
Observações:
Nível hierárquico: 2
Ocorrência: Vários
Campo 01 – Valor Válido: [C800]
Campo 02 – Preenchimento: deve corresponder ao código CF-e-SAT (Valor Válido: 59). Ver tabela reproduzida na
subseção 6.4 deste guia.
Campo 03 – Valores válidos: [00, 01, 02, 03]
Preenchimento: verificar a descrição da situação do documento na Subseção 6.3, respeitando os valores válidos acima
indicados.
Campo 05 – Preenchimento: informar a data de emissão do documento, no formato “ddmmaaaa”, excluindo-se quaisquer
caracteres de separação, tais como: “.”, “/”, “-”.
Validação: o valor informado no campo deve ser menor ou igual ao valor do campo DT_FIN do registro 0000.
Campo 06 – Preenchimento: corresponde ao campo Valor total do CF-e-SAT, constante do leiaute do CF-e-SAT.
Validação: o valor informado neste campo deve ser igual à soma do campo VL_OPR dos registros C850 (“filhos” deste
registro C800).
Campo 07 – Preenchimento: corresponde ao campo Valor Total do PIS, constante do leiaute do CF-e-SAT. Os
contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro 0000 estão
dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 08 – Preenchimento: corresponde ao campo Valor Total do COFINS, constante do leiaute do CF-e-SAT. Os
contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do registro 0000 estão
dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 09 – Preenchimento: informar o CNPJ, com 14 dígitos, ou o CPF, com 11 dígitos, do adquirente.
Validação: se forem informados 14 caracteres, o campo será validado como CNPJ. Se forem informados 11 caracteres, o
campo será validado como CPF. O preenchimento com outra quantidade de caracteres será considerado inválido.
Campo 11 – Validação: é conferido o dígito verificador (DV) da chave do CF-e-SAT. Para confirmação inequívoca de que
a chave do CF-e-SAT corresponde aos dados informados no documento, será comparado o CNPJ existente na CHV_CFE
com o campo CNPJ do registro 0000, que corresponde ao CNPJ do informante do arquivo. Serão verificados a consistência
da informação do campo NUM_CFE e o número do documento contido na chave do CF-e-SAT, bem como comparado se a
informação do AAMM de emissão contido na chave do CFE corresponde ao ano e mês da data de emissão do CF-e-SAT.
Será também comparada a UF codificada na chave do CF-e-SAT com o campo UF informado no registro 0000.
Formação da chave:
Campo Tamanho Obs.
Código da UF 2
AAMM da emissão 4
CNPJ do emitente 14
Modelo do documento fiscal 2 código para o CF-e
Número de série do SAT 9 Número sequencial atribuído pela SEFAZ, iniciando em 000000001
Número do CF-e 6 Numeração sequencial para cada equipamento
Código numérico 6 Número aleatório gerado pelo SAT para cada CF-e
DV 1 Módulo 11
Total 44
Campo 12 – Preenchimento: corresponde ao campo Valor Total dos Descontos sobre item, constante do leiaute do CF-e-
SAT.
Página 82 de 209

--- Página 83 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 13 – Preenchimento: corresponde ao campo Valor Total dos Produtos e Serviços, constante do leiaute do CF-e-
SAT.
Campo 14 – Preenchimento: corresponde ao campo Valor Total de Outras Despesas Acessórias sobre item, constante do
leiaute do CF-e-SAT.
Campo 15 – Preenchimento: corresponde ao campo Valor Total do ICMS, constante do leiaute do CF-e-SAT.
Validação: o valor informado neste campo deve ser igual à soma do campo VL_ICMS dos registros C850 (“filhos” deste
registro C800).
Campo 16 – Preenchimento: corresponde ao campo Valor Total do PIS retido por substituição tributária, constante do
leiaute do CF-e-SAT. Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do
registro 0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
Campo 17 – Preenchimento: corresponde ao campo Valor Total do COFINS retido por substituição tributária, constante
do leiaute do CF-e-SAT. Os contribuintes que entregarem a EFD-Contribuições relativa ao mesmo período de apuração do
registro 0000 estão dispensados do preenchimento deste campo. Apresentar conteúdo VAZIO “||”.
REGISTRO C850: REGISTRO ANALÍTICO DO CF-E-SAT (CODIGO 59)
Este registro tem por objetivo representar a escrituração do CF-e-SAT (código 59) segmentado por CST, CFOP e Alíquota
do ICMS.
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C850" C 004 - O
02 CST_ICMS Código da Situação Tributária, conforme a Tabela indicada no N 003 -
O
item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação do agrupamento de N 004 -
O
itens
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
Não
05 VL_OPR “Valor total do CF-e” na combinação de CST_ICMS, CFOP e N - 02
apre
alíquota do ICMS, correspondente ao somatório do valor O
sen
líquido dos itens.
tar
06 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS, referente à N - 2
O
combinação de CST_ICMS, CFOP, e alíquota do ICMS.
07 VL_ICMS Parcela correspondente ao "Valor do ICMS" referente à N - 02
O
combinação de CST_ICMS, CFOP e alíquota do ICMS.
08 COD_OBS Código da observação do lançamento fiscal (campo 02 do C 006 -
OC
registro 0460)
Observações:
Nível hierárquico: 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C850]
Validação: não poderão existir dois ou mais registros, para cada CF-e-SAT, para o mesmo conjunto CST_ICMS, CFOP e
ALIQ_ICMS.
Campo 02 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária do ICMS, referenciada
no item 4.3.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
ICMS Normal:
a) se os dois últimos dígitos deste campo forem 40, 41, 50, ou 60, então os valores dos campos VL_BC_ICMS,
ALIQ_ICMS e VL_ICMS deverão ser iguais a “0”(zero);
b) se os dois últimos dígitos deste campo forem iguais a 00, então os valores dos campos VL_BC_ICMS, ALIQ_ICMS e
VL_ICMS deverão ser maiores que “0”(zero);
c) se os dois últimos dígitos deste campo forem iguais a 20 ou 90, então os valores dos campos VL_BC_ICMS,
ALIQ_ICMS e VL_ICMS deverão ser maiores ou iguais a “0”(zero);
Campo 03 - Preenchimento: pelo fato de o CF-e-SAT referir-se apenas a operações de saídas internas, deve ser
preenchido como CFOP iniciado por 5 (ex: 5102, 5405, etc.).
Página 83 de 209

--- Página 84 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Validação: o valor informado no campo deve existir na Tabela de Código Fiscal de Operação e Prestação, conforme Ajuste
SINIEF 07/01 e iniciar com dígito “5”.
Campo 05 - Validação: O somatório dos valores deste campo, considerando todos os registros C850 de um determinado
CF-e-SAT, deve corresponder ao respectivo valor total do CF-e-SAT informado no reg. C800.
Campo 06 – Preenchimento: Tendo em vista o uso da alíquota efetiva, seu valor, caso seja maior que “0”, corresponde ao
valor indicado Campo 05.
Validação: Caso maior que “0” (zero), o somatório dos valores deste campo, considerando todos os registros C850 de um
determinado CF-e-SAT, deve corresponder ao valor total do CF-e-SAT informado no reg. C800.
Campo 07 - Validação: O somatório dos valores deste campo, considerando todos os registros C850 de um determinado
CF-e-SAT, deve corresponder ao valor total do ICMS informado no reg. C800.
Campo 08 - Preenchimento: este campo só deve ser informado pelos contribuintes localizados em UF que determine em
sua legislação o seu preenchimento.
Validação: o código informado deve constar do registro 0460.
REGISTRO C860: IDENTIFICAÇÃO DO EQUIPAMENTO SAT-CF-E
Este registro tem por objetivo identificar os equipamentos SAT-CF-e e deve ser informado por todos os
contribuintes que utilizem tais equipamentos na emissão de documentos fiscais.
Não poderão ser informados dois ou mais registros com a mesma combinação COD_MOD, NR_SAT, DOC_INI e
DOC_FIM.
01 REG Texto fixo contendo "C860" C 004 - Entr Saída
02 COD_MOD Código do modelo do documento fiscal, conforme a Tabela C 002 - O
4.1.1 Não
03 NR_SAT Número de Série do equipamento SAT N 009 - apre O
04 DT_DOC Data de emissão dos documentos fiscais N 008 - sen O
05 DOC_INI Número do documento inicial N 006 - tar O
06 DOC_FIM Número do documento final N 006 - O
Observações:
Nível hierárquico: 2
Ocorrência - 1:N
Campo 01 - Valor Válido: [C860]
Validação: não poderão existir dois ou mais registros para o conjunto COD_MOD, NR_SAT, DOC_INI e DOC_FIM
Campo 02 – Preenchimento: deve corresponder ao código CF-e-SAT (Valor Válido: 59). Ver tabela reproduzida na
subseção 6.4 deste Guia.
Campo 04 - Preenchimento: informar a data de emissão do documento, no formato “ddmmaaaa”, excluindo-se quaisquer
caracteres de separação, tais como: “.”, “/”, “-”.
Validação: o valor informado no campo deve estar compreendido dentro das datas informadas no registro 0000. Para data
inferior ao período de apuração informado no registro 0000, o valor do ICMS informado no registro C890 será adicionado
no campo Débitos Especiais do registro E110.
Campo 05 - Preenchimento: informar o número do primeiro CF-e-SAT emitido, mesmo que cancelado, no período, pelo
equipamento.
Validação: o valor informado deve ser menor ou igual ao valor informado no Campo 6.
Campo 06 - Preenchimento: informar o número do último CF-e-SAT emitido, mesmo que cancelado, no período, pelo
equipamento.
Validação: o valor informado deve ser maior ou igual ao valor informado no Campo 5.
REGISTRO C890: RESUMO DIÁRIO DO CF-E-SAT (CÓDIGO 59) POR EQUIPAMENTO
SAT-CF-E
Este registro tem por objetivo promover a consolidação dos CF-e-SAT emitidos no período, por equipamento SAT-CF-e.
Página 84 de 209

--- Página 85 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nº Campo Descrição Tipo Tam Dec Entr Saída
01 REG Texto fixo contendo "C890" C 004 - O
02 CST_ICMS Código da Situação Tributária, conforme a Tabela indicada no N 003 - O
item 4.3.1
03 CFOP Código Fiscal de Operação e Prestação do agrupamento de itens N 004 - O
04 ALIQ_ICMS Alíquota do ICMS N 006 02 OC
05 VL_OPR “Valor total do CF-e” na combinação de CST_ICMS, CFOP e N - 02 Não O
ALÍQUOTA DO ICMS, correspondente ao somatório do valor apre
líquido dos itens. sen
06 VL_BC_ICMS Valor acumulado da base de cálculo do ICMS, referente à N - 2 tar O
combinação de CST_ICMS, CFOP e ALÍQUOTA DO ICMS.
07 VL_ICMS Parcela correspondente ao "Valor do ICMS" referente à N - 02 O
combinação de CST_ICMS, CFOP e alíquota do ICMS.
08 COD_OBS Código da observação do lançamento fiscal (campo 02 do C 006 - OC
registro 0460)
Observações:
Nível hierárquico: 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [C890]
Validação: não poderão existir dois ou mais registros para o conjunto DT_DOC, NR_SAT, CST_ICMS, CFOP e
ALIQ_ICMS.
Campo 02 - Validação: o valor informado no campo deve existir na Tabela da Situação Tributária referente ao ICMS,
constante do Artigo 5º do Convênio SN/70.
Campo 03 - Preenchimento: pelo fato do CF-e-SAT referir-se apenas a operações de saídas internas, deve ser preenchido
com CFOP iniciado por 5 (ex: 5102, 5405, etc.).
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
Validação do Registro: registro único e obrigatório para todos os informantes da EFD-ICMS/IPI.
Nº Campo Descrição Tipo Tam Dec Entr Saida
01 REG Texto fixo contendo "C990" C 004 - O O
02 QTD_LIN_C Quantidade total de linhas do Bloco C N - - O O
Observações: Registro obrigatório
Nível hierárquico - 1
Ocorrência – um por arquivo
Campo 01 - Valor Válido: [C990]
Página 85 de 209

--- Página 86 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco C é igual ao valor informado no campo QTD_LIN_C
(registro C990).
BLOCO D: DOCUMENTOS FISCAIS II - SERVIÇOS (ICMS).
Bloco de registros dos dados relativos à emissão ou ao recebimento de documentos fiscais que acobertam as
prestações de serviços de comunicação, transporte intermunicipal e interestadual.
REGISTRO D001: ABERTURA DO BLOCO D
Este registro deve ser gerado para abertura do bloco D e indica se há informações sobre prestações ou contratações
de serviços de comunicação, transporte interestadual e intermunicipal, com o devido suporte do correspondente documento
fiscal.
Validação do Registro: registro obrigatório e único. Se o campo IND_MOV tiver valor igual a 1 (um), só devem ser
informados este registro de abertura e o registro D990, que é o registro de fechamento do Bloco D.
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
REGISTRO D100: NOTA FISCAL DE SERVIÇO DE TRANSPORTE (CÓDIGO 07) E
CONHECIMENTOS DE TRANSPORTE RODOVIÁRIO DE CARGAS (CÓDIGO 08),
CONHECIMENTOS DE TRANSPORTE DE CARGAS AVULSO (CÓDIGO 8B),
AQUAVIÁRIO DE CARGAS (CÓDIGO 09), AÉREO (CÓDIGO 10), FERROVIÁRIO
DE CARGAS (CÓDIGO 11) E MULTIMODAL DE CARGAS (CÓDIGO 26), NOTA
FISCAL DE TRANSPORTE FERROVIÁRIO DE CARGA ( CÓDIGO 27) E
CONHECIMENTO DE TRANSPORTE ELETRÔNICO – CT-e (CÓDIGO 57).
Este registro deve ser apresentado por todos os contribuintes adquirentes ou prestadores dos serviços que utilizem
os documentos especificados.
O campo CHV_CTE passa a ser de preenchimento obrigatório a partir de abril de 2012 em todas as situações,
exceto para COD_SIT = 4 (denegado)
IMPORTANTE: para documentos de entrada, os campos de valor de imposto/contribuição, base de cálculo e
alíquota só devem ser informados se o adquirente tiver direito à apropriação do crédito (enfoque do declarante).
Validação do Registro: não podem ser informados dois ou mais registros com a combinação de mesmos valores dos
campos :
1. emissão de terceiros : IND_EMIT+NUM_DOC+COD_MOD+SER+SUB+COD_PART;
2. emissão própria: IND_EMIT+NUM_DOC+COD_MOD+SER+SUB.
Página 86 de 209

