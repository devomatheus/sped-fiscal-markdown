# Bloco 9 - Versão 2.0.14

**Data de Criação:** 2014-03-01  
**Páginas:** 175-176  
**Versão:** 2.0.14

---

--- Página 175 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
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
BLOCO 9: CONTROLE E ENCERRAMENTO DO ARQUIVO DIGITAL
Este bloco representa os totais de registros e serve como forma de controle para batimentos e verificações.
REGISTRO 9001: ABERTURA DO BLOCO 9
Este registro deve sempre ser gerado e representa a abertura do bloco 9.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9001”. C 004 - O
02 IND_MOV Indicador de movimento: N 001* - O
0- Bloco com dados informados;
1- Bloco sem dados informados.
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [9001]
Campo 02 - Valor Válido: [0]
REGISTRO 9900: REGISTROS DO ARQUIVO.
Todos os registros referenciados neste arquivo, inclusive os posteriores a este registro, devem ter uma linha
totalizadora do seu número de ocorrências.
Página 175 de 209

--- Página 176 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.14
Atualização: 13/03/2014
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9900”. C 004 - O
02 REG_BLC Registro que será totalizado no próximo campo. C 004 - O
03 QTD_REG_BLC Total de registros do tipo informado no campo anterior. N - - O
Observações:
Nível hierárquico - 2
Ocorrência – vários (por arquivo)
Campo 01 - Valor Válido: [9900]
Campo 02 - Preenchimento: informar cada um dos códigos de registros válidos deste arquivo, que será totalizado no
próximo campo QTD_REG_BLC.
Campo 03 - Validação: verifica se o número de linhas no arquivo do tipo informado no campo REG_BLC do registro
9900 é igual ao valor informado neste campo.
REGISTRO 9990: ENCERRAMENTO DO BLOCO 9
Este registro destina-se a identificar o encerramento do bloco 9 e a informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9990”. C 004 - O
02 QTD_LIN_9 Quantidade total de linhas do Bloco 9. N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [9990]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de
abertura e encerramento do bloco. Para este cálculo, o registro 9999, apesar de não pertencer ao Bloco 9, também deve ser
contabilizado nesta soma.
Validação: o número de linhas (registros) existentes no bloco 9 é igual ao valor informado no campo QTD_LIN_9.
REGISTRO 9999: ENCERRAMENTO DO ARQUIVO DIGITAL.
Este registro destina-se a identificar o encerramento do arquivo digital e a informar a quantidade de linhas
(registros) existentes no arquivo.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9999”. C 004 - O
02 QTD_LIN Quantidade total de linhas do arquivo digital. N - - O
Observações:
Nível hierárquico - 0
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [9999]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também o próprio registro 9999.
Validação: o número de linhas (registros) existentes no arquivo inteiro é igual ao valor informado no campo QTD_LIN.
Página 176 de 209

