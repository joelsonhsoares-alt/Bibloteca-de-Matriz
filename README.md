# Calculadora de Matrizes

Aplicação de consola em **C#** que permite efetuar operações básicas com matrizes através de um menu interativo.

## Funcionalidades

| Opção | Operação | Descrição |
|-------|----------|-----------|
| 1 | Ler e imprimir matriz | Lê uma matriz de dimensão qualquer e mostra-a no ecrã |
| 2 | Multiplicação por escalar | Multiplica todos os elementos de uma matriz por um número |
| 3 | Soma de matrizes | Soma duas matrizes (têm de ter as mesmas dimensões) |
| 4 | Multiplicação de matrizes | Multiplica duas matrizes (colunas de A = linhas de B) |
| 5 | Determinante e inversa (2x2) | Calcula o determinante e a matriz inversa de uma matriz 2x2 |
| 6 | Determinante (3x3) | Calcula o determinante de uma matriz 3x3 pela regra de Laplace |
| 7 | Matriz transposta | Calcula a transposta de uma matriz de dimensão qualquer |
| 0 | Sair | Termina o programa |

## Requisitos

- [.NET SDK](https://dotnet.microsoft.com/download) (versão 6.0 ou superior recomendada)
- Qualquer terminal ou um IDE como Visual Studio / VS Code / Rider

## Como executar

```bash
# Clonar o repositório
git clone <url-do-repositorio>
cd BibliotecaMatrizes

# Compilar e executar
dotnet run
```

## Exemplo de utilização

```
=== CALCULADORA DE MATRIZES ===
1. Ler e imprimir matriz
2. Multiplicar por um escalar
3. Somar duas matrizes
4. Multiplicar duas matrizes
5. Determinante e Inversa (2x2)
6. Determinante (3x3)
7. Matriz Transposta
0. Sair
Escolha uma opcao: 5

--- Matriz 2x2 (Determinante e Inversa) ---
Elemento [1,1]: 4
Elemento [1,2]: 7
Elemento [2,1]: 2
Elemento [2,2]: 6

Matriz:
| 4 7 |
| 2 6 |

Determinante: 10
Inversa:
| 0,6 -0,7 |
| -0,2 0,4 |
```

> O separador decimal depende da configuração regional do sistema (vírgula ou ponto).

## Estrutura do código

Todo o código está em `Program.cs`, dentro do namespace `BibliotecaMatrizes`:

- **`Main`** – ciclo principal com o menu e a seleção das opções.
- **`LerMatriz(linhas, colunas)`** – lê os elementos de uma matriz do teclado.
- **`PedirMatrizGenerica()`** – pede as dimensões ao utilizador e lê a matriz.
- **`ImprimirMatriz(m)`** – imprime a matriz formatada.
- **`MultiplicarEscalar(m, escalar)`** – multiplicação por escalar.
- **`SomarMatrizes(a, b)`** – soma de matrizes (devolve `null` se as dimensões forem incompatíveis).
- **`MultiplicarMatrizes(a, b)`** – produto de matrizes (devolve `null` se as dimensões forem incompatíveis).
- **`Determinante2x2(m)`** – determinante de uma matriz 2x2.
- **`Inversa2x2(m)`** – inversa através da matriz adjunta (devolve `null` se o determinante for 0).
- **`Determinante3x3(m)`** – determinante 3x3 por expansão de Laplace na primeira linha.
- **`Transposta(m)`** – matriz transposta.

## Limitações conhecidas

- Não há validação de entradas: valores que não sejam números fazem o programa lançar uma exceção (`FormatException`).
- A inversa e os determinantes só estão implementados para matrizes 2x2 e 3x3.
- A comparação `det == 0` usa números decimais (`double`), pelo que pode haver pequenas imprecisões em alguns casos.

## Possíveis melhorias

- Usar `double.TryParse` / `int.TryParse` para validar as entradas.
- Implementar determinante e inversa para matrizes `n x n`.
- Separar o código em vários ficheiros/classes (por exemplo, uma classe `Matriz`).
- Adicionar testes unitários.

## Autores

- **Martim** e **Pedro** – ciclo principal e menu
- **Joelson** e **Rui Costa** – funções de operações com matrizes