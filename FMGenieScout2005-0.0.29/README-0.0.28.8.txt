FM Genie Scout 2005 — 0.0.28.8
================================

Diagnóstico: LoanOptionEntryDiagnostic

Objetivo
--------
Localizar múltiplos contratos associados à mesma pessoa, distinguir contrato
profissional e contrato de empréstimo e decompor o payload variável em entradas
brutas de oito bytes.

Casos controlados
-----------------
- Reginaldo Araújo: Coritiba -> Flamengo
- Anderson: Flamengo -> Caxias
- Édson Araújo: Corinthians -> Fortaleza
- Luciano Ratinho: Corinthians -> Grêmio
- Marcelo Magalhães: Corinthians -> Grêmio

Estratégia
----------
1. Procura todas as ocorrências do PersonDatabaseId.
2. Identifica cabeçalhos DBID-8 / DBID-4 / DBID+4.
3. Procura todos os inícios contratuais válidos da mesma InternalPlayerKey.
4. Faz fallback global pela InternalPlayerKey para contratos sem DBID adjacente.
5. Classifica o clube proprietário como PROFESSIONAL_CONTRACT e o clube ativo
   como LOAN_CONTRACT.
6. Divide o payload variável em entradas de oito bytes sem impor semântica.

Arquivos gerados
----------------
- loan-option-entry-report.txt
- loan-multiple-contracts.csv
- loan-option-entries.csv
- loan-case-results.csv
- loan-option-entry-summaries.csv
- loan-multiple-contract-contexts.txt
- loan-unresolved.txt

Versão NuGet: 0.0.28-loan.8
Nenhum arquivo de save é modificado.
