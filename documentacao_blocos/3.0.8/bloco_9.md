# Bloco 9 - Versão 3.0.8

**Data de Criação:** 2021-11-26  
**Páginas:** 294-296  
**Versão:** 3.0.8

---

--- Página 294 ---
Guia Prático EFD-ICMS/IPI – Versão 3.0.8
Atualização: 26 de novembro de 2021
Campo 05 (G4_03) – Preenchimento: informar o valor total das entradas de produtos incentivados (PI) dentro da faixa de
incentivo, conforme estabelecido pelo respectivo decreto concessivo.
Campo 06 (G4_04) – Preenchimento: informar o percentual de incentivo na saída interestadual, de acordo com o
estabelecido no respectivo decreto concessivo.
Validação: o valor informado deve ser maior ou igual a 2, e menor ou igual a 4.
Campo 07 (G4_05) – Preenchimento: informar o valor total das saídas de produtos incentivados (PI) fora da faixa de
incentivo, conforme estabelecido pelo respectivo decreto concessivo.
Campo 08 (G4_06) – Preenchimento: informar o valor total das saídas de produtos incentivados (PI) dentro da faixa de
incentivo, conforme estabelecido pelo respectivo decreto concessivo.
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
Página 294 de 331

--- Página 295 ---
Guia Prático EFD-ICMS/IPI – Versão 3.0.8
Atualização: 26 de novembro de 2021
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
Página 295 de 331

--- Página 296 ---
Guia Prático EFD-ICMS/IPI – Versão 3.0.8
Atualização: 26 de novembro de 2021
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
Seção 5 – Obrigatoriedade dos Registros
Os estabelecimentos obrigados à EFD-ICMS/IPI, mesmo com atividades paralisadas no período, ou seja, SEM
MOVIMENTO, devem apresentar o arquivo informando, no mínimo, os registros obrigatórios. O histórico da
obrigatoriedade dos registros consta nas tabelas do item 2.6.1 da Nota Técnica, instituída pelo Ato COTEPE/ICMS nº
44/2018 e suas alterações (http://www.fazenda.gov.br/confaz/).
Os contribuintes do IPI situados em Pernambuco e no Distrito Federal (obrigados a enviar a EFD-ICMS/IPI, por
força das Instruções Normativas RFB 1371/13 e 1685/17), até a definição de legislação específica quanto à obrigatoriedade
da EFD com relação ao ICMS nestas UF's, deverão observar as orientações disponíveis no sítio do Sped
(http://sped.rfb.gov.br/pasta/show/1575). Até o início da obrigatoriedade na legislação de PE e DF, o ICMS próprio
informado não produz efeitos para as respectivas SEFAZ, mas o ICMS ST declarado produzirá efeitos para as demais UF nas
operações interestaduais (OIE).
Caso o contribuinte opte por preencher qualquer registro dispensado, este será validado conforme as regras de
validação esclarecidas neste Guia, uma vez que o PVA-EFD-ICMS/IPI é único para todos os contribuintes obrigados à EFD-
ICMS/IPI do país.
Tabelas – Item 2.6.1 (Nota Técnica, instituída pelo Ato COTEPE/ICMS nº 44/2018 e alterações)
2.6.1.1 – Abertura do arquivo digital e Bloco 0
Bloco Descrição Registro Nível Ocorrência Obrigatoriedade do registro
(Todos os contribuintes)
0 Abertura do Arquivo Digital e Identificação da entida- 0000 0 1 O
de
0 Abertura do Bloco 0 0001 1 1 O
0 Classificação do Estabelecimento Industrial ou Equipa- 0002 2 1
rado a Industrial OC
0 Dados Complementares da entidade 0005 2 1 O
0 Dados do Contribuinte Substituto ou Responsável pelo 0015 2 V
ICMS Destino OC
0 Dados do Contabilista 0100 2 1 O (se perfil A ou B),
0 Tabela de Cadastro do Participante 0150 2 V OC
Página 296 de 331

