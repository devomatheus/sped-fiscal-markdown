# Bloco 0 - Versão 2.0.12

**Data de Criação:** 2013-03-01  
**Páginas:** 15-29  
**Versão:** 2.0.12

---

--- Página 15 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
BLOCO 0: ABERTURA, IDENTIFICAÇÃO E REFERÊNCIAS.
REGISTRO 0000: ABERTURA DO ARQUIVO DIGITAL E IDENTIFICAÇÃO
DA ENTIDADE
Registro obrigatório e corresponde ao primeiro registro do arquivo.
Obs.: Nos casos de EFD-ICMS/IPI apresentadas por estabelecimentos situados em outra UF e que possuam
Inscrição Estadual nos termos do Convênio ICMS nº 113/04, deve-se observar o seguinte procedimento para
preenchimento do registro 0000:
a) Informar o campo UF da unidade federada do tomador de serviços;
b) Informar no campo IE a inscrição estadual na unidade federada do tomador de serviços;
c) Informar no campo COD_MUN o código de município correspondente à capital do estado do tomador de serviços.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “0000”. C 004 - O
02 COD_VER Código da versão do leiaute conforme a tabela indicada N 003* - O
no Ato COTEPE.
03 COD_FIN Código da finalidade do arquivo: N 001 - O
0 - Remessa do arquivo original;
1 - Remessa do arquivo substituto.
04 DT_INI Data inicial das informações contidas no arquivo. N 008* - O
05 DT_FIN Data final das informações contidas no arquivo. N 008* - O
06 NOME Nome empresarial da entidade. C 100 - O
07 CNPJ Número de inscrição da entidade no CNPJ. N 014* - OC
08 CPF Número de inscrição da entidade no CPF. N 011* OC
09 UF Sigla da unidade da federação da entidade. C 002* - O
10 IE Inscrição Estadual da entidade. C 014 - O
11 COD_MUN Código do município do domicílio fiscal da entidade, N 007* - O
conforme a tabela IBGE
12 IM Inscrição Municipal da entidade. C - - OC
13 SUFRAMA Inscrição da entidade na SUFRAMA C 009* - OC
14 IND_PERFIL Perfil de apresentação do arquivo fiscal; C 001 - O
A – Perfil A;
B – Perfil B.;
C – Perfil C.
15 IND_ATIV Indicador de tipo de atividade: N 001 - O
0 – Industrial ou equiparado a industrial;
1 – Outros.
Observações:
Nível hierárquico - 0
Ocorrência - um por arquivo.
Campo 01 - Valor Válido: [0000]
Campo 02 - Preenchimento: o código da versão do leiaute informado é validado conforme a data referenciada no campo
DT_FIN. Verificar na Tabela Versão (http://www1.receita.fazenda.gov.br/sistemas/sped-fiscal/tabelas-de-codigos.htm),
item 3.1.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008 e alterações.
Validação: Válido para o período informado. A versão do leiaute informada no arquivo deverá ser válida na data final da
escrituração (campo DT_FIN do registro 0000).
Campo 03 - Valores Válidos: [0, 1]
Preenchimento: dentro do prazo normal de entrega o arquivo pode ser substituído.
Após o vencimento do prazo de entrega, com a publicação do Ajuste Sinief 11/2012, que define regras padronizadas em
todo o território nacional para a RETIFICAÇÃO DA EFD-ICMS/IPI, a partir de janeiro de 2013, o procedimento deve ser
o seguinte:
1. EFD-ICMS/IPI de mês de referência janeiro de 2009 a dezembro de 2012 pode ser retificada, sem autorização, até
30 de abril de 2013;
Página 15 de 188

--- Página 16 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
2. EFD-ICMS/IPI de mês de referência janeiro de 2013 em diante, pode ser retificada, sem autorização, até o último
dia do terceiro mês subsequente ao encerramento do mês da apuração (Ex.: Janeiro de 2013 pode ser retificado até 30 de
abril de 2013);
3. Cumpridos estes prazos, retificações somente serão possíveis com autorização, de acordo com o que determina o
referido Ajuste.
Para a entrega da EFD-ICMS/IPI deverá ser utilizado o leiaute vigente à época do período de apuração e, para validação e
transmissão, a versão do Programa de Validação e Assinatura - PVA atualizada.
Campo 04 - Preenchimento: informar o período de validade das informações contidas neste registro, no padrão
“diamêsano” (ddmmaaaa), excluindo-se quaisquer caracteres de separação, tais como: ".", "/", "-".
O valor informado deve ser o primeiro dia do mês, exceto no caso de início de atividades ou de qualquer outro evento que
altere a forma e o período de escrituração fiscal do estabelecimento.
Campo 05 - Preenchimento: informar a última data do período da escrituração, no padrão “diamêsano” (ddmmaaaa),
excluindo-se quaisquer caracteres de separação, tais como: “.”, “/”, “-”.
Validação: Verifica se a data informada neste campo pertence ao mesmo mês/ano da data informada no campo DT_INI.
O valor informado deve ser o último dia do mesmo mês da data inicial, exceto no caso de encerramento de atividades ou de
qualquer outro fato determinante para paralisação das atividades do estabelecimento.
Campo 07 - Preenchimento: informar o número do CNPJ do contribuinte. Se o contribuinte for pessoa física (p.ex.:
produtor rural), deixar o campo em branco.
Validação: será conferido o dígito verificador (DV) do CNPJ informado.
Campo 08 - Preenchimento: informar o número de inscrição do contribuinte no cadastro do CPF. Obrigatório, se o
informante do arquivo for pessoa física e não obrigado à inscrição no CNPJ.
Validação: será conferido o dígito verificador (DV) do CPF informado.
Os campos CNPJ e CPF são mutuamente excludentes, ou seja, é obrigatório o preenchimento de apenas um deles.
Campo 09 - Validação: o valor deve ser a sigla da unidade da federação (UF) do informante.
Campo 10 - Validação: será conferido o dígito verificador (DV) da Inscrição Estadual informada, considerando-se a UF
do informante.
Campo 11 – Preenchimento: Os estabelecimentos situados em outra unidade da federação, sem ter endereço e/ou
estabelecimento físico na unidade federada, devem informar o código de município da capital do estado, constante da
Tabela de Municípios do IBGE.
Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE, possuindo 7 dígitos.
Campo 13 - Validação: será conferido o dígito verificador (DV) do número de inscrição na SUFRAMA, se informado.
Campo 14 - Valores Válidos: [A, B, C]
Preenchimento: informar o perfil de apresentação do arquivo, conforme definido pelo Fisco Estadual para o informante da
EFD-ICMS/IPI. O arquivo será rejeitado se o declarante informar a EFD-ICMS/IPI em perfil diferente do estabelecido.
Campo 15 - Valores Válidos: [0, 1]
Preenchimento: informar “0”, se o contribuinte é industrial ou equiparado a industrial, conforme legislação do Imposto
sobre Produtos Industrializados (IPI). Se o estabelecimento não se enquadrar no disposto nos art. 8º, 9º., 10º e 11º e cujas
operações não se enquadrem dentro do campo de incidência do IPI, conforme parágrafo único do art. 2º, todos do Decreto
nº 4.544/2002, ainda que seja uma indústria, deve informar a opção "1 - Outras" no campo IND_ATIV do registro 0000.
REGISTRO 0001: ABERTURA DO BLOCO 0
Este registro deve ser gerado para abertura do bloco 0 e indica as informações previstas para este bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “0001”. C 004 - O
02 IND_MOV Indicador de movimento: N 001 - O
0- Bloco com dados informados;
1- Bloco sem dados informados.
Observações:
Nível hierárquico - 1
Página 16 de 188

--- Página 17 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Ocorrência – um por arquivo
Campo 01 - Valor Válido: [0001]
Campo 02 - Valor Válido: [0]
REGISTRO 0005: DADOS COMPLEMENTARES DA ENTIDADE
Registro obrigatório utilizado para complementar as informações de identificação do informante do arquivo.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “0005” C 004 - O
02 FANTASIA Nome de fantasia associado ao nome empresarial. C 060 - O
03 CEP Código de Endereçamento Postal. N 008* - O
04 END Logradouro e endereço do imóvel. C 060 - O
05 NUM Número do imóvel. C 010 - OC
06 COMPL Dados complementares do endereço. C 060 - OC
07 BAIRRO Bairro em que o imóvel está situado. C 060 - O
08 FONE Número do telefone (DDD+FONE). C 11 - OC
09 FAX Número do fax. C 11 - OC
10 EMAIL Endereço do correio eletrônico. C - - OC
Observações:
Nível hierárquico - 2
Ocorrência – um por arquivo
Campo 01 - Valor Válido: [0005]
Campo 02 – Preenchimento: caso não possua nome de fantasia, preencher com parte da razão social pela qual é
conhecida.
REGISTRO 0015: DADOS DO CONTRIBUINTE SUBSTITUTO
Registro obrigatório para todos os contribuintes substitutos tributários do ICMS, conforme definidos na legislação
pertinente. Deve ser gerado um registro para cada uma das inscrições estaduais cadastradas nas unidades federadas dos
contribuintes substituídos, ainda que não tenha tido movimentação no período, ficando obrigado à apresentação dos
registros E200 e filhos.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0015" C 004 - O
02 UF_ST Sigla da unidade da federação do contribuinte C 002* - O
substituído.
03 IE_ST Inscrição Estadual do contribuinte substituto na unidade C 014 - O
da federação do contribuinte substituído.
Observações:
Nível hierárquico - 2
Ocorrência – vários (por arquivo)
Campo 01 - Valor Válido: [0015]
Campo 02 - Preenchimento: informar a sigla da UF onde o contribuinte possui inscrição como substituto tributário.
Validação: O valor deve ser a sigla de uma unidade da federação existente.
Campo 03 - Preenchimento: informar a inscrição estadual do contribuinte na unidade de federação onde ele estiver
inscrito como substituto tributário.
Validação: valida a Inscrição Estadual, considerando a UF informada no registro.
Página 17 de 188

--- Página 18 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
REGISTRO 0100: DADOS DO CONTABILISTA
Registro utilizado para identificação do contabilista responsável pela escrituração fiscal do estabelecimento,
mesmo que o contabilista seja funcionário da empresa ou prestador de serviço.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “0100”. C 004 - O
02 NOME Nome do contabilista. C 100 - O
03 CPF Número de inscrição do contabilista no CPF. N 011* - O
04 CRC Número de inscrição do contabilista no Conselho C 015 - O
Regional de Contabilidade.
05 CNPJ Número de inscrição do escritório de contabilidade no N 014* - OC
CNPJ, se houver.
06 CEP Código de Endereçamento Postal. N 008* - OC
07 END Logradouro e endereço do imóvel. C 060 - OC
08 NUM Número do imóvel. C 010 - OC
09 COMPL Dados complementares do endereço. C 060 - OC
10 BAIRRO Bairro em que o imóvel está situado. C 060 - OC
11 FONE Número do telefone (DDD+FONE). C 11 - OC
12 FAX Número do fax. C 11 - OC
13 EMAIL Endereço do correio eletrônico. C - - O
14 COD_MUN Código do município, conforme tabela IBGE. N 007* - OC
Observações:
Nível hierárquico - 2
Ocorrência – um por arquivo
Campo 01 - Valor válido: [0100]
Campo 02 - Preenchimento: informar o nome do contabilista responsável.
Campo 03 - Preenchimento: informar o número do CPF do contabilista responsável; não utilizar os caracteres especiais
de formatação, tais como: ".", "/", "-".
Validação: será conferido o dígito verificador (DV) do CPF informado.
Campo 04 - Preenchimento: informar o número de inscrição do contabilista no Conselho Regional de Contabilidade na
UF do estabelecimento.
Campo 05 - Preenchimento: informar o número de inscrição no Cadastro Nacional de Pessoa Jurídica do escritório de
contabilidade; não informar caracteres de formatação, tais como: ".", "/", "-".
Validação: será conferido o dígito verificador (DV) do CNPJ informado.
Campo 06 - Preenchimento: informar o número do Código de Endereçamento Postal - CEP, conforme cadastro nos
CORREIOS.
Campo 07 - Preenchimento: informar o endereço do contabilista/escritório de contabilidade.
Campo 13 - Preenchimento: informar o endereço de correio eletrônico do contabilista/escritório de contabilidade. Este
endereço de e-mail poderá ser utilizado para envio de correspondências.
Campo 14 - Preenchimento: informar o código do município do domicílio fiscal do contabilista/escritório de
contabilidade.
Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE (combinação do código da UF e o
código de município), possuindo 7 dígitos.
REGISTRO 0150: TABELA DE CADASTRO DO PARTICIPANTE
Registro utilizado para informações cadastrais das pessoas físicas ou jurídicas envolvidas nas transações
comerciais com o estabelecimento, no período. Participantes sem movimentação no período não devem ser informados
neste registro.
Obs.: Não devem ser informados como participantes os CNPJ e CPF apenas citados nos registros C350 e C460.
Página 18 de 188

--- Página 19 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
O código a ser utilizado é de livre atribuição pelo contribuinte e possui validade para o arquivo informado. Este
código deve ser único para o participante, não havendo necessidade, sempre que possível, de se criar um novo para cada
período.
Não podem ser informados dois ou mais registros com o mesmo Código de Participante.
Para o caso de participante pessoa física com mais de um endereço, podem ser fornecidos mais de um registro,
com o mesmo NOME e CPF. Neste caso, deve ser usado um COD_PART para cada registro, alterando os demais dados.
As informações deste registro representam os dados atualizados no último dia da EFD-ICMS/IPI.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “0150”. C 004 - O
02 COD_PART Código de identificação do participante no arquivo. C 060 - O
03 NOME Nome pessoal ou empresarial do participante. C 100 - O
04 COD_PAIS Código do país do participante, conforme a tabela N 005 - O
indicada no item 3.2.1
05 CNPJ CNPJ do participante. N 014* - OC
06 CPF CPF do participante. N 011* - OC
07 IE Inscrição Estadual do participante. C 014 - OC
08 COD_MUN Código do município, conforme a tabela IBGE N 007* - OC
09 SUFRAMA Número de inscrição do participante na SUFRAMA. C 009* - OC
10 END Logradouro e endereço do imóvel C 060 - O
11 NUM Número do imóvel C 010 - OC
12 COMPL Dados complementares do endereço C 060 - OC
13 BAIRRO Bairro em que o imóvel está situado C 060 - OC
Observações:
Nível hierárquico - 2
Ocorrência –vários por arquivo
Campo 01 - Valor válido: [0150]
Campo 02 - Preenchimento: informar o código de identificação do participante no arquivo.
Esta tabela pode conter COD_PART e respectivo registro 0150 com dados do próprio contribuinte informante, quando
apresentar documentos emitidos contra si próprio, em situações específicas (Exemplo: emissão de Nota Fiscal em operação
de retorno de produtos saídos para venda ambulante ou a negociar fora do estabelecimento).
Validação: o valor informado no campo COD_PART deve existir em pelo menos um registro dos demais blocos.
O código de participante, campo COD_PART, é de livre atribuição do estabelecimento, observado o disposto no item
2.4.2.1. do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 04 - Preenchimento: informar o código do país, conforme tabela indicada no item 3.2.1 do Ato COTEPE/ICMS nº
09, de 18 de abril de 2008. O código de país pode ser informado com 05 caracteres ou com 04 caracteres (desprezando o
caractere “0” (zero) existente à esquerda).
Validação: o valor informado no campo deve existir na Tabela de Países. Informar, inclusive, quando o participante for
estabelecido ou residente no Brasil (01058 ou 1058).
Campo 05 - Preenchimento: informar o número do CNPJ do participante, não informar caracteres de formatação, tais
como: ".", "/", "-". Se COD_PAIS diferente de Brasil, o campo não deve ser preenchido.
Validação: é conferido o dígito verificador (DV) do CNPJ informado.
Obrigatoriamente um dos campos, CPF ou CNPJ, deverá ser preenchido.
Campo 06 - Preenchimento: informar o número do CPF do participante; não utilizar os caracteres especiais de
formatação, tais como: “.”, “/”, “-”. Se COD_PAIS diferente de Brasil, o campo não deve ser preenchido.
Validação: é conferido o dígito verificador (DV) do CPF informado.
Obrigatoriamente um dos campos, CPF ou CNPJ, deverá ser preenchido.
Obs.: Os campos 05 e 06 são mutuamente excludentes, sendo obrigatório o preenchimento de um deles quando o campo 04
estiver preenchido com “01058” ou “1058” (Brasil).
Campo 07 - Validação: valida a Inscrição Estadual de acordo com a UF informada no campo COD_MUN (dois primeiros
dígitos do código de município).
Campo 08 - Validação: o valor informado no campo deve existir na Tabela de Municípios do IBGE (combinação do
código da UF e o código de município), possuindo 7 dígitos.
Página 19 de 188

--- Página 20 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Obrigatório se campo COD_PAIS for igual a “01058” ou “1058”(Brasil). Se for exterior, informar campo “vazio” ou
preencher com o código “9999999”.
Campo 09 - Preenchimento: informar o número de Inscrição do participante na SUFRAMA, se houver.
Validação: é conferido o dígito verificador (DV) do número de inscrição na SUFRAMA, se informado.
Campo 10 - Preenchimento: informar o logradouro e endereço do imóvel. Se o participante for do exterior, preencher
inclusive com a cidade e país.
REGISTRO 0175: ALTERAÇÃO DA TABELA DE CADASTRO DE PARTICIPANTE
Este registro é de preenchimento obrigatório quando houver, dentro do período, alteração nos dados informados no
registro 0150, campos: NOME, COD_PAIS, CNPJ, CPF, COD_MUN, SUFRAMA, END, NUM, COMPL e BAIRRO.
Não pode ser utilizado, em um mesmo arquivo, um mesmo código para representar um participante diferente do
referenciado anteriormente por tal código.
Os dados informados neste registro serão considerados até às 24:00 horas do dia anterior à data de alteração.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “0175” C 004 - O
02 DT_ALT Data de alteração do cadastro N 008* - O
03 NR_CAMPO Número do campo alterado (Somente campos 03 a 13) C 002 - O
04 CONT_ANT Conteúdo anterior do campo C 100 - O
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [0175]
Campo 02 - Validação: o valor informado no campo deve estar entre o campo DT_INI e o campo DT_FIN do registro
0000.
Campo 03 - Preenchimento: informar o número do campo alterado, relativo ao registro 0150.
Campo 04 - Preenchimento: os dados informados neste registro são válidos até às 24:00 horas do dia anterior à data de
alteração.
Validação: quando se tratar de alterações nos campos CNPJ, CPF ou Inscrição estadual, referidos campos serão validados
conforme as regras de verificação de dígitos verificadores. Se COD_Mun será verificada sua existência na tabela IBGE.
REGISTRO 0190: IDENTIFICAÇÃO DAS UNIDADES DE MEDIDA
Este registro tem por objetivo descrever as unidades de medidas utilizadas no arquivo digital. Não podem ser
informados dois ou mais registros com o mesmo código de unidade de medida. Somente devem constar as unidades de
medidas informadas em qualquer outro registro.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0190" C 004 - O
02 UNID Código da unidade de medida C 006 - O
03 DESCR Descrição da unidade de medida C - - O
Observações:
Nível hierárquico: 2
Ocorrência: vários por arquivo
Campo 01 - Valor Válido: [0190]
Campo 02 - Validação: o valor informado neste campo deve existir em pelo menos um outro registro do arquivo.
Campo 03 - Validação: não poderão ser informados os campos UNID e DESCR com o mesmo conteúdo.
Página 20 de 188

--- Página 21 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
REGISTRO 0200: TABELA DE IDENTIFICAÇÃO DO ITEM (PRODUTO E
SERVIÇOS)
Este registro tem por objetivo informar mercadorias, serviços, produtos ou quaisquer outros itens concernentes às
transações fiscais. Quando ocorrer alteração somente na descrição do item, sem que haja descaracterização deste, ou seja,
criação de um novo item, a alteração deve constar no registro 0205.
Só devem ser apresentados itens referenciados nos demais blocos, exceto se for apresentado o fator de conversão
no registro 0220 (a partir de julho de 2012).
A identificação do item (produto ou serviço) deverá receber o código próprio do informante do arquivo em
qualquer documento, lançamento efetuado ou arquivo informado (significa que o código de produto deve ser o mesmo
na emissão dos documentos fiscais, na entrada das mercadorias ou em qualquer outra informação prestada ao fisco),
observando-se ainda que:
a) O código utilizado não pode ser duplicado ou atribuído a itens (produto ou serviço) diferentes. Os produtos e
serviços que sofrerem alterações em suas características básicas deverão ser identificados com códigos diferentes. Em caso
de alteração de codificação, deverão ser informados o código e a descrição anteriores e as datas de validade inicial e final
no registro 0205;
b) Não é permitida a reutilização de código que tenha sido atribuído para qualquer produto anteriormente.
c) O código de item/produto a ser informado no Inventário deverá ser aquele utilizado no mês inventariado.
d) A discriminação do item deve indicar precisamente o mesmo, sendo vedadas discriminações diferentes para o
mesmo item ou discriminações genéricas (a exemplo de "diversas entradas", "diversas saídas", "mercadorias para revenda",
etc), ressalvadas as operações abaixo, desde que não destinada à posterior circulação ou apropriação na produção:
1- de aquisição de "materiais para uso/consumo" que não gerem direitos a créditos;
2- que discriminem por gênero a aquisição de bens para o "ativo fixo" (e sua baixa);
3- que contenham os registros consolidados relativos aos contribuintes com atividades econômicas de
fornecimento de energia elétrica, de fornecimento de água canalizada, de fornecimento de gás canalizado, e de prestação de
serviço de comunicação e telecomunicação que poderão, a critério do Fisco, utilizar registros consolidados por classe de
consumo para representar suas saídas ou prestações.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0200" C 004 - O
02 COD_ITEM Código do item C 060 - O
03 DESCR_ITEM Descrição do item C - - O
04 COD_BARRA Representação alfanumérico do código de barra do C - - OC
produto, se houver
05 COD_ANT_ITEM Código anterior do item com relação à última informação C 060 - OC
apresentada.
06 UNID_INV Unidade de medida utilizada na quantificação de C 006 - O
estoques.
07 TIPO_ITEM Tipo do item – Atividades Industriais, Comerciais e N 2 - O
Serviços:
00 – Mercadoria para Revenda;
01 – Matéria-Prima;
02 – Embalagem;
03 – Produto em Processo;
04 – Produto Acabado;
05 – Subproduto;
06 – Produto Intermediário;
07 – Material de Uso e Consumo;
08 – Ativo Imobilizado;
09 – Serviços;
10 – Outros insumos;
99 – Outras
08 COD_NCM Código da Nomenclatura Comum do Mercosul C 008* - OC
09 EX_IPI Código EX, conforme a TIPI C 003 - OC
10 COD_GEN Código do gênero do item, conforme a Tabela 4.2.1 N 002* - OC
11 COD_LST Código do serviço conforme lista do Anexo I da Lei N 004 OC
Complementar Federal nº 116/03.
12 ALIQ_ICMS Alíquota de ICMS aplicável ao item nas operações N 006 02 OC
internas
Página 21 de 188

--- Página 22 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Observações:
1. O Código do Item deverá ser preenchido com as informações utilizadas na última ocorrência do período.
2. O campo COD_NCM é obrigatório:
2.1) para empresas industriais e equiparadas a industrial, referente aos itens correspondentes à atividade
fim, ou quando gerarem créditos e débitos de IPI;
2.2) para contribuintes de ICMS que sejam substitutos tributários;
2.3) para empresas que realizarem operações de exportação ou importação.”
3. Não existe COD-NCM para serviços.
4. O campo COD_GEN é obrigatório a todos os contribuintes somente na aquisição de produtos primários
Nível hierárquico - 2
Ocorrência - vários (por arquivo)
Campo 01 - Valor Válido: [0200]
Campo 02 - Preenchimento: informar com códigos próprios do informante do arquivo os itens das operações de entradas
de mercadorias ou aquisições de serviços, bem como das operações de saídas de mercadorias ou prestações de serviços.
Validação: o valor informado neste campo deve existir em pelo menos um registro dos demais blocos ou no registro 0220.
Campo 03 - Preenchimento: são vedadas descrições diferentes para o mesmo item ou descrições genéricas, ressalvadas as
operações abaixo, desde que não destinada à posterior circulação ou apropriação na produção:
1- de aquisição de "materiais para uso/consumo" que não gerem direitos a créditos;
2- que discriminem por gênero a aquisição de bens para o "ativo fixo" (e sua baixa);
3- que contenham os registros consolidados relativos aos contribuintes com atividades econômicas de
fornecimento de energia elétrica, de fornecimento de água canalizada, de fornecimento de gás canalizado e de prestação de
serviço de comunicação e telecomunicação que poderão, a critério do Fisco, utilizar registros consolidados por classe de
consumo para representar suas saídas ou prestações.
É permitida a modificação da descrição, desde que não implique descaracterização do produto. Neste caso, o
campo deve ser preenchido com a atual descrição utilizada no período. As descrições substituídas devem ser informadas
nos registros 0205.
Campo 04 - Preenchimento: informar o código GTIN-8, GTIN-12, GTIN-13 ou GTIN-14 (antigos códigos EAN, UPC e
DUN-14). Não informar o conteúdo do campo se o produto não possui este código.
Informar o código de barras GTIN (antigo código EAN) do produto..
Campo 05 - Não preencher. Se houver a informação, esta deve ser prestada no registro 0205.
Campo 06 - Validação: existindo informação neste campo, esta deve existir no registro 0190, campo UNID, respectivo.
Campo 07 - Preenchimento: informar o tipo do item aplicável. Nas situações de um mesmo código de item possuir mais
de um tipo de item (destinação), deve ser informado o tipo de maior relevância.
Deve ser informada a destinação inicial do produto, considerando-se os conceitos:
00 - Mercadoria para revenda – produto adquirido para comercialização;
01 – Matéria-prima: a mercadoria que componha, física e/ou quimicamente, um produto em processo ou produto
acabado e que não seja oriunda do processo produtivo. A mercadoria recebida para industrialização é classificada
como Tipo 01, pois não decorre do processo produtivo, mesmo que no processo de produção se produza
mercadoria similar classificada como Tipo 03;
03 – Produto em processo: o produto que possua as seguintes características, cumulativamente: oriundo do
processo produtivo; e, preponderantemente, consumido no processo produtivo. Dentre os produtos em processo
está incluído o produto resultante caracterizado como retorno de produção. Um produto em processo é
caracterizado como retorno de produção quando é resultante de uma fase e processo de produção e é destinado,
rotineira e exclusivamente, a uma fase e processo de produção anterior à qual o mesmo foi gerado.;
04 – Produto acabado: o produto que possua as seguintes características, cumulativamente: oriundo do processo
produtivo; produto final resultante do objeto da atividade econômica do contribuinte; e pronto para ser
comercializado;
05 - Subproduto: o produto que possua as seguintes características, cumulativamente: oriundo do processo
produtivo e não é objeto da produção principal do estabelecimento; tem aproveitamento econômico; não se
enquadre no conceito de produto em processo (Tipo 03) ou de produto acabado (Tipo 04);
06 – Produto intermediário - aquele que, embora não se integrando ao novo produto, for consumido no processo de
industrialização;
Valores válidos: [00, 01, 02, 03, 04, 05, 06, 07, 08, 09, 10, 99]
Página 22 de 188

--- Página 23 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Campo 08 – Preenchimento: para as empresas industriais ou equiparadas é obrigatório informar o Código NCM conforme
a Nomenclatura Comum do MERCOSUL, de acordo com o Decreto nº 6.006/06. Não existe COD-NCM para serviços.
Para as demais empresas, é obrigatória a informação da NCM para os itens importados, exportados ou, no caso de
substituição tributária, para os itens sujeitos à substituição, quando houver a retenção do ICMS.
Validação: o preenchimento do campo é obrigatório se o campo IND_ATIV do registro 0000 for igual a “0” (zero)
(industrial ou equiparado a industrial), mas apenas para os itens correspondentes à atividade fim ou quando gerarem
créditos e débitos de IPI. Fica dispensado o preenchimento deste campo, quando o tipo de item informado no campo
TP_ITEM for igual a 07 - Material de Uso e Consumo; ou 08 – Ativo Imobilizado; ou 09 -Serviços; ou 10 - Outros
insumos; ou 99 - Outras.
Campo 09 - Preenchimento: informar com o Código de Exceção de NCM, de acordo com a Tabela de Incidência do
Imposto de Produtos Industrializados (TIPI), quando existir.
Campo 10 - Preenchimento: obrigatório para todos os contribuintes na aquisição de produtos primários. A Tabela
"Gênero do Item de Mercadoria/Serviço", referenciada no Item 4.2.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008,
corresponde à tabela de "Capítulos da NCM", acrescida do código "00 - Serviço".
Validação: o valor informado no campo deve existir na Tabela “Gênero do Item de Mercadoria/Serviço”, item 4.2.1 do
Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Campo 11 - Preenchimento: informar o código de serviços, de acordo com a Lei Complementar 116/03.
Campo 12 - Preenchimento: neste campo deve ser informada a alíquota prevista em regulamento em operações de saída
interna.
REGISTRO 0205: ALTERAÇÃO DO ITEM
Este registro tem por objetivo informar alterações ocorridas na descrição do produto, desde que não o
descaracterize ou haja modificação que o identifique como sendo novo produto. Caso não tenha ocorrido movimentação no
período da alteração do item, deverá ser informada no primeiro período em que houver movimentação do item ou no
inventário.
Deverá ser ainda informado quando ocorrer alteração na codificação do produto.
Não podem ser informados dois ou mais registros com sobreposição de períodos.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0205" C 004 - O
02 DESCR_ANT_ITEM Descrição anterior do item C - - O
03 DT_INI Data inicial de utilização da descrição do item N 008* - O
04 DT_FIM Data final de utilização da descrição do item N 008* - O
05 COD_ANT_ITEM Código anterior do item com relação à última C 060 - O
informação apresentada.
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [0205]
Campo 03 - Preenchimento: informar a data inicial de utilização da descrição anterior do item.
Validação: o valor informado no campo deve ser uma data válida no formato “ddmmaaaa”.
Campo 04 - Preenchimento: informar o período final de utilização da descrição anterior do item.
Validação: o valor informado no campo deve ser uma data válida, obedecido o formato “ddmmaaaa”. O valor informado
no campo deve ser menor que o valor no campo DT_FIN do registro 0000.
REGISTRO 0206: CÓDIGO DE PRODUTO CONFORME TABELA PUBLICADA
PELA ANP (COMBUSTÍVEIS)
Este registro tem por objetivo informar o código correspondente ao produto constante na Tabela da Agência
Nacional de Petróleo (ANP) para os produtos denominados “Combustíveis”.
Deve ser apresentado apenas pelos contribuintes produtores, importadores, distribuidores e postos de
combustíveis.
Página 23 de 188

--- Página 24 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0206" C 004 - O
02 COD_COMB Código do combustível, conforme tabela publicada pela C - - O
ANP
Observações:
Nível hierárquico - 3
Ocorrência - 1:1
Campo 01 - Valor Válido: [0206]
Campo 02 - Preenchimento: utilizar o código do combustível, conforme Tabela de Produtos para Combustíveis / Solvente
(Tabela 12 de códigos de produtos para o Sistema de Informações de Movimentação de Produtos (SIMP), conforme item
3.2.1 do Ato COTEPE/ICMS nº 09, de 18 de abril de 2008.
Validação: o valor informado no campo deve existir na tabela da ANP.
Perguntas e Respostas
1) Há algum relacionamento com o campo TIPO_ITEM do registro 0200?
Resposta: Sim, esta informação é vinculada ao código do item e obrigatória quando o produto se referir a combustíveis e o
informante do arquivo for produtor, importador, distribuidor ou posto de combustível.
REGISTRO 0220: FATORES DE CONVERSÃO DE UNIDADES
Este registro tem por objetivo informar os fatores de conversão dos itens discriminados na Tabela de Identificação
do Item (Produtos e Serviços) entre a unidade informada no registro 0200 e as unidades informadas nos registros dos
documentos fiscais.
Quando for utilizada unidade de inventário diferente da unidade comercial do produto é necessário informar o
registro 0220 para informar os fatores de conversão entre as unidades.
Não podem ser informados dois ou mais registros com o mesmo conteúdo no campo UNID_CONV.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0220" C 004 - O
02 UNID_CONV Unidade comercial a ser convertida na unidade de C 006 - O
estoque, referida no registro 0200.
03 FAT_CONV Fator de conversão: fator utilizado para converter N - 6 O
(multiplicar) a unidade a ser convertida na unidade
adotada no inventário.
Observações:
Nível hierárquico - 3
Ocorrência - 1:N
Campo 01 - Valor Válido: [0220]
Campo 02 - Validação: o valor informado no campo deve existir no campo UNID do registro 0190.
Campo 03 - Validação: o valor informado no campo deve ser maior que “0” (zero).
REGISTRO 0300: CADASTRO DE BENS OU COMPONENTES DO ATIVO
IMOBILIZADO
Este registro tem o objetivo de identificar e caracterizar todos os bens ou componentes arrolados no registro G125
do Bloco G e os bens em construção.
O bem ou componente deverá ter código individualizado atribuído pelo contribuinte em seu controle patrimonial
do ativo imobilizado e não poderá ser reutilizado, duplicado, atribuído a bens ou componentes diferentes.
A discriminação do bem ou componente deve indicar precisamente o mesmo, sendo vedadas discriminações
diferentes para o mesmo bem ou componente no mesmo período ou discriminações genéricas.
As informações nos campos IDENT_MERC, DESCR_ITEM, COD_PRNC e COD_CTA devem se referir às
características atuais do bem ou componente.
Página 24 de 188

--- Página 25 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Deverá também ser apresentado registro que identifique e caracterize o bem que está sendo construído no
estabelecimento do contribuinte, a partir do período de apuração em que adquirir ou consumir o 1º componente.
Nº Campo Descrição tipo tam Dec Obrig
01 REG Texto fixo contendo "0300" C 004* - O
02 COD_IND_BEM Código individualizado do bem ou componente C 060 - O
adotado no controle patrimonial do estabelecimento
informante
03 IDENT_MERC Identificação do tipo de mercadoria: C 001* - O
1 = bem;
2 = componente.
04 DESCR_ITEM Descrição do bem ou componente (modelo, marca e C - - O
outras características necessárias a sua
individualização)
05 COD_PRNC Código de cadastro do bem principal nos casos em C 060 - OC
que o bem ou componente ( campo 02) esteja
vinculado a um bem principal.
06 COD_CTA Código da conta analítica de contabilização do bem C 060 - O
ou componente (campo 06 do Registro 0500)
07 NR_PARC Número total de parcelas a serem apropriadas, N 003 - OC
segundo a legislação de cada unidade federada
Observações:
Nível hierárquico - 2
Ocorrência – Vários (por arquivo)
Campo 01 - Valor Válido: [0300]
Campo 03: Preenchimento:
a) bem: uma mercadoria será considerada “bem” quando possua todas as condições necessárias para ser utilizado
nas atividades do estabelecimento. Quando se tratar de “bem” não poderá ser informado registro G125 com tipo de
movimentação igual a “IA”.
b) componente: uma mercadoria será considerada “componente” quando fizer parte de um bem móvel que
estiver sendo construído no estabelecimento do contribuinte, onde somente o bem móvel resultante é que possuirá as
condições necessárias para ser utilizado nas atividades do estabelecimento. Para “componentes” não poderá ser informado
o registro G125 com tipo de movimentação igual a “IM” e “CI”.
Campo 05: código do bem que esteja vinculado ao bem ou componente informado no campo 02, seja por se tratar:
a) de uma imobilização em andamento – código do bem resultante;
b) de um bem vinculado a um bem principal – código do bem principal.
Validação:
a) se o conteúdo do campo IDENT_MERC for igual a “2”, este campo deve obrigatoriamente estar preenchido com o
código do bem principal;
b) O conteúdo deste campo deve existir em outro registro no campo COD_IND_BEM que não tenha o campo
IDENT_MERC igual a “2”.
Obs.: Caso esteja digitando entrada de componentes no registro 0300 (opção CRIAR EFD-ICMS/IPI) é necessário
informar antes os registros 0500, 0600 e o código do bem principal no registro 0300.
Campo 06: Preenchimento: conta contábil de acordo com o Plano de Contas adotado pela empresa.
Validações: o conteúdo informado deve existir no campo COD_CTA e ser conta do ativo (COD_NAT_CC igual a “01”),
ambos do registro 0500 ;
Campo 07 - Preenchimento:
a) número total de parcelas a serem apropriadas do bem ou componente, segundo a legislação de cada Unidade
Federada. A maioria das Unidades Federadas adota o número total de parcelas definidas na Lei Complementar 87/96 –
48 parcelas. Entretanto, algumas Unidades Federadas podem definir um número total de parcelas de forma diversa,
seja em função da periodicidade de apuração do ICMS ou até mesmo em função de um determinado bem;
b) esta informação é obrigatória quando o bem ou componente gerar direito ao crédito de ICMS no momento da sua
entrada ou consumo.
Validação: informação obrigatória quando os campos 09 e 10 do Registro G125 estiverem preenchidos.
Página 25 de 188

--- Página 26 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
REGISTRO 0305: INFORMAÇÃO SOBRE A UTILIZAÇÃO DO BEM
Este registro tem o objetivo de prestar informações sobre a utilização do bem, sendo obrigatório quando o
conteúdo do campo IDENT_MERC do registro 0300 for igual a “1”.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0305" C 004* - O
02 COD_CCUS Código do centro de custo onde o bem está sendo ou será C 060 - O
utilizado (campo 03 do Registro 0600)
03 FUNC Descrição sucinta da função do bem na atividade do C - - O
estabelecimento
04 VIDA_UTIL Vida útil estimada do bem, em número de meses N 003 - OC
Observações:
Nível hierárquico - 3
Ocorrência – 1:1
Campo 01 - Valor Válido: [0305]
Campo 02: caso o contribuinte não adote centros de custos deverão ser informados os seguintes códigos:
a) tratando-se de atividade econômica comercial ou de serviços:
Código “1”: área operacional;
Código “2”: área administrativa;
b) tratando-se de atividade econômica industrial:
Código “3”: área produtiva;
Código “4”: área de apoio à produção;
Código “5”: área administrativa.
Validação: o conteúdo informado deve existir no campo COD_CCUS do registro 0600.
REGISTRO 0400: TABELA DE NATUREZA DA OPERAÇÃO/PRESTAÇÃO
Este registro tem por objetivo codificar os textos das diferentes naturezas da operação/prestação discriminadas nos
documentos fiscais. Esta codificação e suas descrições são livremente criadas e mantidas pelo contribuinte.
Este registro não se refere a CFOP. Algumas empresas utilizam outra classificação além das apresentadas nos
CFOP. Esta codificação permite informar estes agrupamentos próprios.
Não podem ser informados dois ou mais registros com o mesmo conteúdo no campo COD_NAT
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0400" C 004 - O
02 COD_NAT Código da natureza da operação/prestação C 010 - O
03 DESCR_NAT Descrição da natureza da operação/prestação C - - O
Observações:
Nível hierárquico - 2
Ocorrência – vários (por arquivo)
Campo 01 - Valor Válido: [0400]
Campo 02 - Validação: o valor informado no campo COD_NAT deve existir em pelo menos um registro dos demais
blocos.
REGISTRO 0450: TABELA DE INFORMAÇÃO COMPLEMENTAR DO
DOCUMENTO FISCAL
Este registro tem por objetivo codificar todas as informações complementares dos documentos fiscais exigidas
pela legislação fiscal. Estas informações constam no campo “Dados Adicionais” dos documentos fiscais.
Esta codificação e suas descrições são livremente criadas e mantidas pelo contribuinte e não podem ser informados
dois ou mais registros com o mesmo conteúdo no campo COD_INF.
Deverão constar todas as informações complementares de interesse do fisco existentes nos documentos fiscais.
Exemplo: nos casos de documentos fiscais de entradas de devolução, informar o documento fiscal referenciado.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0450" C 004 - O
Página 26 de 188

--- Página 27 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
02 COD_INF Código da informação complementar do documento C 006 - O
fiscal.
03 TXT Texto livre da informação complementar existente no C - - O
documento fiscal, inclusive espécie de normas legais,
poder normativo, número, capitulação, data e demais
referências pertinentes com indicação referentes ao
tributo.
Observações:
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [0450]
Campo 02 - Validação: o valor informado deve existir em pelo menos um registro dos demais blocos.
REGISTRO 0460: TABELA DE OBSERVAÇÕES DO LANÇAMENTO FISCAL
Este registro é utilizado para informar anotações de escrituração determinadas pela legislação pertinente aos
lançamentos fiscais, tais como: ajustes efetuados por diferimento parcial de imposto, antecipações, diferencial de alíquota e
outros.
Esta codificação e suas descrições são de atribuição do contribuinte e não podem ser informados dois ou mais
registros com o mesmo conteúdo no campo COD_OBS.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0460" C 004 - O
02 COD_OBS Código da Observação do lançamento fiscal. C 006 - O
03 TXT Descrição da observação vinculada ao lançamento fiscal C - - O
Observações:
Nível hierárquico - 2
Ocorrência –vários (por arquivo)
Campo 01 - Valor Válido: [0460]
Campo 02 -Validação: o valor informado neste campo deve existir em pelo menos um registro dos demais blocos.
Campo 03 - Preenchimento: este campo corresponde às informações lançadas na coluna “Observação” dos Livros Fiscais
de Entradas, Saídas e de Apuração, de acordo com o estabelecido na legislação de cada unidade federada.
REGISTRO 0500: PLANO DE CONTAS CONTÁBEIS
Este registro tem o objetivo de identificar as contas contábeis utilizadas pelo contribuinte informante em sua
Contabilidade Geral, relativas às contas referenciadas no registro 0300. Não podem ser informados dois ou mais registros
com a mesma combinação de conteúdo nos campos DT_ALT e COD_CTA.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo “0500” C 004* - O
02 DT_ALT Data da inclusão/alteração N 008* - O
03 COD_ NAT_CC Código da natureza da conta/grupo de contas: C 002* - O
01 - Contas de ativo;
02 - Contas de passivo;
03 - Patrimônio líquido;
04 - Contas de resultado;
05 - Contas de compensação;
09 - Outras.
04 IND_CTA Indicador do tipo de conta: C 001* - O
S - Sintética (grupo de contas);
A - Analítica (conta).
05 NÍVEL Nível da conta analítica/grupo de contas. N 005 - O
06 COD_CTA Código da conta analítica/grupo de contas. C 60 - O
07 NOME_CTA Nome da conta analítica/grupo de contas. C 60 - O
Página 27 de 188

--- Página 28 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Observações:
Nível hierárquico - 2
Ocorrência - vários (por arquivo)
Campo 01 - Valor Válido: [0500];
Campo 02 - Preenchimento: informar no padrão “diamêsano” (ddmmaaaa), excluindo-se quaisquer caracteres de
separação, tais como: ".", "/", "-".
Validação: a data não pode ser maior que a constante no campo DT_FIN.
Campo 03:Valores Válidos: [01, 02, 03, 04, 05, 09];
Campo 04:Valores Válidos: [S, A];
REGISTRO 0600: CENTRO DE CUSTOS
Este registro tem o objetivo de identificar os centros de custos referenciados no registro 0305.
Não podem ser informados dois ou mais registros com a mesma combinação de conteúdo nos campos DT_ALT e
COD_CCUS.
Nº Campo Descrição tipo TAM Dec Obrig
01 REG Texto fixo contendo “0600”. C 004* - O
02 DT_ALT Data da inclusão/alteração. N 008* - O
03 COD_CCUS Código do centro de custos. C 060 - O
04 CCUS Nome do centro de custos. C 060 - O
Observações:
Nível hierárquico - 2
Ocorrência - vários (por arquivo)
Campo 01 - Valor Válido: [0600].
Campo 02 - Preenchimento: informar no padrão “diamêsano” (ddmmaaaa), excluindo-se quaisquer caracteres de
separação, tais como: ".", "/", "-".
Validação: a data não pode ser maior que a constante no campo DT_FIN.
Campo 03 - Preenchimento: caso o contribuinte não adote centros de custos deverão ser informados os seguintes códigos:
a) tratando-se de atividade econômica comercial ou de serviços:
Código “1”: área operacional;
Código “2”: área administrativa;
b) tratando-se de atividade econômica industrial:
Código “3”: área produtiva;
Código “4”: área de apoio à produção;
Código “5”: área administrativa.
REGISTRO 0990: ENCERRAMENTO DO BLOCO 0
Este registro tem por objetivo identificar o encerramento do bloco 0 e informar a quantidade de linhas (registros)
existentes no bloco.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "0990" C 004 - O
02 QTD_LIN_0 Quantidade total de linhas do Bloco 0 N - - O
Observações:
Nível hierárquico - 1
Ocorrência – um por arquivo
Campo 01 - Valor Válido: [0990]
Campo 02 - Preenchimento: a quantidade de linhas (registros) a ser informada deve considerar também os próprios
registros de abertura e encerramento do bloco. Para este cálculo, o registro 0000, mesmo não pertencendo ao bloco 0, deve
ser somado.
Página 28 de 188

--- Página 29 ---
Guia Prático EFD-ICMS/IPI – Versão 2.0.12
Atualização: março 2013
Validação: o número de linhas (registros) existentes no bloco 0 é igual ao valor informado neste campo.
BLOCO C: DOCUMENTOS FISCAIS I - MERCADORIAS (ICMS/IPI)
REGISTRO C001: ABERTURA DO BLOCO C
Este registro tem por objetivo identificar a abertura do bloco C, indicando se há informações sobre documentos
fiscais.
Nº Campo Descrição Tipo Tam Dec Obrig
01 REG Texto fixo contendo "C001" C 004 - O
02 IND_MOV Indicador de movimento: C 001 - O
0- Bloco com dados informados;
1- Bloco sem dados informados
Observações:
Nível hierárquico - 1
Ocorrência - um por arquivo
Campo 01 - Valor válido: [C001]
Campo 02 - Valores válidos: [0, 1]
Validação: se o valor deste campo for igual a “1” (um), somente podem ser informados os registros de abertura e
encerramento do bloco. Se o valor neste campo for igual a “0” (zero), deve ser informado pelo menos um registro além dos
registros de abertura e encerramento do bloco.
REGISTRO C100: NOTA FISCAL (CÓDIGO 01), NOTA FISCAL AVULSA (CÓDIGO
1B), NOTA FISCAL DE PRODUTOR (CÓDIGO 04), NF-e (CÓDIGO 55) e
NFC-e (CÓDIGO 65).
Este registro deve ser gerado para cada documento fiscal código 01, 1B, 04, 55 e 65, conforme item 4.1.1 do Ato
COTEPE/ICMS nº 09, de 18 de abril de 2008, registrando a entrada ou saída de produtos ou outras situações que envolvam
a emissão dos documentos fiscais mencionados.
A partir do mês de referência abril de 2012, a informação do campo CHV_NFE passa a ser obrigatória em todas as
situações, exceto para NFe com numeração inutilizada (COD_SIT = 05).
IMPORTANTE: para documentos de entrada, os campos de valor de imposto/contribuição, base de
cálculo e alíquota só devem ser informados se o adquirente tiver direito à apropriação do crédito
(enfoque do declarante).
Para cada registro C100, obrigatoriamente deve ser apresentado, pelo menos, um registro C170 e um registro
C190, observadas as exceções abaixo relacionadas:
Exceção 1: Para documentos com código de situação (campo COD_SIT) cancelado (código “02”), cancelado
extemporâneo (código “03”), Nota Fiscal Eletrônica (NF-e) denegada (código “04”), preencher somente os campos REG,
IND_OPER, IND_EMIT, COD_MOD, COD_SIT, SER, NUM_DOC e CHV_NF-e. Para COD-SIT = 05 (numeração
inutilizada), todos os campos referidos anteriormente devem ser preenchidos, exceto o campo CHV_NF-e. Demais campos
deverão ser apresentados com conteúdo VAZIO “||”. Não informar registros filhos. A partir de janeiro de 2011, no caso de
NF-e de emissão própria com código de situação (campo COD_SIT) cancelado (código “02”) e cancelado extemporâneo
(código “03”) deverão ser informados os campos acima citados incluindo ainda a chave da NF-e.
Exceção 2: Notas Fiscais Eletrônicas - NF-e de emissão própria: regra geral, devem ser apresentados somente os registros
C100 e C190, e, se existirem ajustes de documento fiscais determinados por legislação estadual (tabela 5.3 do Ato
COTEPE ICMS 09/08), devem ser apresentados também os registros C195 e C197; somente será admitida a informação
do registro C170 quando também houver sido informado o registro C176, hipótese de emissão de documento fiscal quando
houver direito a Ressarcimento de ICMS em Operações com Substituição Tributária. A critério de cada UF, informar os
registros C110 e C120, a partir de julho de 2012. ;
Exceção 3: Notas Fiscais Complementares e Notas Fiscais Complementares Extemporâneas (campo COD_SIT igual a
“06” ou “07”): nesta situação, somente os campos REG, IND_EMIT, COD_PART, COD_MOD, COD_SIT, NUM_DOC e
DT_DOC são de preenchimento obrigatório, devendo ser preenchida a data de efetiva saída, para os contribuintes das UFs
Página 29 de 188

