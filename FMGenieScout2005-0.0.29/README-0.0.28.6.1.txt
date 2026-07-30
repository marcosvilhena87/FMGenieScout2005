FM Genie Scout 2005 — 0.0.28.6.1
====================================

Correção principal
------------------
O parser 0.0.28.6 lia clube, salário e data um byte antes da posição real.
O registro possui um byte separador/flags após a InternalPlayerKey:

  record+0  UInt32 InternalPlayerKey
  record+4  Byte separator/flags
  record+5  UInt32 CurrentClubSaveIndex
  record+9  UInt32 InternalWeeklyWage
  record+13 UInt16 ContractEndDayOfYearZeroBased
  record+15 UInt16 ContractEndYear
  record+17 payload variável
  DBID-8    UInt32 ContractStartYear
  DBID-4    UInt32 InternalPlayerKey repetida
  DBID+0    UInt32 PersonDatabaseId
  DBID+4    Byte PlayerRecordSubtype

Estratégia corrigida
--------------------
1. Extrai identidades confiáveis e adiciona os 19 IDs de validação.
2. Varre ocorrências desses PersonDatabaseIds.
3. Confirma StartYear, InternalKey e Subtype ao redor do DBID.
4. Procura a mesma InternalKey entre 40 e 160 bytes antes.
5. Valida clube, salário e término usando os offsets desalinhados corretos.
6. Escolhe o melhor candidato por pessoa.

Validação esperada
------------------
A execução deve localizar os jogadores conhecidos de Flamengo e Corinthians,
incluindo Jean, que não era resolvido pelo parser textual de identidades.

Arquivos produzidos
-------------------
- player-contract-header-report.txt
- player-contract-headers.csv
- player-contract-options.csv
- player-current-club-validation.csv
- player-contract-contexts.txt

Execute:
  dotnet clean
  dotnet build
