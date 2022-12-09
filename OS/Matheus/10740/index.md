
**** Abertura Tramite
- Módulo: Sped Reinf
- Problema: O relatório esta realizando a somatória de registro que tem o status de excluído com sucesso
- Solução: Retirar estes registro que estão com status 6, excluído com sucesso, da consulta.
- Objeto(s) (Oracle / SQL Server):
- Script(s):
- Formulário(s) (Delphi):
  - relatoriosrf_r2010.pas - versao: 12
  - relatoriosrf_r2010_sintetico.pas - versao: 7
  - relatoriosrf_r2020.pas - versao: 11
  - relatoriosrf_r2020_sintetico.pas - versao: 7
  - relatoriosrf_r2040.pas - versao: 2
  - relatoriosrf_r2050.pas - versao: 8
  - relatoriosrf_r2055.pas - versao: 10
  - relatoriosrf_r2060.pas - versao: 7
- Testes no Banco: Oracle / SQL Server
Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - O mesmo registro vc irá transmitir e depois exclui-lo e em seguida irá criar o mesmo registro e transmiti-lo. Ao fazer o relatório deve aparecer somente 1 registro. Fazer para todos os eventos. R2010, R2020, R2040, R2050, R2055 e R2060.


-------------------retorno--------------------------

- Testes apresentaram erros que estão descritos "conforme lista abaixo":

R2010 - SQL E ORACLE - feito
  

- No relatório o campo do CNPJ não aparece todos os digitos.  - FEITO

Nome do Formulário: frmSRF_R2010_1
Caminho do Menu: 

--------------------------------------------------


R2020 - ORACLE (VERIFICAR SE OCORRE EM SQL)

-- NR_ITEM_EVENTO_DELETADO

** Ao excluir um registro na nota fiscal de saida e tamb�m já existe um retificação para este registro 
esta gerando o r9000 errado. Ele gera o r9000 do retificado e do transmtido com sucesso. 
Sendo necessário só gerar o que foi transmitido com sucesso.
** obs verificar o insert do NR_ITEM_EVENTO_DELETADO do r9000. -  feito
 
--------------------------------------------------

R2040 - SQL E ORACLE

- falta de hit. 
- Corrigir as telas do R2040, aba evento e exportação.

Nome do Formulário: frmSRF_R2040
Caminho do Menu: 
Manutenção -> Movimentação -> R2040 - Recursos Repassados para Associação Desportiva

--------------------------------------------------

R2050 - SQL E ORACLE

- No caminho abaixo em 'EVENTOS' a aba 'TOTAIS' os botões de navegação da parte inferior não funcionam.
- falta de hit.

Caminho do Menu: Manutenção -> Movimentação -> R2050 - Comercial. da Produção por Produtor Rural PJ/Agroin.

--------------------------------------------------

R2055 - SQL E ORACLE - feito

- Verificar a somatória da coluna 'Vl. Desc. GILRAT' no relatório. - feito
- Verificar no relatório as quebras e repetição de período. - esta certo

Caminho do Menu: Manutenção -> Movimentação -> R2055 - Aquisição de produção rural

--------------------------------------------------
R2060 - SQL E ORACLE - feito

- Trocar a data de Oracle para SQL da TMP R2060, pois consta erro. - Feito

Caminho do Menu: Manutenção -> Movimentação -> R2060 - Contrib. Previdenciária sobre a Receita Bruta - CPRB


-----------------------------------RETORNO------------------------------------------------------------------

**** Abertura Tramite
- Módulo: Sped Reinf
- Problema: Achado erros na geração 2010 e 2020, relatório do 2010 e 2055 e TMP do 2060
- Solução: Correção na geração 2010 e 2020, melhorias no relatório 2010 e 2055 e corrido a tmp do 2060
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_gera_srf_movimentacao.sql - versao: 20
  - dbo.sp_tmp_srf_r2060_atividade.sql - versao: 4
  - sp_gera_srf_movimentacao.sql - versao: 22
- Formulário(s) (Delphi):
  - relatoriosrf_r2010_sintetico.pas - versao: 8
  - relatoriosrf_r2055.pas - versao: 11
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Testar geração 2010 e 2020. Inserir uma nota fiscal, gerar reinf e transmitir. 
Na sequência editar a nota fiscal e gerar o reinf e não transmitir e excluir a nota fiscal
então deve gerar o r9000 e deixar o evento que foi transmitido como A transmitir.
  - não relatório do 2010 aumentou o campo da descrição da pessoa, assim parecendo o cnpj
e a razão social completa.
  - relatório 2055 o campo Vl. Desc. GILRAT o ultimo campo deve esta com a somatória.
  - Na TMP corridigo a importação da data. Portanto tem que importar o registro.
  - 2040 e 2050 não será feito aqui nesta OS

----------------------RETORNO COM ERRO---------------------------------------------

- Testes apresentaram erros que estão descritos "conforme lista abaixo":

2010 E 2020

Nome do Formulário: frmSRF_R2020
Caminho do Menu: 
Manutenção -> Movimentação -> R2020 - Retenção Contrib. Previdenciária - Serviços Prest.

Nome do Formulário: frmSRF_R2010
Caminho do Menu: 
Manutenção -> Movimentação -> R2010 - Retenção Contrib. Previdenciária - Serviços Tomados

STATUS TRANSMITIDO COM ERRO DEPOIS DE EXCLUIR A NOTA E GERAR O 
STATUS DOS EVENTOS não estão COERENTES.

--------------------------------------------------

2010 E 2020

Aba 'Pesquisa'/botão 'Exclusóo' funciona somente com o atalho F7.

Nome do Formulário: frmIN_NF_Entrada_Servico
Caminho do Menu: 
Manutenção -> Notas -> Nota Fiscal de Entrada Serviço s/ Icms


- Módulo: Sped Fiscal
- Problema: Excluir um evento quando estiver com status gerado durante a retificação
- Solução: Feito a correção para conseguir excluir em qualquer momento que o status estiver
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_gera_srf_movimentacao.sql - versao: 22
  - dbo.sp_tmp_srf_r2060_atividade.sql - versao: 4
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Exemplos para fazer o 2010 e 2020.
  - Lançaar nota -> gerar reinf -> transmitir -> editar a nota -> gera reinf -> excluie a nota -> gera -> transmite. Analisa o que acontece. Tem que esta com o evento excluido
  - Lançaar nota -> gerar reinf -> excluie a nota -> Analisa o que acontece. Tem que ficar com status excluido
  - Lançaar nota -> gerar reinf -> transmitir -> editar a nota -> gera reinf -> transmite -> editar a nota -> gera reinf -> excluie a nota -> gera -> transmite. Analisa o que acontece. Tem que esta com o evento excluido