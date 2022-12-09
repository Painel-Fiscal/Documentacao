
# Documentação / Guia
- [091_raiz-cnpj_aaaammddhhmm_ttttttttttttttt.xlsx](/OS/Matheus/10776/Anp_diario/091_raiz-cnpj_aaaammddhhmm_ttttttttttttttt.xlsx) 
- [carga-edc-orientacoes-empresas.pptx](/OS/Matheus/10776/Anp_diario/carga-edc-orientacoes-empresas.pptx)
- [manual-carga-091.pdf](/OS/Matheus/10776/Anp_diario/manual-carga-091.pdf)
- [manual-web-service.pdf](/OS/Matheus/10776/Anp_diario/manual-web-service.pdf)
- [perguntas-frequentes-ranp868-2022.pdf](/OS/Matheus/10776/Anp_diario/perguntas-frequentes-ranp868-2022.pdf)
- [ResoluçãoANP_868_18022022.docx](/OS/Matheus/10776/Anp_diario/Resolu%C3%A7%C3%A3oANP_868_18022022.docx)

# Desenvolver

OS 10776
- Nome da Tela: Estoque Diário
- Desenvolver Tela
- Geração
- Exportação (em excel)
- Trigger para as tabelas
- Tabela - anp_estoque_diario;
- Menu:
- ![menu](/OS/Matheus/10776/diret%C3%B3rio%20do%20novo%20menu.png "Diretório do novo menu")


# Tramites

**Abertura Tramite**

- Módulo: Sped Tributações Acessorias
- Problema: Gerar Planilha de Estoque Diário
- Solução: Precisou criar um tela das movimentações de Estoque Diário, feito a geração e exportação da planilha.
- Objeto(s) (Oracle / SQL Server): 
  - bi_anp_estoque_diario.sql - versao: 2
  - dbo.bi_anp_estoque_diario.sql - versao: 2
  - dbo.sp_gera_anp_estoque_diario.sql - versao: 2
  - sp_gera_anp_estoque_diario.sql - versao: 2
  - config_oof.txt - versao: 77
- Script(s):
  - script_1413.script
- Formulário(s) (Delphi):
  - abre_form_outras_obrigacoes.pas - versao: 20
  - anp_estoque_diario.pas - versao: 3
  - ctrl_feriado.pas - versao: 1
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Caminho do Menu: Federal -> Anp -> Manutenção -> Nota Fiscal de Entrada
  - Caminho do Menu: Federal -> Anp -> Manutenção -> Estoque Diário
  - Caminho do Menu: Federal -> Anp -> Manutenção -> Cadastro de Feriado
  - Testar a tela Estoque Diário, fazer todas as operações, adicionar, editar e deletar.
  - Testar a tela Cadastro de Feriado, fazer todas as operações, adicionar, editar e deletar.
  - Gerar dados no Estoque Diário Os dados será gerado atraves dos dados informado na Nota Fiscal de Entrada.
  - A geração deve escolher um periodo para gerar e a geração deve respeitar as datas escolhidas.
  - A geração deve seguir algumas regras de filtro para gerar o estoque Diário
	- Regras - Finais de Semana/Feriados não deve levar os registros que tem o campo código instalação 2 informado
  - Exportar o excel, deve exportar 1 excel por dia. E deve respeitar e deve respeitar as datas do periodo informado.
  - A exportação deve ser exportado com os dados do Estoque Diário

-------------------------------------------------------------

- Testes apresentaram erros que estão descritos "conforme lista abaixo"

- Caminho do Menu: Federal -> Anp -> Manutenção -> Nota Fiscal de Entrada
    - Gerar dados no Estoque Diário Os dados seráo gerados através dos dados informado na Nota Fiscal de Entrada. 
  
Erro: quando tira as informações do CD instalação2 ele apresenta erro na tela de estoque Diário
--------------------------------------------------

-exportação em excel gera com dia e mês invertido.(Data Referencia e Data da Chegada).

- Quando é gerado com data de feriado ele não retorna informação até então esta correto. 
Eu edito a nota de entrada pra dia util dentro do meso mês e tento gerar novamente ele traz esta mensagem de erro: 
Access violation at address 006BF4F1 in module 'MF_Tributacoes_Acessorias.exe'. Read of address 000003D8.

---

**Abertura Tramite**

- Módulo: Sped Tributações Acessorias
- Problema: Melhorar os feriados com data moveis
- Solução: Para os feriados com data moveis, por exemplo carnaval onde cada ano tem uma data diferente, criamos opção para o cliente informar este feriados quando for data moveis.
Também criamos um importa/ exporta arquivo de configuração com os feriados nacionais e estaduais. Os feriados municipais vai ficar ao critério do cliente preencher.
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_gera_anp_estoque_diario.sql - versao: 3
  - sp_gera_anp_estoque_diario.sql - versao: 3
  - ctrl_feriado.txt - versao: 1
- Formulário(s) (Delphi):
  - anp_estoque_diario.pas - versao: 5
  - anp_exportacao_importacao_conf.pas - versao: 2
  - atualizacao.pas - versao: 27
  - ctrl_feriado.pas - versao: 2
  - export_import_conf.pas - versao: 45
  - importa_config.pas - versao: 48
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - Testar a tela de cadastro de feriado. "Caminho do Menu: Federal -> Anp -> Manutenção -> Cadastro de Feriado"
  - Este cadastro acima é exportado/importado testar tbm esta funcionalidade. "Caminho do Menu: Federal -> Anp -> configuração -> Importação/exportação de configuração"
  - Testar esta mesma Importação dentro do systemupdate, onde atualizamos a versão.
  - Testar novamente a geração do estoque Diário onde foram corrigidas o tramite anterior
  - Testar novamente a geração da planilha periodo do mes 1 para os dias 2,3,4, não esta mais invertendo o dia pelo mes.
  - não esta gerando no estoque Diário os feriados e nem os feriados com data moveis. Testa-los.
  - Quando informado a instalação 2 não deve gerar o estoque Diário
  - Sabado e domingo não devem ser gerados no estoque Diário

----

- Módulo: Sped Tributações Acessorias
- Problema: O excel a data tem que ter este formato yyyymmdd. A geração do estoque diario deve pegar as movimentação das empresas filiais. 
A geração deve contabilizar as movimentações dos finais de semana e feriados e jogar para o proximo dia util.
Tambem foi craido o relatério na tela. E criado relatério de log em caso de erro na geração.
- Solução:         
- Objeto(s) (Oracle / SQL Server): 
  - dbo.sp_gera_anp_estoque_diario.sql - versao: 6
  - sp_gera_anp_estoque_diario.sql - versao: 5
- Formulário(s) (Delphi):
  - anp_estoque_diario.pas - versao: 8
  - relatorio_anp_estoque_diario.pas - versao: 1
  - relatorio_in_log_importacao_sped.pas - versao: 24
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - O excel as datas deve esta com o formato yyyymmdd (ano/mes/dia sem as barras)
  - Deve fazer movimentação nas empresas filiais e na matriz e na matriz gerar a movimentação e os valores devem ser agrupados na matriz.
  - Os finais de semana e feriado deve ser somados e inseridos no dia util. então deve fazer movimentação nos finais de semana e feriado e verificar na geração o proximo dia util
se foi somado os valore referentes ao dias anteriores. Lembrar tbm de fazer este teste com as filiais.
  - Verificar se o relatério esta abrindo e analisar o conteudo, ou seja, se o estoque esta sendo gerado corretamente.
  - A geração se ocorrer qualquer erro deve apresentar um relatério contendo o erro.

---

- Módulo: Sped Tributações Acessorias
- Problema: Nome do excel precisa de numero de versão para identificar um novo envio a cada vez que for gerado
- Solução: O Nome do arquivo excel ao final ter� 15 digitos para identificar o numero de versão
- Script(s):
  - script_1427.script
- Formulário(s) (Delphi):
  - anp_estoque_diario.pas - versao: 9
- Testes no Banco: Oracle e SQL Server
- Sugestão de teste / Resultado esperado :
  - O nome do arquivo excel no final ter� 15 digitos sequencial, iniciando com _000000000000001 e será incrementado conforme for sendo gerado o excel.