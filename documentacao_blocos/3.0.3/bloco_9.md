# Bloco 9 - Versão 3.0.3

**Data de Criação:** 2019-10-14  
**Páginas:** 270-271  
**Versão:** 3.0.3

---

--- Página 270 ---
Guia Prático EFD-ICMS/IPI – Versão 3.0.3
Atualização: 14 de outubro de 2019
Campo 09 (G4_07) – Preenchimento: informar o saldo do ICMS (débitos - créditos) relativo aos produtos com e sem
incentivo, calculado de acordo com as entradas e saídas e os ajustes da apuração no código de apuração informado no campo
IND_ESP.
Campo 10 (G4_08) – Validação: o valor informado deve ser menor ou igual que o produto dos campos G4_01 (entradas -
percentual de incentivo) e G4_03 (entradas incentivadas de PI) por sub-apuração.
Campo 11 (G4_09) – Validação: o valor informado deve ser menor ou igual que o produto dos campos G4_04 (saídas -
percentual de incentivo) e G4_06 (saídas incentivadas de PI) por sub-apuração.
Campo 12 (G4_10) – Validação: o valor informado deve ser igual ao campo G4_08 (crédito presumido nas entradas
incentivadas de PI) acrescido do campo G4_09 (crédito presumido nas saídas incentivadas de PI), por sub-apuração. O valor
deste campo deve ser igual ao valor do ajuste informado no campo VL_AJ_APUR do Registro E111, com o COD_AJ_APUR
igual a “UF04XX14”, onde “XX” é referente a sub-apuração informada no campo 02-IND_AP deste registro.
Campo 13 (G4_11) – Validação: o valor informado deve ser igual ao campo G4_07 (saldo devedor do ICMS antes das
deduções do incentivo - PI e itens não incentivados) subtraído do campo G4_10 (dedução de incentivo da Central de
Distribuição), por sub-apuração.
Campo 14 (G4_12) – Preenchimento: informar o índice de recolhimento, conforme estabelecido pelo respectivo decreto
concessivo.
REGISTRO 1990: ENCERRAMENTO DO BLOCO 1
Este registro destina-se a identificar o encerramento do bloco 1 e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "1990" C 004 - O
02 QTD_LIN_1 Quantidade total de linhas do Bloco 1 N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 (REG) - Valor Válido: [1990]
Campo 02 (QTD_LIN_1) - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios
registros de abertura e encerramento do bloco.
Validação: o número de linhas (registros) existentes no bloco 1 é igual ao valor informado no campo QTD_LIN_1.
BLOCO 9: CONTROLE E ENCERRAMENTO DO ARQUIVO DIGITAL
Este bloco representa os totais de registros e serve como forma de controle para batimentos e verificações.
REGISTRO 9001: ABERTURA DO BLOCO 9
Este registro deve sempre ser gerado e representa a abertura do bloco 9.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9001”. C 004 - O
02 IND_MOV Indicador de movimento: N 001* - O
0 - Bloco com dados informados;
1 - Bloco sem dados informados.
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 (REG) - Valor Válido: [9001]
Página 270 de 304

--- Página 271 ---
Guia Prático EFD-ICMS/IPI – Versão 3.0.3
Atualização: 14 de outubro de 2019
Campo 02 (IND_MOV) - Valor Válido: [0]
REGISTRO 9900: REGISTROS DO ARQUIVO.
Todos os registros referenciados neste arquivo, inclusive os posteriores a este registro, devem ter uma linha
totalizadora do seu número de ocorrência.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9900”. C 004 - O
02 REG_BLC Registro que será totalizado no próximo campo. C 004 - O
03 QTD_REG_BLC Total de registros do tipo informado no campo anterior. N - - O
Observações:
Nível hierárquico - 2
Ocorrência – vários (por arquivo)
Campo 01 (REG) - Valor Válido: [9900]
Campo 02 (REG_BLC) - Preenchimento: informar cada um dos códigos de registros válidos deste arquivo, que será
totalizado no próximo campo QTD_REG_BLC.
Campo 03 (QTD_REG_BLC) - Validação: verifica se o número de linhas no arquivo do tipo informado no campo
REG_BLC do registro 9900 é igual ao valor informado neste campo.
REGISTRO 9990: ENCERRAMENTO DO BLOCO 9
Este registro destina-se a identificar o encerramento do bloco 9 e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9990”. C 004 - O
02 QTD_LIN_9 Quantidade total de linhas do Bloco 9. N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 (REG) - Valor Válido: [9990]
Campo 02 (QTD_LIN_9) - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios
registros de abertura e encerramento do bloco. Para este cálculo, o registro 9999, apesar de não pertencer ao Bloco 9, também
deve ser contabilizado nesta soma.
Validação: o número de linhas (registros) existentes no bloco 9 é igual ao valor informado no campo QTD_LIN_9.
REGISTRO 9999: ENCERRAMENTO DO ARQUIVO DIGITAL.
Este registro destina-se a identificar o encerramento do arquivo digital e a informar a quantidade de linhas (registros)
existentes no arquivo.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9999”. C 004 - O
02 QTD_LIN Quantidade total de linhas do arquivo digital. N - - O
Observações:
Nível hierárquico - 0
Ocorrência – um por Arquivo
Campo 01 (REG) - Valor Válido: [9999]
Campo 02 (QTD_LIN) - Preenchimento: a quantidade de linhas a ser informada deve considerar também o próprio registro
9999.
Validação: o número de linhas (registros) existentes no arquivo inteiro é igual ao valor informado no campo QTD_LIN.
Página 271 de 304

