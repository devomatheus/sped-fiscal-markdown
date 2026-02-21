# Bloco G - Versão 2.0.0

**Data de Criação:** 2009-12-17  
**Páginas:** 116-122  
**Versão:** 2.0.0

---

--- Página 116 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
ressarcimento do PIS/Pasep e da cimento do PIS/Pasep e da Cofins nas operações de ex-
Cofins - Lei nº 9.363/1996 portação de produtos industrializados (Lei nº 9.363/1996,
art. 1º)
011 Crédito Presumido de IPI - C valor do crédito presumido de IPI decorrente do ressar-
ressarcimento do PIS/Pasep e da cimento do PIS/Pasep e da Cofins nas operações de ex-
Cofins - Lei nº 10.276/2001 portação de produtos industrializados (Lei nº
10.276/2001, art. 1º)
012 Crédito Presumido de IPI - C valor do crédito presumido relativo ao IPI incidente nas
regiões incentivadas - Lei nº saídas, do estabelecimento industrial, dos produtos clas-
9.826/1999 sificados nas posições 8702 a 8704 da Tipi (Lei nº
9.826/1999, art. 1º)
013 Crédito Presumido de IPI - frete C valor do crédito presumido de IPI relativamente à parcela
- MP 2.158/2001 do frete cobrado pela prestação do serviço de transporte
dos produtos classificados nos códigos 8433.53.00,
8433.59.1, 8701.10.00, 8701.30.00, 8701.90.00,
8702.10.00 Ex 01, 8702.90.90 Ex 01, 8703, 8704.2,
8704.3 e 87.06.00.20, da TIPI (MP nº 2.158/2001, art.
56)
019 Crédito Presumido de IPI - C outros valores de crédito presumido de IPI
outros
098 Créditos decorrentes de medida C valores de crédito de IPI decorrentes de medida judicial
judicial
099 Outros créditos C Valor de outros créditos do IPI
101 Estorno de crédito D Valor do crédito do IPI estornado
102 Transferência de crédito D Valor do crédito do IPI transferido no período, para
outro(s) estabelecimento(s) da mesma empresa, confor-
me previsto na legislação tributária.
103 Ressarcimento / compensação D Valor do crédito de IPI, solicitado junto à RFB/MF
de créditos de IPI
199 Outros débitos D Valor de outros débitos do IPI
(*) Natureza: "C" - Crédito; "D" - Débito
Campo 05 - Valores válidos: [0, 1, 2, 9]
Campo 07 – Preenchimento: informar a descrição resumida do ajuste, incluindo, se for o caso, o período a que se refere o
ajuste, especialmente quando se tratar de períodos de apuração anteriores.
REGISTRO E990: ENCERRAMENTO DO BLOCO E
Este registro destina-se a identificar o encerramento do Bloco E e a informar a quantidade de linhas (registros) existentes
no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "E990" C 004 - O
02 QTD_LIN_E Quantidade total de linhas do Bloco E N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [E990]
Campo 02 - Preenchimento: s quantidade de linhas a ser informada deve considerar também os próprios registros de aber-
tura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco E é igual ao valor informado no campo QTD_LIN_E.
BLOCO G – CONTROLE DO CRÉDITO DE ICMS DO ATIVO PERMANENTE
– CIAP – modelos “C” e “D”
Bloco de registros dos dados relativos ao CIAP.
Página 116 de 158

--- Página 117 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
REGISTRO G001: ABERTURA DO BLOCO G
Este registro deve ser gerado para abertura do Bloco G, indicando se há registros de informações no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G001" C 004* - O
02 IND_MOV Indicador de movimento: C 001* - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência - um (por arquivo)
Campo 01 - Valor Válido: [G001]
Campo 02 - Valores Válidos: [0, 1]
Validação: se preenchido com ”1” (um), então somente pode ser informado o registro G990 (encerramento do Bloco). Se
preenchido com ”0” (zero), então deve ser informado pelo menos um registro além do registro G990 (encerramento do
Bloco).
REGISTRO G110 – ICMS – ATIVO PERMANENTE – CIAP
Este registro tem o objetivo de informar:
a) o saldo inicial de ICMS do CIAP (Modelo “C”), composto pelo valor do ICMS sobre os bens que ingressaram
no CIAP em período anterior ao período de apuração;
b) o saldo final de ICMS do CIAP (Modelo “C”), utilizado como base de cálculo do ICMS apropriado no período
de apuração;
c) o somatório das parcelas de ICMS passíveis de apropriação de cada bem (Modelo “D”), inclusive de bens que
entraram na apuração do CIAP em período anterior ao período de apuração
d) a participação percentual do somatório do valor das saídas tributadas e saídas para exportação no valor total das
saídas;
e) a parcela de ICMS a ser apropriada no Registro de Apuração do ICMS.
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos DT_INI e DT_FIN e
esta combinação deve ser igual à informada em um Registro E100.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G110" C 004* - O
02 DT_INI Data inicial a que a apuração se refere N 008* - O
03 DT_FIN Data final a que a apuração se refere N 008* - O
04 MOD_CIAP Modelo de CIAP adotado: “C” ou “D” C 001* - O
05 SALDO_IN_ICMS Saldo inicial de ICMS do CIAP, composto por N - 02 O(para o
ICMS de bens que entraram anteriormente ao Modelo C)
período de apuração (Modelo C)
06 SALDO_FN_ICMS Saldo final de ICMS do CIAP, utilizado como N - 02 O(para o
base de cálculo do ICMS apropriado no período Modelo C)
de apuração (Modelo C)
07 SOM_PARC Somatório das parcelas de ICMS passível de N - 02 O(para o
apropriação de cada bem – campo 10 do G125 Modelo D)
(Modelo D)
08 VL_TRIB_EXP Valor do somatório das saídas tributadas e saí- N - 02 O
das para exportação
09 VL_TOTAL Valor total de saídas N - 02 O
Página 117 de 158

--- Página 118 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
10 PER_SAI_TRIB Participação percentual do valor do somatório N - 04 O
das saídas tributadas e saídas para exportação no
valor total de saídas
11 ICMS_APROP Parcela de ICMS a ser apropriada no Registro N - 02 O
de Apuração do ICMS.
Observações:
Nível hierárquico - 2
Ocorrência – um (por período de apuração)
Campo 01 - Valor Válido: [G110];
Campos 02 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação e compreendidas
no período informado no Registro 0000;
Campos 03 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação e compreendidas
no período informado no Registro 0000;
Campo 04 - Valores válidos: [“C”, “D”];
Campo 05 - Preenchimento: só deve ser informado quando o conteúdo do campo MOD_CIAP for igual a “C”.Validação:
seu valor deve ser igual ao somatório dos valores dos campos VL_IMOB_ICMS_OP, VL_IMOB_ICMS_OP_ST,
VL_IMOB_ICMS_OP_FRT, VL_IMOB_ICMS_DIF do Registro G125, cujo conteúdo do campo TIPO_MOV do Registro
G125 seja igual a “SI”;
Campo 06 - Preenchimento: só deve ser informado quando o conteúdo do campo MOD_CIAP for igual a “C”.
Validação: seu valor deve ser igual à soma dos campos VL_IMOB_ICMS_OP, VL_IMOB_ICMS_OP_ST,
VL_IMOB_ICMS_OP_FRT, VL_IMOB_ICMS_DIF do Registro G125, cujo conteúdo do campo TIPO_MOV do Registro
G125 seja “SI”, “IM”, “CI ” ou “MC” menos a soma dos mesmos campos, cujo conteúdo do campo TIPO_MOV do Regis-
tro G125 seja “BA”, “AT”, “PE” ou “OT”;
Campo 07 - Preenchimento: só deve ser informado quando o conteúdo do campo MOD_CIAP for igual a “D”.
Validação: seu valor deve ser igual ao somatório dos valores do campo VL_PARC_PASS do Registro G125.
Campo 08 - Validação: o valor informado deve ser menor ou igual ao valor informado no campo VL_TOTAL deste Re-
gistro.
Validação: o valor informado deve ser menor ou igual ao valor informado no campo VL_TOTAL deste Registro.
Campo 09 - Preenchimento: verificar se a legislação da unidade federada exige a exclusão das saídas com suspensão do
imposto.
Campo 10 - Validação: o valor neste campo deve ser igual a divisão do campo VL_TRIB_EXP pelo campo VL_TOTAL,
multiplicado por 100.
Campo 11 - Preenchimento: este valor deve ser informado em um Registro E111 relativo ao crédito pelo Ativo Imobili-
zado, para ser considerado na apuração do ICMS, salvo se a legislação da Unidade Federada exigir que seja emitido docu-
mento fiscal.
Validação: se o conteúdo do campo MOD_CIAP for “C”, este campo deve ser igual à multiplicação do campo SAL-
DO_FN_ICMS pelo campo PER_SAI_TRIB, dividido por 100. Se o conteúdo do campo MOD_CIAP for “D”, este campo
deve ser igual ao somatório do campo VL_PARC_APROP dos Registros G125.
REGISTRO G125 – MOVIMENTAÇÃO DE BEM OU COMPONENTE DO A-
TIVO IMOBILIZADO
Este registro tem o objetivo de informar as movimentações de bens ou componentes e a apropriação de créditos do Ativo
Imobilizado.
Inclui-se no conceito de movimentação:
a) entrada de bem ou componente;
b) saída de bem ou componente;
c) baixa de bem ou componente;
d) entrada pela conclusão de bem principal que estava sendo construído.
Página 118 de 158

--- Página 119 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos COD_IND_BEM e
TIPO_MOV.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G125" C 004* - O
02 COD_IND_BEM Código individualizado do bem ou componente C 015 - O
adotado no controle patrimonial do estabeleci-
mento informante
03 DT_MOV Data da movimentação ou do saldo inicial N 008* - O
04 TIPO_MOV Tipo de movimentação do bem ou componente: C 002* - O
SI = Saldo inicial de bens imobilizados;
IM = Imobilização de bem individual;
IA = Imobilização em Andamento - Componen-
te;
CI = Conclusão de Imobilização em Andamento
– Bem Resultante;
MC = Imobilização oriunda do Ativo Circulante;
BA = Baixa do Saldo de ICMS - Fim do período
de apropriação;
AT = Alienação ou Transferência;
PE = Perecimento, Extravio ou Deterioração;
OT = Outras Saídas do Imobilizado
05 VL_IMOB_ICMS_OP Valor do ICMS da Operação Própria na entrada N - 02 O
do bem ou componente
06 VL_IMOB_ICMS_ST Valor do ICMS da Oper. por Sub. Tributária na N - 02 OC
entrada do bem ou componente
07 VL_IMOB_ICMS_FRT Valor do ICMS sobre Frete do Conhecimento de N - 02 OC
Transporte na entrada do bem ou componente
08 VL_IMOB_ICMS_DIF Valor do ICMS - Diferencial de Alíquota, con- N - 02 OC
forme Doc. de Arrecadação, na entrada do bem
ou componente
09 NUM_PARC Número da parcela do ICMS N 003 - OC
10 VL_PARC_PASS Valor da parcela de ICMS passível de apropria- N - 02 O(para o
ção - antes da aplicação da participação percen- Modelo
tual do valor das saídas tributadas/exportação D)
sobre as saídas totais (Modelo D)
Valor da parcela apropriada de ICMS (Modelo
11 VL_PARC_APROP N - 02 O(para o
D).
Modelo
D)
Observações:
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [G125];
Campo 02 - Validação: o valor informado neste campo deve constar de um Registro 0300;
Campo 03 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação.
Validações:
a) quando o valor no campo TIPO_MOV for igual a “SI”, a data deve ser igual à data inicial constante do campo DT_INI
do Registro G110;
b) quando o valor no campo TIPO_MOV for igual a “IM”, “CI”, “MC”, “BA”, “AT”, “PE” ou “OT”, a data deve estar
compreendida no período de apuração constante dos campos DT_INI e DT_FINdo Registro G110.
c) quando o valor no campo TIPO_MOV for igual a “IA”, a data deve ser igual ou menor à data final constante do campo
DT_FIN do Registro G110;
Campo 04 - Valores Válidos: [SI, IM, IA, CI, MC, BA, AT, PE, OT];
Página 119 de 158

--- Página 120 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Preenchimento:
1) os bens que compõem o saldo inicial de ICMS do período de apuração (Modelo “C”) ou os bens que ainda exis-
tem parcelas a serem apropriadas (Modelo “D”), bens estes que entraram em período anterior ao período de apuração, de-
vem ser informados com o tipo de movimentação “SI”. A data de movimentação deve ser a data inicial do período de apu-
ração;
2) a entrada de bem no CIAP oriunda de estoque do Ativo Circulante deverá ser informada com o tipo de movi-
mentação “MC”;
3) a baixa pelo fim do período de apropriação deve ser informada no período de apuração imediatamente subse-
qüente à ocorrência. Será informado um registro com o tipo de movimentação igual a “SI” e um outro registro com tipo de
movimentação igual a “BA”. Em ambos, os campos NUM_PARC, VL_PARC_PASS e VL_PARC_APROP não devem ser
informados.
4) a saída de um bem ou componente deve ser informada no período de ocorrência do fato. Será informado um re-
gistro com o tipo de movimentação igual a “SI” e um outro registro com tipo de movimentação igual a “AT”, “PE” ou
“OT”, conforme o caso.
5) para o preenchimento dos campos VL_IMOB_ICMS_OP, VL_IMOB_ICMS_ST, VL_IMOB_ICMS_FRT,
VL_IMOB_ICMS_DIF:
5.1 quando o tipo de movimentação for referente a uma entrada dos tipos: “SI”, “IM”, “IA”, “MC”, con-
siderar-se-á o valor do ICMS originado do documento fiscal;
5.2 quando o tipo de movimentação for uma entrada do tipo “CI”, considerar-se-á o valor do ICMS como
o somatório do valor do ICMS dos seus respectivos componentes, cujas imobilizações ocorreram com o tipo “IA”.
5.3 quando o tipo de movimentação for referente a uma saída do CIAP – “BA” ou “AT” ou “PE” ou
“OT”, considerar-se-á o valor do ICMS como o valor de entrada do bem respectivo no CIAP;
6) quando o tipo de movimentação for igual a “SI”(observado o item 3), “IM”, “CI” ou “MC”:
6.1. se Modelo C, deve ser informado o campo NUM_PARC. Não informar os campos VL_PARC_PASS
e VL_PARC_APROP;
6.2. se Modelo D, devem ser informados os campos NUM_PARC, VL_PARC_PASS e
VL_PARC_APROP.
7) para contribuinte localizado em UF que considere o critério do termo inicial de apropriação do crédito somente
quando o bem estiver pronto para ser utilizado:
7.1) a entrada de componente de um bem que está sendo construído no estabelecimento do contribuinte
deverá ser informada com o tipo de movimentação “IA”, mesmo que esse bem ainda não tenha sido concluído;
7.2) a conclusão de um bem que está sendo construído no estabelecimento do contribuinte deverá ser in-
formada com o tipo de movimentação “CI”;
7.3) caso ocorra a conclusão de um bem que está sendo construído no estabelecimento do contribuinte no
período de apuração, e caso exista a entrada de componentes respectivos em período anterior ao período de apura-
ção, a entrada desses componentes deverá ser informada com o tipo de movimentação “IA”, e com a data de mo-
vimentação em que ocorreu;
7.4) caso o tipo de movimentação seja “SI” e caso o bem seja originado do tipo de movimentação “CI”,
deverão ser informadas as entradas dos respectivos componentes com o tipo de movimentação “IA”.
Campo 09 - Validação: o valor informado não pode ser maior que o valor informado no campo NR_PARC do Registro
0300 do bem ou componente correspondente.
Campo 10 - Preenchimento - Somente deve ser informado quando adotado o modelo D, previsto no Ajuste SINIEF nº
08/97.
Validação: o valor informado deve ser igual ao somatório dos campos VL_IMOB_ICMS_OP, VL_IMOB_ICMS_ST,
VL_IMOB_ICMS_FRT, VL_IMOB_ICMS_DIF, dividido pelo valor informado no campo NR_PARC do Registro 0300.
Campo 11 - Preenchimento - Somente deve ser informado quando adotado o modelo D, previsto no Ajuste SINIEF nº
08/97.
Validação: o valor informado deve ser igual ao valor do campo VL_PARC_PASS do Registro G125, multiplicado pelo
campo PER_SAI_TRIB do Registro G110, dividido por 100.
REGISTRO G130 – IDENTIFICAÇÃO DO DOCUMENTO FISCAL
Este registro tem o objetivo de identificar o documento fiscal que acobertou a entrada ou a saída do bem ou componente do
CIAP, quando
o campo TIPO_MOV do Registro G125 for igual a “SI”, “IM”, “IA”, “MC”, “AT”, “PE” ou “OT”;
Página 120 de 158

--- Página 121 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Quando o contribuinte for de UF que considere o critério do termo inicial de apropriação do crédito somente quando o bem
estiver pronto para ser utilizado e o valor do campo TIPO_MOV do Registro G125 for igual a “SI”, originado de uma en-
trada com o tipo de movimentação “CI”, essa informação não deve ser prestada.
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos IND_EMIT,
COD_PART, COD_MOD, SERIE, NUM_DOC, CHV_NFE_CTE
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G130" C 004 - O
02 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O
0- Emissão própria;
1- Terceiros
03 COD_PART Código do participante : C 060 - O
- do emitente do documento ou do remetente das mercado-
rias, no caso de entradas;
- do adquirente, no caso de saídas
04 COD_MOD Código do modelo de documento fiscal, conforme tabela C 002* - O
4.1.1
05 SERIE Série do documento fiscal C 003 - O
06 NUM_DOC Número de documento fiscal N 009 - O
07 CHV_NFE_CTE Chave do documento fiscal eletrônico N 044* - OC
08 DT_DOC Data da emissão do documento fiscal N 008* - O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [G130];
Campo 08 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação.
REGISTRO G140 – IDENTIFICAÇÃO DO ITEM DO DOCUMENTO FISCAL
Este registro tem o objetivo de identificar o item do documento fiscal informado no Registro G130.
Não podem ser informados dois ou mais registros com o mesmo valor no campo COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G140" C 004 - O
02 NUM_ITEM Número seqüencial do item no documento fiscal N 003 - O
03 COD_ITEM Código correspondente do bem no documento fiscal C 060 - O
Observações:
Nível hierárquico - 5
Ocorrência - 1:N
Campo 01: valor válido: [G140];
Campo 03 - validação: o valor informado neste campo deve existir no registro 0200.
REGISTRO G990: ENCERRAMENTO DO BLOCO G
Este registro deve ser gerado para o encerramento do Bloco G e indica o número total de registros existentes neste Bloco.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G990" C 004* - O
02 QTD_LIN_G Quantidade total de linhas do Bloco G N - - O
Página 121 de 158

--- Página 122 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Observações:
Nível hierárquico - 1
Ocorrência - um (por arquivo)
Campo 01: valor válido: [G990];
BLOCO H: INVENTÁRIO FÍSICO
Este bloco destina-se a informar o inventário físico do estabelecimento, nos casos e prazos previstos na legislação pertinen-
te.
REGISTRO H001: ABERTURA DO BLOCO H
Este registro deve ser gerado para abertura do Bloco H, indicando se há registros de informações no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H001" C 004 - O
02 IND_MO Indicador de movimento: C 001* - O
V 0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [H001]
Campo 02 - Valores Válidos: [0,1]
Validação: se preenchido com ”1” (um), então somente pode ser informado o registro H990 (encerramento do Bloco). Se
preenchido com ”0” (zero), então deve ser informado pelo menos um registro além do registro H990 (encerramento do
Bloco).
REGISTRO H005: TOTAIS DO INVENTÁRIO
Este registro deve ser apresentado para discriminar os valores totais dos itens/produtos do inventário realizado em 31 de
dezembro de cada exercício, ou nas demais datas estabelecidas pela legislação fiscal ou comercial. . O inventário deverá ser
apresentado no arquivo da EFD, até o segundo mês subseqüente ao evento. Ex. inventário realizado em 31/12/08 deverá ser
apresentado até a EFD de período de referência fevereiro de 2009.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H005" C 004 - O
02 DT_INV Data do inventário N 008* - O
03 VL_INV Valor total do estoque N - 02 O
Observações:
Nível hierárquico - 2
Ocorrência – 1:N
Campo 01 - Valor Válido: [H005]
Campo 02 - Preenchimento: informar a data do inventário no formato “ddmmaaaa”, sem separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 03 - Validação: deve ser igual à soma do campo VL_ITEM do registro H010. Se não houver registro H010, o
valor neste campo deve ser “0” (zero).
REGISTRO H010: INVENTÁRIO.
Este registro deve ser informado para discriminar os itens existentes no estoque. Este registro não pode ser fornecido se o
campo 03 (VL_INV) do registro H005 for igual a “0” (zero).
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H010" C 004 - O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
03 UNID Unidade do item C 006 - O
04 QTD Quantidade do item N - 03 O
Página 122 de 158

