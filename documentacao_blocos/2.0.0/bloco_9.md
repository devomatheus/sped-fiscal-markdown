# Bloco 9 - Versão 2.0.0

**Data de Criação:** 2009-12-17  
**Páginas:** 138-139  
**Versão:** 2.0.0

---

--- Página 138 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
BLOCO 9: CONTROLE E ENCERRAMENTO DO ARQUIVO DIGITAL
Este bloco representa os totais de registros e serve como forma de controle para batimentos e verificações.
REGISTRO 9001: ABERTURA DO BLOCO 9
Este registro deve sempre ser gerado e representa a abertura do Bloco 9.
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
Todos os registros referenciados neste arquivo, inclusive os posteriores a este registro, devem ter uma linha totalizadora do
seu número de ocorrências.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9900”. C 004 - O
02 REG_BLC Registro que será totalizado no próximo campo. C 004 - O
03 QTD_REG_BLC Total de registros do tipo informado no campo anterior. N - - O
Observações:
Nível hierárquico - 2
Ocorrência – vários por Arquivo
Campo 01 - Valor Válido: [9900]
Campo 02 - Preenchimento: informar cada um dos códigos de registros válidos deste arquivo, que será totalizado no pró-
ximo campo QTD_REG_BLC.
Campo 03 - Validação: verifica se o número de linhas no arquivo do tipo informado no campo REG_BLC do registro
9900 é igual ao valor informado neste campo.
REGISTRO 9990: ENCERRAMENTO DO BLOCO 9
Este registro destina-se a identificar o encerramento do Bloco 9 e a informar a quantidade de linhas (registros) existentes no
bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9990”. C 004 - O
02 QTD_LIN_9 Quantidade total de linhas do Bloco 9. N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [9990]
Página 138 de 158

--- Página 139 ---
Guia Prático EFD – Versão 2.0.0
Atualização: 17 de dezembro de 2009
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também os próprios registros de aber-
tura e encerramento do bloco. Para este cálculo, o Registro 9999, apesar de não pertencer ao Bloco 9, também deve ser
contabilizado nesta soma.
Validação: o número de linhas (registros) existentes no bloco 9 é igual ao valor informado no campo QTD_LIN_9.
REGISTRO 9999: ENCERRAMENTO DO ARQUIVO DIGITAL.
Este registro destina-se a identificar o encerramento do arquivo digital e a informar a quantidade de linhas (registros) exis-
tentes no arquivo.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “9999”. C 004 - O
02 QTD_LIN Quantidade total de linhas do arquivo digital. N - - O
Observações:
Nível hierárquico - 0
Ocorrência – um por Arquivo
Campo 01 - Valor Válido: [9999]
Campo 02 - Preenchimento: a quantidade de linhas a ser informada deve considerar também o próprio registro 9999.
Validação: o número de linhas (registros) existentes no arquivo inteiro é igual ao valor informado no campo QTD_LIN.
Seção 5 – Obrigatoriedade dos Registros
Os estabelecimentos obrigados a EFD, mesmo com atividades paralisadas no período, devem
apresentar o arquivo informando, no mínimo, os registros obrigatórios, conforme as tabelas abaixo.
Tabela 2.6.1.1 – Abertura do arquivo digital e Bloco 0
2.6.1.1 – Abertura do arquivo digital e Bloco 0
Bloco Descrição Registro Nível Ocorrência Obrigatoriedade
do registro (To-
dos os contribu-
intes)
0 Abertura do Arquivo Digital e Identificação da 0000 0 1 O
entidade
0 Abertura do Bloco 0 0001 1 1 O
0 Dados Complementares da entidade 0005 2 1 O
0 Dados do Contribuinte Substituto 0015 2 V OC
0 Dados do Contabilista 0100 2 1 O
0 Tabela de Cadastro do Participante 0150 2 V OC
0 Alteração da Tabela de Cadastro de Participante 0175 3 1:N OC
0 Identificação das unidades de medida 0190 2 V OC
0 Tabela de Identificação do Item (Produtos e Ser- 0200 2 V
viços) OC
0 Alteração do Item 0205 3 1:N OC
0 Código de produto conforme Tabela ANP (Com- 0206 3 1:1
bustíveis) OC
0 Fatores de Conversão de Unidades 0220 3 1:N OC
0 Cadastro de bens ou componentes do Ativo Imo- 0300 2 V
bilizado OC
0 Informação sobre a Utilização do Bem 0305 3 1:1 OC
0 Tabela de Natureza da Operação/ Prestação 0400 2 V OC
0 Tabela de Informação Complementar do docu- 0450 2 V
mento fiscal OC
0 Tabela de Observações do Lançamento Fiscal 0460 2 V OC
0 Plano de contas contábeis 0500 2 V O (se existir
0300 ou 0305
Página 139 de 158

