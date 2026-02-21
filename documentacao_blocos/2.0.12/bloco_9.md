# Bloco 9 - Versão 2.0.12

**Data de Criação:** 2013-03-01  
**Páginas:** 166-167  
**Versão:** 2.0.12

---

--- Página 166 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
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
Página 166 de 188

--- Página 167 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
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
Página 167 de 188

