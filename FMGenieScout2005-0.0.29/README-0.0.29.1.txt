FM Genie Scout 2005 — versão 0.0.29.1
=====================================

Objetivo
--------
Estabilizar a qualidade da primeira base consolidada de jogadores criada na
0.0.29, tratando corretamente datas sentinela, contratos de formação e
jogadores sem clube/sem contrato ativo.

Principais correções
--------------------
1. A combinação EndYear=1900 e EndDay=1 não é mais convertida para 02/01/1900.
   Ela passa a representar término não definido (N/D).
2. Os valores brutos da data são preservados no modelo e no CSV.
3. Jogadores com a sentinela 1900/1 são classificados como FormationContract.
4. Clubes, salários e dados contratuais passam a ser anuláveis no modelo Player.
5. Vasilis Tsiartas (DatabaseId 12774), confirmado como jogador sem clube, é
   incluído conservadoramente como FreeAgent quando não existe contrato.
6. DisplayName e IdentityName deixam de ser duplicados artificialmente.
7. Novas flags e estados de qualidade são exportados.

Estados de vínculo
------------------
- Contracted
- OnLoan
- FormationContract
- FreeAgent
- Unknown

Estados da data final
---------------------
- Defined
- NotDefined
- Invalid
- NotApplicable

Arquivos gerados
----------------
- fm2005-player-parser-report.txt
- players.csv
- players-on-loan.csv
- players-free-agents.csv
- players-formation-contracts.csv
- players-with-undefined-contract-end.csv
- players-data-quality-flags.csv
- players-by-active-club.csv
- player-parser-validation.csv
- player-parser-contexts.txt

Casos de validação adicionados
------------------------------
- Celso Luís (8832899): contrato de formação, término N/D.
- Jonas (8835083): contrato de formação, término N/D.
- Vasilis Tsiartas (12774): agente livre, sem clube e sem contrato ativo.

Versão NuGet
------------
0.0.29-data.1

Observação
----------
A inclusão automática de agentes livres ainda é conservadora. Nesta versão,
apenas o caso confirmado de Vasilis Tsiartas é acrescentado sem contrato. Uma
etapa posterior deverá descobrir estruturalmente todos os jogadores livres sem
confundir jogadores com membros da comissão técnica.
