FM Genie Scout 2005 — correção CS8600
======================================

Correção aplicada em:
src/FMGenieScout2005.Core/Parsing/Fm2005PlayerContractHeaderParser.cs

Alteração:
- a saída de IReadOnlyDictionary.TryGetValue agora é recebida como Club?;
- o fluxo valida explicitamente club is null antes de usar o valor.

Trecho corrigido:

if (!clubBySaveIndex.TryGetValue(clubSaveIndex, out Club? club) || club is null)
    continue;

A versão NuGet permanece válida:
0.0.28-rev.6.1

Após extrair, execute:

dotnet restore
dotnet build

Observação: não foi possível compilar no ambiente de geração porque o SDK .NET não está instalado.
