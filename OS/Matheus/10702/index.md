**Abertura Tramite**

- Módulo: Sped Reinf
- Problema:  Ao importar a planilha do 2055 para excluir um arquivo não esta gerando o r9000
- Solução: Problema estava na geração do 9000, estava pegando a empresa errada. Após fazer a correção passou a gerar na empresa certa.
- Objeto(s) (Oracle / SQL Server): 
  - sp_tmp_srf_r2055_aquisicao.sql - versao: 15
- Testes no Banco: Oracle
- Sugestão de teste / Resultado esperado :
  - Importar a planilha do 2055 para incluir e transmitir. Depois na planilha colocar o registro para excluir e deve gerar o r9000. E emm seguida transmitir novamente.

**Abertura Tramite**

- Módulo: Sped Reinf
- Problema: Ao importar o registro do 2055 com status I sendo este registro já transmitido esta deletando o registro filho.
- Solução: Feito a correção para não deletar o registro filho dos registro já transmitidos e na planinha esta com o status I.
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_tmp_srf_r2055_aquisicao.sql - versao: 15
  - sp_tmp_srf_r2055_aquisicao.sql - versao: 16
- Testes no Banco: Oracle / SQL Server
- Sugestão de teste / Resultado esperado :
  - Transmitir registro com sucesso do 2055
  - Na sequencia importar o excel com os registro de status I para os registro já transmitido com sucesso e não deve deletar os registro filhos do mesmo e não deve mudar nenhum status.

**Abertura Tramite**

- Módulo: Sped Reinf
- Problema: Retificar o registro 2055 com erro.
- Solução: Fizemos uma reformulação para abranger todos os status possivel do evento.
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_auditoria_srf_r2055.sql - versao: 3
  - sp_auditoria_srf_r2055.sql - versao: 4
  - sp_tmp_srf_r2055_aquisicao.sql - versao: 17
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Precisa testar todas as possibilidades e montar todos os possiveis erros que pode ocorrer. Seguir a planilha que a flávia fez.



**Abertura Tramite**

- Módulo: Sped Reinf
- Problema:  Ao importar a planilha do 2055 para excluir um arquivo não esta gerando o r9000
- Solução: Problema estava na geração do 9000, estava pegando a empresa errada. Após fazer a correção passou a gerar na empresa certa.
- Objeto(s) (Oracle / SQL Server): 
  - sp_tmp_srf_r2055_aquisicao.sql - versao: 15
- Testes no Banco: Oracle
- Sugestão de teste / Resultado esperado :
  - Importar a planilha do 2055 para incluir e transmitir. Depois na planilha colocar o registro para excluir e deve gerar o r9000. E emm seguida transmitir novamente.

**Abertura Tramite**

- Módulo: Sped Reinf
- Problema: Ao importar o registro do 2055 com status I sendo este registro já transmitido esta deletando o registro filho.
- Solução: Feito a correção para não deletar o registro filho dos registro já transmitidos e na planinha esta com o status I.
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_tmp_srf_r2055_aquisicao.sql - versao: 15
  - sp_tmp_srf_r2055_aquisicao.sql - versao: 16
- Testes no Banco: Oracle / SQL Server
- Sugestão de teste / Resultado esperado :
  - Transmitir registro com sucesso do 2055
  - Na sequencia importar o excel com os registro de status I para os registro já transmitido com sucesso e não deve deletar os registro filhos do mesmo e não deve mudar nenhum status.


*Para sql server*

**Abertura Tramite**

- Módulo: Sped Reinf
- Problema: Retificar o registro 2055 com erro.
- Solução: Fizemos uma reformulação para abranger todos os status possivel do evento.
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_tmp_srf_r2055_aquisicao.sql - versao: 16
- Testes no Banco: SQL Server
- Sugestão de teste / Resultado esperado :
  - Precisa testar todas as possibilidades e montar todos os possiveis erros que pode ocorrer. Seguir a planilha que a flávia fez.

**Retornos da daiane**

Fechamento com erros

- Testes apresentaram erros que estão descritos "conforme lista abaixo":

- Mudar mensagem de erro não legível, na auditoria do R2055.
   'Verificar cadastro do Participante. Cadastro provavelmente não possui registro item.' - feito

- *Nome do Formulário: frmSRF_Manutencao_TMP_Reinf Caminho do Menu: Manutenção -> Tabela Temporária


***STATUS 5: ERRO "NÃO É PERMITIDO INCLUIR REGISTRO EM EVENTO A EXCLUIR. SE NECESSÁRIO UTLIZA DA SITUAÇÃO
"A" PARA ALTERAR O REGSITRO." status 8: Erro REGISTRO N?O PODE SER ALTERADO, CONSULTE AO SUPORTE!" 
***Status 8: Erro REGISTRO N?O PODE SER ALTERADO, CONSULTE AO SUPORTE!"   
 
 Palavra registro e não estão escritos errados. -- FEITO

- Verificar status 1 (XML Gerado) com mudança de dados e situação de registro I = erro "ESTE REGISTRO JÁ 
 EXISTE INSERIDO. SE NECESSÁRIO UTILZE DA SITUAÇÃO "A" PARA ALTERA-LO." (verificar se o sistema deve 
 acatar e mudar ou se realmente só trazer a msg de erro). ----- sim, este está certo.

- VERIFICAR: STATUS 1 (XML Gerado) com mudança de dados e situação de registro A = status voltou para 0 
 confirmar se era a ação esperada. ------- sim, este está certo.

- Situação: Status 2 (Transmitido com sucesso)sem mudança de dados e situação de registro A = ELE NÃO 
 RECONHECEU MANTEVE AS MESMAS INFORMAÇÕES PORÉM MUDOU O STATUS PARA 0. -- FEITO

- Situação: Status 3 (Transmitido com erro) com mudança de dados e situação de registro A = ELE FEZ AS 
 MUDANÇAS PORÉM NÃO TRANSMITE. -- FEITO

- Situação: Status 5 (A Excluir) com situação de registro E = Criou evento de retificado no anterior. 
 O esperado era não fazer nada. -- JÁ ESTAVA CERTO

- Situação: Status 7 (Excluido com erro)com situação de registro E = ele muda para status 5 (A Excluir),
porém NÃO CONSIGO TRANSMITIR O EVENTO/ Não criou mais eventos. 

- Situação: Status 8 (retificado)com situação de registro E = "TRAVOU" VERIFICAR: REGISTRO NÃO PODE SER 
ALTERADO, CONSULTE AO SUPORTE! - certo


**Abertura Tramite**

- Módulo: Sped Reinf
- Problema: Erros encontrados na importação planilha do 2055
- Solução: Feito a analise dos erro e corrigidos os que eram erro de fato um erro.
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_auditoria_srf_r2055.sql - versao: 4
  - dbo.sp_tmp_srf_r2055_aquisicao.sql - versao: 18
  - sp_auditoria_srf_r2055.sql - versao: 5
  - sp_tmp_srf_r2055_aquisicao.sql - versao: 19
- Testes no Banco: Oracle e SQL
- Sugestão de teste / Resultado esperado :
  - Na auditori do 2055. Gerar erro na pessoa. APagar o cpf/cnpj da pessoa que será importada na planilha e verificar se a mensagem de erro está coerente.
  - Verificar se as mensagem dos Log estão chegando com a acentuáção correto, sem os caracteres estranhos.
  - Status 2 e 3 e a situação A na planilha, dar messagem se os dados forem iguais ao que já esta cadastrado, se os dados forem diferntes deve acatar e mudar o status para gerado.
  - Refaça o teste do Status 7, não pode fazer update para 7 se o status estiver 2, só pode fazer update se o status estiver 5. Foi testado e esta tudo certo.
  - O restante da lista do retono estão certo.

-----------------------------------------------------------

**Abertura Tramite**

- Módulo: Sped Reinf
- Problema:Na tmp permite inserir código deferente de pessoa com o mesmo cnpj sendo importado um por um. Portanto precisa que a auditoria pegue essas pessoas com o mesmo cnpj/cpf
- Solução: Feito na auditoria a validação de cpf/cnpj duplicado para pessoas diferentes.
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_auditoria_srf_r2055.sql - versao: 5
  - sp_auditoria_srf_r2055.sql - versao: 6
  - in_definicao_erro.txt - versao: 500
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Criar duas pessoas com o mesmo cnpj/cpf
  - Importar elas pela planilha uma por vez
  - E fazer a transmissão, neste momento a auditoria deve pegar essas 2 pessoas que tem o mesmo cnpj/cpf

---

- Solução e dependências: Reformulação da importação R2055
- Objeto(s) (Oracle / SQL Server) a ser atualizado:
  - dbo.sp_auditoria_srf_r2055.sql - versao: 6
  - dbo.sp_tmp_srf_r2055_aquisicao.sql - versao: 20
  - sp_auditoria_srf_r2055.sql - versao: 6
  - sp_tmp_srf_r2055_aquisicao.sql - versao: 21
  - in_definicao_erro.txt - versao: 500
- Versão: 243.
- Data de liberação: 10/10/2022.