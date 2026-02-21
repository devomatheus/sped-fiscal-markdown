# Bloco H - Versão 2.0.7

**Data de Criação:** 2011-12-01  
**Páginas:** 136-140  
**Versão:** 2.0.7

---

--- Página 136 ---
Guia Prático EFD – Versão 2.0.7
Atualização: dezembro de 2011
Campo 07 - Preenchimento: Informar o valor total das saídas do período referido neste registro, conforme a legislação da
unidade federada.
Campo 08 - Preenchimento: Informar o valor do índice de participação correspondente ao resultado da divisão do campo
VL_TRIB_EXP pelo campo VL_TOTAL.
Campo 09 - Preenchimento: Informar o valor do crédito de ICMS a ser apropriado na apuração do imposto.
Validação: O valor informado neste campo deve ser menor ou igual ao resultado da multiplicação do valor constante no
campo 05 (VL_PARC_PASS) pelo índice de participação calculado no campo 08 (IND_PER_SAI).
REGISTRO G130: IDENTIFICAÇÃO DO DOCUMENTO FISCAL
Este registro tem o objetivo de identificar o documento fiscal que acobertou a entrada ou a saída do bem ou
componente do CIAP.
Quando o tipo de movimentação – TIPO_MOV do registro G125 – for igual a "MC", "IM", "IA" ou "AT", este
registro é obrigatório.
Caso exista previsão legal de emissão de documento fiscal para os demais tipos de movimentação – TIPO_MOV
do registro G125 – esse registro deverá ser informado.
No período em que se iniciar a obrigação de escrituração fiscal digital do CIAP ou quando isso ocorrer de forma
espontânea, este registro é obrigatório nas seguintes situações:
a) quando o tipo de movimentação – TIPO_MOV do registro G125 – for igual a “SI” e esse “SI” for originado dos
tipos de movimentação “IM”, “IA” ou “MC”;
b) quando o tipo de movimentação – TIPO_MOV do registro G125 – for igual a “SI” e esse “SI” for originado do
tipo de movimentação “CI”, devem ser informados os documentos fiscais relativos ao tipo de movimentação “IA” dos seus
componentes que entraram antes desse período;
c) quando o tipo de movimentação – TIPO_MOV do registro G125 – for igual a “CI”, devem ser informados os
documentos fiscais relativos ao tipo de movimentação “IA” dos seus componentes que entraram antes desse período.
Independentemente das situações referidas, esse registro será informado uma única vez.
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos IND_EMIT,
COD_PART, COD_MOD, SERIE, NUM_DOC, CHV_NFE_CTE para o mesmo bem ou componente.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G130" C 004 - O
02 IND_EMIT Indicador do emitente do documento fiscal: C 001* - O
0- Emissão própria;
1- Terceiros
03 COD_PART Código do participante : C 060 - O
- do emitente do documento ou do remetente das mercadorias, no
caso de entradas;
- do adquirente, no caso de saídas
04 COD_MOD Código do modelo de documento fiscal, conforme tabela 4.1.1 C 002* - O
05 SERIE Série do documento fiscal C 003 - OC
06 NUM_DOC Número de documento fiscal N 009 - O
07 CHV_NFE_CTE Chave do documento fiscal eletrônico N 044* - OC
08 DT_DOC Data da emissão do documento fiscal N 008* - O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [G130];
Campo 03 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 07 - Preenchimento: Informar chave dos documentos eletrônicos somente quando for documento de emissão
própria.
Campo 08 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação.
REGISTRO G140: IDENTIFICAÇÃO DO ITEM DO DOCUMENTO FISCAL
Este registro tem o objetivo de identificar o item do documento fiscal informado no registro G130.
Página 136 de 174

--- Página 137 ---
Guia Prático EFD – Versão 2.0.7
Atualização: dezembro de 2011
Não podem ser informados dois ou mais registros com o mesmo valor no campo NUM_ITEM + COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G140" C 004 - O
02 NUM_ITEM Número sequencial do item no documento fiscal N 003 - O
03 COD_ITEM Código correspondente do bem no documento fiscal (campo 02 do C 060 - O
registro 0200)
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
02 IND_MOV Indicador de movimento: C 001* - O
0- Bloco com dados informados;
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
Página 137 de 174

--- Página 138 ---
Guia Prático EFD – Versão 2.0.7
Atualização: dezembro de 2011
deverá ser apresentado no arquivo da EFD, no segundo mês subsequente ao evento. Ex. inventário realizado em 31/12/08
deverá ser apresentado na EFD de período de referência fevereiro de 2009.
Atribuir valor Zero ao inventário significa escriturar sem estoque.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H005" C 004 - O
02 DT_INV Data do inventário N 008* - O
03 VL_INV Valor total do estoque N - 02 O
04 MOT_INV Informe o motivo do Inventário: C 002* - O
01 – No final no período;
02 – Na mudança de forma de tributação da
mercadoria (ICMS);
03 – Na solicitação da baixa cadastral, paralisação
temporária e outras situações;
04 – Na alteração de regime de pagamento – condição
do contribuinte;
05 – Por determinação dos fiscos.
Observações:
Nível hierárquico - 2
Ocorrência – 1:N
Campo 01 - Valor Válido: [H005]
Campo 02 - Preenchimento: informar a data do inventário no formato “ddmmaaaa”, sem separadores de formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000.
Campo 03 - Validação: deve ser igual à soma do campo VL_ITEM do registro H010. Se não houver registro H010, o
valor neste campo deve ser “0” (zero).
Campo 04 – Valores Válidos: [ 01, 02, 03, 04, 05, 06]
Preenchimento: Informe o motivo do Inventário:
01 - No final no período - quando se tratar do estoque final mensal ou outra periodicidade. Deverá ser
informado pela empresa que está obrigada a inventário periódico ou que espontaneamente queira apresentá-
lo;
02 – Na mudança de forma de tributação da mercadoria - quando, por exigência da legislação ou por
regime especial, houver alteração da forma de tributação da mercadoria. Neste caso, se a legislação
determinar, o inventário pode ser parcial.
Exemplo: mercadoria no sistema de tributação por conta corrente fiscal (crédito e débito) e a legislação passa
a cobrar o ICMS por substituição tributária;
03 - Na solicitação de baixa cadastral – por ocasião da solicitação de baixa;
04 - Na alteração de regime de pagamento – condição do contribuinte – quando o contribuinte muda de
condição, alterando o regime de pagamento.
Exemplo: Mudança da condição “Normal” por inclusão no “Simples Nacional” ou inclusão em “Regime
Especial”;
05 - Por solicitação da fiscalização - quando se tratar de solicitação especifica da fiscalização.
REGISTRO H010: INVENTÁRIO.
Este registro deve ser informado para discriminar os itens existentes no estoque. Este registro não pode ser fornecido se o
campo 03 (VL_INV) do registro H005 for igual a “0” (zero).
N Campo Descrição Tipo Tam Dec Obrig
º
01 REG Texto fixo contendo "H010" C 004 - O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
03 UNID Unidade do item C 006 - O
04 QTD Quantidade do item N - 03 O
05 VL_UNIT Valor unitário do item N - 06 O
06 VL_ITEM Valor do item N - 02 O
07 IND_PROP Indicador de propriedade/posse do item: C 001* - O
Página 138 de 174

--- Página 139 ---
Guia Prático EFD – Versão 2.0.7
Atualização: dezembro de 2011
0- Item de propriedade do informante e em seu poder;
1- Item de propriedade do informante em posse de terceiros;
2- Item de propriedade de terceiros em posse do informante
08 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - OC
- proprietário/possuidor que não seja o informante do arquivo
09 TXT_COMP Descrição complementar. C - - OC
L
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
devedora principal, podendo ser informada a conta sintética (nível acima da conta analítica). Nas situações de um mesmo
código de item possuir mais de uma destinação deve ser informada a conta referente ao item de maior relevância.
REGISTRO H020: Informação complementar do Inventário.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H020" C 004 - O
02 CST_ICMS Código da Situação Tributária referente ao ICMS, conforme a N 003* - O
Tabela indicada no item 4.3.1
03 BC_ICMS Informe a base de cálculo do ICMS N - 02 OC
04 VL_ICMS Informe o valor do ICMS a ser debitado ou creditado N 02 OC
Obs.: O registro é obrigatório quando o motivo do inventário, informado no campo MOV_INV do registro H005 for de
“02” a “05”.
Nível hierárquico - 4
Ocorrência – 1:N
REGISTRO H990: ENCERRAMENTO DO BLOCO H.
Este registro destina-se a identificar o encerramento do bloco H e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H990" C 004 - O
02 QTD_LIN_H Quantidade total de linhas do Bloco H N - - O
Observações:
Nível hierárquico - 1
Ocorrência –um por arquivo
Campo 01 - Valor Válido: [H990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco H é igual ao valor informado no campo QTD_LIN_H.
Página 139 de 174

--- Página 140 ---
Guia Prático EFD – Versão 2.0.7
Atualização: dezembro de 2011
Página 140 de 174

