**Abertura Tramite**

- Módulo: Sped ECF
- Problema: Corrigir a importação excel
- Solução: Na tela "Contas Parte B - eLalur e eLacs" na aba de importação foi corrigido a importação excel
- Formulário(s) (Delphi):
  - scf_parte_b.pas - versao: 6
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Caminho do Menu: Manutenção -> CADASTRO AUXILIAR -> Contas Parte B - eLalur e eLacs
  - Na aba de importação realizar a importação excel e os dados precisam serem importados para esta mesma tela.
  - Planilha se encontra em anexo para realizar o teste.

----------------------------------------

**Abertura Tramite**

- Módulo: Sped ECF
- Problema: Só importa somente 1 linha do registo que existem 2 linhas do mesmo registro.
- Solução: As 2 linhas é referente á 1 pai e 2 filhos, Portanto o "Saldo" deve haver 2 registro para 1 "Conta Parte - B". 
Feito a correção na validação de busca pelo saldo, onde faltava validar o tipo do imposto.
- Formulário(s) (Delphi):
  - scf_parte_b.pas - versao: 7
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
   - Ao importar a planilha, nela existe 2 registro "IFRS 16" onde tem que inserir um registro para a "Conta Parte - B" e dois registro para o "Saldo".
   - Segue em anexo uma amostra de como deve ficar o registro após a importação.


**Fechamento com sucesso**

- Solução: Corrigido para importar pai e filhos da mesma planilha. Fazendo o Saldo importar corretamente.
- Versão:243.
- Data de liberação: 01/08/2022. 