# Bloco G - Versão 2.0.1

**Data de Criação:** 2010-05-26  
**Páginas:** 117-123  
**Versão:** 2.0.1

---

--- Página 117 ---
Guia Prático EFD – Versão 2.0.1
Atualização: 26 de maio de 2010
BLOCO G – CONTROLE DO CRÉDITO DE ICMS DO ATIVO PERMANENTE
CIAP
Bloco de registros dos dados relativos ao CIAP.
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
Validação: se preenchido com ”1” (um), então somente pode ser informado o registro G001 e G990 (encerramento do
Bloco), significando que não há escrituração do documento CIAP e portanto não há crédito a apropriar. Se preenchido com
”0” (zero), então deve ser informados pelo menos um registro G110 e respectivos registros filhos.
REGISTRO G110 – ICMS – ATIVO PERMANENTE – CIAP
Este registro tem o objetivo de prestar informações sobre o CIAP:
a) o somatório das parcelas de ICMS passíveis de apropriação de cada bem, inclusive de bens que foram
escriturados no CIAP em período anterior ao período de apuração;
b) o valor do índice percentual resultante do somatório do valor das saídas tributadas e saídas para exportação no
valor total das saídas (o valor é sempre igual ou menor que 1 (um));
c) a parcela de ICMS a ser apropriada no Registro de Apuração do ICMS, como ajuste de apuração, salvo se, a
legislação obrigar à emissão de documento fiscal.
d) o valor de ICMS a ser apropriado como crédito. Esse valor será apropriado diretamente no Registro de
Apuração do ICMS, como ajuste de apuração, salvo se a legislação obrigar à emissão de documento fiscal;
e) o valor de outras parcelas de ICMS a ser apropriado. Esse valor será apropriado diretamente no Registro de
Apuração do ICMS, como ajuste de apuração, salvo se a legislação obrigar à emissão de documento fiscal.
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos DT_INI e
DT_FIN e esta combinação deve ser igual à informada em um Registro E100.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G110" C 004* - O
02 DT_INI Data inicial a que a apuração se refere N 008* - O
03 DT_FIN Data final a que a apuração se refere N 008* - O
04 SALDO_IN_ICMS Saldo inicial de ICMS do CIAP, composto por N - 02 O
ICMS de bens que entraram anteriormente ao
período de apuração (somatório dos campos 05
a 08 dos registros G125)
05 SOM_PARC Somatório das parcelas de ICMS passível de N - 02 O
apropriação de cada bem (campo 10 do G125)
06 VL_TRIB_EXP Valor do somatório das saídas tributadas e N - 02 O
saídas para exportação
Página 117 de 159

--- Página 118 ---
Guia Prático EFD – Versão 2.0.1
Atualização: 26 de maio de 2010
07 VL_TOTAL Valor total de saídas N - 02 O
08 IND_PER_SAI Índice de participação do valor do somatório das N - 04 O
saídas tributadas e saídas para exportação no
valor total de saídas (Campo 06 dividido pelo
campo 07)
09 ICMS_APROP Valor de ICMS a ser apropriado na apuração do N - 02 O
ICMS, correspondente á multiplicação do
campo 05 pelo campo 08.
10 SOM_ICMS_OC Valor de outros créditos a ser apropriado na N - 02 O
Apuração do ICMS, correspondente ao
somatório do campo 09 do registro G126.
Observações:
Nível hierárquico - 2
Ocorrência – um (por período de apuração)
Campo 01 - Valor Válido: [G110];
Campos 02 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação e compreendidas
no período informado no Registro 0000;
Campos 03 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação e compreendidas
no período informado no Registro 0000;
Campo 04 – Preenchimento:
O saldo inicial do período de apuração, é composto pelos totais de créditos de ICMS de Ativo Imobilizado
(somatório dos campos VL_IMOB_ICMS_OP + VL_IMOB_ICMS_ST + VL_IMOB_ICMS_FRT +
VL_IMOB_ICMS_DIF) de cada bem ou componentes, que foram escriturados no CIAP em períodos anteriores ao indicado
nos campos 02 e 03, bens estes que já tiveram parcela do crédito apropriado. Estes bens ou componentes devem ser
informados com o tipo de movimentação “SI” no reg. G125, sendo que a data de movimentação informada neste registro
deverá ser a data inicial do período de apuração.
Não compõe o saldo inicial o valor dos créditos de ICMS escriturados no período anterior com tipo de
movimentação “IA – Imobilização em andamento”, cujos créditos somente serão apropriados a partir da conclusão do bem
principal.
Campo 05 - Preenchimento: Informar o somatório das parcelas de ICMS (totalização dos valores contidos no campo 10
do registro G125)
Validação: O valor preenchido corresponde ao somatório de todos os valores informados no campo 10 (VL_PARC_PASS)
dos registros G125.
Campo 06 - Validação: o valor informado deve ser menor ou igual ao valor informado no campo VL_TOTAL deste
Registro.
Campo 07 - Preenchimento: Informar o valor total das saídas, conforme a legislação da unidade federada.
Campo 08 - Validação: Informar o valor do índice de participação do valor das saídas tributadas/exportação no valor total
das saídas, correspondente ao resultado da divisão do campo VL_TRIB_EXP pelo campo VL_TOTAL.
Campo 09 - Preenchimento: Informar o valor de ICMS a ser apropriado como crédito no período. Esse valor será
apropriado diretamente no Registro de Apuração do ICMS, como ajuste de apuração, salvo se a legislação obrigar à
emissão de documento fiscal.Validação: O valor corresponde à multiplicação do valor constante no campo 05
(SOM_PARC) pelo índice calculado no campo 08 (IND_PER_SAI)
Campo 10 - Preenchimento: Informe o somatório de valores de outros créditos CIAP, apropriados no período e
discriminados no registro G126. Esse somatório será apropriado diretamente no Registro de Apuração do ICMS, como
ajuste de apuração, salvo se a legislação obrigar à emissão de documento fiscal.
Validação: O valor preenchido corresponde ao somatório de todos os valores informados no campo 09
(VL_PARC_APROP) dos registros G126.
Página 118 de 159

--- Página 119 ---
Guia Prático EFD – Versão 2.0.1
Atualização: 26 de maio de 2010
REGISTRO G125 – MOVIMENTAÇÃO DE BEM OU COMPONENTE DO ATIVO
IMOBILIZADO
Este registro tem o objetivo de informar as movimentações de bens ou componentes e a apropriação de créditos do
Ativo Imobilizado.
Inclui-se no conceito de movimentação:
a) entrada de bem ou componente;
b) saída de bem ou componente;
c) baixa de bem ou componente;
d) entrada pela conclusão de bem que estava sendo construído pelo contribuinte.
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos
COD_IND_BEM e TIPO_MOV.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G125" C 004* - O
02 COD_IND_BEM Código individualizado do bem ou componente adotado C 015 - O
no controle patrimonial do estabelecimento informante
03 DT_MOV Data da movimentação ou do saldo inicial N 008* - O
04 TIPO_MOV Tipo de movimentação do bem ou componente: C 002* - O
SI = Saldo inicial de bens imobilizados;
IM = Imobilização de bem individual;
IA = Imobilização em Andamento - Componente;
CI = Conclusão de Imobilização em Andamento – Bem
Resultante;
MC = Imobilização oriunda do Ativo Circulante;
BA = Baixa do bem - Fim do período de apropriação;
AT = Alienação ou Transferência;
PE = Perecimento, Extravio ou Deterioração;
OT = Outras Saídas do Imobilizado
05 VL_IMOB_ICMS Valor do ICMS da Operação Própria na entrada do bem N - 02 OC
_OP ou componente
06 VL_IMOB_ICMS Valor do ICMS da Oper. por Sub. Tributária na entrada N - 02 OC
_ST do bem ou componente
07 VL_IMOB_ICMS Valor do ICMS sobre Frete do Conhecimento de N - 02 OC
_FRT Transporte na entrada do bem ou componente
08 VL_IMOB_ICMS Valor do ICMS - Diferencial de Alíquota, conforme N - 02 OC
_DIF Doc. de Arrecadação, na entrada do bem ou
componente
09 NUM_PARC Número da parcela do ICMS N 003 - OC
10 VL_PARC_PASS Valor da parcela de ICMS passível de apropriação N - 02 OC
(antes da aplicação da participação percentual do valor
das saídas tributadas/exportação sobre as saídas totais)
Observações: Os preenchimentos dos campos 09 e 10, indicará sempre a escrituração e aproveitamento do crédito de ICMS no período.
Nível hierárquico – 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [G125];
Campo 02 - Validação: o código informado neste campo deve constar de um Registro 0300;
Campo 03 - Preenchimento: informar a data no formato “ddmmaaaa”.
Validações:
a) quando o valor no campo TIPO_MOV for igual a “SI”, a data deve ser igual à data inicial constante do campo DT_INI
do Registro G110;
b) quando o valor no campo TIPO_MOV for igual a “IM”, “CI”, “MC”, “BA”, “AT”, “PE” ou “OT”, a data deve estar
compreendida no período de apuração constante dos campos DT_INI e DT_FIN do Registro G110.
c) quando o valor no campo TIPO_MOV for igual a “IA”, a data deve ser igual ou menor à data final constante do campo
DT_FIN do Registro G110;
Página 119 de 159

--- Página 120 ---
Guia Prático EFD – Versão 2.0.1
Atualização: 26 de maio de 2010
Campo 04 - Valores Válidos: [SI, IM, IA, CI, MC, BA, AT, PE, OT];
Preenchimento:
1) os bens que ainda possuem parcelas a serem apropriadas e que foram escriturados em período anterior ao
atual, devem ser informados com o tipo de movimentação “SI”. A data de movimentação deve ser a data inicial do
período de apuração;
2) os bens que entrarem no estabelecimento, no período, devem ser informados com o tipo de movimentação
“IM”;
3) Os componentes, cujos créditos são utilizados a partir da data e entrada ou consumo no estabelecimento,
serão informados com tipo de movimentação “IA”, devendo ser informados os campos NUM_PARC e
VL_PARC_PASS. Nos períodos seguintes devem ser informados com o tipo de movimentação “SI” e a
apropriação das parcelas deverá ser controlada pelo código individual de cada componente até a sua respectiva
baixa;
4) a entrada de bem no CIAP oriunda de estoque do Ativo Circulante deverá ser informada com o tipo de
movimentação “MC”;
5) a baixa pelo fim de apropriação, deverá ser feita no próprio período de apuração e neste caso deverá ser
apresentado dois registros: um com tipo de movimentação “SI” e outro com o tipo de movimentação “BA”. Os
registros, com tipo de movimentação igual a “BA”, não poderão ter os campos 09 (NUM_PARC) e 10
(VL_PARC_PASS) preenchidos.
6) a saída de um bem ou componente deve ser informada no período de ocorrência do fato. Deverá ser
apresentado: um registro com o tipo de movimentação igual a “SI” e um outro registro com tipo de movimentação
igual a “BA”, “AT”, “PE” ou “OT”, conforme o caso. Nesse caso, os campos NUM_PARC e VL_PARC_PASS
não podem ser informados. (inciso V do § 5º do art. 20 da LC 87/96).
7) para o preenchimento dos campos VL_IMOB_ICMS_OP, VL_IMOB_ICMS_ST,
VL_IMOB_ICMS_FRT, VL_IMOB_ICMS_DIF:
7.1 quando o tipo de movimentação for referente a uma entrada dos tipos: “SI”, “IM”, “IA”, “MC”,
considerar-se-á o valor do ICMS originado do documento fiscal;
7.2 quando o tipo de movimentação for uma entrada do tipo “CI”, considerar-se-á o valor do ICMS como o
somatório do valor do ICMS dos seus respectivos componentes, cujas imobilizações ocorreram com o tipo “IA”.
7.3 quando o tipo de movimentação for “IA” e for apropriado o crédito a partir da entrada do componente,
deverão ser informados o NUM_PARC e VL_PARC_PASS deste registro e nos períodos seguintes os valores
passíveis de apropriação deverão ser controlados pelo código individual de cada componente, visto que o número
da parcela pode ser diferente para cada um;
7.4 quando o tipo de movimentação for referente a uma saída do CIAP – “BA” ou “AT” ou “PE” ou “OT”,
considerar-se-á o valor do ICMS como o valor de entrada do bem respectivo no CIAP;
8) quando o tipo de movimentação for igual a “SI”, “IM”, “CI” ou “MC” devem ser informados os campos
NUM_PARC e VL_PARC_PASS, observado o item 3.
9) para o contribuinte localizado em UF que considere o critério que o componente não atende as condições
para se ter direito ao crédito de ICMS, mas sim o bem móvel resultante que está sendo construído no
estabelecimento do contribuinte:
9.1 a entrada de componente de um bem que está sendo construído no estabelecimento do contribuinte deverá ser
informada com o tipo de movimentação “IA”, mesmo que o bem que está sendo construído não tenha sido
concluído;
9.2 a conclusão de um bem que está sendo construído no estabelecimento do contribuinte deverá ser informada
com o tipo de movimentação “CI”;
9.3 caso ocorra a conclusão de um bem que está sendo construído no estabelecimento do contribuinte no período
de apuração, e caso exista a entrada de componentes respectivos em período anterior ao período de apuração, a
entrada desses componentes deverá ser informada com o tipo de movimentação “IA”, e com a data de
movimentação em que ocorreu;
9.4 caso o tipo de movimentação seja “SI” e caso o bem seja originado do tipo de movimentação “CI”, deverão
ser informadas as entradas dos respectivos componentes com o tipo de movimentação “IA”.
9.5 nos períodos posteriores ao período em que ocorreu a entrada do componente com o tipo de movimentação
“IA”, excluindo o período em que for concluído o bem resultante, não deverá ser prestada novamente a
informação deste tipo de movimentação.
Campo 09 – Preenchimento: informe o número da parcela que está sendo escriturada.
Validações: informação obrigatória quando o conteúdo do campo 10 - VL_PARC_PASS for maior que Zero. (Erro)
Campo 10 - Preenchimento – Informe o valor passível de apropriação do crédito (total de créditos de ICMS do bem ou
componente dividido pela quantidade de parcelas) antes da aplicação do índice de participação do valor das saídas
tributadas/exportação no valor total das saídas (campo 08 - PER_SAI_TRIB do reg. G110). O valor informado neste
campo, quando maior que Zero, indica a escrituração e apropriação de valor de crédito de ICMS no período,
independentemente da informação constante no campo 04 - TIPO_MOV (tipo de movimentação).
Página 120 de 159

--- Página 121 ---
Guia Prático EFD – Versão 2.0.1
Atualização: 26 de maio de 2010
Validações:
a) o valor informado deve ser igual o somatório dos campos VL_IMOB_ICMS_OP, VL_IMOB_ICMS_ST,
VL_IMOB_ICMS_FRT, VL_IMOB_ICMS_DIF, dividido pelo valor informado no campo NR_PARC do Registro 0300;
b) informação obrigatória quando o conteúdo do campo 09 – NUM_PARC for maior que Zero.
REGISTRO G126 –OUTROS CRÉDITOS CIAP
Este registro tem por objetivo discriminar todos os demais créditos a serem apropriados como créditos de ICMS de
Ativo Imobilizado que não foram escriturados nos períodos anteriores.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G126" C 004* - O
02 DT_INI Data inicial do período de apuração N 008* - O
03 DT_FIM Data final do período de apuração N 008* O
04 NUM_PARC Número da parcela do ICMS N 003 - O
05 VL_PARC_PASS Valor da parcela de ICMS passível de apropriação - antes N - 02 O
da aplicação da participação percentual do valor das saídas
tributadas/exportação sobre as saídas totais
06 VL_TRIB_OC Valor do somatório das saídas tributadas e saídas para N - 02 O
exportação no período indicado neste registro
07 VL_TOTAL Valor total de saídas no período indicado neste registro N - 02 O
08 IND_PER_SAI Índice de participação do valor do somatório das saídas N - 04 O
tributadas e saídas para exportação no valor total de saídas
(Campo 06 dividido pelo campo 07)
09 VL_PARC_APRO Valor de outros créditos de ICMS a ser apropriado na N - 02 O
P apuração (campo 05 vezes o campo 08)
Observações: Este registro deve ser apresentado somente para discriminar os demais valores de outros créditos de ICMS
sobre ativo imobilizado não escriturados em períodos anteriores, quando a legislação assim permitir.
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [G126];
Campos 02 - Preenchimento: informar a data inicial do período de apuração a que se refere a apropriação no formato
“ddmmaaaa”;
Campos 03 - Preenchimento: informar a data final do período de apuração a que se refere a apropriação no formato
“ddmmaaaa”;
Campo 04 – Preenchimento: informar o número da parcela que está sendo apropriada;
Campo 05 – Preenchimento: informar o valor do crédito de ICMS passível de apropriação.
Campo 06 - Preenchimento: informar o valor das saídas tributadas e para a exportação do período referido neste registro.
Campo 07 - Preenchimento: Informar o valor total das saídas do período referido neste registro, conforme a legislação da
unidade federada.
Campo 08 - Preenchimento: Informar o valor do índice de participação correspondente ao resultado da divisão do campo
VL_TRIB_EXP pelo campo VL_TOTAL.
Campo 09 - Preenchimento: Informar o valor do crédito de ICMS a ser apropriado na apuração do imposto.
Validação: O valor corresponde à multiplicação do valor constante no campo 05 (VL_PARC_PASS) pelo índice calculado
no campo 08 (IND_PER_SAI).
Página 121 de 159

--- Página 122 ---
Guia Prático EFD – Versão 2.0.1
Atualização: 26 de maio de 2010
REGISTRO G130 – IDENTIFICAÇÃO DO DOCUMENTO FISCAL
Este registro tem o objetivo de identificar o documento fiscal que acobertou a entrada ou a saída do bem ou
componente do CIAP, quando o campo TIPO_MOV do Registro G125 for igual a “SI”, “IM”, “IA”, “MC”, “AT”, “PE” ou
“OT”;
Quando o valor do campo TIPO_MOV do Registro G125 for igual a “SI”, originado de uma entrada com o tipo de
movimentação “CI”, essa informação não deve ser prestada.
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos IND_EMIT,
COD_PART, COD_MOD, SERIE, NUM_DOC, CHV_NFE_CTE para o mesmo bem ou componente.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G130" C 004 - O
02 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O
0- Emissão própria;
1- Terceiros
03 COD_PART Código do participante : C 060 - O
- do emitente do documento ou do remetente das
mercadorias, no caso de entradas;
- do adquirente, no caso de saídas
04 COD_MOD Código do modelo de documento fiscal, conforme tabela C 002* - O
4.1.1
05 SERIE Série do documento fiscal C 003 - OC
06 NUM_DOC Número de documento fiscal N 009 - O
07 CHV_NFE_CTE Chave do documento fiscal eletrônico N 044* - OC
08 DT_DOC Data da emissão do documento fiscal N 008* - O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [G130];
Campo 07 - Preenchimento: Informar chave dos documentos eletrônicos, somente quando for documentos de emissão
própria.
Campo 08 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação.
REGISTRO G140 – IDENTIFICAÇÃO DO ITEM DO DOCUMENTO FISCAL
Este registro tem o objetivo de identificar o item do documento fiscal informado no Registro G130.
Não podem ser informados dois ou mais registros com o mesmo valor no campo NUM_ITEM + COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G140" C 004 - O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - O
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
Observações:
Página 122 de 159

--- Página 123 ---
Guia Prático EFD – Versão 2.0.1
Atualização: 26 de maio de 2010
Nível hierárquico - 1
Ocorrência - um (por arquivo)
Campo 01: valor válido: [G990];
BLOCO H: INVENTÁRIO FÍSICO
Este bloco destina-se a informar o inventário físico do estabelecimento, nos casos e prazos previstos na legislação
pertinente.
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
Validação: se preenchido com ”1” (um), então somente pode ser informado o registro H990 (encerramento do Bloco),
significando que não há escrituração de inventário. Se preenchido com ”0” (zero), então deve ser informado pelo menos um
registro além do registro H990 (encerramento do Bloco).
REGISTRO H005: TOTAIS DO INVENTÁRIO
Este registro deve ser apresentado para discriminar os valores totais dos itens/produtos do inventário realizado em
31 de dezembro de cada exercício, ou nas demais datas estabelecidas pela legislação fiscal ou comercial. O inventário
deverá ser apresentado no arquivo da EFD, no segundo mês subsequente ao evento. Ex. inventário realizado em 31/12/08
deverá ser apresentado na EFD de período de referência fevereiro de 2009.
Atribuir valor Zero ao inventário significa escriturar sem estoque.
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
Página 123 de 159

