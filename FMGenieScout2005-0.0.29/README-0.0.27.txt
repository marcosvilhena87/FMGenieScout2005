FM Genie Scout 2005 — 0.0.27
================================

Diagnóstico: ContractFieldCorrelationDiagnostic

Objetivo
--------
Localizar a estrutura do contrato atual correlacionando quatro sinais independentes:
- PersonDatabaseId / InternalPersonId;
- salário mensal conhecido;
- data de expiração conhecida;
- SaveIndex do clube atual.

Amostras detalhadas
-------------------
Andrezinho, Dimba, André Bahia, Júnior Baiano, Fábio Costa, Fábio Baiano,
Luciano Ratinho e Dinélson.

Representações testadas
-----------------------
Salário: mensal, anual, semanal aproximado, diário aproximado e mensal x100,
em UInt16 e UInt32 quando aplicável.

Datas: YMD/DMY em UInt16 e UInt32, DOS date, YYYYMMDD, DDMMYYYY e dias desde
1900/1970.

Arquivos gerados
----------------
- contract-field-correlation-report.txt
- known-contracts.csv
- full-roster-validation.csv
- contract-reference-occurrences.csv
- contract-salary-hits.csv
- contract-date-hits.csv
- contract-club-hits.csv
- contract-correlation-candidates.csv
- contract-field-offset-summaries.csv
- contract-correlation-contexts.txt

O arquivo principal é contract-correlation-candidates.csv. Priorize candidatos
CONTRACT_CANDIDATE_STRONG e padrões SHARED_FIELD_STRONG.

O save é lido somente para análise e não é modificado.

Atualização — amostra de alta informação Jean
---------------------------------------------
A versão inclui Jean (PersonDatabaseId 315116) como âncora contratual detalhada:
- salário mensal: 2700
- início: 2001-01-01
- expiração: 2006-01-31
- bônus de presença: 240
- bônus por gol: 65
- bônus por assistência: 35
- cláusula de rescisão: 11000000
- valor: 3000000
- aumento salarial anual: 15%

Arquivos adicionais:
- jean-high-information-marker-hits.csv
- high-information-contract-candidates.csv
- high-information-contract-contexts.txt
