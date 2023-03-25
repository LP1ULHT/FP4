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


## Recursividade

8. Crie uma função que receba 2 números e retorne o maior valor.

9.	Crie uma função que receba 2 números e retorne o menor valor.

10.	Crie uma função que receba 3 números e retorne o maior valor, use a função da questão 8.

11.	Crie uma função que receba 3 números e retorne o menor valor, use a função da questão 9.

12.	Crie uma função chamada Dado() que retorna, através de sorteio, um número de 1 até 6.

13.	Use a função da questão anterior e lance o dado mil vezes. Conte quantas vezes cada número saiu.
A probabilidade deu certo? Ou seja, a percentagem dos números foi parecida?

