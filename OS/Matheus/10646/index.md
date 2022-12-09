
**Abertura Tramite**

- Módulo: Sped Fiscal
- Problema: Relatório abre por de trás da tela Ac_C050
- Solução: Transformado a tela em fsMDIChild para o relatório abrir normal
- Formulário(s) (Delphi):
  - ac_c050_entrada.pas - versao: 5
  - ac_c050_saida.pas - versao: 4
  - in_nota_fiscal_entrada.pas - versao: 32
  - in_nota_fiscal_saida.pas - versao: 36
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
- Caminho do Menu: Manutenção - (C e D) Documento Fiscal - Mercadoria e Serviço - Nota Fiscal Entrada Emitida por Terceiro - Botõo Engrenagem - PIS/COFINS
- Caminho do Menu: Manutenção - (C e D) Documento Fiscal - Mercadoria e Serviço - Nota Fiscal Saída/Entrada Emitida pela Pessoa Jurídica
- Nestas 2 telas abrir o relatório para verificar se o relatório abre sem nada na sua frente
- Nestas 2 telas abrir o relatório de log (Botão com uma Imagem de I) para verificar se o relatório abre sem nada na sua frente
  
---

- Solução e dependências: Permitir abrir o relatório sem que a tela dele fiquei na frente.
- Caminho Completo Menu:
  - Caminho do Menu: Manutenção - (C e D) Documento Fiscal - Mercadoria e Serviço - Nota Fiscal Entrada Emitida por Terceiro - Botão Engrenagem - PIS/COFINS
  - Caminho do Menu: Manutenção - (C e D) Documento Fiscal - Mercadoria e Serviço - Nota Fiscal Saída/Entrada Emitida pela Pessoa Jurídica - Botão Engrenagem - PIS/COFINS
- Versão: 242
- Data de liberação: 27/05/2022