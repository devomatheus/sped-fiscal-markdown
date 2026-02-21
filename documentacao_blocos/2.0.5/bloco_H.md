# Bloco H - Versão 2.0.5

**Data de Criação:** 2011-05-19  
**Páginas:** 130-132  
**Versão:** 2.0.5

---

--- Página 130 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Campo 07 - Preenchimento: Informar chave dos documentos eletrônicos somente quando for documento de emissão
própria.
Campo 08 - Preenchimento: informar a data no formato “ddmmaaaa” sem separadores de formatação.
REGISTRO G140 – IDENTIFICAÇÃO DO ITEM DO DOCUMENTO FISCAL
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
02 IND_MO Indicador de movimento: C 001* - O
V 0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [H001]
Campo 02 - Valores Válidos: [0,1]
Página 130 de 163

--- Página 131 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
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
10 COD_CTA Código da conta analítica contábil debitada/creditada C - - O
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [H010]
Campo 02 - Validação: o valor informado no campo deve existir no campo COD_ITEM do registro 0200.
Campo 03 - Validação: o valor deve ser informado no registro 0200, campo UNID_INV.
Campo 07 - Valores Válidos: [0, 1, 2]
Página 131 de 163

--- Página 132 ---
Guia Prático EFD – Versão 2.0.5
Atualização: 19 de maio de 2011
Validação: se preenchido com valor ‘1’ (posse de terceiros) ou ‘2’ (propriedade de terceiros), o campo COD_PART será
obrigatório.
Campo 08 – Preenchimento obrigatório quando o indicador de propriedade do item do campo 07 for “1” ou “2”.
Validação: o valor fornecido deve constar no campo COD_PART do registro 0150.
Campo 10 - Preenchimento: informar o código da conta analítica contábil correspondente. Deve ser a conta credora ou
devedora principal, podendo ser informada a conta sintética (nível acima da conta analítica). Nas situações de um mesmo
código de item possuir mais de uma destinação deve ser informada a conta referente ao item de maior relevância.
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
Página 132 de 163

