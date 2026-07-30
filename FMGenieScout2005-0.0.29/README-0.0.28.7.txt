FM Genie Scout 2005 — 0.0.28.7
================================

Objetivo
--------
Identificar empréstimos, clube proprietário e clube ativo usando o parser de
contratos validado na 0.0.28.6.1.

Casos controlados
-----------------
- Reginaldo Araújo: Coritiba -> Flamengo (emprestado para o Flamengo)
- Anderson: Flamengo -> Caxias (emprestado pelo Flamengo)
- Édson Araújo: Corinthians -> Fortaleza
- Luciano Ratinho: Corinthians -> Grêmio
- Marcelo Magalhães: Corinthians -> Grêmio

Estratégia
----------
1. Extrair o contrato ativo pelo PersonDatabaseId.
2. Confirmar o clube ativo em recordStart+5.
3. Examinar todo o registro variável entre recordStart e PersonDatabaseId.
4. Resolver cada BYTE/UInt16/UInt32 que corresponde a um SaveIndex de clube.
5. Procurar a segunda referência que coincide com o clube proprietário.
6. Agrupar offsets repetidos em relação ao início do registro e ao DBID.

Arquivos gerados
----------------
- loan-relationship-report.txt
- loan-known-cases.csv
- loan-case-results.csv
- loan-club-reference-hits.csv
- loan-owner-offset-summaries.csv
- loan-record-contexts.txt
- loan-unresolved.txt

Versão NuGet
------------
Os projetos usam 0.0.28-loan.7, uma versão SemVer válida. O nome funcional da
etapa continua sendo 0.0.28.7.

Execução
--------
dotnet restore
dotnet build

Nenhum arquivo do save é modificado.
