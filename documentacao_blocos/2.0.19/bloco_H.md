# Bloco H - Versão 2.0.19

**Data de Criação:** 2016-05-01  
**Páginas:** 166-183  
**Versão:** 2.0.19

---

--- Página 166 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Campo 07 (CHV_NFE_CTE) - Preenchimento: Informar chave dos documentos eletrônicos.
Campo 08 (DT_DOC) - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação.
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
Campo 01 (REG) -: valor válido: [G140];
Campo 03 (COD_ITEM) - validação: o valor informado neste campo deve existir no registro 0200.
REGISTRO G990: ENCERRAMENTO DO BLOCO G
Este registro deve ser gerado para o encerramento do bloco G e indica o número total de registros existentes neste bloco.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "G990" C 004* - O
02 QTD_LIN_G Quantidade total de linhas do Bloco G N - - O
Observações:
Nível hierárquico - 1
Ocorrência - um (por arquivo)
Campo 01 (REG) -: valor válido: [G990];
BLOCO H: INVENTÁRIO FÍSICO
Este bloco destina-se a informar o inventário físico do estabelecimento, nos casos e prazos previstos na legislação
pertinente.
Para que o Bloco H seja utilizado como Registro de Inventário para efeito de imposto de renda o contribuinte
deve:
a) acrescentar os bens cujo inventário não é exigido para fins do IPI/ICMS, mas apenas pela legislação do
Imposto de Renda (bens em almoxarifado);
b) acrescentar o valor unitário dos bens, de acordo com os critérios exigidos pela legislação do Imposto de Renda,
quando discrepante dos critérios previstos na legislação do IPI/ICMS, conduzindo-se ao valor contábil dos estoques. Esse
acréscimo é autorizado pelo Convênio Sinief/1970, art. 63, § 12, como "Outras indicações" e será informado no campo 11
- VL_ITEM_IR do registro H010 - Inventário.
As pessoas jurídicas do segmento de construção civil dispensadas de apresentar a Escrituração Fiscal Digital
(EFD) pelos estados e obrigadas a escriturar o livro Registro de Inventário devem apresentá-lo na Escrituração Contábil
Digital, como um livro auxiliar, conforme art. 3º, parágrafo 5º, da IN RFB 1420/2013, com a nova redação da IN RFB
1486/2014.
REGISTRO H001: ABERTURA DO BLOCO H
Este registro deve ser gerado para abertura do bloco H, indicando se há registros de informações no bloco.
Obrigatoriamente deverá ser informado “0” no campo IND_MOV no período de referência fevereiro de cada ano. , ,
Contribuinte que apresente inventário com periodicidade anual ou trimestral, caso apresente o inventário de 31/12
na EFD ICMS IPI de dezembro ou janeiro, deve repetir a informação na escrituração de fevereiro.
Página 166 de 246

--- Página 167 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H001" C 004 - O
02 IND_MOV Indicador de movimento: C 001* - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 (REG) - Valor Válido: [H001]
Campo 02 (IND_MOV) - Valores Válidos: [0,1]
Validação: se preenchido com ”1” (um), devem ser informados os registros H001 e H990 (encerramento do bloco),
significando que não há escrituração de inventário. Se preenchido com ”0” (zero), então deve ser informado pelo menos
um registro além do registro H990 (encerramento do bloco).
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
Campo 01 (REG) - Valor Válido: [H005]
Campo 02 (DT_INV) - Preenchimento: informar a data do inventário no formato “ddmmaaaa”, sem separadores de
formatação.
Validação: o valor informado no campo deve ser menor ou igual ao valor no campo DT_FIN do registro 0000. O
inventário (MOT_INV = 1) não pode ser apresentado após o 2o. mês subsequente à data informada no campo 02
(DT_INV).
Campo 03 (VL_INV) - Validação: deve ser igual à soma do campo VL_ITEM do registro H010. Se não houver registro
H010, o valor neste campo deve ser “0” (zero).
Campo 04 (MOT_INV) – Valores Válidos: [ 01, 02, 03, 04, 05]
Preenchimento: Informe o motivo do Inventário:
Página 167 de 246

--- Página 168 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
01 - No final no período - quando se tratar do estoque final mensal ou outra periodicidade. Deverá ser
informado pela empresa que está obrigada a inventário periódico ou que espontaneamente queira apresentá-
lo;
02 – Na mudança de forma de tributação da mercadoria - quando, por exigência da legislação ou por
regime especial, houver alteração da forma de tributação da mercadoria. Neste caso, se a legislação
determinar, o inventário pode ser parcial.
Exemplo: mercadoria no sistema de tributação por conta corrente fiscal (crédito e débito) e a legislação passa
a cobrar o ICMS por substituição tributária;
03 - Na solicitação de baixa cadastral – por ocasião da solicitação da baixa cadastral, paralisação
temporária e outras situações.
04 - Na alteração de regime de pagamento – condição do contribuinte – quando o contribuinte muda de
condição, alterando o regime de pagamento.
Exemplo: Mudança da condição “Normal” por inclusão no “Simples Nacional” ou inclusão em “Regime
Especial”;
05 - Por solicitação da fiscalização - quando se tratar de solicitação específica da fiscalização.
REGISTRO H010: INVENTÁRIO.
Este registro deve ser informado para discriminar os itens existentes no estoque. Este registro não pode ser
fornecido se o campo 03 (VL_INV) do registro H005 for igual a “0” (zero). A partir de janeiro de 2015, caso o
contribuinte utilize o bloco H para atender à legislação do Imposto de Renda, especificamente o artigo 261 do
Regulamento do Imposto de Renda – RIR/99 – Decreto nº 3.000/1999, deverá informar neste registro, além dos itens
exigidos pelas legislações do ICMS e do IPI, aqueles bens exigidos pela legislação do Imposto de Renda.
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
Campo 01 (REG) - Valor Válido: [H010]
Campo 02 (COD_ITEM) - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
Campo 03 (UNID) - Validação: o valor deve ser informado no registro 0200, campo UNID_INV.
Campo 07 (IND_PROP) - Valores Válidos: [0, 1, 2]
Validação: se preenchido com valor ‘1’ (posse de terceiros) ou ‘2’ (propriedade de terceiros), o campo COD_PART será
obrigatório.
Campo 08 (COD_PART) – Preenchimento obrigatório quando o indicador de propriedade do item do campo 07 for
“1” ou “2”.
Validação: o valor fornecido deve constar no campo COD_PART do registro 0150.
Página 168 de 246

--- Página 169 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Campo 10 (COD_CTA) - Preenchimento: informar o código da conta analítica contábil correspondente. Deve ser a conta
credora ou devedora principal, podendo ser informada a conta sintética (nível acima da conta analítica). Nas situações de
um mesmo código de item possuir mais de uma destinação deve ser informada a conta referente ao item de maior
relevância. Este campo é obrigatório somente para os perfis A e B.
Campo 11 (VL_ITEM_IR) - Preenchimento: válido a partir de 01 de janeiro de 2015. É igual ao campo 06 – VL_ITEM
com adições ou exclusões previstas no RIR/99. Informar o valor do item utilizando os critérios previstos na legislação do
Imposto de Renda, especificamente artigos 292 a 297 do RIR/99 – Decreto nº 3.000/99, por vezes discrepantes dos
critérios previstos na legislação do IPI/ICMS, conduzindo-se ao valor contábil dos estoques. Esse acréscimo é autorizado
pelo Convênio Sinief/1970, art. 63, § 12, como "Outras indicações". Um exemplo de diferença entre as legislações é o
valor do ICMS recuperável mediante crédito na escrita fiscal do adquirente, que não integra o custo de aquisição para
efeito do Imposto de Renda. O montante desse imposto, destacado em nota fiscal, deve ser excluído do valor dos estoques
para efeito do imposto de renda. Tratamento idêntico deve ser aplicado ao PIS-Pasep e à Cofins não cumulativos,
instituídos pelas Leis nºs 10.637/2002 e 10.833/2003, respectivamente. Observe-se, porém, que as legislações do IPI e do
ICMS não contemplam essas exclusões. Trata-se dos valores para fins fiscais não contemplando as informações da
contabilidade societária.
REGISTRO H020: Informação complementar do Inventário.
Este registro deve ser preenchido para complementar as informações do inventário, quando o campo MOT_INV
do registro H005 for de “02” a “05”. Não informar, se o campo 03 (VL_INV) do registro H005 for igual a “0” (zero).
No caso de mudança da forma de tributação do ICMS da mercadoria (MOT_INV=2 do H005), somente deverá
ser gerado esse registro para os itens que sofreram alteração da tributação do ICMS.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H020" C 004 - O
02 CST_ICMS Código da Situação Tributária referente ao ICMS, conforme a N 003* - O
Tabela indicada no item 4.3.1
03 BC_ICMS Informe a base de cálculo do ICMS N - 02 O
04 VL_ICMS Informe o valor do ICMS a ser debitado ou creditado N 02 O
Obs.:Registro válido a partir de julho/2012.
Nível hierárquico - 4
Ocorrência – 1:N
Campo 02 (CST_ICMS) - Preenchimento: informar o código CST (sob o enfoque do declarante) aplicável ao item,
válido na data do levantamento do estoque. Se MOT_INV = 2 ou 4 (campo 04 do registro H005), informar o CST
aplicável ao item, após a alteração.
Campo 03 (BC_ICMS) -: Preenchimento: informar a base de cálculo aplicável ao item (valor unitário). Se MOT_INV =
2 ou 4 (campo 04 do registro H005), informar a base de cálculo aplicável ao item (valor unitário), após a alteração.
Campo 04 (VL_ICMS) -: Preenchimento: informar o ICMS aplicável ao item (valor unitário), utilizando a alíquota
interna. Se MOT_INV = 2 ou 4 (campo 04 do registro H005), informar o ICMS aplicável ao item (valor unitário), após a
alteração.
REGISTRO H990: ENCERRAMENTO DO BLOCO H.
Este registro destina-se a identificar o encerramento do bloco H e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "H990" C 004 - O
02 QTD_LIN_H Quantidade total de linhas do Bloco H N - - O
Observações:
Nível hierárquico - 1
Ocorrência –um por arquivo
Campo 01 (REG) - Valor Válido: [H990]
Campo 02 (QTD_LIN_H) - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios
registros de abertura e encerramento do bloco.
Página 169 de 246

--- Página 170 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Validação: o número de linhas (registros) existentes no bloco H é igual ao valor informado no campo QTD_LIN_H.
BLOCO K: CONTROLE DA PRODUÇÃO E DO ESTOQUE
Este bloco se destina a prestar informações mensais da produção e respectivo consumo de insumos, bem como do
estoque escriturado, relativos aos estabelecimentos industriais ou a eles equiparados pela legislação federal e pelos
atacadistas, podendo, a critério do Fisco, ser exigido de estabelecimento de contribuintes de outros setores (conforme § 4º
do art. 63 do Convênio s/número, de 1970). O bloco K entrará em vigor na EFD a partir de 2016.
Os contribuintes optantes pelo Simples Nacional estão dispensados de apresentarem este bloco, em virtude da
Resolução Comitê Gestor do Simples Nacional nº 94, de 29 de novembro de 2011, e alterações posteriores
(http://www.receita.fazenda.gov.br/Legislacao/Resolucao/2011/CGSN/Resol94.htm), que lista os livros
obrigatórios do Regime Especial Unificado de Arrecadação de Tributos e Contribuições devidos pelas Microempresas e
Empresas de Pequeno Porte - Simples Nacional.
REGISTRO K001: ABERTURA DO BLOCO K
Este registro deve ser gerado para abertura do bloco K, indicando se há registros de informações no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "K001" C 004 - O
02 IND_MOV Indicador de movimento: C 001* - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações: obrigatoriedade a partir de 2016
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 (REG) - Valor Válido: [K001]
Campo 02 (IND_MOV) - Valores Válidos: [0,1]
Validação: se preenchido com ”1” (um), devem ser informados os registros K001 e K990 (encerramento do bloco),
significando que não há informação do controle da produção e do estoque. Se preenchido com ”0” (zero), então deve ser
informado pelo menos um registro K100 e seus respectivos registros filhos, além do registro K990 (encerramento do
bloco).
REGISTRO K100: PERÍODO DE APURAÇÃO DO ICMS/IPI
Este registro tem o objetivo de informar o período de apuração do ICMS ou do IPI, prevalecendo os períodos
mais curtos. Contribuintes com mais de um período de apuração no mês declaram um registro K100 para cada período no
mesmo arquivo. Não podem ser informados dois ou mais registros com os mesmos campos DT_INI e DT_FIN.
Os períodos informados neste registro deverão abranger todo o período da escrituração, conforme informado no
Registro 0000.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K100" C 4 - O
02 DT_INI Data inicial a que a apuração se refere N 8 - O
03 DT_FIN Data final a que a apuração se refere N 8 - O
Observações:
Nível hierárquico - 2
Ocorrência – Vários
Campo 01 (REG) - Valor Válido: [K100]
Campo 02 (DT_INI) – Validação: a data inicial deve estar compreendida no período informado nos campos DT_INI e
DT_FIN do Registro 0000.
Campo 03 (DT_FIN) – Validação: a data final deve estar compreendida no período informado nos campos DT_INI e
DT_FIN do Registro 0000.
Página 170 de 246

--- Página 171 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
REGISTRO K200: ESTOQUE ESCRITURADO
Este registro tem o objetivo de informar o estoque final escriturado do período de apuração informado no Registro
K100, por tipo de estoque e por participante, nos casos em que couber, das mercadorias de tipos 00 – Mercadoria para
revenda, 01 – Matéria-Prima, 02 - Embalagem, 03 – Produtos em Processo, 04 – Produto Acabado, 05 – Subproduto, 06 –
Produto Intermediário e 10 – Outros Insumos – campo TIPO_ITEM do Registro 0200.
A informação de estoque zero (quantidade = 0) não deixa de ser uma informação e o PVA não a impede.
Entretanto, caso não seja prestada essa informação, será considerado que o estoque é igual a zero. Portanto, é desnecessária
a informação de estoque zero caso não exista quantidade em estoque, independentemente de ter havido movimentação.
A quantidade em estoque deve ser expressa, obrigatoriamente, na unidade de medida de controle de estoque
constante no campo 06 do registro 0200 –UNID_INV.
A chave deste registro são os campos: DT_EST, COD_ITEM, IND_EST e COD_PART (este, quando houver).
O estoque escriturado informado no Registro K200 deve refletir a quantidade existente na data final do período de
apuração informado no Registro K100, estoque este derivado dos apontamentos de estoque inicial / entrada / produção
/consumo / saída / movimentação interna. Considerando isso, o estoque escriturado informado no K200 é resultante da
seguinte fórmula:
Estoque final = estoque inicial + entradas/produção/movimentação interna – Saída / consumo /movimentação
interna.
Os estabelecimentos equiparados a industriais e atacadistas devem informar o estoque escriturado – K200 - e,
caso ocorram movimentações internas, o K220.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K200" C 4 - O
02 DT_EST Data do estoque final N 8 - O
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 60 - O
04 QTD Quantidade em estoque N - 3 O
05 IND_EST Indicador do tipo de estoque: C 1 - O
0 = Estoque de propriedade do informante e
em seu poder;
1 = Estoque de propriedade do informante e
em posse de terceiros;
2 = Estoque de propriedade de terceiros e em
posse do informante
06 COD_PART Código do participante (campo 02 do Registro C 60 - OC
0150):
- proprietário/possuidor que não seja o
informante do arquivo
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K200]
Campo 02 (DT_EST) – Validação: a data do estoque deve ser igual à data final do período de apuração – campo DT_FIN
do Registro K100.
Campo 03 (COD_ITEM) – Validação: o código do item deverá existir no campo COD_ITEM do Registro 0200. Somente
podem ser informados nesse campo valores de COD_ITEM cujos tipos sejam iguais a 00, 01, 02, 03, 04, 05, 06 e 10 –
campo TIPO_ITEM do Registro 0200.
Campo 05 (IND_EST) - Valores Válidos: [0, 1, 2]
Validação: se preenchido com valor ‘1’ (posse de terceiros) ou ‘2’ (propriedade de terceiros), o campo COD_PART será
obrigatório.
A quantidade em estoque existente no estabelecimento industrializador do produto industrializado para terceiro por
encomenda deverá ser:
a) quando o informante for o estabelecimento industrializador , do tipo 2 - estoque de propriedade de terceiros e em posse
do informante;
Página 171 de 246

--- Página 172 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
b) quando o informante for o estabelecimento encomendante, do tipo 1 - estoque de propriedade do informante e em posse
de terceiros.
A quantidade em estoque existente no estabelecimento industrializador de insumo recebido do encomendante para
industrialização por encomenda deverá ser:
a) quando o informante for o estabelecimento industrializador, do tipo 2 - estoque de propriedade de terceiros e em posse
do informante,;
b) quando o informante for o estabelecimento encomendante, do tipo 1 - estoque de propriedade do informante e em posse
de terceiros.
Campo 06 (COD_PART) – Preenchimento: obrigatório quando o IND_EST for “1” ou “2”.
Validação: o valor fornecido deve constar no campo COD_PART do registro 0150.
REGISTRO K210: DESMONTAGEM DE MERCADORIAS – ITEM DE ORIGEM
Este registro tem o objetivo de escriturar a desmontagem de mercadorias de tipos: 00 – Mercadoria para revenda; 01 –
Matéria-Prima; 02 – Embalagem; 03 – Produtos em Processo; 04 – Produto Acabado; 05 – Subproduto e 10 – Outros
Insumos – campo TIPO_ITEM do Registro 0200, no que se refere à saída do estoque do item de origem.
A quantidade deve ser expressa, obrigatoriamente, na unidade de medida de controle de estoque constante no campo 06 do
registro 0200: UNID_INV.
Quando houver identificação da ordem de serviço, a chave deste registro são os campos: COD_DOC_OS e
COD_ITEM_ORI.
Nos casos em que a ordem de serviço não for identificada, o campo chave passa a ser COD_ITEM_ORI.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K210" C 004 - O
02 DT_INI_OS Data de início da ordem de serviço N 008* - OC
03 DT_FIN_OS Data de conclusão da ordem de serviço N 008* - OC
04 COD_DOC_OS Código de identificação da ordem de C 030 - OC
serviço
05 COD_ITEM_ORI Código do item de origem (campo 02 C 060 - O
do Registro 0200)
06 QTD_ORI Quantidade de origem – saída do N - 03 O
estoque
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K210]
Campo 02 (DT_INI_OS) - Preenchimento: a data de início deverá ser informada se existir ordem de serviço, ainda que
iniciada em período de apuração (K100) anterior.
Validação: obrigatório se informado o campo COD_DOC_OS ou o campo DT_FIN_OS. A data informada deve ser
menor ou igual a DT_FIN do registro K100.
Campo 03 (DT_FIN_OS) - Preenchimento: informar a data de conclusão da ordem de serviço. Ficará em branco, caso a
ordem de serviço não seja concluída até a data de encerramento do período de apuração.
Validação: se preenchido, DT_FIN_OS deve estar compreendida no período de apuração do K100 e ser maior ou igual a
DT_INI_OP.
Campo 04 (COD_DOC_OS) – Preenchimento: informar o código da ordem de serviço, caso exista.
Validação: obrigatório se informado o campo DT_INI_OS.
Campo 05 (COD_ITEM_ORI) - Validação: o código do item de origem deverá existir no campo COD_ITEM do Registro
0200.
Página 172 de 246

--- Página 173 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Campo 06 (QTD_ORI) – Preenchimento: não é admitida quantidade negativa.
REGISTRO K215: DESMONTAGEM DE MERCADORIAS – ITENS DE DESTINO
Este registro tem o objetivo de escriturar a desmontagem de mercadorias de tipos: 00 – Mercadoria para revenda; 01 –
Matéria-Prima; 02 – Embalagem; 03 – Produtos em Processo; 04 – Produto Acabado; 05 – Subproduto e 10 – Outros
Insumos – campo TIPO_ITEM do Registro 0200, no que se refere à entrada em estoque do item de destino.
Este registro é obrigatório caso exista o registro-pai K210 e o controle da desmontagem não for por ordem de serviço
(campos DT_INI_OS, DT_FIN_OS e COD_DOC_OS do Registro K210 em branco). Nesse caso, a saída do estoque do
item de origem e a entrada em estoque do item de destino têm de ocorrer no período de apuração do Registro K100.
A quantidade deve ser expressa, obrigatoriamente, na unidade de medida de controle de estoque constante no campo 06 do
registro 0200: UNID_INV.
A chave deste registro é o campo COD_ITEM_DES.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K215" C 004 - O
02 COD_ITEM_DES Código do item de destino (campo 02 C 060 - O
do Registro 0200)
03 QTD_DES Quantidade de destino – entrada em N - 03 O
estoque
Observações:
Nível hierárquico - 4
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K215]
Campo 02 (COD_ITEM_DES) - Validação:
a) o código informado deve ser diferente do campo COD_ITEM_ORI do Registro K210;
b) o código do item de destino deverá existir no campo COD_ITEM do Registro 0200.
Campo 03 (QTD_DES) – Preenchimento: não é admitida quantidade negativa.
REGISTRO K220: OUTRAS MOVIMENTAÇÕES INTERNAS ENTRE
MERCADORIAS
Este registro tem o objetivo de informar a movimentação interna entre mercadorias de tipos: 00 – Mercadoria para
revenda; 01 – Matéria-Prima; 02 – Embalagem; 03 – Produtos em Processo; 04 – Produto Acabado; 05 – Subproduto e 10
– Outros Insumos – campo TIPO_ITEM do Registro 0200; que não se enquadre nas movimentações internas já informadas
nos demais tipos de registros.
Exemplo: reclassificação de um produto em outro código em função do cliente a que se destina. O contribuinte
aponta a quantidade produzida de determinado produto, por exemplo, código 1. Este produto, quando destinado a
determinado cliente recebe uma outra codificação, código 2. Neste caso há a necessidade de controle do estoque por
cliente. Assim o contribuinte deverá fazer um registro K220 dando saída no estoque do produto 1 e entrada no estoque do
produto 2.
A quantidade movimentada deve ser expressa, obrigatoriamente, na unidade de medida do item de origem,
constante no campo 06 do registro 0200: UNID_INV.
A chave deste registro são os campos: DT_MOV, COD_ITEM_ORI e COD_ITEM_DEST.
Página 173 de 246

--- Página 174 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K220" C 4 - O
02 DT_MOV Data da movimentação interna N 8 - O
03 COD_ITEM_ORI Código do item de origem (campo 02 do C 60 - O
Registro 0200)
04 COD_ITEM_DEST Código do item de destino (campo 02 do C 60 - O
Registro 0200)
05 QTD Quantidade movimentada N - 3 O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K220]
Campo 02 (DT_MOV) -: Validação: a data deve estar compreendida no período informado nos campos DT_INI e
DT_FIN do Registro K100.
Campo 03 (COD_ITEM_ORI) -: Validação: o código do item de origem deverá existir no campo COD_ITEM do
Registro 0200.
Campo 04 (COD_ITEM_DEST) -: Validação: o código do item de destino deverá existir no campo COD_ITEM do
Registro 0200. O valor informado deve ser diferente do COD_ITEM_ORI.
Campo 05 (QTD) -: Preenchimento: informar a quantidade movimentada do item de origem codificado no campo
COD_ITEM_ORI.
REGISTRO K230: ITENS PRODUZIDOS
Este registro tem o objetivo de informar a produção acabada de produto em processo (tipo 03 – campo
TIPO_ITEM do registro 0200) e produto acabado (tipo 04 – campo TIPO_ITEM do registro 0200), inclusive daquele
industrializado para terceiro por encomenda. O produto resultante é classificado como tipo 03 – produto em processo,
quando não estiver pronto para ser comercializado, mas estiver pronto para ser consumido em outra fase de produção. O
produto resultante é classificado como tipo 04 – produto acabado, quando estiver pronto para ser comercializado.
Deverá existir mesmo que a quantidade de produção acabada seja igual a zero, nas situações em que exista o
consumo de item componente/insumo no registro filho K235. Nessa situação a produção ficou em elaboração. Essa
produção em elaboração não é quantificada, uma vez que a matéria não é mais um insumo e nem é ainda um produto
resultante.
Devem ser informadas:
a) as OP iniciadas e concluídas no período de apuração (K100);
b) as OP iniciadas e não concluídas no período de apuração (OP em que a produção ficou em elaboração), em que
haja informação de produção e/ou consumo de insumos (K235);
c) as OP iniciadas em período anterior e concluídas no período de apuração;
d) as OP iniciadas em período anterior e não concluídas no período de apuração, em que haja informação de
produção e/ou consumo de insumos (K235).
Quando a informação for por período de apuração (K100), o K230 somente deve ser informado caso ocorra
produção no período, com o respectivo consumo de insumos no K235 para se ter essa produção, uma vez que não se teria
como vincular a quantidade consumida de insumos com a quantidade produzida do produto resultante envolvendo mais de
um período de apuração. Somente podemos ter produção igual a zero no K230 quando a informação for por ordem de
produção e quando essa OP não for concluída até a data final do período de apuração do K100 e quando houver o
apontamento de consumo de insumos no K235.
A ordem de produção que não for finalizada no período de apuração deve informar a data de conclusão da ordem
de produção em branco, campo 03 – DT_FIN_OP. No período seguinte, e assim sucessivamente, a ordem de produção
deve ser informada até que seja concluída e caso exista apontamento de quantidade produzida e/ou quantidade consumida
de insumo (K235).
A quantidade de produção acabada deve ser expressa, obrigatoriamente, na unidade de medida de controle de
estoque constante no campo 06 do registro 0200: UNID_INV.
Quando houver identificação da ordem de produção, a chave deste registro são os campos: COD_DOC_OP e
COD_ITEM.
Nos casos em que a ordem de produção não for identificada, o campo chave passa a ser COD_ITEM.
Página 174 de 246

--- Página 175 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K230" C 4 - O
02 DT_INI_OP Data de início da ordem de produção N 8 - OC
03 DT_FIN_OP Data de conclusão da ordem de produção N 8 - OC
04 COD_DOC_OP Código de identificação da ordem de produção C 30 - OC
05 COD_ITEM Código do item produzido (campo 02 do C 60 - O
Registro 0200)
06 QTD_ENC Quantidade de produção acabada N - 3 O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K230]
Campo 02 (DT_INI_OP) - Preenchimento: a data de início deverá ser informada se existir ordem de produção, ainda que
iniciada em período de apuração cujo registro K100 correspondente esteja em um arquivo relativo a um mês anterior.
Validação: obrigatório se informado o campo COD_DOC_OP ou o campo DT_FIN_OP. O valor informado deve ser
menor ou igual a DT_FIN do registro K100.
Campo 03 (DT_FIN_OP) - Preenchimento: informar a data de conclusão da ordem de produção. Ficará em branco, caso
a ordem de produção não seja concluída até a data de encerramento do período de apuração. Nesta situação a produção
ficou em elaboração.
Validação: se preenchido, DT_FIN_OP deve estar compreendida no período de apuração do K100 e ser maior ou igual a
DT_INI_OP.
Campo 04 (COD_DOC_OP) – Preenchimento: informar o código da ordem de produção.
Validação: obrigatório se informado o campo DT_INI_OP.
Campo 05 (COD_ITEM) – Validação: o código do item produzido deverá existir no campo COD_ITEM do Registro
0200.
Campo 06 (QTD_ENC) – Preenchimento: não é admitida quantidade negativa.
REGISTRO K235: INSUMOS CONSUMIDOS
Este registro tem o objetivo de informar o consumo de mercadoria no processo produtivo, vinculado ao produto
resultante informado no campo COD_ITEM do Registro K230 – Itens Produzidos.
Na industrialização efetuada para terceiro por encomenda devem ser considerados os insumos recebidos do
encomendante e os insumos próprios do industrializador.
Este registro é obrigatório quando existir o registro pai K230 e:
a)a informação da quantidade produzida (K230) for por período de apuração(K100); ou
b) a ordem de produção (K230) se iniciar e concluir no período de apuração (K100); ou
c) a ordem de produção (K230) se iniciar no período de apuração (K100) e não for concluída no mesmo período.
A quantidade consumida deve ser expressa, obrigatoriamente, na unidade de medida de controle de estoque
constante no campo 06 do registro 0200: UNID_INV.
A chave deste registro são os campos DT_SAÍDA e COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K235" C 4 - O
02 DT_SAÍDA Data de saída do estoque para alocação ao N 8 - O
produto
03 COD_ITEM Código do item componente/insumo (campo C 60 - O
02 do Registro 0200)
04 QTD Quantidade consumida do item N - 3 O
05 COD_INS_SUBST Código do insumo que foi substituído, caso C 60 - OC
ocorra a substituição (campo 02 do Registro
0210)
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Página 175 de 246

--- Página 176 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Campo 01 (REG) - Valor Válido: [K235]
Campo 02 (DT_SAÍDA) - Validação: a data deve estar compreendida no período da ordem de produção, se existente,
campos DT_INI_OP e DT_FIN_OP do Registro K230. Se DT_FIN_OP do Registro K230 – Itens Produzidos estiver em
branco, o campo DT_SAÍDA deverá ser maior que o campo DT_INI_OP do Registro K230 e menor ou igual a DT_FIN
do Registro K100. E em qualquer hipótese a data deve estar compreendida no período de apuração – K100.
Campo 03 (COD_ITEM) – Validações:
a) o código do item componente/insumo deverá existir no campo COD_ITEM do Registro 0200;
b) caso o campo COD_INS_SUBST esteja em branco, o código do item componente/insumo deve existir também no
Registro 0210 para o mesmo produto resultante – K230/0200;
c) o código do item componente/insumo deve ser diferente do código do produto resultante (COD_ITEM do Registro
K230);
d) o tipo do componente/insumo (campo TIPO_ITEM do Registro 0200) deve ser igual a 00, 01, 02, 03, 04, 05 ou 10.
A quantidade consumida de produto intermediário – tipo 06 no processo produtivo não é escriturada na EFD ICMS/IPI,
tanto no Bloco K quanto no Bloco C (NF-e). Se o Fisco quiser saber qual foi a quantidade consumida de produto
intermediário no processo produtivo basta aplicar a fórmula : Quantidade consumida = estoque inicial (K200) + entrada
(C170) – saída (C100/NF-e - Devolução) – estoque final (K200).
Campo 04 (QTD) – Preenchimento: não é admitida quantidade negativa. O apontamento de insumo/componente, cujo
controle não permita um apontamento direto ao produto resultante, poderá ser efetuado pelo critério de rateio do
contribuinte, limitado ao total consumido no período de apuração.
Campo 05 (COD_INS_SUBST) – Preenchimento: informar o código do item componente/insumo que estava previsto
para ser consumido no Registro 0210 e que foi substituído pelo COD_ITEM deste registro.
Validação: o código do insumo substituído deve existir no Registro 0210 para o mesmo produto resultante – K230/0200.
REGISTRO K250: INDUSTRIALIZAÇÃO EFETUADA POR TERCEIROS – ITENS
PRODUZIDOS
Este registro tem o objetivo de informar os produtos que foram industrializados por terceiros por encomenda e sua
quantidade.
A quantidade produzida deve ser expressa, obrigatoriamente, na unidade de medida de controle de estoque
constante no campo 06 do registro 0200: UNID_INV.
A chave deste registro são os campos DT_PROD e COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K250" C 4 - O
02 DT_PROD Data do reconhecimento da produção ocorrida no N 8 - O
terceiro
03 COD_ITEM Código do item produzido (campo 02 do Registro C 60 - O
0200)
04 QTD Quantidade produzida N - 3 O
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K250]
Campo 02 (DT_PROD) - Validação: a data deve estar compreendida no período informado nos campos DT_INI e
DT_FIN do Registro K100.
Campo 03 (COD_ITEM) – Validações:
a) o código do item produzido deverá existir no campo COD_ITEM do Registro 0200;
b) o TIPO_ITEM do Registro 0200 deve ser igual a 03 – Produto em Processo ou 04 – Produto Acabado.
Campo 04 (QTD) - Preenchimento: a quantidade produzida deve considerar a quantidade que foi recebida do terceiro e a
variação de estoque ocorrida em terceiro. Cada legislação estadual prevê situações específicas. Consulte a Secretaria de
Fazenda/Tributação de seu estado. Não é admitida quantidade negativa.
Página 176 de 246

--- Página 177 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
REGISTRO K255: INDUSTRIALIZAÇÃO EM TERCEIROS – INSUMOS
CONSUMIDOS
Este registro tem o objetivo de informar a quantidade de consumo do insumo que foi remetido para ser
industrializado em terceiro, vinculado ao produto resultante informado no campo COD_ITEM do Registro K250. É
obrigatório caso exista o registro pai K250. No caso de SP considerar insumos remetidos ao industrializador e os
adquiridos pelo industrializador e consumidos no processo produtivo.
A quantidade consumida deve ser expressa, obrigatoriamente, na unidade de medida de controle de estoque
constante no campo 06 do registro 0200: UNID_INV.
A chave deste registro são os campos DT_CONS e COD_ITEM deste Registro.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K255" C 4 - O
02 DT_CONS Data do reconhecimento do consumo do N 8 - O
insumo referente ao produto informado no
campo 04 do Registro K250
03 COD_ITEM Código do insumo (campo 02 do Registro C 60 - O
0200)
04 QTD Quantidade de consumo do insumo. N - 3 O
05 COD_INS_SUBST Código do insumo que foi substituído, caso C 60 - OC
ocorra a substituição (campo 02 do Registro
0210)
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 (REG) - Valor Válido: [K255]
Campo 02 (DT_CONS) - Validação: a data deve estar compreendida no período informado nos campos DT_INI e
DT_FIN do Registro K100.
Campo 03 (COD_ITEM) – Validações:
a) o código do insumo deverá existir no campo COD_ITEM do Registro 0200;
b) caso o campo COD_INS_SUBST esteja em branco, o código do item componente/insumo deve existir também no
Registro 0210 para o mesmo produto resultante – K250/0200;
c) O código do insumo deve ser diferente do código do produto resultante (COD_ITEM do Registro K250 –
Indutrialização efetuada por terceitos – itens produzidos);
d) o tipo do componente/insumo (campo TIPO_ITEM do Registro 0200) deve ser igual a 00, 01, 02, 03, 04, 05 ou 10.
Campo 04 (QTD) - Preenchimento: a quantidade de consumo do insumo deve refletir a quantidade consumida para se ter
a produção acabada informada no campo QTD do Registro K250. . Não é admitida quantidade negativa. O apontamento de
insumo/componente, cujo controle não permita um apontamento direto ao produto resultante, poderá ser efetuado pelo
critério de rateio do contribuinte, limitado ao total consumido no período de apuração.
Campo 05 (COD_INS_SUBST) – Preenchimento: informar o código do item componente/insumo que estava previsto
para ser consumido no Registro 0210 e que foi substituído pelo COD_ITEM deste registro.
Validação: o código do insumo substituído deve existir no Registro 0210 para o mesmo produto resultante – K250/0200.
REGISTRO K260: REPROCESSAMENTO/REPARO DE PRODUTO/INSUMO
Este registro tem o objetivo de informar o produto que será reprocessado ou que foi reprocessado e o insumo que será
reparado ou que foi reparado no período de apuração do Registro K100.
Página 177 de 246

--- Página 178 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Quando a informação for por período de apuração (K100), onde não existirá o controle por ordem de produção ou serviço,
o registro K260 somente deve ser informado caso ocorra saída e respectivo retorno ao estoque de produto/insumo no
período de apuração, com o respectivo consumo de mercadorias no K265 para se ter esse reprocessamento/reparo, caso
seja necessário, uma vez que não se teria como vincular a quantidade consumida de mercadorias com a quantidade que
saiu do produto/insumo envolvendo mais de um período de apuração.
As quantidades de saída ou retorno ao estoque devem ser expressas, obrigatoriamente, na unidade de medida de controle
de estoque constante no campo 06 do registro 0200: UNID_INV.
Quando houver identificação da ordem de produção ou serviço, a chave deste registro são os campos: COD_OP_OS e
COD_ITEM. No caso em que a ordem de produção ou serviço não for identificada, o campo chave passa a ser
COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K260" C 004 - O
02 COD_OP_OS Código de identificação da ordem de C 030 - OC
produção, no reprocessamento, ou da
ordem de serviço, no reparo
03 COD_ITEM Código do produto/insumo a ser C 060 - O
reprocessado/reparado ou já
reprocessado/reparado (campo 02 do
Registro 0200)
04 DT_SAÍDA Data de saída do estoque N 008* - O
05 QTD_SAÍDA Quantidade de saída do estoque N - 03 O
06 DT_RET Data de retorno ao estoque (entrada) N 008* - OC
07 QTD_RET Quantidade de retorno ao estoque (entrada) N - 03 OC
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K260]
Campo 02 (COD_OP_OS) – Preenchimento: informar o código de identificação da ordem de produção, no
reprocessamento, ou da ordem de serviço, no reparo, caso exista.
Validação: obrigatório se o campo DT_RET não for preenchido e o campo DT_SAÍDA estiver no período de apuração do
K100.
Campo 03 (COD_ITEM) – Validação: o código do produto/insumo a ser reprocessado ou já processado deverá existir no
campo COD_ITEM do Registro 0200.
Campo 04 (DT_SAÍDA) - Validação: a data informada deve ser menor ou igual a DT_FIN do registro K100.
Campo 05 (QTD_SAÍDA) – Preenchimento: não é admitida quantidade negativa.
Campo 06 (DT_RET) – Validação: a data deve estar compreendida no período de apuração – K100 e ser maior que
DT_SAÍDA.
Campos 04 e 06 (DT_SAÍDA e DT_RET) – as datas de saída e retorno ao estoque do produto/insumo substituem,
respectivamente, as datas de início e conclusão da ordem de produção/serviço.
Campo 07 (QTD_RET) – Preenchimento: não é admitida quantidade negativa.
Validação: este campo será obrigatório caso o campo DT_RET estiver preenchido.
REGISTRO K265: REPROCESSAMENTO/REPARO - MERCADORIAS
CONSUMIDAS E/OU RETORNADAS
Este registro tem o objetivo de informar o consumo de mercadoria e/ou o retorno de mercadoria ao estoque, ocorridos no
reprocessamento/reparo de produto/insumo informado no Registro K260.
Página 178 de 246

--- Página 179 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
A quantidade deve ser expressa, obrigatoriamente, na unidade de medida de controle de estoque constante no campo 06 do
registro 0200: UNID_INV.
A chave deste registro é o campo COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K265" C 004 - O
02 COD_ITEM Código da mercadoria (campo 02 do C 060 - O
Registro 0200)
03 QTD_CONS Quantidade consumida – saída do N - 03 OC
estoque
04 QTD_RET Quantidade retornada – entrada em N - 03 OC
estoque
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 (REG) - Valor Válido: [K265]
Campo 02 (COD_ITEM) – Validações:
a) o código da mercadoria deverá existir no campo COD_ITEM do Registro 0200;
b) o código da mercadoria deve ser diferente do código do produto/insumo reprocessado/ reparado (COD_ITEM do
Registro K260);
c) o tipo da mercadoria (campo TIPO_ITEM do Registro 0200) deve ser igual a 00, 01, 02, 03, 04, 05 ou 10.
Campos 03 (QTD_CONS) e 04 (QTD_RET) – Preenchimento: não é admitida quantidade negativa.
Validação: pelo menos um dos campos é obrigatório.
REGISTRO K270: CORREÇÃO DE APONTAMENTO DOS REGISTROS K210,
K220, K230, K250 E K260
Este registro tem o objetivo de escriturar correção de apontamento de período de apuração anterior, relativo ao Registro-
pai, por tipo de Registro e por período de apuração em que o apontamento será corrigido.
Caso ocorra correção de apontamento apenas do Registro-filho, este Registro deverá ser informado com os campos de
quantidade zerados.
A correção de apontamento tem que ocorrer, obrigatoriamente, entre o levantamento de 02 inventários, uma vez que, com
a contagem do estoque se terá conhecimento de uma eventual necessidade de correção de apontamento.
As quantidades devem ser expressas, obrigatoriamente, na unidade de medida de controle de estoque constante no campo
06 do registro 0200: UNID_INV.
Quando houver identificação da ordem de produção ou da ordem de serviço e do período de apuração, a chave deste
registro são os campos: DT_INI_AP, DT_FIN_AP, COD_OP_OS e COD_ITEM.
No caso em que a ordem de produção ou a ordem de serviço não forem identificadas, a chave deste registro passa a ser
DT_INI_AP, DT_FIN_AP e COD_ITEM.
No caso em que a ordem de produção ou a ordem de serviço e o período de apuração não forem identificados, a chave
deste registro passa a ser COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K270" C 004 - O
02 N 008* - OC
Data inicial do período de apuração em
DT_INI_AP que ocorreu o apontamento que está sendo
corrigido
Página 179 de 246

--- Página 180 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
03 N 008* - OC
Data final do período de apuração em que
DT_FIN_AP ocorreu o apontamento que está sendo
corrigido
04 COD_OP_OS Código de identificação da ordem de C 030 - OC
produção ou da ordem de serviço que está
sendo corrigida
05 COD_ITEM Código da mercadoria que está sendo C 060 - O
corrigido (campo 02 do Registro 0200)
06 N - 03 OC
Quantidade de correção positiva de
QTD_COR_POS apontamento ocorrido em período de
apuração anterior
07 N - 03 OC
Quantidade de correção negativa de
QTD_COR_NEG apontamento ocorrido em período de
apuração anterior
08 1 - correção de apontamento de produção C 001 - O
e/ou consumo relativo aos Registros
K230/K235;
2 - correção de apontamento de produção
e/ou consumo relativo aos Registros
K250/K255;
3 - correção de apontamento de
ORIGEM desmontagem e/ou consumo relativo aos
Registros K210/K215;
4 - correção de apontamento de
reprocessamento/reparo e/ou consumo
relativo aos Registros K260/K265;
5 - correção de apontamento de
movimentação interna relativo ao Registro
K220.
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K270]
Campos 02 e 03 (DT_INI_AP e DT_FIN_AP) – Preenchimento: estes campos poderão não ser preenchidos somente na
hipótese em que o campo 4 (COD_OP_OS), na correção de apontamento, se referir:
a) a uma ordem de produção que esteja em aberto (DT_FIN_OP do Registro K230 em branco) com o campo 08
(ORIGEM) do registro K270 igual a 1, no presente período de apuração do K100 ou em período de apuração
imediatamente anterior ao presente período de apuração do K100;
b) a uma ordem de serviço que esteja em aberto (DT_FIN_OS do Registro K210 em branco) com o campo 08 (ORIGEM)
do registro K270 igual a 3, no presente período de apuração do K100 ou em período de apuração imediatamente anterior
ao presente período de apuração do K100;
c) a uma ordem de produção ou ordem de serviço que esteja em aberto (COD_OP_OS do Registro K260 em branco) com
o campo 08 (ORIGEM) do registro K270 igual a 4, no presente período de apuração do K100 ou em período de apuração
imediatamente anterior ao presente período de apuração do K100.
Validação: a data inicial e a data final têm de ser anteriores à data inicial do período informado no Registro 0000.
Campo 05 (COD_ITEM) – Validação: o código do item produzido que está sendo corrigido deverá existir no campo
COD_ITEM do Registro 0200.
Campos 06 e 07 (QTD_COR_POS e QTD_COR_NEG) – Validação: não é admitida quantidade negativa.
Validação: somente um dos campos pode ser preenchido.
Página 180 de 246

--- Página 181 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
Campo 08 (ORIGEM) – Valores Válidos: [1, 2, 3, 4, 5]
Preenchimento: quando a correção de apontamento se referir ao Registro K220 – origem 5: a correção deste Registro será
relativa ao item de origem da movimentação interna; no Registro-filho K275 será apontada a correção do item de destino.
REGISTRO K275: CORREÇÃO DE APONTAMENTO E RETORNO DE INSUMOS
DOS REGISTROS K215, K220, K235, K255 E K265.
Este registro tem o objetivo de escriturar correção de apontamento de período de apuração anterior, relativo ao Registro-
filho, por tipo de Registro e por período de apuração em que o apontamento será corrigido.
A correção de apontamento tem que ocorrer, obrigatoriamente, entre o levantamento de 02 inventários, uma vez que, com
a contagem do estoque se terá conhecimento de uma eventual necessidade de correção de apontamento.
Este registro poderá também ser escriturado para substituição ou retorno de insumo/componente que já tenha sido baixado
do estoque por consumo efetivo em período de apuração de exercício anterior, desde que vinculado à Ordem de Produção
não encerrada no próprio exercício de abertura da OP.
Caso ocorra correção de apontamento apenas do Registro-pai (K270), este Registro não deverá ser escriturado, exceto
quando a correção tiver como origem o Registro K220 (origem 5 do Registro K270), onde este Registro será obrigatório
para identificação do item de destino, mesmo que não ocorra correção de quantidades.
As quantidades devem ser expressas, obrigatoriamente, na unidade de medida de controle de estoque constante no campo
06 do registro 0200: UNID_INV.
A chave deste registro é o campo COD_ITEM.
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K275" C 004 - O
02 COD_ITEM Código da mercadoria (campo 02 do C 060 - O
Registro 0200)
03 N - 03 OC
Quantidade de correção positiva de
QTD_COR_POS apontamento ocorrido em período de
apuração anterior
04 N - 03 OC
Quantidade de correção negativa de
QTD_COR_NEG apontamento ocorrido em período de
apuração anterior
05 COD_INS_SUBST Código do insumo que foi substituído, C 060 - OC
caso ocorra a substituição, relativo aos
Registros K235/K255.
Observações:
Nível hierárquico - 4
Ocorrência - 1:N
Campo 01 (REG) - Valor Válido: [K275]
Campo 02 (COD_ITEM) – Validação: o código da mercadoria deverá existir no campo COD_ITEM do Registro 0200 e
somente são admitidas mercadorias de tipos 00 a 05 e 10 – campo TIPO_ITEM do Registro 0200.
Campos 03 e 04 (QTD_COR_POS e QTD_COR_NEG) – Validação: não é admitida quantidade negativa.
Validação: somente um dos campos pode ser preenchido.
Campo 05 (COD_INS_SUBST) – Preenchimento: este campo deverá ser informado quando se estiver escriturando
quantidade consumida não apontada em período anterior, e desde que exista a substituição.
Validação: este campo somente pode existir quando a origem da correção de apontamento for dos tipos 1 ou 2 (campo
ORIGEM do Registro K270).
Página 181 de 246

--- Página 182 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
REGISTRO K280: CORREÇÃO DE APONTAMENTO – ESTOQUE ESCRITURADO
Este registro tem o objetivo de escriturar correção de apontamento de estoque escriturado de período de apuração anterior,
escriturado no Registro K200.
A correção de apontamento tem que ocorrer, obrigatoriamente, entre o levantamento de 02 inventários, uma vez que, com
a contagem do estoque se terá conhecimento de uma eventual necessidade de correção de apontamento.
A correção do estoque escriturado de um período de apuração poderá influenciar estoques escriturados de períodos
posteriores, até o período imediatamente anterior ao período de apuração em que se está fazendo a correção, uma vez que o
estoque final de um período de apuração é o estoque inicial do período de apuração seguinte.
As quantidades devem ser expressas, obrigatoriamente, na unidade de medida de controle de estoque constante no campo
06 do registro 0200: UNID_INV.
A chave deste registro são os campos: DT_EST, COD_ITEM, IND_EST e COD_PART (este, quando houver).
Nº Campo Descrição Tipo Tam Dec Obrig.
01 REG Texto fixo contendo "K280" C 004 - O
02 DT_EST Data do estoque final escriturado que está N 008* - O
sendo corrigido
03 COD_ITEM Código do item (campo 02 do Registro 0200) C 060 - O
04 N - 03 OC
Quantidade de correção positiva de
QTD_COR_POS apontamento ocorrido em período de apuração
anterior
05 N - 03 OC
Quantidade de correção negativa de
QTD_COR_NEG apontamento ocorrido em período de apuração
anterior
06 IND_EST Indicador do tipo de estoque: C 001 - O
0 = Estoque de propriedade do informante e
em seu poder;
1 = Estoque de propriedade do informante e
em posse de terceiros;
2 = Estoque de propriedade de terceiros e em
posse do informante
07 COD_PART Código do participante (campo 02 do Registro C 060 - OC
0150):
- proprietário/possuidor que não seja o
informante do arquivo
Observações:
Nível hierárquico - 3
Ocorrência – 1:N
Campo 01 (REG) - Valor Válido: [K280]
Campo 02 (DT_EST) – Validação: a data do estoque deve ser anterior à data inicial do período de apuração – campo
DT_FIN do Registro K100.
Campo 03 (COD_ITEM) – Validação: o código do item deverá existir no campo COD_ITEM do Registro 0200. Somente
podem ser informados nesse campo valores de COD_ITEM cujos tipos sejam iguais a 00, 01, 02, 03, 04, 05, 06 e 10 –
campo TIPO_ITEM do Registro 0200.
Campos 04 e 05 (QTD_COR_POS e QTD_COR_NEG) – Validação: não é admitida quantidade negativa.
Validação: somente um dos campos pode ser preenchido.
Campo 06 (IND_EST) - Valores Válidos: [0, 1, 2]
Validação: se preenchido com valor “1” (posse de terceiros) ou “2” (propriedade de terceiros), o campo COD_PART será
obrigatório.
Página 182 de 246

--- Página 183 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.19
Atualização: 05/05/2016
A quantidade em estoque existente no estabelecimento industrializador do produto industrializado para terceiro por
encomenda deverá ser:
a) quando o informante for o estabelecimento industrializador, do tipo 2 - estoque de propriedade de terceiros e em posse
do informante;
b) quando o informante for o estabelecimento encomendante, do tipo 1 - estoque de propriedade do informante e em posse
de terceiros.
A quantidade em estoque existente no estabelecimento industrializador de insumo recebido do encomendante para
industrialização por encomenda deverá ser:
a) quando o informante for o estabelecimento industrializador, do tipo 2 - estoque de propriedade de terceiros e em posse
do informante;
b) quando o informante for o estabelecimento encomendante, do tipo 1 - estoque de propriedade do informante e em posse
de terceiros.
Campo 07 (COD_PART) – Preenchimento: obrigatório quando o IND_EST for “1” ou “2”.
Validação: o valor fornecido deve constar no campo COD_PART do registro 0150.
REGISTRO K990: ENCERRAMENTO DO BLOCO K
Este registro destina-se a identificar o encerramento do bloco K e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "K990" C 004 - O
02 QTD_LIN_K Quantidade total de linhas do Bloco K N - - O
Observações:
Nível hierárquico - 1
Ocorrência –um por arquivo
Campo 01 (REG) - Valor Válido: [K990]
Campo 02 (QTD_LIN_K) - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios
registros de abertura e encerramento do bloco.
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
Campo 01 (REG) - Valor Válido: [1001]
Campo 02 (IND_MOV) - Valores Válidos: [0, 1]
Validação: além dos registros de abertura e encerramento, sempre deve ser informado o registro 1010 (Obrigatoriedade de
Registros do Bloco 1).
Página 183 de 246

