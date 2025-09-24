# Lab 1 - Descrição de algoritmos com **fluxogramas**

## Aplicação Flowgorithm

Deverá desenvolver os seguintes algoritmos com recurso à aplicação [Flowgorithm](http://www.flowgorithm.org/index.html), cuja instalação e uso foi introduzida no enunciado do **Lab0**.

Para evitar que tenha de criar um projeto diferente para cada exercício, recomenda-se que elabore cada algoritmo como uma _função_ independente, através de `Program > AddFunction...` (coloque só o nome do algoritmo, e.g., `C2F` no exercício 1, e ignore os outros detalhes).

Para alternar entre a execução de exercícios diferentes, adicione apenas um bloco `Call` no algoritmo `Main`, invocando o algoritmo respetivo, e.g. para o exercício `1`:

![](main.png)

Sempre que necessitar de mudar de algoritmo para execução, altere a função invocada neste bloco.

> [!CAUTION]
> Não se esqueça de guardar o seu trabalho! A aplicação permite guardar o "projeto" através de `File > Save As...` (ficheiro com extensão `.fprg`). Mais tarde, pode voltar a abri-lo na aplicação.

## Exercícios :pen:

> [!TIP]
> No final deste enunciado encontra "🆘 Ajudas" para alguns exercícios, mas só as deverá utilizar se não conseguir mesmo encontrar a solução.

1. Crie um algoritmo (`C2F`) que converte temperaturas em graus _celsius_ para graus _fahrenheit_. A temperatura a converter deve ser solicitada ao utilizador.

    - Fórmula de conversão: $F = C * \frac{9}{5} + 32$

    - Execução exemplificativa desejada:

    ![](C2F.png)

---

2. Crie um algoritmo (`Swap`) que solicita ao utilizador dois valores inteiros (um de cada vez, guardando-os em variáveis diferentes, e.g., `x` e `y`) e posteriormente troque o conteúdo das variáveis e as mostre. 

    - :bulb: Irá necessitar de uma terceira variável para a troca, dado que não consegue fazer duas operaçoes de atribuição em simultâneo.

    - Execução exemplificativa desejada:

    ![](Swap.png)

---

3. Crie um algoritmo (`Grade`) para calcular a classificação qualitativa de uma nota.

    - Este algoritmo avalia a nota de um aluno e mostra uma classificação com base nos seguintes intervalos de notas:

    Intervalo de notas | Classificação (output)
    ---|---
    $\lt50$ | "Insuficiente"
    $[50, 70[$ | "Suficiente"
    $[70, 90[$ | "Bom"
    $\geq 90$ | "Excelente"

---

4. Crie um algoritmo (`LeapYear`) para determinar se um ano é _bissexto_ (i.e., fevereiro tem 29 dias). O ano a determinar deve ser solicitado ao utilizador.

    A lógica de verificação segue uma regra simples baseada na divisão do ano por 4, 100 e 400. Um ano é bissexto se:

    1. For divisível por 4 **e**
    2. **Não** for divisível por 100, **exceto** se também for divisível por 400.
    
    - :bulb: Ser _divisível_ significa que o resto da divisão é `0` (zero). Utilize o **operador _módulo_** para este efeito.

    > [!TIP]
    > **Descrição da lógica necessária a implementar**
    > - Primeiro, verifica-se se o ano é divisível por 4. Se não for, o ano não é bissexto.
    > - Se for divisível por 4, verifica-se se é divisível por 100. Se não for, o ano é bissexto.
    > - Se for divisível por 100, então precisa também ser divisível por 400 para ser bissexto. Caso contrário, não é.

    - Teste o seu algoritmo:
      - Exemplos de anos bissextos (366 dias): 2008, 2012, 2020.
      - Exemplos de anos não bissextos (365 dias): 2005, 2011, 2019.

---

1. Crie um algoritmo (`RockPaperScissors`) que simule o jogo do "Pedra, papel ou tesoura". 
   
   - O algoritmo começa por solicitar ao utilizador a sua escolha, devendo este escrever "Papel", "Pedra" ou "Tesoura" (valor lido para uma variável do tipo _String_);
   
   - Como não há forma de "obrigar" o utilizador a fornecer uma opção válida, deve ser feita uma **validação** (_if_), i.e., se não for uma palavra válida, o algoritmo deve terminar com a mensagem `"Opção inválida!"`. Tente utilizar uma única condição/if. Se for válida, executa os passos seguintes;
   
   - Com o intuito de simplificar os passos seguintes, o algoritmo deverá **converter** a opção do utilizador para um valor numérico, i.e., coloque numa variável inteira um valor de acordo com o introduzido pelo utilizador:

      Valor convertido | Valor introduzido
      :---: | :---:
      0 | "Pedra"
      1 | "Papel"
      2 | "Tesoura"
  
   - O algoritmo depois deve gerar aleatoriamente um valor (ver dica abaixo) no conjunto `{0, 1, 2}`, que correspondem respetivamente a `{"Pedra", "Papel", "Tesoura"}` (tal e qual como no passo anterior).
  
   - Por fim, indica quem ganhou (i.e., o programa ou o utilizador) seguindo as regras do jogo: a tesoura ganha ao papel, a pedra ganha à tesoura e o papel ganha à pedra.
     - Pense na forma mais simples de testar todas as possíveis situações/condições; 

      > [!TIP]
      > Utilize uma atribuição, e.g., `x = Random(3)` para gerar um número no intervalo `[0,2]`. `Random` é uma função existente no Flowgorithm - pode consultar as funções existentes [aqui](http://www.flowgorithm.org/documentation/language/intrinsic-functions.html).

---

6. Se tiver tempo durante o laboratório, idealize um pequeno problema que gostasse de resolver através de um algoritmo. Proceda à sua implementação.


## Exercício Autónomo (TPC) :rocket:

> [!IMPORTANT]
> Antes da próxima aula PL tente resolver este exercício de consolidação.

Crie um algoritmo (`Quadratic`) que resolva uma equação quadrática do tipo $ax^2 + bx + c = 0$.

- Solicite ao utilizador os valores de a, b e c.

- Calcule o discriminante: $\Delta = b^2 - 4ac$.

- Caso $\Delta < 0$: mostre "Sem soluções reais".

- Caso $\Delta = 0$: mostre "Uma solução real" e calcule $x = -b / (2a)$.

- Caso $\Delta > 0$: mostre "Duas soluções reais" e calcule
$x_1 = \frac{-b + \sqrt{\Delta}}{2a}$,
$x_2 = \frac{-b - \sqrt{\Delta}}{2a}$.

### Exemplos de entradas e saídas esperadas

**Situação 1** – Sem soluções reais (Δ < 0)

- Equação: $x^2 + 2x + 5 = 0$

- a = 1, b = 2, c = 5

- $\Delta = b^2 - 4ac = 2^2 - 4(1)(5) = 4 - 20 = -16$

- Resultado esperado: "Sem soluções reais"

**Situação 2** – Uma solução real (Δ = 0)

- Equação: $x^2 - 2x + 1 = 0$

- a = 1, b = -2, c = 1

- $\Delta = (-2)^2 - 4(1)(1) = 4 - 4 = 0$

- Resultado esperado: "Uma solução real: x = 1"

**Situação 3** – Duas soluções reais (Δ > 0)

- Equação: $x^2 - 3x + 2 = 0$

- a = 1, b = -3, c = 2

- $\Delta = (-3)^2 - 4(1)(2) = 9 - 8 = 1$

- $x_1 = \frac{-(-3) + \sqrt{1}}{2(1)} = \frac{3 + 1}{2} = 2$

- $x_2 = \frac{-(-3) - \sqrt{1}}{2(1)} = \frac{3 - 1}{2} = 1$

- Resultado esperado: "Duas soluções reais: x₁ = 2, x₂ = 1"


## 🆘 Ajudas

Se não conseguir encontrar uma solução, utilize os seguintes algoritmos em _pseudo-código_ para o ajudar.

### `Grade`

```markdown
Entrada: nota
Se (nota >= 90) então:
   Exibir "Excelente"
Senão se (nota >= 70) então:
   Exibir "Bom"
Senão se (nota >= 50) então:
   Exibir "Satisfatório"
Senão:
   Exibir "Insuficiente"
```

### `LeapYear`

```pseudocódigo
Entrada: ano
Se (ano % 4 == 0) então:
   Se (ano % 100 == 0) então:
      Se (ano % 400 == 0) então:
         Exibir "Ano bissexto"
      Senão:
         Exibir "Ano não é bissexto"
   Senão:
      Exibir "Ano bissexto"
Senão:
   Exibir "Ano não é bissexto"
```

---

bruno.silva@estsetubal.ips.pt