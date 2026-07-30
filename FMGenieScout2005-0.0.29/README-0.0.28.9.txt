FM Genie Scout 2005 — 0.0.28.9
================================

Objetivo
--------
Transformar a descoberta de múltiplos contratos em um parser permanente de
relacionamentos contratuais por jogador.

Componentes novos
-----------------
- Domain/PlayerContractRelationship.cs
- Parsing/Fm2005PlayerContractRelationshipParser.cs
- Parsing/Fm2005PlayerContractRelationshipParseResult.cs
- Diagnostics/PlayerContractRelationshipParserDiagnostic.cs
- Models/PlayerContractRelationshipParserModels.cs

Campos consolidados
-------------------
- contrato profissional;
- contrato de empréstimo, quando existir;
- clube proprietário;
- clube ativo;
- estado de empréstimo;
- salário interno e datas de ambos os contratos;
- direção do empréstimo relativa a qualquer clube consultado.

Arquivos produzidos
-------------------
- player-contract-relationship-report.txt
- player-contract-relationships.csv
- player-professional-contracts.csv
- player-loan-contracts.csv
- player-loan-validation.csv
- player-contract-relationship-contexts.txt

Validação incorporada
---------------------
Reginaldo Araújo, Anderson, Édson Araújo, Luciano Ratinho, Marcelo Magalhães,
Jean e Athirson.

Versão NuGet
------------
0.0.28-rel.9

O save é aberto somente para leitura.
