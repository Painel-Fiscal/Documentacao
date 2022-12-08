# OS 10801
|PASSO|DESCRICAO|STATUS|
|:---:|---------|------|
|1|Telas/Relatorios/Atualizações|Realizado/Liberado|
|2|Exportações|Realizado/Liberado|
|3|Importações|Em Andamento|
|4|Auditorias|Não Realizado|
||||

## Scripts 1415 e 1416

---

## Principais alterações no Guia Prático da EFD-ICMS/IPI - versão 3.1.0

---

### 1. Descontinuação dos códigos 04 e 05 da tabela 4.1.2 - Tabela Situação de Documentos a partir de 31/12/2022.

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|1.1|Incluir verificação nas auditorias de NF's|Passo 4|

---

### 2. Inclusão dos registros 0221, C855, C857, C895, C897, D700, D730, D731, D735, D737, D750, D760 e D761

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|2.1|0221 - Somente para 2024 - será criada nova Os;|----------|
|2.2|C855, C857, C895, C897 - novas tabelas SF_C855 e SF_C857;|----------|
|2.2.1|Criar novas telas|Realizado/Liberado|
||Criar Ids Arquivo|Realizado/Liberado|
||Exportação|Realizado/Liberado|
||Verificar procedures de gerações de dados na exportação de Speds;|Realizado/Liberado|
||Importação TMP|Realizado|
||Importação Layouts|Em Andamento|
|2.3|D700, D730, D731, D735, D737, D750, D760 e D761 - novos campos nas tabelas AC_C700_ENTRADA e AC_C700_SAIDA;|----------|
|2.3.1|Criar novo id_modelo_documento para código 62;|Realizado/Liberado|
|2.3.2|Alterar telas de notas fiscais|Realizado/Liberado|
||Incluir novos campos|Realizado/Liberado|
||Criar Ids Arquivo|Realizado/Liberado|
||Exportação|Realizado/Liberado|
||Verificar procedures de gerações de dados na exportação de Speds;|Realizado/Liberado|
||Importação TMP|Realizado|
||Importação Layouts|Em Andamento|

---

#### 3. Inclusão da exceção n° 2 na validação do registro C800

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|3.1|Tratar na importação de dados||

---

#### 4. Alteração da regra de validação do campo 06 do registro C170

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|4.1|Verificar validação na auditoria para incluir a excessão: exceto se o campo 07 - TIPO_ITEM do registro 0200 for igual a 07 (Material de Uso e Consumo);||

---

#### 5. Alteração da regra de validação do campo 09 do registro C800

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|5.1|Verificar validação na auditoria para incluir a excessão: A partir de Jan/2023, o destinatário não deverá ser informado.|----------|
||Layout|Realizado/Liberado|
||Auditoria|Passo 4|

---

#### 6. Alteração da regra de validação do campo 02 dos registros C181, C330, C380, C430, C480, C815 e C880

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|6.1|Verificar validações nas auditorias conforme listadas no guia prático|Passo 4|

---

#### 7. Alteração da regra de validação do campo 06 do registro C185 

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|7.1|Verificar validações nas auditorias conforme listadas no guia prático|Passo 4|

---

#### 8. Alteração do tamanho do campo 02 (15 para 60 caracteres) do registro C111 

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|8.1|Alterar Tela|Realizado/Liberado| 
||Relatórios|Realizado/Liberado|
||Trigger|Realizado/Liberado| 
||Exportação|Realizado/Liberado|
||Layouts Importação|Em Andamento| 

---

#### 9. Alteração do tamanho do campo 03 (15 para 60 caracteres) dos registros E112, E230, E312 e 1922

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|9.1|Alterar Tela|Realizado/Liberado| 
||Relatórios|Realizado/Liberado|
||Trigger|Realizado/Liberado| 
||Exportação|Realizado/Liberado|
||Layouts Importação|Em Andamento| 

---

#### 10. Alteração do tamanho do campo 06 (15 para 60 caracteres) dos registros E116, E250, E316 e 1926

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|10.1|Alterar Tela|Realizado/Liberado| 
||Relatórios|Realizado/Liberado|
||Trigger|Realizado/Liberado| 
||Exportação|Realizado/Liberado|
||Layouts Importação|Em Andamento| 

---

#### 11. Inclusão de uma nova opção de indicador para o campo 02 do registro K010.

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|11.1|Novo parametro IN_PARAMETRO_EMPRESA.DM_BLOCOK_TP_LAYOUT|----------| 
||Telas|Realizado/Liberado|
||Trigger|Realizado/Liberado| 
||Exportação |Realizado/Liberado|
||Layouts Importação|Em Andamento| 
||Auditorias|Passo 4|

---

## Principais alterações no Guia Prático da EFD-ICMS/IPI - versão 3.1.1

---

#### 1. Correção da orientação de preenchimento do campo 05 do registro C190 - retirada do termo FCP

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|1.1|Verificar view e layouts de exportação|Sem alteração|

---

#### 2. Inclusão dos registros C597, C857, C897 e D737 na regra de obrigatoriedade do registro 1900

|ITEM|DESCRICAO|STATUS|
|----|---------|------|
|2.1|Alterar procedure de geração SP_GERA_SF_1900, verificar layouts de exportação.|Realizado/Liberado|

---

## OBSERVAÇÕES

---

    Por favor aplicar a alteração indicada abaixo, verificar se precisa colocar a mesma regra no 
    arquivo do sped fiscal. Utilizar a OS 10801. Email Flavia/Gabriel

---