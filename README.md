**UNIVERSIDADE LUSÓFONA DE HUMANIDADES E TECNOLOGIAS**

*Linguagens de Programação I*

# Ficha de Exercícios 4 - Funções

> Na resolução destes exercícios deve ser utilizada a Linguagem de Programação C. Para além da correta implementação dos requisitos, tenha em conta os seguintes aspetos:
>* O código apresentado deve ser bem indentado. 
>* O código deve compilar sem erros ou *warnings* utilizando o *gcc* com as seguintes flags:
>* `-Wall -Wextra -Wpedantic -Wvla -g`
>* Tenha em atenção os nomes dados das variáveis, para que sejam indicadores daquilo que as mesmas vão conter.
>* Evite o uso de constantes mágicas. 
>* Evite duplicação de código. 

## Funções simples

1. Considere as seguintes funções que retornam o máximo entre dois inteiros e o mínimo entre dois inteiros, respectivamente:
```C
int max2(int a, int b)
{
    return a > b ? a : b;
}
int min2(int a, int b)
{
    return a > b ? b : a;
}
```
Considere também as funções seguintes que retornam os valores máximo e mínimo entre 3 números inteiros:
```C
int max3(int a, int b, int c)
{
	return max2(a, max2(b, c));
}

int min3(int a, int b, int c)
{
	return min2(a, min2(b, c));
}
```

  1.1 Crie uma função com o nome `med3` que utiliza (invoca) as funções `max3` e `max2`, e que retorna o valor do meio (segundo maior) entre 3 números inteiros recebidos como parâmetro.

  1.2 Crie duas funções com o nome `max4` e `min4` que utilizam as funções anteriores e que retornam, respectivamente, o valor máximo e mínimo, entre 4 valores inteiros recebidos como parâmetro.
  
  1.3 Crie duas funções: com o nome `med4_1` e `med4_2` que utilizam as funções desenvolvidas anteriormente, e que retornam, o segundo maior valor e o segundo menor valor, respectivamente, entre 4 valores recebidos como parâmetros.
  
  1.4 Por fim experimente a seguinte função `main` que pede 4 números ao utilizador e os apresenta por ordem crescente:
  
  ```C
int main(void)
{
	int x, y, z, w;
	puts("Introduza 4 numeros inteiros:\n>");
	if (scanf("%d %d %d %d", &x, &y, &z, &w) != 4)
	{
		puts("erro na introducao dos numeros");
		return 0;
	}

	puts("Numeros por ordem");
	printf("%d\n", max4(x, y, z, w));
	printf("%d\n", med4_1(x, y, z, w));
	printf("%d\n", med4_2(x, y, z, w));
	printf("%d\n", min4(x, y, z, w));

	return 0;
}
```
2. Considere o jogo de crianças conhecido como [FIZZBUZZ](https://en.wikipedia.org/wiki/Fizz_buzz). Neste jogo todos os números múltiplos de 3 são substituídos pela palavra FIZZ enquanto que todos os números múltiplos de 5 são substituídos pela palavra BUZZ. Os números múltiplos de 3 e 5 são substituídos pela palavra FIZZBUZZ. O objetivo deste exercício é construir um programa que dado um número imprime no ecrã a sequência FIZZBUZZ até esse número. Por exemplo, para o número 25:
```
1
2
FIZZ
4
BUZZ
FIZZ
7
8
FIZZ
BUZZ
11
FIZZ
13
14
FIZZBUZZ
16
17
FIZZ
19
BUZZ
FIZZ
22
23
FIZZ
BUZZ
```
2.1 Escreva uma função que dado um número imprime no ecrã a palavra FIZZ, BUZZ ou FIZZBUZZ conforme as regras do jogo.

2.2 Escreva uma função, usando um loop, que chama a função do ponto anterior, até terminar a sequência.

2.3 Escreva uma função que implemente a mesma funcionalidade do ponto anterior utilizando recursividade.

3. Escreva uma função que recebe um caracter, verifica se este é minúsculo e converte para maíusculo através do `return` da função. Se o caracter for maíusculo converte para minúsculo.

## Recursividade

1. Defina uma função recursiva para calcular o máximo divisor comum de dois números inteiros não negativos a e b, usando o algoritmo de [Euclides](https://pt.wikipedia.org/wiki/Algoritmo_de_Euclides), definido da seguinte forma:
```
mdc(a,b) = a se b = 0,
mdc(a,b) = mdc(b,a mod b) se b > 0,
mdc(a,b) = mdc(a,−b) se b < 0
```

2. Crie uma função recursiva que lê números do teclado enquando os números introduzidos forem positivos. Quando encontrar um número negativo, apresenta os números lidos pela ordem inversa.

3. Crie uma função recursiva que calcula o resultado da multiplicação entre dois inteiros recebidos como parâmetro.

