# Sistema de Análise de Consumo de Energia

Projeto 2 da disciplina **Algoritmos e Programação II** (Faculdade de Computação e Informática — Universidade Presbiteriana Mackenzie), implementado em **linguagem C** utilizando **arrays paralelos** (sem `struct`).

## Como funciona

Ao iniciar, o programa carrega dois arquivos de entrada:
- `leituras.txt`: registros no formato `id unidade_id mes ano consumo`
- `unidades.csv`: catálogo de unidades no formato `id;descricao_da_unidade`

Os dados são armazenados em arrays paralelos (capacidade `MAX = 1000`), mantendo cada leitura sincronizada pelo mesmo índice em `ids`, `unidadeIds`, `meses`, `anos` e `consumos`, e cada unidade em `unidadeIdsCatalogo` e `descricoes`.

Em seguida, o sistema exibe um menu interativo com 6 opções:
1. **Mostrar leituras ordenadas por ID** — na primeira execução, permite escolher entre Bubble Sort, Insertion Sort, Selection Sort, Quick Sort ou Merge Sort.
2. **Buscar leitura por ID** — permite escolher entre Busca Linear ou Busca Binária (caso os dados ainda não estejam ordenados, o sistema ordena automaticamente via `mergeSortLeituraPorId` antes da busca binária).
3. **Calcular consumo de uma unidade** — soma todos os registros em kWh da unidade informada (exibindo `"Unidade nao encontrada."` caso não esteja em `unidades.csv`).
4. **Calcular consumo em um período** — valida o intervalo `mes/ano` inicial e final e soma o consumo total do período.
5. **Identificar unidade com maior consumo** — calcula o consumo acumulado por unidade e retorna a de maior consumo (em caso de empate, vence o menor ID).
6. **Sair da aplicação** — encerra o programa.

## Divisão e contribuições

- **Gabriel Alves Possato (`possatogabriel`)**
  - Carregamento de arquivos (`carregarLeituras`, `carregarUnidades`)
  - Mapeamento de unidades (`indiceUnidade`)
  - Algoritmos de busca (`buscaLinear`, `buscaBinaria`)
  - Estrutura principal do programa e menu (`main`)

- **Henrique Silva Pereira (`HsapDev`)**
  - Ordenação com Merge Sort em arrays paralelos (`mergeSortLeituraPorId` e `intercalar`)
  - Funções de análise de consumo (`calcularConsumoUnidade`, `calcularConsumoPeriodo`, `encontrarUnidadeMaiorConsumo`)
  - Implementação complementar dos algoritmos de ordenação (`trocarLeituras`, `bubbleSortLeituraPorId`, `insertionSortLeituraPorId`, `selectionSortLeituraPorId`, `particionar`, `quickSortLeituraPorId`)

## Como compilar e executar

No terminal, dentro da pasta do projeto:

```bash
gcc -o main.exe main.c
./main.exe
```

*(No Prompt de Comando do Windows, execute `main.exe`.)*
