FM Genie Scout 2005 — 0.0.28.1
================================

Diagnóstico
-----------
TwoPlayerContractSemanticDiagnostic

Objetivo
--------
Comparar diretamente os registros de Jean (PersonDatabaseId 315116) e
Athirson (PersonDatabaseId 3301535) nos mesmos offsets relativos.

Valores conhecidos
------------------
Jean:
- nascimento: 1982
- contrato iniciado: 2001
- contrato expira: 2006
- salário semanal: 675
- bônus de presença: 240
- bônus por gol: 65
- bônus por assistência: 35
- valor exibido: 3.000.000
- cláusula: 11.000.000
- aumento anual: 15%

Athirson:
- nascimento: 1977
- contrato iniciado: 2004
- contrato expira: 2006
- salário semanal: 5.000
- bônus por assistência: 240
- valor exibido: 2.600.000
- cláusula: 12.750.000

Arquivos produzidos
-------------------
- two-player-contract-semantic-report.txt
- jean-athirson-offset-matrix.csv
- jean-athirson-known-value-hits.csv
- jean-athirson-shared-semantic-candidates.csv
- jean-athirson-record-contexts.txt
- jean-athirson-known-contracts.csv

Interpretação
-------------
Priorize SEMANTIC_PAIR_CONFIRMED. Esse resultado exige que o mesmo offset
relativo contenha o valor esperado do Jean e o valor esperado do Athirson.

O save não é modificado.
