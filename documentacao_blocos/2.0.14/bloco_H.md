# Bloco H - Versão 2.0.14

**Data de Criação:** 2014-03-01  
**Páginas:** 143-152  
**Versão:** 2.0.14

---

--- Página 143 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
07 CHV_NFE_CTE Chave do documento fiscal eletrônico N 044* - OC
08 DT_DOC Data da emissão do documento fiscal N 008* - O
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [G130].
Campo 03 - Validação: o valor informado deve existir no campo COD_PART do registro 0150.
Campo 04 - Valores Válidos: [01, 1B, 04, 07, 08, 8B, 09, 10, 26, 27, 55 e 57]. Quando se tratar de NF-e ou CT-e, serão
validadas as chaves eletrônicas do respectivo documento.
Campo 07 - Preenchimento: Informar chave dos documentos eletrônicos somente quando for documento de emissão
própria.
Campo 08 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação.
REGISTRO G140: IDENTIFICAÇÃO DO ITEM DO DOCUMENTO FISCAL
Este registro tem o objetivo de identificar o item do documento fiscal informado no registro G130.
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
Este registro deve ser gerado para o encerramento do bloco G e indica o número total de registros existentes neste bloco.
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
Este registro deve ser gerado para abertura do bloco H, indicando se há registros de informações no bloco.
Obrigatoriamente deverá ser informado “0” no campo IND_MOV no período de referência fevereiro de cada ano,
relativamente a 31/12 do ano anterior.
Página 143 de 209

--- Página 144 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
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
Validação: se preenchido com ”1” (um), devem ser informados os registros H001 e H990 (encerramento do bloco),
significando que não há escrituração de inventário. Se preenchido com ”0” (zero), então deve ser informado pelo menos um
registro além do registro H990 (encerramento do bloco).
REGISTRO H005: TOTAIS DO INVENTÁRIO
Este registro deve ser apresentado para discriminar os valores totais dos itens/produtos do inventário realizado em
31 de dezembro de cada exercício, ou nas demais datas estabelecidas pela legislação fiscal ou comercial.
O inventário deverá ser apresentado no arquivo da EFD-ICMS/IPI até o segundo mês subsequente ao evento. Ex.
inventário realizado em 31/12/08 deverá ser apresentado na EFD-ICMS/IPI de período de referência fevereiro de 2009.
A partir de julho de 2012, as empresas que exerçam as atividades descritas na Classificação Nacional de
Atividades Econômicas /Fiscal (CNAE-Fiscal) sob os códigos 4681-8/01 e 4681-8/02 deverão apresentar este registro,
mensalmente, para discriminar os valores itens/produtos do Inventário realizado ao final do mesmo período de referência
do arquivo da EFD-ICMS/IPI. Informar como MOT_INV o código “01”. Exemplo: o inventário realizado no final do mês
de janeiro, deverá ser apresentado na escrituração do mês de janeiro.
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
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000. O
inventário (MOT_INV = 1) não pode ser apresentado após o 2o. mês subsequente à data informada no campo 02
(DT_INV).
Campo 03 - Validação: deve ser igual à soma do campo VL_ITEM do registro H010. Se não houver registro H010, o
valor neste campo deve ser “0” (zero).
Campo 04 – Valores Válidos: [ 01, 02, 03, 04, 05]
Preenchimento: Informe o motivo do Inventário:
01 - No final no período - quando se tratar do estoque final mensal ou outra periodicidade. Deverá ser
informado pela empresa que está obrigada a inventário periódico ou que espontaneamente queira apresentá-lo;
Página 144 de 209

--- Página 145 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
02 – Na mudança de forma de tributação da mercadoria - quando, por exigência da legislação ou por
regime especial, houver alteração da forma de tributação da mercadoria. Neste caso, se a legislação
determinar, o inventário pode ser parcial.
Exemplo: mercadoria no sistema de tributação por conta corrente fiscal (crédito e débito) e a legislação passa
a cobrar o ICMS por substituição tributária;
03 - Na solicitação de baixa cadastral – por ocasião da solicitação da baixa cadastral, paralisação temporária
e outras situações.
04 - Na alteração de regime de pagamento – condição do contribuinte – quando o contribuinte muda de
condição, alterando o regime de pagamento.
Exemplo: Mudança da condição “Normal” por inclusão no “Simples Nacional” ou inclusão em “Regime
Especial”;
05 - Por solicitação da fiscalização - quando se tratar de solicitação específica da fiscalização.
REGISTRO H010: INVENTÁRIO.
Este registro deve ser informado para discriminar os itens existentes no estoque. Este registro não pode ser
fornecido se o campo 03 (VL_INV) do registro H005 for igual a “0” (zero). A partir de janeiro de 2015, caso o contribuinte
utilize o bloco H para atender à legislação do Imposto de Renda, especificamente o artigo 261 do Regulamento do Imposto
de Renda – RIR/99 – Decreto nº 3.000/1999, deverá informar neste registro, além dos itens exigidos pelas legislações do
ICMS e do IPI, aqueles bens exigidos pela legislação do Imposto de Renda.
N Campo Descrição Tipo Tam Dec Obrig
º
01 REG Texto fixo contendo "H010" C 004 - O
02 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
03 UNID Unidade do item C 006 - O
04 QTD Quantidade do item N - 03 O
05 VL_UNIT Valor unitário do item N - 06 O
06 VL_ITEM Valor do item N - 02 O
07 IND_PROP Indicador de propriedade/posse do item: C 001* - O
0- Item de propriedade do informante e em seu poder;
1- Item de propriedade do informante em posse de terceiros;
2- Item de propriedade de terceiros em posse do informante
08 COD_PART Código do participante (campo 02 do Registro 0150): C 060 - OC
- proprietário/possuidor que não seja o informante do arquivo
09 TXT_COMPL Descrição complementar. C - - OC
10 COD_CTA Código da conta analítica contábil debitada/creditada C - - OC
11 VL_ITEM_IR Valor do item para efeitos do Imposto de Renda. N - 02 OC
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
código de item possuir mais de uma destinação deve ser informada a conta referente ao item de maior relevância. Este
campo é obrigatório somente para os perfis A e B.
Página 145 de 209

--- Página 146 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 11 - Preenchimento: válido a partir de 01 de janeiro de 2015. Informar o valor do item utilizando os critérios
previstos na legislação do imposto de renda, especificamente artigos 292 a 297 do RIR/99 – Decreto nº 3.000/99.
REGISTRO H020: Informação complementar do Inventário.
Este registro deve ser preenchido para complementar as informações do inventário, quando o campo MOT_INV
do registro H005 for de “02” a “05”. Não informar, se o campo 03 (VL_INV) do registro H005 for igual a “0” (zero).
No caso de mudança da forma de tributação do ICMS da mercadoria (MOT_INV=2 do H005), somente deverá ser
gerado esse registro para os itens que sofreram alteração da tributação do ICMS.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H020" C 004 - O
02 CST_ICMS Código da Situação Tributária referente ao ICMS, conforme a N 003* - O
Tabela indicada no item 4.3.1
03 BC_ICMS Informe a base de cálculo do ICMS N - 02 O
04 VL_ICMS Informe o valor do ICMS a ser debitado ou creditado N 02 O
Obs.:Registro válido a partir de julho/2012.
Nível hierárquico - 4
Ocorrência – 1:N
Campo 02 - Preenchimento: informar o código CST (sob o enfoque do declarante) aplicável ao item, válido na data do
levantamento do estoque. Se MOT_INV = 2 ou 4 (campo 04 do registro H005), informar o CST aplicável ao item, após a
alteração.
Campo 03: Preenchimento: informar a base de cálculo aplicável ao item (valor unitário). Se MOT_INV = 2 ou 4 (campo
04 do registro H005), informar a base de cálculo aplicável ao item (valor unitário), após a alteração.
Campo 04: Preenchimento: informar o ICMS aplicável ao item (valor unitário), utilizando a alíquota interna. Se
MOT_INV = 2 ou 4 (campo 04 do registro H005), informar o ICMS aplicável ao item (valor unitário), após a alteração.
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
BLOCO K: CONTROLE DA PRODUÇÃO E DO ESTOQUE
Este bloco se destina a prestar informações mensais da produção e respectivo consumo de insumos, bem como do
estoque escriturado, relativos aos estabelecimentos industriais ou a eles equiparados pela legislação federal e pelos
atacadistas, podendo, a critério do Fisco, ser exigido de estabelecimento de contribuintes de outros setores (conforme § 4º
do art. 63 do Convênio s/número, de 1970).
REGISTRO K001: ABERTURA DO BLOCO K
Este registro deve ser gerado para abertura do bloco K, indicando se há registros de informações no bloco.
Página 146 de 209

--- Página 147 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "K001" C 004 - O
02 IND_MOV Indicador de movimento: C 001* - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [K001]
Campo 02 - Valores Válidos: [0,1]
Validação: se preenchido com ”1” (um), devem ser informados os registros K001 e K990 (encerramento do bloco),
significando que não há informação do controle da produção e do estoque. Se preenchido com ”0” (zero), então deve ser
informado pelo menos um registro K100 e seus respectivos registros filhos, além do registro K990 (encerramento do
bloco).
REGISTRO K100: PERÍODO DE APURAÇÃO DO ICMS/IPI
Este registro tem o objetivo de informar o período de apuração do ICMS ou do IPI, prevalecendo os períodos mais
curtos. Contribuintes com mais de um período de apuração no mês declaram um registro K100 para cada período no
mesmo arquivo. Não podem ser informados dois ou mais registros com os mesmos campos DT_INI e DT_FIN.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K100" C 4 - O
02 DT_INI Data inicial a que a apuração se refere N 8 - O
03 DT_FIN Data final a que a apuração se refere N 8 - O
Observações:
Nível hierárquico - 2
Ocorrência – Vários
Campo 01 - Valor Válido: [K100]
Campo 02 – Validação: a data inicial deve estar compreendida no período informado nos campos DT_INI e DT_FIN do
Registro 0000.
Campo 03 – Validação: a data final deve estar compreendida no período informado nos campos DT_INI e DT_FIN do
Registro 0000.
REGISTRO K200: ESTOQUE ESCRITURADO
Este registro tem o objetivo de informar o estoque final escriturado do período de apuração informado no Registro
K100, por tipo de estoque e por participante, nos casos em que couber, das mercadorias de tipos 00 – Mercadoria para
revenda, 01 – Matéria-Prima, 02 - Embalagem, 03 – Produtos em Processo, 04 – Produto Acabado, 05 – Subproduto e 10 –
Outros Insumos – campo TIPO_ITEM do Registro 0200.
A unidade de medida é, obrigatoriamente, a de controle de estoque constante no campo 06 do registro 0200 –
UNID_INV.
A chave deste registro são os campos: DT_EST, COD_ITEM, IND_EST e COD_PART (este, quando houver).
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K200" C 4 - O
02 DT_EST Data do estoque final N 8 - O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 60 - O
04 QTD Quantidade em estoque N 17 3 O
05 IND_EST Indicador do tipo de estoque: C 1 - O
0 = Estoque de propriedade do informante e
em seu poder;
1 = Estoque de propriedade do informante e
Página 147 de 209

--- Página 148 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
em posse de terceiros;
2 = Estoque de propriedade de terceiros e em
posse do informante
06 COD_PART Código do participante (campo 02 do Registro C 60 - OC
0150):
- proprietário/possuidor que não seja o
informante do arquivo
Observações:
Nível hierárquico - 3
Ocorrência – Vários
Campo 01 - Valor Válido: [K200]
Campo 02 – Validação: a data do estoque deve ser igual à data final do período de apuração – campo DT_FIN do Registro
K100.
Campo 03 – Validação: o código do item deverá existir no campo COD_ITEM do Registro 0200.
Campo 05 - Valores Válidos: [0, 1, 2]
Validação: se preenchido com valor ‘1’ (posse de terceiros) ou ‘2’ (propriedade de terceiros), o campo COD_PART será
obrigatório.
Campo 06 – Preenchimento: obrigatório quando o IND_EST for “1” ou “2”.
Validação: o valor fornecido deve constar no campo COD_PART do registro 0150.
REGISTRO K220: OUTRAS MOVIMENTAÇÕES INTERNAS ENTRE
MERCADORIAS
Este registro tem o objetivo de informar a movimentação interna entre mercadorias, que não se enquadre nas
movimentações internas já informadas nos Registros K230 – Itens Produzidos e K235 – Insumos Consumidos: produção
acabada e consumo no processo produtivo, respectivamente.
Exemplo: reclassificação de um produto em outro código em função do cliente a que se destina.
A unidade de medida é, obrigatoriamente, aquela constante no campo 06 do registro 0200: UNID_INV. A
quantidade movimentada deve ser expressa na unidade de medida do item de origem.
A chave deste registro são os campos: DT_MOV, COD_ITEM_ORI e COD_ITEM_DEST.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K220" C 4 - O
02 DT_MOV Data da movimentação interna N 8 - O
03 COD_ITEM_ORI Código do item de origem (campo 02 do C 60 - O
Registro 0200)
04 COD_ITEM_DEST Código do item de destino (campo 02 do C 60 - O
Registro 0200)
05 QTD Quantidade movimentada N 17 3 O
Observações:
Nível hierárquico - 3
Ocorrência – Vários
Campo 01 - Valor Válido: [K220]
Campo 02: Validação: a data deve estar compreendida no período informado nos campos DT_INI e DT_FIN do Registro
K100.
Campo 03: Validação: o código do item de origem deverá existir no campo COD_ITEM do Registro 0200.
Página 148 de 209

--- Página 149 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 04: Validação: o código do item de destino deverá existir no campo COD_ITEM do Registro 0200. O valor
informado deve ser diferente do COD_ITEM_ORI.
Campo 05: Preenchimento: informar a quantidade movimentada do item de origem codificado no campo 03.
REGISTRO K230: ITENS PRODUZIDOS
Este registro tem o objetivo de informar a produção acabada de produto em processo (tipo 03 – campo
TIPO_ITEM do registro 0200) e produto acabado (tipo 04 – campo TIPO_ITEM do registro 0200).
Deverá existir mesmo que a quantidade de produção acabada seja igual a zero, nas situações em que exista o
consumo de item componente/insumo no registro filho K235. Nessa situação a produção ficou em elaboração. Essa
produção em elaboração não é quantificada, uma vez que a matéria não é mais um insumo e nem é ainda um produto
resultante.
A unidade de medida é, obrigatoriamente, a de controle de estoque constante no campo 06 do registro 0200:
UNID_INV.
Quando houver identificação da ordem de produção, a chave deste registro são os campos: COD_DOC_OP e
COD_ITEM.
Nos casos em que a ordem de produção não for identificada, o campo chave passa a ser COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K230" C 4 - O
02 DT_INI_OP Data de início da ordem de produção N 8 - OC
03 DT_FIN_OP Data de conclusão da ordem de produção N 8 - OC
04 COD_DOC_OP Código de identificação da ordem de produção C 30 - OC
05 COD_ITEM Código do item produzido (campo 02 do C 60 - O
Registro 0200)
06 QTD_ENC Quantidade de produção acabada N 17 3 O
Observações:
Nível hierárquico - 3
Ocorrência – Vários
Campo 01 - Valor Válido: [K230]
Campo 02 - Preenchimento: a data de início deverá ser informada se existir ordem de produção, ainda que iniciada em
período de apuração cujo registro K100 correspondente esteja em um arquivo relativo a um mês anterior.
Validação: obrigatório se informado o campo COD_DOC_OP. O valor informado deve ser menor ou igual a DT_FIN do
registro 0000.
Campo 03 - Preenchimento: informar a data de conclusão da ordem de produção. Ficará em branco, caso a ordem de
produção não seja concluída até a data de encerramento do período de apuração. Nesta situação a produção ficou em
elaboração.
Validação: Se preenchido, DT_FIN_OP deve ser menor ou igual a DT_FIN do registro K100 e maior ou igual a
DT_INI_OP.
Campo 04 – Preenchimento: informar o código da ordem de produção.
Campo 05 – Validação: o código do item produzido deverá existir no campo COD_ITEM do Registro 0200.
REGISTRO K235: INSUMOS CONSUMIDOS
Este registro tem o objetivo de informar o consumo de mercadoria no processo produtivo, vinculado ao produto
resultante informado no campo COD_ITEM do Registro K230 – Itens Produzidos.
A unidade de medida é, obrigatoriamente, a de controle de estoque constante no campo 06 do registro 0200:
UNID_INV.
A chave deste registro são os campos DT_SAÍDA e COD_ITEM.
Página 149 de 209

--- Página 150 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K235" C 4 - O
02 DT_SAÍDA Data de saída do estoque para alocação ao N 8 - O
produto
03 COD_ITEM Código do item componente/insumo (campo C 60 - O
02 do Registro 0200)
04 QTD Quantidade consumida do item N 17 3 O
05 COD_INS_SUBST Código do insumo que foi substituído, caso C 60 - OC
ocorra a substituição (campo 02 do Registro
0210)
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [K235]
Campo 02 - Validação: a data deve estar compreendida no período da ordem de produção, se existente, campos
DT_INI_OP e DT_FIN_OP do Registro K230. Se DT_FIN_OP do Registro K230 – Itens Produzidos estiver em branco, o
campo DT_SAÍDA deverá ser maior que o campo DT_INI_OP do Registro K230 e menor ou igual a DT_FIN do Registro
0000.
Campo 03 – Validações:
a) o código do item componente/insumo deverá existir no campo COD_ITEM do Registro 0200;
b) caso o campo COD_INS_SUBST esteja em branco, o código do item componente/insumo deve existir também no
Registro 0210 para o mesmo produto resultante – K230/0200;
c) o código do item componente/insumo deve ser diferente do código do produto resultante (COD_ITEM do Registro
K230).
Campo 05 – Preenchimento: informar o código do item componente/insumo que estava previsto para ser consumido no
Registro 0210 e que foi substituído pelo COD_ITEM deste registro.
Validação: o código do insumo substituído deve existir no Registro 0210 para o mesmo produto resultante – K230/0200.
REGISTRO K250: INDUSTRIALIZAÇÃO EFETUADA POR TERCEIROS – ITENS
PRODUZIDOS
Este registro tem o objetivo de informar os produtos que foram industrializados por terceiros e sua quantidade.
A unidade de medida é, obrigatoriamente, a de controle de estoque constante no campo 06 do registro 0200:
UNID_INV.
A chave deste registro são os campos DT_PROD e COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K250" C 4 - O
02 DT_PROD Data do reconhecimento da produção ocorrida no N 8 - O
terceiro
03 COD_ITEM Código do item produzido (campo 02 do Registro C 60 - O
0200)
04 QTD Quantidade produzida N 17 3 O
Observações:
Nível hierárquico - 3
Ocorrência – Vários
Campo 01 - Valor Válido: [K250]
Campo 02 - Validação: a data deve estar compreendida no período informado nos campos DT_INI e DT_FIN do Registro
K100
Campo 03 – Validações:
a) o código do item produzido deverá existir no campo COD_ITEM do Registro 0200;
b) o TIPO_ITEM do Registro 0200 deve ser igual a 03 – Produtos em Processo ou 04 – Produto Acabado.
Página 150 de 209

--- Página 151 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Campo 04 - Preenchimento: a quantidade produzida deve considerar a quantidade que retornou do terceiro e a variação de
estoque ocorrida.
REGISTRO K255: INDUSTRIALIZAÇÃO EM TERCEIROS – INSUMOS
CONSUMIDOS
Este registro tem o objetivo de informar a quantidade de consumo do insumo que foi remetido para ser
industrializado em terceiro, vinculado ao produto resultante informado no campo COD_ITEM do Registro K250.
A unidade de medida é, obrigatoriamente, a de controle de estoque constante no campo 06 do registro 0200:
UNID_INV.
A chave deste registro são os campos DT_CONS e COD_ITEM deste Registro.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K255" C 4 - O
02 DT_CONS Data do reconhecimento do consumo do N 8 - O
insumo referente ao produto informado no
campo 04 do Registro K250
03 COD_ITEM Código do insumo (campo 02 do Registro C 60 - O
0200)
04 QTD Quantidade de consumo do insumo. N 17 3 O
05 COD_INS_SUBST Código do insumo que foi substituído, caso C 60 - OC
ocorra a substituição (campo 02 do Registro
0210)
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 - Valor Válido: [K255]
Campo 02 - Validação: a data deve estar compreendida no período informado nos campos DT_INI e DT_FIN do Registro
K100.
Campo 03 – Validações:
a) o código do insumo deverá existir no campo COD_ITEM do Registro 0200;
b) caso o campo COD_INS_SUBST esteja em branco, o código do item componente/insumo deve existir também no
Registro 0210 para o mesmo produto resultante – K250/0200;
c) O código do insumo deve ser diferente do código do produto resultante (COD_ITEM do Registro K250 –
Indutrialização efetuada por terceitos – itens produzidos).
Campo 04 - Preenchimento: a quantidade de consumo do insumo deve refletir a quantidade consumida para se ter a
produção acabada informada no campo QTD do Registro K250.
Campo 05 – Preenchimento: informar o código do item componente/insumo que estava previsto para ser consumido no
Registro 0210 e que foi substituído pelo COD_ITEM deste registro.
Validação: o código do insumo substituído deve existir no Registro 0210 para o mesmo produto resultante – K250/0200.
REGISTRO K990: ENCERRAMENTO DO BLOCO K
Este registro destina-se a identificar o encerramento do bloco K e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "K990" C 004 - O
02 QTD_LIN_H Quantidade total de linhas do Bloco K N - - O
Página 151 de 209

--- Página 152 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Observações:
Nível hierárquico - 1
Ocorrência –um por arquivo
Campo 01 - Valor Válido: [K990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco K é igual ao valor informado no campo QTD_LIN_K.
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
Página 152 de 209

