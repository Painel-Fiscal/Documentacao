**Abertura Tramite**

- Módulo: Sped Reinf
- Problema: Relatório tem calculo do campo Op. Contrib. Previ. Colocar opção de calcular ou não com este campo preenchido.
- Solução: Criado uma nova opção no filtro do relatório onde o cliente terá opção de somar ou não com o campo Op. Contrib Previ informado no registro do 2055.
- Formulório(s) (Delphi):
  - filtro_movimento_reinf.pas - versao: 6
  - relatoriosrf_r2055.pas - versao: 7
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Caminho do Menu: Manutenção -> Movimentação -> R2055 - Aquisição de produção rural -> Relatório
  - Importar o excel do 2055 com o campo Tipo Contrib Prev. com 'S'
  - No relatório ele irá somar esse registro quando estiver marcado, caso contrário não irá somar.


- Solução e dependências:
  - Criado uma nova opção no filtro do relatório onde o cliente terá opção de somar ou não com o campo Op. Contrib Previ informado no registro do 2055.
- Caminho Completo Menu:
  - Caminho do Menu: Manutenção -> Movimentação -> R2055 - Aquisição de produção rural -> Relatório
- Versão: 242
- Data de liberação: 20/05/2022